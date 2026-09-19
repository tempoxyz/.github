<br>
<br>

<p align="center">
  <a href="https://tempo.xyz">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/tempoxyz/tempo/refs/heads/main/.github/assets/tempo-wordmark-white.svg">
      <img alt="Tempo wordmark" src="https://raw.githubusercontent.com/tempoxyz/tempo/refs/heads/main/.github/assets/tempo-wordmark-black.svg" width="360">
    </picture>
  </a>
</p>

<br>
<br>

## What is Tempo?

Tempo is a payments-first blockchain incubated by Stripe and Paradigm, purpose-built for stablecoins and real-world payments at scale.

Tempo is EVM-compatible and built on Reth, the Ethereum execution client also maintained by the Tempo team. Smart contracts deploy with familiar tooling: Solidity, Foundry, Hardhat. The network is live on mainnet after a public testnet phase, with sub-second finality, gas fees payable in stablecoins, and an independent, diverse validator set as part of Tempo's roadmap toward permissionless validation.

Tempo also powers the Machine Payments Protocol (MPP), an open standard for machine-to-machine payments co-authored by Stripe and Tempo. MPP runs on Tempo's settlement layer, letting AI agents pay for resources — APIs, data, compute — inline with a request, with no API keys or billing accounts required.

## What makes Tempo different?

- **TempoTransaction:** Tempo includes a new EIP-2718 transaction type (0x76), providing features like passkey authentication, call batching, scheduled and parallel transactions, and fee sponsorship built natively into the protocol.
- **TIP-20 token standard:** Enshrined stablecoin token standard optimized for payments and reconciliation.
- **Predictable, low fees:** Gas is paid directly in USD-stablecoins via a built-in fee AMM, with TIP‑20 transfers targeting sub-millidollar costs.
- **Payment lanes:** Tempo ensures that payment transactions always have available blockspace, even during periods of high network congestion from DeFi activity.
- **Built with the Reth SDK:** High-performance, modular EVM execution layer under the hood powered by Reth.
- **Simplex consensus:** Optimized for low-latency, low-overhead finality under normal conditions.
- **Fully EVM-compatible.**

## What is MPP?

The Machine Payments Protocol (MPP) is an open standard for machine-to-machine payments, co-developed by Tempo and Stripe (with payment-method specs contributed by partners including Visa). It extends HTTP with a native 402 Payment Required flow, so any client — an AI agent, an app, or a person — can pay for a resource in the same request that asks for it, without API keys or checkout flows.

MPP is payment-method agnostic — it supports Tempo, Stripe, and other rails through the same protocol — which is why it lives alongside Tempo's core repos rather than being Tempo-exclusive. Primary use cases include agentic payments (an AI agent paying per API call), usage-based billing, and machine-to-machine commerce.

Learn more at [mpp.dev](https://mpp.dev/).

## Start Building

- [Quickstart](https://tempo.xyz/developers/docs/quickstart/integrate-tempo)
- [Documentation](https://tempo.xyz/developers/)
- [Tempo Overview](https://tempo.xyz/about/)
- [SDKs](https://tempo.xyz/developers/docs/sdk)
- [Machine Payments Protocol (MPP)](https://mpp.dev/)

If you've found a security vulnerability in a Tempo project, please see [SECURITY.md](https://github.com/tempoxyz/.github?tab=security-ov-file).

## Repositories

| Category | Repositories |
| --- | --- |
| Core Infrastructure | [`tempo`](https://github.com/tempoxyz/tempo), [`zones`](https://github.com/tempoxyz/zones) |
| SDKs | [`tempo-go`](https://github.com/tempoxyz/tempo-go), [`pympp`](https://github.com/tempoxyz/pympp), [`mpp-go`](https://github.com/tempoxyz/mpp-go), [`mpp-rs`](https://github.com/tempoxyz/mpp-rs), [`accounts`](https://github.com/tempoxyz/accounts) |
| Protocols | [`mpp`](https://github.com/tempoxyz/mpp), [`mpp-specs`](https://github.com/tempoxyz/mpp-specs) |
| Applications | [`tempo-apps`](https://github.com/tempoxyz/tempo-apps) |
| Developer Tooling | [`wallet-cli`](https://github.com/tempoxyz/wallet-cli), [`tidx`](https://github.com/tempoxyz/tidx) |
