---
title: "Black Mirror: Blockchain Edition"
hidden: true
description: "How Rollups *Actually Actually Actually Actually* Work"
header: 
  teaser: "https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeielzz7kfwx4rafc4jydlq7aapul75ihacypuzqyhxj4nblixfvkie"
date: 2024-12-11T15:34:30-04:00
---
<style>
  .dialogue {
    overflow: hidden;
    margin-bottom: 15px;
  }
  .dialogue img {
    width: 31%;
    height: auto;
  }
  .left img {
    float: left;
    margin-right: 15px;
  }
  .right img {
    float: right;
    margin-left: 15px;
  }
  .left p {
    text-align: left;
  }
  .right p {
    text-align: right;
  }
</style>

This story was inspired by [How Rollups *actually actually actually* work](https://dba.mirror.xyz/LYUb_Y2huJhNUw_z8ltqui2d6KY8Fc3t_cnSE9rDL_o), by Jon Charbonneau, which was inspired by [How Rollups *actually actually* work](https://www.youtube.com/watch?v=GlxSP_ABE4Y), by Toghrul Maharramov, which was inspired by [How Rollups *actually* work](https://www.youtube.com/watch?v=NKQz9jU0ftg), by Kelvin Fichter.

<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiag2j7ea3st7qvgveo3t64ffhmcs2yg5lrqhixaqgvveoufwtoj5i" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiho7t3vxg3tgxruus2tq4nhlgnhnbi2gzwgwnkgumd2epdfrgx2yi" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeidbppeqv7fbvifcvnebm6tq2g67jr3cctqczdzxveg3c727723kxi" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
</div>
<br />

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeigzswrj5syxmmwkvmgu26ns5inq3rk2fjcqjq2fd245haoqlahgrm" alt="drawing">
  <p>Borinkski. This better be important.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Sir, we have a big problem.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeigzswrj5syxmmwkvmgu26ns5inq3rk2fjcqjq2fd245haoqlahgrm" alt="drawing">
  <p>Okay. Well get on with it.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Jelly Finance got hacked. There was a vulnerability in one of the contracts.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeia44q7nhwd7q6fhvalxjyjp362x7f7doayxzqz3ctwg7fx66o3l2m" alt="drawing">
  <p>Fuck. Which contract? Not the liquid staking...</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>It's the liquid staking.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeidjsprtl5mtq42wwl3dlxc74qn22lepwfjf7fxszdxkryqlyhpwqm" alt="drawing">
  <p>Shit. When?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Started about 10 minutes ago. They’re still draining accounts. The Jelly team is trying to patch the contract, but they can't get the transactions to post. The attacker's still draining funds and everyone is trying to pull out. The chain is all bogged down.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeidjsprtl5mtq42wwl3dlxc74qn22lepwfjf7fxszdxkryqlyhpwqm" alt="drawing">
  <p>What’s the damage?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>We’re still analyzing. Two billion at least. Losses are still climbing.</p>
</div>

<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeic46djruliudbbwmeokl46so6hfvtluu57zifk5rf36vw364qzky4" alt="drawing" style="width: 50%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeih4y2cyakxcl427asambrgvyzztn55sbzfjuwx6rp23e7s4733gjq" alt="drawing" style="width: 50%; height: auto; font-size: initial;"/>
</div>
<br />

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Give me an upper bound. What’s the TVL in those contracts?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>30 billion.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Fucking hell. I warned the Jelly team about this bullshit. They're too careless. They have no regard for security. Did we post those transactions to the L1 yet?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>I don't know. Patrick, can you check on that?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Hasn’t posted yet. Next update is in 5 min--</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Shut it down. Shut down the sequencer.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Shut it down? Are you... sure?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Shut it down.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Okay, it's just... X is gonna have a field day with this. They already give us a hard time about the centralized sequencer. When they find out we intentionally shut it down...</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>That's the least of our worries. If those transactions post, we can’t roll back anymore. We need to keep our options open. Shut it down.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Roll back? You can’t be serious. What about the transactions that aren't involved in the hack?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>They haven’t posted to the L1. They’re not finalized.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Well, technically, yeah, but we’ve never rolled back anything. Our users trust the preconfirmations. They don’t wait for the L1.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Judith. We can debate the rollback later. Shut down the sequencer.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Patrick, can you handle that?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>I'm trying. I don’t have access. There's a lot of security guardrails on this machine. I need Jill to approve the SSH request. She's on vacation.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Gah. Are you kidding me? Patrick, how long do we have?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>3 minutes.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Page everyone. Get me the data center. We need someone on-site, now. Do <i>not</i> let those transactions post.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>I'm paging the data center now.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Bulldoze the building. I don't care how you do it. Turn the sequencer off.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>We've got about 1 minute, 20 seconds.</p>
</div>

<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihaf7oueyv3m2aye4zgglsdiktimlgucye55r3bejzbmylsvv6zme" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibw6psmb7opdcuejqv4c2fk2k74t737wpqklrc3726gnwlpmrg5cu" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeigsczf3oj6cqahlcxrjzd2wnhtxe6wxblfzbeu4pihwlezqaepetm" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
</div>
<br />


<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Where's the damn N.O.C. rep? What the fuck do we pay them for?</p>
</div>


<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiaymhsntltlmxgttwvhqxd7ggtsayrh32b5krixotkqxygc6vroma" alt="drawing">
  <p>Hey this is Jack over at--</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Jack, you're at the data center?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiaymhsntltlmxgttwvhqxd7ggtsayrh32b5krixotkqxygc6vroma" alt="drawing">
  <p>Yeah.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Jack, we need you to kill our sequencer, immediately. Pull the plug, and we need it done in the next 30 seconds.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiaymhsntltlmxgttwvhqxd7ggtsayrh32b5krixotkqxygc6vroma" alt="drawing">
  <p>Guys, you know I can't do that. I can't even prove this call is authentic. They got these AI voice clone th--.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Listen to me, Jack. There's been a major hack. Look it up. It's all over X. If you don't kill that server in the next 30 seconds, billions of dollars are going to go down the fucking shitter! You're the only person that can stop it.</p>
</div>

<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibvakolpq6fdq6uj45uikpeseee5uixrm55xb5ousvy23o4wsfsda" alt="drawing" style="width: 50%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihxz3kibzzm6atligi72ftkrd276mlmmenitdizeleny2qewwmyky" alt="drawing" style="width: 50%; height: auto; font-size: initial;"/>
</div>
<br />

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Now, Jack!</p>
</div>

<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeidxi6sb7x4dhgfe6hgukwtdbjzsyetssjp3lr65x6xeffiwfoja5e" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeicml6tlh75w277y4q4qofvkmjgnbt3a7fkt2bkhzop7jex4inroha" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiahebqcn6fny5jvm77rdr6g4oxj5trgabkdv2k6pw4birhthazoo4" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
</div>
<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeidcvvx6elgbsggb42uue2yhuwrvrx52mxcjazqh2n4rs4usdsnpce" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeier456limcxfkuqtsurnepfdt77mz75e2qdgrjre3n2phi3abz6ky" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiaw4weoyp5tqqyucrssvlybf5dqpqorvcgzfsggai6cer4m7h3df4" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
</div>
<br />
<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Patrick. Time check.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Hard to say. Less than a minute. Seconds, maybe.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Hurry up, Jack. Nuke everything.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Jack. Did you kill it?</p>
</div>

<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeielzz7kfwx4rafc4jydlq7aapul75ihacypuzqyhxj4nblixfvkie" alt="drawing" style="width: 50%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihuwfc2jcalyvwpm4w4e23dbityhwc6a4o6pqepiko5cnaj7ch2qm" alt="drawing" style="width: 50%; height: auto; font-size: initial;"/>
</div>
<br />

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeieerpxf6ke6lotchsyy6pnyebtubn6wonmh5jhiq7vnohmze56u34" alt="drawing">
  <p>Yeah. I got it.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Patrick, can you confirm we're down?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>One sec, let me refresh... Yeah, stats are flatlined. Can someone open up their wallet and try a test transaction?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Never mind that. Patrick, check the L1. Did we kill it before the update?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Hold on, I’m checking....</p>
</div>

<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeigmnh66lbi6fu7bqfbuyojbxikttjkes4vggijtpmuyn53ps4ujme" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
    <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihq5cfp2g5kik6o45bhbm3v64qwv26n7q5rpzxspu74lx3v3gfwoi" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
</div>
<br />

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Oh fuck. It posted.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Are you fuckin' with me?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>No. The transactions posted to the L1. I can send you the hash.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Fuck.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>There's a user on X that calculated the losses. It’s almost 25 billion. As far as I can tell, the calculations seem right.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Holy shit.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>It's blowing up. Everybody’s saying roll back. We need to prepare a statement.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Can we call Vitalik? What if they roll back the L1?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>It’ll never happen. Judith... How much value is locked in the bridge contract on the L1?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Let me see... Looks like about 4 billion.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibiqluicewk6yyddl2qemscxo2zjhzpeeeorex77dhej5a3g727wa" alt="drawing">
  <p>Jesus. Okay. Everyone grab some coffee. It’s going to be a long night. What we’re about to do is something we said could never happen. Everybody take a minute. I’m gonna step outside. I need a cigarette.</p>
</div>

<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeig5e2f2mgk7zyhqo2vuwdlfy5n33syimornim3thgwomoqccw2a7y" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeicxdfk4hmbnw4dl6mqkdy445hw6elgkihdkzvcseimubsgfim4xqq" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeifv36im7diamawpspd5rjdvonffeoz4iccclb4jdu7oltku65us5e" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
</div>
<div style="border: 5px solid black; padding: 10px; display: inline-block; font-size: 0;">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeibakc2vrcnvqkok765nr5zmn5nmkf7c25e3wrzh7wu3cvbh2csoiu" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeid4m6v2c7jkejvnh5sqhrdvzulyu75o3j24nxv3fclqbhlggyqecm" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeigoq5qi2cfhvs4p3fvd7lnwn6h26cp437sgtlnehodbfreui4g2gu" alt="drawing" style="width: 33.33%; height: auto; font-size: initial;"/>
</div>
<br />

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Okay. Here’s where things stand. 25 billion was lost in the hack. Unfortunately, those transactions have already posted to the L1, and that's going to make this rollback very complicated. The cascading impacts of this are something I'm still wrapping my head around.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>I mean, we can't roll back anymore, right?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Yes we can.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>What do you mean? The bridge contract on the L1 is immutable. It won’t let us revert to an older block. We can’t roll back once we post to the L1. You said it yourself.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>I know what I said, but that was before I knew the full extent of the losses. We can roll back, it's just going to be extremely painful. The L1 bridge can't roll back with us, and so we're going to have to fork away from the L1.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Fork away? What do you mean?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>What I mean is that the L1 bridge will have one view of the chain, which is not rolled back, and our sequencer is going to have a completely different view... a fork. On our fork, we will perform the rollback. This fork will be completely disconnected from the L1 bridge.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>What? We can’t fork away from the bridge. We’re a rollup. It’s in our whitepaper. We’re an L2. Ethereum is the source of truth.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>I know what’s in the whitepaper, Judith — I wrote it. But this isn’t up to us. We’re a decentralized blockchain. Things are decided by social consensus.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Sounds to me like <i>you're</i> deciding.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>I'm not. We’re going to launch <i>two</i> sequencers. One sequencer will have the rollback, and one won’t. The community will determine which chain is canonical, but based on the losses we’re looking at, I'm certain the rollback fork is going to win.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>How do you know?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Because it's happened before. In 2016, there was a hack on Ethereum and the chain rolled back. Our losses are bigger than that. 20% of all the value on chain was just hacked.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>There were no L2s or bridges back then. We can’t fork away from the L1. We’re an L2 — An extension of Ethereum.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>You wanna know what happens if we don’t give the users a rollback option? Someone in the community is going to launch an alternate sequencer, a sequencer that has the rollback, and that sequencer will become the canonical chain. There's nothing we can do to stop the rollback. The sooner we accept that, the better. If we fight this, we will lose our sequencer and all the transaction fees that go along with it, and we all better start looking for new work. Running the sequencer is a privilege, not a right, and I have no intention of losing that privilege.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>I’m still confused. There’s a bunch of ETH locked in the bridge contract, right? If our fork isn’t connected to the bridge, how will people get their ETH out?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>The users will have wrapped ETH on both forks. They can use the fork that is connected to the bridge to redeem their ETH on the L1.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>So what about the wrapped ETH on <i>our</i> fork?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>It’s worthless. It’s not connected to the bridge. It’s not backed up by anything.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>If the tokens on our fork have no value, why are we doing this?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Not <i>all</i> the tokens on our fork are worthless. This only applies to the <i>wrapped</i> tokens — The L1 tokens locked in the bridge. Those bridged tokens live on Ethereum, and so they have no value if you can’t redeem them on the L1. All the other tokens — Our native token, our NFTs, our ERC20 tokens... Those tokens live on our chain. They will only have value on <i>our</i> fork.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>But all the tokens will exist on both forks, right?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Right. All the tokens will exist on both forks, but the wrapped tokens will have no value on our fork, and our native tokens will have no value on the bridge fork.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>I’m trying to wrap my head around this... You’re saying that <i>all</i> the tokens will exist in both forks, but each token will only have value on a single fork.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Right. The tokens can't have value on both forks. It's not like we can all just double our money by forking.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>So the users' funds are all safe?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Yes.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Not exactly.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>What do you mean, Patrick? What funds aren't safe?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Well, let’s say I own wrapped ETH. My wrapped ETH is safe, because I can pull it out on the bridge fork.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Right.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>But I also have wrapped ETH on our fork, right?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Right. The wrapped ETH on our fork is worthless, but that's fine. You have your value on the bridge fork.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Yeah, but then on our fork, I can still use a DEX to swap the worthless wrapped ETH for a native token. Now I have the valuable ETH on the bridge fork, but I <i>also</i> have valuable native tokens on our fork. I doubled up.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Ah, Shit. Yeah. Patrick is right.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>It’s not like everyone can just double their money though, right? Someone’s gotta hold the bag here.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Yeah, it’s the liquidity providers. People are going to remove all the valuable tokens from the liquidity pools. If you’re providing liquidity in one of these pools, you’re gonna get cooked by divergence loss.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Yes, but this only applies to pools where the trading pair is one native asset and one wrapped asset. If the assets in the pool are both native, or both wrapped, you should be fine. For pools that have one native asset and one wrapped asset, they're straddling the fork, so they're exposed on both forks. Each fork will have one useless asset in the pool, and one valuable one.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>We can’t let that happen, right?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>There’s nothing we can do about it. This is the risk you take when you provide liquidity.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>You're saying they signed up for this?! We told them we were part of Ethereum. We said this kind of thing was impossible!</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Listen. Like I said before, there's nothing we can do to stop this fork. There's 25 billion dollars in the hack, and there's only 4 billion L1 assets locked in the bridge. The majority of those wrapped assets are safe. Yes, some of those funds are in these liquidity pools, and there's nothing we can do about that. This fork is happening. If I were a liquidity provider, I would exit these pools as quickly as possible.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Even if they want to get out, it's gonna be hard to get the transactions through. There’s going to be a frenzy of activity when we turn on the sequencers. The congestion will be insane. The sharks are going to use lending protocols to borrow whatever assets they need to drain these pools. The pools will be empty in minutes. I have half a mind to do it myself. If <i>someone's</i> gonna slaughter them anyway, might as well be us.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Patrick... you better--</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>Just kidding, geez. Come to think of it, it’s not just the liquidity pools, either. Any contract that lets you exchange native tokens and wrapped tokens is exposed.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>That's just the liquidity pools, right?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihfgmywf6lpgx3k2p6j23qw636x3hg3jap2vwhufi4izyj3ifnwoy" alt="drawing">
  <p>No. Like imagine you have an NFT listed for sale for 1 wrapped ETH. That NFT will live on our fork, but the wrapped ETH is worthless there, so anybody can buy your NFT for almost nothing.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Ah, yeah. That's right. Those are at risk as well. That's a much smaller market though, compared to the liquidity pools.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>I have an idea. What if we give all these exposed people a chance to get out?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>How?</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Well, we know the sharks are going to try to drain the liquidity pools. What if we disallow any trading in these pools for a short period? We can give the liquidity providers a chance to exit the pools first. During the grace period, the sequencer will only accept requests to exit those liquidity pools.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>It’s a good idea. Ethically, it's the right thing to do. Unfortunately, though, we can't.</p>
</div>

<div class="dialogue right">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeihkf5xiyp3so7qfro3hdzhtewst3f3rw7jh25pcmyl55v5otnkmzy" alt="drawing">
  <p>Why?</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Because what you’re talking about is censorship. Once we censor transactions, we will lose all trust from our users.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>We need to act fast here. Patrick, I want you to work on launching the new sequencer. Work with Jelly to patch the fucking bug in their contract first. We'll also need to create a new L1 bridge for the new sequencer.</p>
</div>

<div class="dialogue left">
  <img src="https://emerald-frequent-panther-621.mypinata.cloud/ipfs/bafybeiai3i7qsdsc5hj47ajhpevwifnxowcd6idbdcwbnrznyqmn47zmjq" alt="drawing">
  <p>Judith, prepare comms. We should encourage the users to withdraw their ETH from the bridge fork, and then send those funds to the new bridge that's connected to <i>our</i> fork. Make sure the users understand that there was no exploit in our chain. The problem was an exploit in the Jelly Finance contract. Loop in the team at Circle and any other stablecoin issuers. Their tokens will exist on both forks, but only the tokens on our fork will be backed up by the issuer.</p>
</div>





















