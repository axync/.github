<div align="center">

# Axync

**Trade locked tokens. Cross-chain. Trustless.**

The marketplace for vesting positions, locked tokens, and OTC deals — settled with zero-knowledge proofs.

---

[App](https://app.axync.xyz) · [Docs](https://axync.gitbook.io/axync-docs) · [Twitter](https://x.com/axaboratory)

</div>

## The Problem

Billions of dollars sit locked in vesting contracts (Sablier, Hedgey, custom schedules). Token holders who need liquidity today have two options: wait months, or sell OTC on Telegram with zero guarantees.

## The Solution

Axync is a cross-chain escrow marketplace where sellers list locked tokens or NFTs and buyers purchase them at a discount. Settlement happens through a ZK sequencer — atomic, verifiable, no trusted intermediaries.

**Sell on Ethereum. Get paid on Base. One click.**

### How a deal works

1. **Seller lists** — Deposit any ERC-20 token or ERC-721 NFT into the on-chain escrow, set a price and payment chain
2. **Buyer pays** — Deposit payment on any supported chain via AxyncVault
3. **Sequencer settles** — Matches payment to listing, produces a ZK proof of the state transition
4. **Buyer claims** — Withdraw the asset on the seller's chain using the merkle proof

Cross-chain settlement is handled entirely by the protocol. No bridges, no wrapped tokens, no counterparty risk.

## Architecture

| Repository | Stack | What it does |
|-----------|-------|-------------|
| **[core](https://github.com/axync/core)** | Rust | Sequencer, state machine, ZK prover, chain watchers, API |
| **[contracts](https://github.com/axync/contracts)** | Solidity | AxyncEscrow, AxyncVault, AxyncVerifier (Groth16) |
| **[ui](https://github.com/axync/ui)** | Next.js | Marketplace interface with wallet integration |
| **[relayer](https://github.com/axync/relayer)** | Node.js | Submits block proofs and state roots on-chain |

## Supported Assets & Chains

**Assets:** Any ERC-20 token, any ERC-721 NFT — including vesting positions from Sablier, Hedgey, and custom contracts.

**Chains:** Ethereum and Base (Sepolia testnet). Mainnet and additional L2s coming soon.

## What makes Axync different

- **Cross-chain native** — Asset on Ethereum, payment on Base. No bridges needed.
- **Any token** — Not limited to specific vesting protocols. List any ERC-20 or ERC-721.
- **ZK settlement** — Every state transition is provable. No trusted sequencer assumptions.
- **Permissionless** — No KYC, no minimum amounts, no approval from token issuers.

<div align="center">

---

<sub>

[app.axync.xyz](https://app.axync.xyz) · Built with Rust, Solidity, and zero-knowledge proofs

</sub>

</div>
