---
title: "Eigenlayer Musings"
hidden: true
description: "Eigenlayer game-theory."
header: 
  teaser: "https://docs.safe.global/_next/static/media/safenet-introduction.cf3046fd.png"
date: 2024-12-11T15:34:30-04:00
---

# Eigenlayer Stream-Of-Consciousness

I've been studying a lot about Eigenlayer recently.

Eigen defines two terms

cryptoeconomic security:
strong cryptoeconomic security:

A key input into these calculations is "cost-of-corruption". When Eigen computes cost-of-corruption, the only input to this calculation is generally slashing conditions.

Slashing is just one of many costs that could be incurred if a validator where to do something malicious. Consider the cost of acting maliciously when participating in Ethereum consensus. 

| Cost | Description |
|  -------  |  ------  |
| Asset Loss | Slashing |
| Asset Value Loss | If you successfully corrupt the network, it erodes trust in the network, which harms the value of the asset you own and have staked. |
| Forgone Rewards | You forgo the reward you're supposed to get for doing the right thing. |
| Reputational Loss  | All other things held constant, a brand like Coinbase is less likely to do something malicious as it would damage the Brand. |
| Legal Consequences | All other things held constant, a doxed actor is less likely to do something malicious |


Protocols secured with restaked assets give up a critical piece of this table, asset value loss. 

To illustrate, imagine you were able to acquire a controlling stake of Ethereum. If you were to do something malicious to the Ethereum network, it would erode trust in Ethereum. By the time you're able to unstake and sell your ETH, the value of that ETH might be near zero. The cost of such an attack would be akin to a 100% slashing condition.

This is the big reason that Ethereum proof-of-stake works despite the fact that slashing has not been implemented yet.

Now imagine you use that same controlling stake of Ethereum, but instead of attacking the Ethereum network, you use it on Eigenlayer to attack an AVS. This would erode trust in the AVS, but that would not impact the price of your ETH.

**If Eigenlayer isn't subject to a loss Asset Value Loss, and it hasn't implemented slashing yet (Asset loss), then what is currently securing AVSs on Eigenlayer?**

Unfortunately, "forgone rewards" are generally not costly enough to ensure economic security. The profit that can be generated by corrupting an oracle is far greater than the foregone rewards it would cost. This means that Eigenlayer is currently almost entirely secured by "reputational loss" and "legal consequences".

The cost of malicious behavior in terms of reputational loss and legal consequences is difficult to quantify, but Eigenlayer today is proof of their effectiveness. A huge portion of restaked assets are delegated to names you know and trust. Coinbase, Kiln, P2P, etc. If these actors behave maliciously, it puts their entire business at stake. In some ways, this is the most valuable form of security, since the loss can amount to **more than 100% of the staked assets**. In that sense, it can be an even more powerful deterrent than slashing. If Coinbase had 1000 ETH staked in a small AVS, and then used that stake to corrupt the AVS, the cost to the Coinbase brand would far outweigh the cost of losing the entire stake.

Legal consequences are another powerful incentive against malicious behavior. If a doxed actor like Coinbase where do participate in an attack on an Eigenlayer AVS, Brian Armstrong (or others) could face fines or even jail time.

**If reputational loss and legal consequences have such a powerful impact on cryptoeconomic security, why are they always missing from our threat models?**

**Reputational loss** Is hard to measure, and even harder to incentivize. 

To measure the security provided by reputational loss, we would have to be able to quantify the brand-damage of malicious behavior, and this differs from brand to brand. If Coinbase or Kiln were to attack an AVS, not only would the Eigenlayer stakers undelegate, every staker on every chain they support would undelegate too (due to fear of getting slashed). The cascading impacts would be catastrophic. On the other hand, if Apple were to corrupt an AVS, it is not clear that the public would stop buying iPhones.

Even if we could measure reputational loss, in order to make it part of cryptoeconomic-security, we would have to incentivize actors with a lot of reputation at stake to join the network. We'd need some kind of on-chain proof-of-reputation and rewards would have to be tied to this somehow.

There are ways we can increase the opportunity of **Legal Consequences** for malicious behavior, but they come with serious drawbacks. 

Let's imagine a protocol which enforces KYC for all participants. In this setup, a malicious participant faces potential legal consequences for malicious behavior. The protocol could even enforce diversity by enacting per-participant and per-region stake-limits. Global KYC information is notoriously hard to validate, but assuming the information is accurate, this would make it harder to collaborate on a 51% attack. 


