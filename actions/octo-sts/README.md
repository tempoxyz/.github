# octo-sts

Mint a short-lived GitHub App installation token from Tempo's
[Octo STS](https://github.com/octo-sts/app) instance. No stored
credentials: the runner's GitHub OIDC token is exchanged directly.

## Usage

```yaml
permissions:
  id-token: write # required for both the tailnet join and the exchange

steps:
  - id: sts
    uses: tempoxyz/.github/actions/octo-sts@main
    with:
      scope: tempoxyz/target-repo
      identity: my-identity

  - name: Use the token
    env:
      GH_TOKEN: ${{ steps.sts.outputs.token }}
    run: gh api /installation/repositories
```

On a self-hosted runner already on the tailnet, add `join-tailnet: "false"`.

## Target repository opt-in

The target repository (`scope`) must have a trust policy on its default
branch at `.github/chainguard/<identity>.sts.yaml`, and the Octo STS
GitHub App must be installed on it:

```yaml
issuer: https://token.actions.githubusercontent.com
# GitHub issues ID-annotated subjects (org@id/repo@id); match both
# formats and pin the IDs. Find them: gh api repos/ORG/REPO --jq .id
subject_pattern: repo:tempoxyz(@211589300)?/source-repo(@<REPO_ID>)?:ref:refs/heads/main

claim_pattern:
  event_name: workflow_dispatch

permissions:
  contents: write
```

The minted token has exactly the permissions the policy grants, scoped
to the policy's repository, and expires after one hour. The action
revokes it in a post step.

## Notes

- A freshly minted token can briefly 404 (GitHub replication); retry
  once if the first use races the mint.
- `ts-oauth-client-id` and `ts-audience` are public identifiers, not
  secrets; defaults point at the org-wide trust credential
  (subject `repo:tempoxyz@211589300/*`).
