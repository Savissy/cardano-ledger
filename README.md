# Cardano Ledger

## Introduction: What the Cardano Ledger Is and How It Works

The **Cardano Ledger** is the core set of rules that defines how the Cardano blockchain behaves. It determines how transactions are validated, how blocks are processed, how smart contracts execute, and how the overall blockchain state transitions from one moment to the next. In simple terms, if Cardano were a global computer, the ledger would be its **state machine**—its source of truth.

The ledger ensures that every node in the network, no matter where it is located, can **independently and deterministically** verify the correct state of the blockchain. This makes Cardano secure, decentralized, and predictable.

---

## 🧩 Key Concepts

### **1. State Transitions**

The ledger represents the blockchain as a series of **state transitions**. Each valid transaction moves the ledger from one valid state to another by following strict rules.

### **2. Transactions and the eUTXO Model**

Cardano uses an improved version of the Bitcoin UTXO model known as the **extended UTXO (eUTXO)** model. This model provides:

* Deterministic smart contract execution
* Easy parallelization of transactions
* Higher security
* Precise resource usage through scripts, datums, and redeemers

Every transaction:

* **Consumes** existing outputs
* **Produces** new outputs
* Optionally executes smart contracts
* Must satisfy all ledger validation rules

### **3. Scripts and Smart Contracts**

With the **Alonzo** era, Cardano gained support for smart contracts through **Plutus**. The ledger defines how:

* Scripts are evaluated
* Datums and redeemers are used
* Fees and execution units are enforced
* Script failures are handled deterministically

### **4. Era-by-Era Evolution**

Cardano evolves through a series of eras, each adding new capabilities:

| Era         | Key Features                                           |
| ----------- | ------------------------------------------------------ |
| **Byron**   | Core blockchain + basic transactions                   |
| **Shelley** | Decentralization, staking, delegation                  |
| **Allegra** | Time-based scripts (timelocks)                         |
| **Mary**    | Native multi-asset support                             |
| **Alonzo**  | Smart contracts (Plutus)                               |
| **Babbage** | On-chain referencing, inline datums, reference scripts |
| **Conway**  | Governance system (CIP-1694)                           |

This repository implements the ledger rules for all eras.

---

## 🛠️ Purpose of This Repository

This repository provides:

* Formal ledger specifications
* Executable models for testing and research
* Reference implementations for Cardano developers
* Documented transition rules for each era
* Serialization schemas (CDDL)
* Supporting documents and tooling

It is the primary reference for teams building:

* Cardano nodes
* Wallets and explorers
* Smart contract tooling
* Research models or academic implementations

---

<p align="center">
  <a href="https://input-output-hk.github.io/cardano-engineering-handbook">
    <img alt="CEH" src="https://img.shields.io/badge/policy-Cardano%20Engineering%20Handbook-informational?style=for-the-badge" />
  </a>
  <a href="https://github.com/intersectmbo/cardano-ledger/actions/workflows/haskell.yml">
    <img alt="GitHub Workflow Status (master)" src="https://img.shields.io/github/actions/workflow/status/intersectmbo/cardano-ledger/haskell.yml?branch=master&style=for-the-badge" />
  </a>
  <a href="https://cardano-ledger.cardano.intersectmbo.org/">
    <img alt="Haddock (master)" src="https://img.shields.io/badge/documentation-Haddock-yellow?style=for-the-badge" />
  </a>
</p>

This repository contains the formal specifications, executable models, and implementations of the Cardano Ledger.

The documents are built in our CI and can be readily accessed using the following links:

| Era     | Design Documents                 | Formal Specification    | CDDL      |
| ------- | -------------------------------- | ----------------------- | --------- |
| Byron   |                                  | Chain Spec, Ledger Spec | CDDL, PDF |
| Shelley | Design                           | Spec                    | CDDL      |
| Allegra | Same as Mary                     | Same as Mary            | CDDL      |
| Mary    | Multi-Currency, UTXOma           | Spec                    | CDDL      |
| Alonzo  | eUTXO                            | Spec                    | CDDL      |
| Babbage | batch-verification, CIP-31/32/33 | Spec                    | CDDL      |
| Conway  | CIP-1694                         | Spec (WIP)              | CDDL      |

Other Documents:

* Non-integer calculations specification
* Stake pool ranking specification
* Small-step semantics explanation

Isabelle/HOL formalization is available online.

User documentation is published on Read the Docs.

Haddock code documentation is available from the master branch.

---

# Repository structure

(Structure preserved exactly as original.)

* Byron
* Shelley
* Allegra
* Mary
* Alonzo
* Babbage
* Conway
* Libraries

---

# Building

It is recommended to use **nix** for building everything. Enter the nix shell using:

```
nix develop
```

Inside the shell, build Haskell with **cabal**.

---

# Nix Cache

(Adds performance improvements for compiling dependencies.)

---

# Building LaTeX Documents and Executable Specifications

```
nix build .#specs
```

Outputs appear in the `result` directory.

---

# Testing

Enter the nix shell, then:

```
cabal test all
```

---

# Submitting an Issue

File issues in the GitHub Issue tracker.

---

# Contributing

See CONTRIBUTING.md for guidelines.

---

# Using `git fsck`

Contains instructions for resolving `.gitmodules` issues in older versions.
