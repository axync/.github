<div align="center">

# Axync

**Trade any token. Cross-chain. Trustless.**

A universal peer-to-peer marketplace for tokens and NFTs — settled with zero-knowledge proofs across EVM chains.

---

[App](https://app.axync.xyz) · [Docs](https://axync.gitbook.io/axync-docs) · [Twitter](https://x.com/axync_xyz)

</div>

## The Problem

Cross-chain token trading is fragmented. Bridges are slow and risky. OTC deals on Telegram have zero guarantees. DEXs don't work across chains. There's no simple way to sell tokens on one chain and receive payment on another without trusting an intermediary.

## The Solution

Axync is a cross-chain escrow marketplace where anyone can trade ERC-20 tokens and ERC-721 NFTs across chains. Settlement happens through a ZK sequencer — atomic, verifiable, no trusted intermediaries.

**Sell on Ethereum. Get paid on Base. One click.**

### Two trading paths

**Fungible (AxyncVault)** — for token trading with partial fills:
1. **Deposit** tokens into AxyncVault on any supported chain
2. **Create deal** — set offer, price, and payment chain via EIP-712 signed message
3. **Counterparty accepts** — full or partial fill
4. **Withdraw** proceeds on the payment chain with a merkle proof

**Escrowed (AxyncEscrow)** — for NFTs and fixed-price sales:
1. **List** any ERC-721 NFT or ERC-20 tokens into the on-chain escrow
2. **Buyer pays** — deposits payment on any supported chain via AxyncVault
3. **Sequencer settles** — matches payment to listing, produces a ZK proof
4. **Buyer claims** — withdraws the asset using a merkle proof

Cross-chain settlement is handled entirely by the protocol. No bridges, no wrapped tokens, no counterparty risk.

## Architecture

| Repository | Stack | What it does |
|-----------|-------|-------------|
| **[core](https://github.com/axync/core)** | Rust | Sequencer, state machine, ZK prover, chain watchers, REST API |
| **[contracts](https://github.com/axync/contracts)** | Solidity | AxyncVault, AxyncEscrow, AxyncVerifier (Groth16 on BN254) |
| **[ui](https://github.com/axync/ui)** | Next.js | Marketplace interface with wallet integration |
| **[relayer](https://github.com/axync/relayer)** | Node.js | Submits block proofs and state roots on-chain |
| **[docs](https://axync.gitbook.io/axync-docs)** | Markdown | Protocol documentation |

## Supported Assets & Chains

**Assets:** Any ERC-20 token (via Vault with partial fills), any ERC-721 NFT (via Escrow), native ETH.

**Chains:** Ethereum and Base (Sepolia testnet). Mainnet and additional L2s coming soon.

## What makes Axync different

- **Cross-chain native** — Asset on Ethereum, payment on Base. No bridges needed.
- **Two paths** — Fungible trading with partial fills via Vault, or escrowed NFT/token sales via Escrow.
- **ZK settlement** — Every state transition is provable. Groth16 proofs verified on-chain.
- **Permissionless** — No KYC, no minimum amounts, no approval from token issuers.
- **EIP-712 signatures** — Gasless deal creation and acceptance through the sequencer.

<div align="center">

---

<sub>

[app.axync.xyz](https://app.axync.xyz) · Built with Rust, Solidity, and zero-knowledge proofs

</sub>

</div>
