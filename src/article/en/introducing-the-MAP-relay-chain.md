---
title: "Introducing the RATS Relay Chain: The Core of RATS Protocol"
description: 
lang: en
---


In an era dominated by blockchain isolation, the RATS protocol emerges as a groundbreaking innovation, aiming to seamlessly connect heterogeneous blockchains. This article delves into the unique features of the RATS Relay Chain, underscoring its pivotal role in the RATS protocol ecosystem, and explores its profound implications for the future of blockchain interoperability.


# Introduction

Blockchain technology, since its inception, has seen tremendous growth and diversification. However, this growth has led to a fragmented landscape, with myriad blockchains operating in isolation. The RATS (Multi-chain Asset Protocol) Relay Chain seeks to address this challenge by bridging the gaps between disparate blockchain ecosystems.


# RATS Relay Chain: At a Glance

Inspired by the foundational elements of Polkadot and Cosmos, the RATS Relay Chain leverages cryptographic proofs over trusted entities, supporting cross-chain transfers and swaps. Its distinctiveness lies in its inclusive approach, connecting not just isomorphic chains within a single ecosystem, but heterogeneous blockchains, encompassing the burgeoning EVM realm.


## Technical Foundation

The RATS Relay Chain is built on a robust Proof-of-Stake mechanism and a Byzantine Fault Tolerant consensus protocol, ensuring energy efficiency, security, and stability. Its EVM compatibility allows seamless integration and development, making it a universal connector in the blockchain domain.


## Core Functionality

At the heart of the RATS Relay Chain's functionality is the maintenance of light clients for all connected blockchains. This architecture underpins a trustless verification process for cross-chain messages, eliminating human errors and ensuring asset security through mathematical certainty.


## Consensus Protocol

Embracing the IBFT (Istanbul Byzantine Fault Tolerant) consensus, the RATS Relay Chain offers simplicity, immediate finality, and adaptability to dynamic validator sets. This consensus model, coupled with continuous research and engineering advancements, positions the RATS Relay Chain as a resilient and user-friendly platform.


## Validator Dynamics

The RATS Relay Chain supports a diverse and robust network with a validator set that is dynamically updated based on the staking weight in RATS tokens. Staked validators and token holders are incentivized to participate actively in the ecosystem's security and growth, fostering a healthy and vibrant community.


## Incentive Structure

RAON token holders are rewarded through various means, including operating validator nodes, delegating tokens, or contributing directly to the RATS ecosystem. The dynamic adjustment of incentives ensures a balanced distribution of staked and circulating tokens, maintaining the ecosystem's liquidity and stability.


## Epoch-Based Block Generation

The RATS Relay Chain adopts an epoch-based approach to block generation. Validator sets are refreshed at the end of each epoch, and within an epoch, block production follows a weighted round-robin methodology, reflecting the staking weight of validators.


## Design Philosophy

Echoing the ethos of Ethereum's sandwich complexity model, the RATS Relay Chain maintains a minimalist bottom-level architecture. This design philosophy allows for rapid integration of new features, such as additional light clients, without compromising the integrity of the consensus layer.

# Using Bitcoin Network to Enhance RATS Relay Chain Security

Long-range attacks are a type of assault specifically aimed at Proof of Stake (PoS) systems. Attackers attempt to create a forked chain starting from the early history of the blockchain. If successful, this could redefine the authoritative historical record of the chain, leading to double-spending issues or undermining network trust. In the relay chain architectures, this issue is particularly critical because they often coordinate interactions between multiple independent blockchains within a network. If a relay chain suffers a long-range attack, it could impact all chains that rely on it as a basis for trust and communication.

Bitcoin, with its immense computational power, can be considered a natural source of trust and serves as a timestamp server supported by proof of work. It provides an irreversible time order for events. In its native application, events involve various transactions executed on the Bitcoin ledger. In current applications aimed at enhancing the security of other blockchains, Bitcoin can also be used to timestamp events occurring in other blockchains. Each such event triggers a transaction sent to miners, who subsequently insert it into the Bitcoin ledger, thus timestamping the event. Transactions that timestamp events are referred to as [checkpoints](https://bitcoin.stackexchange.com/questions/1797/what-are-checkpoints).

Checkpoints can be implemented using the` OP_RETURN` opcode of Bitcoin, which allows the publication of arbitrary 80-byte data in unspendable Bitcoin transactions. Each checkpoint must contain at least the hash of the PoS block to be checked (32 bytes) and a signature finalizing that block (32 bytes each). Here, the hash is used to identify the PoS block being checkpointed, and the signature is required to prevent adversaries from sending arbitrary hashes and pretending to checkpoint PoS blocks on Bitcoin.

A PoS chain can enhance its security and address the long-range attack problem by utilizing the Bitcoin timestamp service's features. The RAON platform regularly (every epoch) submits the hash and signature of the last block of each epoch as a checkpoint to the Bitcoin network. These checkpoints consist of the hash of the block and a single aggregated BLS signature, corresponding to the signature of the 2/3 set of validators who signed the block for finality, as well as the epoch number and bitmap number. 

As a result, RAON clients can determine the final canonical chain of the RATS Protocol ‘s PoS chain by retrieving checkpoints from the Bitcoin network, thus protecting against long-range attacks by malicious validators on the RATS Protocol network.



# Conclusion

The RATS Relay Chain stands as a testament to the innovative spirit of blockchain technology. By fostering interoperability and bridging diverse blockchain ecosystems, it not only enhances the functionality and reach of existing platforms but also paves the way for a more interconnected and efficient future in the blockchain universe. Moreover, by leveraging the security mechanism of Bitcoin network, RATS Relay Chain further enhances its security and prevents potential long-range attacks.

