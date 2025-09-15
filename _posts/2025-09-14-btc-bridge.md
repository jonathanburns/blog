---
title: "BTC Bridge"
hidden: true
description: "BTC Bridge"
header: 
  teaser: "https://ipfs.io/ipfs/bafybeibakz4oz56c6bwtmz3qfooiqetyxym3r2lqso6mc5ouxjzrzglybe"
date: 2024-12-11T15:34:30-04:00
---


## Overview


Ethereum was created to enable decentralized financial applications (smart contracts). These decentralized applications will almost certainly replace large portions of the world’s financial infrastructure.

In a perfect world, the ETH token would not have been necessary. Instead, users would transfer BTC to the Ethereum blockchain, and BTC would function as digital currency for the Ethereum ecosystem. 

Unfortunately, transferring BTC to other chains is hard. All known methods require a decentralized group of participants who manage the bridge, and the majority of the participants in the group must be honest. We call this an “honest-majority” trust assumption. This honest-majority assumption is not good enough to power the world’s financial infrastructure. The ETH token is necessary because the Ethereum blockchain needs a token that cannot be corrupted by a dishonest majority.

A trust-minimized bridge is one where only one actor in the group needs to be honest. Until recently, building a trust-minimized bridge on Bitcoin was thought to be impossible without changes to the Bitcoin protocol. 

However, a recent series of white papers introduced a novel algorithm called “BitVM” which proposes a method for creating a trust-minimized Bitcoin bridge. 

Multiple teams are working on various implementations of BitVM. 

To keep this document focused, I’ll cover the Strata bridge design, which is being built by the team at Alpen Labs. It’s worth noting that other implementations (Citrea or others) differ in various ways which may come with different security trade-offs.

In this paper, I will describe:

* What is required to create a functioning bridge?
* Why is it hard to create a bridge on Bitcoin, and how do BitVM and the Strata bridge attempt to solve these problems?
* Why don’t these solutions work?


## Creating A Functioning Bridge

A bridge is a system which allows users to move funds from a source blockchain (Bitcoin in our case) to a destination blockchain (an L2). The bridge typically must support 3 operations:

#### Deposit Funds:

To initiate a transfer to the destination chain, the users lock BTC into the bridge. This action makes the funds available on the L2 as “Wrapped BTC”. It’s vital that the funds remain locked on the source chain until a user “burns” the “Wrapped BTC” on the L2.

#### Update State Of the L2: 

Users sign transactions off-chain (i.e., on the L2) to interact with it. There must be a method by which the current L2 state can be recorded on the L1 (Bitcoin).

#### Withdraw Funds From The Bridge: 

When a user burns “Wrapped BTC” on the L2, eventually that state will get propagated to the L1 (as described above).

Once the L1 is updated, a user should be able to unlock an equivalent amount of Bitcoin from the bridge.

To do this, the bridge must understand the state of the L2. To do this, it must enforce two important things:

1. **Validating The L2’s State Transition Function**

The bridge should not trust the L2 updates without verification.

The bridge encodes a “state transition function”, which defines what a valid state update is (for example, all transactions must have the proper signatures). The bridge will not respect an L2 state update which violates the state transition function.

2. **Validating The Fork Choice Rule**

In blockchain, it is possible to create two valid versions of the chain (where both versions comply with the state transition function).

For example, I can create one version of the blockchain where I sign a transaction which sends my funds to Sophie, and another version where I send my funds to Felix.


![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafkreiagvyjceouvgh3vhtelolmoctn7hedxhnczmhuqqyfgi65bxksvoa)


In this case, the bridge must encode rules that define which fork is the real one. This is called the “Fork Choice Rule”. 

If the bridge does not enforce the “Fork Choice Rule”, an actor can create a private fork and submit that fork to the L1 (this fork will pass the state transition function verification).



## Problems & Solutions


Bitcoin does support scripting. All funds on the Bitcoin blockchain are separated into something called “UTXOs”. A Bitcoin script can be attached to a UTXO to apply “spending conditions” to that UTXO.

Think of it like the Bitcoin is on an island, and the script protects that coin from being stolen from the island. The script will not let anyone take the coin from the island unless the conditions are met.

![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeia57p3s5r44mowfxoxwgnvi5fxuttoaplkym7b3x7kxexijzsp3pq)

These scripts provide a lot of programmability, but they come with some important limitations. I’ll explain how these limitations create problems when trying to build a bridge, and how the [BitVM2 white paper](https://bitvm.org/bitvm_bridge.pdf), and the [Strata Bridge white paper](https://www.alpenlabs.io/blog/introducing-the-strata-bridge) propose solving these problems.


#### Problem 1: Enforcing The State Transition Function

The BitVM white paper shows that Bitcoin scripts are expressive enough to validate a ZK proof (which can enforce the state transition function). However, the process requires a dispute resolution flow. Funds must be sent to the correct party depending on the result of the dispute.

Unfortunately, Bitcoin scripts have no access to the transaction outputs. This means the script cannot enforce that the funds go to the right place.

![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibse2jpy6meffj5ebgirrkb4gj6cyumm5leqvfu6p3bwlu5jgmmwe)

**Solution:**

At deposit time, the bridge participants create a pre-planned route for the flow of funds.

![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibakz4oz56c6bwtmz3qfooiqetyxym3r2lqso6mc5ouxjzrzglybe)


To enforce that the funds **only** follow the approved route, the bridge participants create an n-of-n multisig (one signature for each participant).

At deposit time, the actors pre-sign every transaction in the route. At the end of this process, each actor permanently deletes their signing key so that no other transactions can be signed with the multisig. 

So long as **any** actor in the group throws away the key as instructed, no other transactions can be signed (since signing these transactions requires approval from all n parties).

This ensures that the funds always follow the pre-planned route, so long as one actor is honest. This is how the system achieves 1-of-n trust assumptions.


#### Problem 2: Enforcing the Fork Choice Rule

Remember that the L2 posts state updates back to the L1 (Bitcoin).

Unfortunately, Bitcoin scripts cannot access any blockchain state.

This means that even though the state of the L2 has been posted to Bitcoin, the script cannot see it, and thus, it cannot use that state to accept or reject a withdrawal based on that state.

![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeienybbrjruzwkz4g7h2huwvhvhkzmvy5qgn6dkjrv5n6pbo2tr3wy)

The script can accept inputs, but those inputs must be passed by the submitter. This means the transaction submitter must tell the script about the state of the blockchain by passing in the current block as an input.

But what if the submitter lies?

For example, imagine that an attacker creates a private fork of the Bitcoin chain, and tells the withdrawal script that this private fork is the head of the Bitcoin blockchain. The script cannot determine if this block is in its own chain.

![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeigd4zkrvnxiwa3br23e67xpcd64fzdwfro5chkrmske4w7dt3iycm)


ZK proofs cannot solve this problem (since both forks are valid and follow the state transition function), so we need another way to prevent an attacker from submitting a malicious (but valid) fork.

**Solution:**

In addition to signing deposits, the bridge participants periodically sign messages attesting to the canonical tip of the Bitcoin chain. Because these messages are signed by all parties (n-of-n signatures), it proves that all signers agree that this block is the current tip of Bitcoin. So long as there is 1 honest actor in the group, the group will never sign a dishonest private fork (this fork would be missing at least one signature).

Now, when the submitter tells the script that a certain block is the tip of the Bitcoin chain, the submitter can also provide a signature showing that the block was signed by the n-of-n multisig.


## Putting It All Together


Let’s look at how the Strata Bridge handles bridge operations:


#### Deposit Funds to The Bridge:

For each deposit, the bridge participants create a pre-planned route which represents the possible paths along which funds can flow (including the ZK proof dispute procedure). This set of transactions is signed by the group at deposit time. As long as at least one participant in the group is honest, the route cannot be compromised. 

Once the funds are locked in the bridge, the Wrapped BTC tokens are minted on the L2.

#### Update State of the L2: 

Before a user can withdraw funds that are locked in a bridge deposit, they’ll need to burn the corresponding amount of Wrapped BTC on the L2.

The L2 sequencer periodically posts the current L2 state back to Bitcoin, so this state update will eventually be available on Bitcoin.

#### Withdraw Funds From The Bridge: 

When submitting a withdrawal, the submitter tells the withdrawal script about the state of the L1 and L2. Using the solutions described above, the withdrawal script enforces:

* The state transition function was satisfied for the L1 and L2
* The Fork Choice Rule was satisfied for the L1 and L2
* The withdrawal conditions are met.

If all three of these conditions are met, the bridge releases the funds.


## Why These Solutions Are Not Sufficient 

On the L1, each deposit is locked in its own UTXO (each of these UTXOs has a script protecting that UTXO). The L2 mints “Wrapped BTC” tokens, and these L2 tokens are fungible (they are indistinguishable from one another).

We can imagine the 3 BTC deposits, each locked in a UTXO (on the left of this image), and 3 Wrapped BTC on the L2 (on the right). The Wrapped BTC are all in a shared pool and not tied to a specific deposit.

![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeigdlisrhclrykkxuxraj7x2xx4aqye76bnsq6wnmowq6raodscy6u)


Because the tokens on the L2 are fungible, when you burn “Wrapped BTC” on the L2, and withdraw it on the L1, the tokens you get back may come from a different deposit.

![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafkreignytyl6m6p4gdto3c3pbyqpmg3k3tz2odhnmkbwg3iy4xqatbceq)

For this reason, the withdrawal script must enforce that **all deposits are secure** (even deposits which occur **after** the deposit this script is attached to). If any deposit is insecure (i.e. a deposit where all the signers are dishonest), then the entire bridge is compromised.

Consider the following scenario.

* An attacker creates an unsafe deposit where all participants are dishonest (the top deposit in the image above).
* The L2 sequencer mints 1 Wrapped BTC on the L2.
* The attacker burns the BTC on the L2, and withdraws it on the L1. Note that the insecure deposit (the top one) is still locked in the bridge.

Now, the attacker has retrieved their 1 BTC back on the L1, but the insecure deposit is still locked in the bridge. The attacker can easily withdraw that insecure BTC from the bridge without burning funds on the L2.

After the attacker retrieves both deposits, there is only one deposit left on the L1, but there are 2 tokens on the L2 (the L2 is no longer fully collateralized).

**How Can We Protect Against This Attack?**

The withdrawal script must protect against this case by enforcing a set of “required participants” for **all** deposits (even those that came after the deposit which the script is attached to).

![fork](https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiau2ea4b4kzzuygef3v5pu32zxh6idhk2pwgm5fzc72225xnp4biq)


If a deposit is made which does not include all the required participants, and the L2 mints wrapped tokens for that deposit, the withdrawal script should consider that L2 state transition **invalid** (the minting of those tokens violates the state transition function).

This means that the set of “required participants” must be defined **during the first deposit to the bridge**, and the withdrawal scripts must enforce that every deposit includes that enshrined set of signers. As long as there is one honest actor among the enshrined signers, the deposits are secure.

This solution is effective in what it aims to do. It makes it exceedingly difficult to create an insecure deposit. However, it makes it exceedingly simple for an actor to make the system stop functioning.

**Liveness Failures**

Remember that in this system, deposits require n-of-n signers, and all deposits require a signature from all signers. Additionally, to make a withdrawal, you need to submit a block which has been signed by this group of signers (this is how the system enforces the Fork Choice Rule).

So what happens if one or more signers stop signing? 

In this case, the system can no longer process deposits (because a signer is missing). Additionally, if an actor stops signing Bitcoin blocks, the system cannot process withdrawals. Users can still burn Wrapped BTC on the L2, and the L2 can post that data to Bitcoin, but remember that the withdrawal script cannot read the Bitcoin blockchain. This means a user cannot prove to the withdrawal script that this block is not a private fork. Proving this block is in the canonical chain requires a group signature from the n-of-n signers.

If an actor in the system can cause the system to stop functioning, this is called a “liveness failure”.

The ability to cause a liveness failure like this is effectively as dangerous as the ability to steal funds. An actor who creates this liveness failure could hold the funds in the bridge hostage. They might say “I’ll only sign transactions on the condition that you pay me a ransom”.


## The Unfortunate Solution 

If the system requires an enshrined set of n-of-n signers for all deposits and withdrawals, any actor in that signing group can halt deposits and withdrawals, causing a liveness failure. This makes the system extremely vulnerable to attack.

To solve this, there must be an escape hatch which allows the signers to remove an actor who is not signing, but this escape hatch creates problems:

Firstly, it is difficult to prove that an actor is refusing to sign. 

Further, if one actor in the group is refusing to sign, it might be because that actor is trying to cause a liveness failure, or it might be because that actor is the only honest actor in the group (refusing to sign a malicious transaction).

Unfortunately, the best solution we have to this problem is to allow the group to remove a member through majority vote.

This does work, but it turns the system into a very complex honest-majority bridge.


## Conclusion

BitVM and Alpen have made major breakthroughs. They have devised a way to verify ZK proofs on Bitcoin. Recent advancements from Alpen like Glock have greatly improved the efficiency of these ZK proving algorithms.

However, to build a functional bridge, we need more than ZK proofs. Namely:

* We must ensure that a single actor cannot cause the system to stop processing deposits. Currently, this requires honest-majority trust assumptions.
* We must ensure that a single actor cannot cause the system to stop processing withdrawals. Currently, this requires honest-majority trust assumptions.

These are still unsolved problems. 

It is worth noting that potential changes to the Bitcoin protocol like OP_CAT might change this. Exploring how OP_CAT changes things is an exercise for another post. 
