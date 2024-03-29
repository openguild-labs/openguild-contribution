---
id: learn-hyperbridge
title: Hyperbridge
sidebar_label: Hyperbridge
description: A brief overview of Hyperbridge, the innovative interoperability solution for crosschain bridges.
keywords: [bridges, cross-chain, bridge-methods]
slug: ../learn-hyperbridge
---

import RPC from "./../../components/RPC-Connection";

:::info Learn about Parachain and Bridges

To fully follow the material on this page, it is recommended to be familiar with the concepts of the [Parachain](https://wiki.polkadot.network/docs/learn-parachains) and [Bridges](./learn-bridges.md).

:::

Interoperability is the core vision of the Polkadot technology. Through years of blockchain development, there has been many effort into making a secure interoperability solution to communicate between blockchains.

With that vision in mind, Hyperbridge (short for hyper-scalable bridge) is innovated as a cross-chain solution built as an interoperability coprocessor. Hyperbridge is crafted to scale cryptographically secure, consensus, and state-proof-based interoperability across all blockchains. Before diving deeper into the core technology of the Hyperbridge, let's go through a first few foundational concepts.

## Coprocessor Model

Ensuring secure cross-chain communication involves the meticulous verification of various aspects, including: [Consensus Mechanisms](https://wiki.polkadot.network/docs/learn-consensus), [Consensus Faults](https://research.polytope.technology/consensus-proofs), [State Proofs](https://research.polytope.technology/state-machine-proofs) and [State Transitions](https://wiki.polkadot.network/docs/learn-parachains#state-transitions).

> What is a coprocessor?
>
> **Coprocessor**, in the context of hardware, can be referred to a microprocessor designed to supplement the capabilities of the primary processor. For example, GPU is a coprocessor of the CPU to be optimized for graphical and simultaneous computation.

Due to the complexity and expensiveness of the onchain verification process, in coprocessor model, the computation is performed off-chain and the outcomes of the execution, along with cryptographic proofs validating their accuracy, are subsequently presented on-chain.

Expanding more about the coprocessor model, it has been applied in other solutions of offloading cryptographic computation as well, particularly, **SNARK coprocessor model**.

<!-- %% Add more information about the state problems of the ZK coprocessor model %% -->

### Parachain as Coprocessors

By leveraging the cost-effective consensus proofs facilitated by [BEEFY](https://spec.polkadot.network/sect-finality#sect-grandpa-beefy), Hyperbridge affirms the legitimacy of all parachain state transitions safeguarded by the network.

This capability enables the distribution of the validation workload for consensus, state proofs, and state transition re-execution across various designated [Parachain Cores](https://github.com/polkadot-fellows/RFCs/blob/6f29561a4747bbfd95307ce75cd949dfff359e39/text/0001-agile-coretime.md). Hence, Polkadot is utilized by the Hyperbridge as a verifiable computation layer to provide the ["Full Node Security"](https://blog.polytope.technology/introducing-hyperbridge-interoperability-coprocessor#full-node-level-security) in cross-chain bridges.

Hence, an additional layer of security is provided, allowing Hyperbridge to detect and prevent [Byzantine](https://en.wikipedia.org/wiki/Byzantine_fault) behaviors across connected chains.

<!-- Explain more about full node security -->

### Interoperable State Machine Protocol (ISMP)

<!-- Give more information about the ISMP. -->

Interoperable State Machine Protocol (ISMP) provides a familiar HTTP-like API for developers who want to make cross-chain requests to trigger certain logic on the counterparty chain. It allows making POST requests to send arbitrary data to connected chains, as well as GET requests to read the storage (verified through state proofs) of applications on connected chains.

In addition to facilitating cross-chain message passing among connected chains, ISMP also serves as a synchronisation primitive across Hyperbridge's internal state machines. This enables its parachain cores to communicate with each other and delegate tasks.

### Underlying technologies

Underlying technologies of the Hyperbridge is integrated with:

- **PLONK verifier**
- [BEEFY consensus](https://spec.polkadot.network/sect-finality#sect-grandpa-beefy)

- The Barretenberg backend

## Terminology

### State Proofs

State proofs are a critical primitive of the blockchain stack that enable things like trustless bridges, off-chain light clients that can access on-chain data in a permissionless and secure manner as well as modular blockchains architectures where the execution layer can be decoupled from the consensus layer.

### Consensus Proofs

Consensus Proofs in a blockchain system denote the mechanism by which participants, often nodes or validators, collectively agree on the validity of new transactions or blocks. The nature of consensus proofs varies across different blockchain architectures, such as Proof-of-Work, Proof-of-Stake, or other consensus algorithms.

The ultimate goal is to ensure a widespread and verifiable agreement among network participants, enhancing the security and reliability of the distributed ledger.

For example, Consensus Proofs in a proof of stake system is given as the signatures over the latest block header in the chain from a supermajority (two-thirds plus one) subset of the full authority set.

## Learn More

The information provided here is subject to change; keep up to date using the following resources:

- [Introducing Hyperbridge: An Interoperability Coprocessor](https://blog.polytope.technology/introducing-hyperbridge-interoperability-coprocessor) - Article by Seun Lanlege, Polytope Lab founder.
- [Digital Services as State Machines](https://polkadot-blockchain-academy.github.io/pba-book/blockchain-contracts/services-as-state-machines/page.html) - Lecture about state machine from Polkadot Blockchain Academy
- [Polkadot Wiki - Bridges](https://wiki.polkadot.network/docs/learn-bridges) - Learn about bridges in Polkadot
- [Polkadot Wiki - Parachain](https://wiki.polkadot.network/docs/learn-parachains) - Learn about parachain in Polkadot
- [Hyperbridge Source Code](https://github.com/polytope-labs/hyperbridge) - Public codebase repository of hyperbridge.
- [Interoperable State Machine Protocol (ISMP) Book](https://ismp.polytope.technology/) - Guidebook of the ISMP
- [The Puzzle of Blockchain Interoperability](https://twitter.com/stakenode_dev/status/1744653040764817675)
- [RFC-1: Agile Coretime](https://github.com/polkadot-fellows/RFCs/blob/6f29561a4747bbfd95307ce75cd949dfff359e39/text/0001-agile-coretime.md) - Agile periodic-sale-based model for assigning Coretime on the Polkadot Ubiquitous Computer.
- [ISMP, The Endgame for Parachain Interoperability | Sub0 2023
  ](https://www.youtube.com/watch?v=MCOAwooWecs)
