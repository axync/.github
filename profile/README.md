<div align="center">

# Axync

**Proof, not promises.**

Cross-chain settlement verified by zero-knowledge proofs.

---

`Deposit` · `Trade` · `Settle` · `Withdraw`

</div>

## What is Axync?

Axync is a cross-chain settlement protocol that lets you move value across blockchains without traditional bridges. Every settlement is verified by ZK proofs — no trusted intermediaries, no multisigs, no waiting for finality on multiple chains.

> Deposit on one chain. Trade at any rate. Settle on another. Withdraw with a proof.

## How it works

```
 Chain A                    Axync                    Chain B
┌──────────┐          ┌──────────────┐          ┌──────────┐
│          │ deposit  │              │ withdraw │          │
│ Ethereum ├─────────►│  Sequencer   ├─────────►│   Base   │
│          │          │  ┌────────┐  │          │          │
│          │          │  │ZK Proof│  │          │          │
│          │◄─────────┤  └────────┘  │◄─────────┤          │
│          │ withdraw │              │ deposit  │          │
└──────────┘          └──────────────┘          └──────────┘
```

1. **Deposit** — Lock assets on any supported chain
2. **Create Deal** — Set your terms: amount, rate, chains
3. **Accept Deal** — Counterparty fills your deal
4. **Settle** — Sequencer executes the atomic swap
5. **Withdraw** — Claim on the destination chain with a ZK proof

## Architecture

| Component | Stack | Description |
|-----------|-------|-------------|
| **[core](https://github.com/axync/core)** | Rust | Sequencer, state machine, ZK proof generation, block production |
| **[ui](https://github.com/axync/ui)** | Next.js | Trading interface with EIP-712 wallet signing |
| **[contracts](https://github.com/axync/contracts)** | Solidity | Deposit, withdrawal & verifier contracts (Groth16) |

## Supported Chains

| Chain | Status |
|-------|--------|
| Ethereum | Testnet |
| Base | Testnet |


## Key Design Decisions

- **No bridge tokens** — native assets only, no wrapped representations
- **EIP-712 typed signing** — human-readable transaction approval in wallets
- **STARK → SNARK composition** — fast proving with on-chain verification efficiency
- **Sequencer with ZK validity proofs** — trustless state transitions, anyone can verify

<div align="center">

---

<sub>

[app.axync.xyz](https://app.axync.xyz)

</sub>

</div>
