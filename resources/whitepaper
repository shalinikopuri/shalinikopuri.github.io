# Blockchain POC

By Kushal Pagolu

## PROBLEM – Double Spending

The problem of double spending existed since the times of Digital Currency. This double
spending can happen in many real time scenarios. Not just IT but this problem can transpire
across all the industries. In this paper I will explain how this double spending problem can be
solved in IT, let _’_ s say Onboarding a Customer or a Resource. After we have built a chain of this
data, we no longer have to depend on sub standard third party vendors that waste lot of time and
money(Double Spending) for the end client.

## Introduction

What is needed is an electronic system based on cryptographic proof instead of Trust/Ve
ndors/BGC companies, allowing any two willing parties to Onboard directly into their
organization with each other without the need for a trusted third party. The trusted third
party not only uses other sub-standard methods to work on the back ground check, but also
wastes a lot of valuable time during Onboarding. This time can be immutable and even critical for
the end client.
As a vendor if we can onboard a Resource from already existing blockchain, Remember in time
we will build a valuable chain of genuine resources/customer with industry defined


metrics.These metrics will help the Onboarding manager to quickly decide on the available
resources by simply using a Report Definition and a filter, let’s say an LSA with Pega 8
experience and specifically having knowledge in Pega Decision Hub.
To get the bigger picture I can take an example of a Customer who has been onboarded and
permanently recorded on our private Blockchain.Let’s say in future,The same company with it’s
child company wants to get Financial help from our client(BANK). You don’t have to spend
extra money to run a full financial background check of the Parent company.This saves a lot of
time and money after the Blockchain is evolved,holding all the previous state of the
Customers/Resources.
The metrics, Properties are available in the LEDGER or Smart Contract we build to hold the
values. A smart contract is not a legal contract but an agreement between the 2 parties during the
Onboarding.

In this paper, I propose a solution to the double-spending problem using PEGA PRPC,
peer-to-peer distributed
timestamp server to generate computational proof of the chronological order of work(Onb
oarding).
Thesystem is secure as long as honest nodes collectively control more CPU power than
any cooperating group of attacker nodes. It only takes time from the first Generic block to
extend into a continuous, long chain of verified Onboarding blocks. Once enough blocks are
generated and the blockchain is verified with enough honest nodes, it can be difficult to
manipulate any block. This will need the attacker to expend the proof of work to create that
block and also the previous genuine blocks before this.
To accomplish this without a trusted party, onboarding smart contract must be
publicly announced,
and we need a system for participants to agree on a single history of the
order in which they were received. The payee needs proof that at the time of each transa
ction, the majority of nodes agreed it was the first received.

## Timestamp Server + CaseId


The solution I propose begins with a timestamp server. A timestamp server works by taking a
hash of a block of items(CaseId+Properties) to be timestamped and widely publishing the
hash, such as in a newspaper or Usenet post.The timestamp proves that the data must have existed
at the time, obviously, in order to get into the hash. Each timestamp includes the previous
timestamp in its hash, forming a chain, with each additional timestamp reinforcing the ones
before it.
We can add or append the CasedId to the TimeStamp or even take CaseId as one more

## parameter to the Hash function.

## The Blockchain Paradigm

Ethereum, taken as a whole, can be viewed as a transaction-based state machine: we begin with a
genesis state and incrementally execute transactions to morph it into some final state. It is this
final state which we accept as the canonical “version” of the world of Ethereum. The state can
include such information as account balances, reputations, trust arrangements, data pertaining to
information of the physical world; in short, anything that can currently be represented by a
computer is admissible. Transactions thus represent a valid arc between two states; the ‘valid’
part is important, there exist far more invalid state changes than valid state changes. Invalid state
changes might, e.g., be things such as reducing an account balance without an equal and opposite
increase elsewhere. A valid state transition is one which comes about through a transaction.

In our case, TRANSACTION can be our CaseId or the entire business process of an
Onboarding/Hiring.

## GHOST PROTOCOL

Since the system is decentralized and all parties have an opportunity to create a new block on
some older pre-existing block, the resultant structure is necessarily a tree of blocks. In order to
form a consensus as to which path, from root (the genesis block) to leaf (the block containing the
most recent transactions) through this tree structure, known as the blockchain, there must be an
agreed-upon scheme. If there is ever a disagreement between nodes as to which root-to-leaf path
down the block tree is the ‘best’ blockchain, then a fork occurs. This would mean that past a
given point in time (block), multiple states of the system may coexist: some nodes believing one
block to contain the canonical transactions, other nodes believing some other block to be
canonical, potentially containing radically different or incompatible transactions. This is to be
avoided at all costs as the uncertainty that would ensue would likely kill all confidence in the
entire system. The scheme we use in order to generate consensus is a simplified version of the
GHOST protocol introduced by Sompolinsky and Zohar.


## Smart Contracts

A smart contract is not a legal contract but an agreement between the 2 parties during the
Onboarding.
The metrics, properties and the business logic are available in the LEDGER or Smart Contract
we build to hold the values.

## PoS

I have a stake in that particular transaction.
To add a block to the chain we need to put some computational effort into solving a complex
math problem. This will help slow down the malicious activities to be posted on to the chain
quickly. This involves lot of computational power and electricity. In our case we design a PROOF
OF STAKE algorithm for our nodes to be able to add the right block with all processed CaseId's
to the Blockchain as the N+1th block with N previous blocks. We use our own Cryptocurrency to
be able to raise the stake and the Node with the highest stake can win the race and add the N+
block to the Blockchain.
PoS can be implemented in Smart Contracts.

## Storage

This looks like huge amount of data to be stored in multiple nodes which can get add more
blocks as we go. We solve memory issue with Merkle Petrecia Trees(Trie) data structure.

The canonical blockchain is a path from root to leaf through the entire block tree. In order to
have consensus over which path it is, conceptually we identify the path that has had the most
computation done up on it, or, the heaviest path. Clearly one factor that helps determine the
heaviest path is the block number of the leaf, equivalent to the number of blocks, not counting
the unmined genesis block, in the path. The longer the path, the greater the total mining effort
that must have been done in order to arrive at the leaf. This is akin into existing schemes, such as
that employed in Bitcoin-derived protocols. Since a block header includes the difficulty, the
header alone is enough to validate the computation done. Any block contributes toward the total
computation or total difficulty of a chain.

## Conclusion


I have proposed a system for Onboardingcustomers/resources without relying on trust.
We started with the usual framework of our own
currency made from digital signatures, which provides strong control of ownership(Proof Of
Stake), but is incomplete without a way to prevent double-spending.
To solve this, Iproposed a peer-to-peer network using proof-of-
stake to record a public history of transactions(CaseId)that quickly becomes computationally im
practical for an attacker to change if honest nodes control a majority of CPU power.
The network is robust in its unstructured simplicity. Nodes
work all at once with little coordination.
They do not need to be identified, since messages are
not routed to any particular place and only need to be delivered on a best effort basis. N
odes can leave and rejoin the network at will, accepting the proof-of-
stake chain as proof of what
happened while they were gone. They vote with their CPU power, expressing their acce
ptance of
valid blocks by working on extending them and rejecting invalid blocks by refusing to w
ork on them. This mechanism needs a consensus algorithm with pre defined specific steps to be
satisfied for the block to be verified as valid.
Any needed rules and incentives can be enforced with this consensus mechanism.

I have introduced, discussed and formally defined the protocol of Ethereum. Through this protocol
the reader may implement a node on the Ethereum network and join others in a decentralized
secure social operating system. Contracts may be authored in order to algorithmically specify and
autonomously enforce RULES of interaction.
This can be done by using the PEGA Ethereum Component on Pega PRPC v7.4 and above. We
can run a full Ethereum node using GETH implementation, or we can run a PRIVATE Ethereum
Test Node(using GETH commands) - We need an Ethereum node to be installed and running on
the same server as PEGA is running for the PEGA Ethereum Component to work.

You can build a rich Blockchain with vital historical data which is verified thoroughly and only
when it is verified gets to the Blockchain. This data can be used for solving double spending or
even share the Network with say our new acquisition or even work with our competitor to be able
to work on a completely new application. This chain can act as a SOURCE OF QUALITY. By
Onboarding new customers, over a period of time, I am trying to achieve that quality eventually
by using available technologies at my disposal.

## Sources

1. Bitcoin white paper.

2. Ethereum White paper.

3. Pega Ethereum Component PW2018 Demo.

4. https://towardsdatascience.com/top-industries-that-blockchain-will-disrupt-in-future-
    855695038260


