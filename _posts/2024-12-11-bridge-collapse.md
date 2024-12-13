---
title: "Bridge Collapse"
hidden: true
description: "Bridge Collapse."
header: 
  teaser: "https://docs.safe.global/_next/static/media/safenet-introduction.cf3046fd.png"
date: 2024-12-11T15:34:30-04:00
---


3:00 am



I’m paged.



Borinksi calls in, his voice is groggy from sleep.



“Borinkski here. This better be important”



“Sir. We have a big problem.”



“Okay. We’ll get on with it.”



“Jelly finance was hacked.”



“Fuck. When?”



“Started about 10 minutes ago. They’re still draining accounts. The jelly team are trying to patch the contract but they’re having trouble getting the transactions to go through. The attacker is still taking funds and everyone is trying to pull out. The chain is bogged down.”



“What’s the damage?”



“We’re still analyzing. At least 2 billion. Losses are still climbing.“



“Give me an upper bound. What’s the TVL in Jelly?”



“Around 30 billion. 20% of the chain is locked up in those accounts.” 



“Fucking hell. Did we post the transactions on the L1 yet?”



“Patrick, can you check on that?”



….



“Hasn’t posted yet. Next state dump should land in 5 minutes”



“Shut it down. Shut down the sequencer”



Shut down the sequencer? Are you sure? We could be looking at brand damage if we intentionally shut down the sequencer. They’ll say we’re centralized.



If we post the transactions on the L1, we can’t roll back anymore. We need to keep our options open. Shut it down ASAP. 



Roll back? You can’t be serious. What about the transactions that have happened since the hack?



Those transactions haven’t posted to the L1.  They’re not finalized.



Technically, yeah. But We’ve never rolled back anything before. In practice, the users don’t wait for the L1. They trust the sequencer.



Those are pre confirmations. The transactions are not finalized until they hit the L1. Shut it down. Now.



“Tim, can you handle that?”



“I’m trying to get in to the sequencer but I don’t have SSH access. It’s a highly secure machine. I’m paging the engineers now.”



“Time check. We’ve got 2 minutes until the state root updates”



“Page everyone. Do whatever you have to. Set the data center on fire. Do not let those transactions post. How long do we have?”



1 minute, 20 seconds…



“We’re trying.”



“Tony is on the call now. He’s an engineer on the team”



“Hey this is Tony. I’m gonna ssh and try to kill the process. I need someone to approve the ssh request. Tim, can you approve?”



“The page isn’t loading…. Oh wait. There, I got it. Tony, are you in?”



“Yep. I gotta find the process now. Hold on.”



“Time check”



“10 seconds”



“Just nuke everything”



“I think I found the process. Hold on.”



“3 seconds”



…



“Did you get it?”



“Maybe. Let me double check…. Yeah. Looks like it’s shut down.”



“Did we make it in time?”



Hold on, I’m checking the L1.



Oh fuck… it posted.



Tell me you’re kidding.



No. The transactions posted to the L1.



Fuck.

… 



“We’ve got a calculation update on the losses. It’s north of 25 billion”



“Holy shit.”



“X is blowing up. Everybody’s saying roll back”



“It’s not possible”



“Can we call Vitalik? What if they roll back the ethereum and erase our transaction update”



“It’ll never happen”



“Judith… What’s the total value bridged from Eth?”



“Let me see: Looks like 4 billion.”



“Jesus. Okay. Everyone grab some coffee. It’s going to be a long night. What we’re about to do is something we said could never happen. Everybody take a minute. I’m gonna step outside. I need a cigarette.”



He walks out and flicks a lighter.



“Here’s where things stand. 25 billion was lost in the hack. It’s 5x the value that’s locked in the L1 bridge. What we’re about to do will be recorded in textbooks and studied for years to come. We’re going to roll back to a block that is prior to what’s currently recorded on the L1. The cascading impacts of this are something even I can’t totally wrap my head around.”



That’s not possible. The state is already posted to the L1.



It is possible.



What do you mean? The bridge contract is immutable. The bridge contract on the L1 won’t let us update the state to an older block. You said it yourself. We can’t roll back once we post to the L1.



I know what I said, but we didn’t know the extent of the losses at the time. I said we can’t roll back, but we can. We can revert, it’s the L1 bridge that can’t. What were gonna have to do now is to hard fork away from the L1 bridge…



Fork away? What do you mean?



What I mean is that the L1 bridge will have one view of the chain, which is not rolled back, and our sequencer is going to have a completely different view. A fork. On our fork, we will perform the rollback. This fork will be completely disconnected from the L1 bridge.



We can’t. We can’t fork away from the bridge. We’re a rollup. It’s in our whitepaper for christs sake. We’re an L2. Ethereum is the source of truth.



I know what’s in the white-paper, Judith. I wrote it. This isn’t up to us. The chain is a decentralized system. The social consensus gets to decide. We’re going to have to launch two sequencers. One sequencer will have the rollback, and one won’t. Social consensus will determine which chain is canonical, but based on the total losses we’re looking at, it’s clear that the rollback fork is going to preserve here.



How do you know?



Because users chose the rollback fork in 2016 during the ethereum DAO hack, and the losses here are greater.



There were no bridges back then. We can’t fork away from the bridge. The L1 is supposed to be the source of truth.



This isn’t our call. I can’t make that any more clear. Here’s what’s gonna happen if we don’t give the users a rollback option. Someone in the community is going to launch an alternate sequencer which has the rollback, and that rollback will become the canonical chain. We will loose control of our own chain and the rollback will still go through. Theres nothing we can do to stop the rollback. This is a decentralized system. Welcome to web3.



Judy, call circle and loop them in.



Sorry. Loop them in on what?



There will be two versions of the chain now. Users can’t redeem the same USDC on both chains. The USDC on the canonical chain will be backed up by circle. The USDC on the other fork will have no value. 



What about the L1 bridge?



L1 bridge cannot be rolled back. This means the bridge will have no connection to the canonical chain. The bridge will follow the the other fork.



You mean the fork without the rollback?



Right. The bridge will be connected to the fork without the rollback.



Okay. What does that mean in practice?



It means that any wrapped assets that were bridged from ethereum can only be redeemed via the bridge fork. These assets will have no value on the canonical fork.



But the wrapped eth still exists on both forks, right?



Right. If you own wrapped eth, your assets will exist on both forks. You can use the bridge fork and pull out your funds on the L1. 



What about your wrapped eth on the canonical fork?



The canonical fork is disconnected from the L1 bridge. Any wrapped eth on that fork will not be redeemable for eth on the L1. Those assets have little to no value.



If the bridge fork holds all the value, why don’t we just make the bridge fork the canonical one?



The bridge fork only holds the value the assets bridged from ethereum. Wrapped eth. Wrapped USDC. Those kinds of things. For those assets, the bridge fork is the source of truth. It’s the only way to redeem the assets for the unwrapped token.



For any other assets on our chain, including our native token, all our NFTs, our ERC20 tokens, etc. The source of truth for those tokens will be the canonical chain. On the bridge fork, those assets will have no value.



I’m trying to wrap my head around this… you’re staying that all the tokens will exist in both chains, but each token one fork where it is valuable, and one fork where it is worthless. Depending on the token, it might have value on one fork or the other.



Right. Any wrapped assets will live on the bridge fork. They will have no value on the canonical fork. Any other assets will live on the canonical fork. Those assets will have no value on the bridge fork.



Wait….



Okay, so let’s say I own some wrapped eth. That will exist on both forks, right? But the wrapped eth is worthless on the canonical fork. So let’s say I go on the canonical fork and I use a Dex to swap out all my useless wrapped eth for a native coin. That coin has value on the canonical chain.



Now… on the bridge fork, I still have the wrapped eth. I can safely redeem that for eth on the L1.



Yes. That’s right.



So I just doubled my money, right? That’s not possible. Someone has to lose.



Right. The liquidity providers are going to lose their shirts here. Well… depending on the pool.



Depending on the pool?



If you’re providing liquidity in a pool where both assets are native, you’re fine. If you’re in a pool where both assets are bridged, you’re fine.



If you’re providing liquidity in a pool where one asset is native and the other asset is bridged, you have extreme loss exposure. One asset in the pair is useless. That asset will be swapped for the asset of value until the pool has nothing but worthless tokens left. When you withdraw from the pool, there won’t be any value left. You’ll have lost everything to divergence loss.



We can’t let that happen, right?



This is the risk you take when you provide liquidity. If I were an LP, I would exit the pool as quickly as possible. 



Remember that the liquidity pool exists on both forks. Each fork will have the opposite effect. Let’s take a liquidity pair which has wrapped-eth and the native token.



On the bridge fork, all the native L2 tokens are worthless because it’s not the canonical chain for the L2. Users will swap out the native tokens for wrapped eth until the only thing left in the liquidity pool is the useless native tokens.



The same liquidity pool exists on the canonical fork. On the canonical fork, the wrapped eth is useless because that fork is not connected to the bridge. On that fork, the wrapped eth will be swapped out for the native asset until all that’s left in the liquidity pool is the useless wrapped eth.



There’s going to be a frenzy of activity when we turn on the sequencer. Gas prices will go through the roof as users clamor to capitalize on the situation or protect their assets. I expect users will leverage borrowing protocols to borrow the worthless tokens and swap them out for useful ones.



What other kinds of protocols are at risk?



It’s hard to say. It’s hard to foresee all the repercussions of this. Anyone who is in a contract which allows swapping a native token and an L1 token can be exposed to extreme losses. 



So NFTs sales.



If your NFT is for sale, and the sale is denominated in wrapped eth, you’re in trouble. The wrapped eth is useless on the canonical chain. Anyone will be able to get wrapped eth for very low prices and buy your NFT.



There are also problems on the bridge chain. Imagine you made an offer for an NFT to buy it for 1 wETH.



The seller can accept your offer on the bridge chain and collect the valuable wETH. However, the NFT you getting back is useless, because it’s on the bridge chain, which is not the canonical chain for the NFTs. The seller still owns the NFT on the canonical chain.



Okay. So if you hold a token, you’re safe, but if you’re in a contract which allows for swapping native tokens and bridged ones, you’re in big trouble. The sharks are going to eat them alive.



What if we give the liquidity providers a chance to get out? When we turn on the sequencer, we can ignore all transactions that are trying to swap in those pools. This will give the liquidity providers a grace period to exit the liquidity pool before we allow trading in the pool. 



That would be the ethical thing to do, but unfortunately we can’t do that. What you’re describing is censorship. If we do that, even for good reasons, We’ll lose the community.





