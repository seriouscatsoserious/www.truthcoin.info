---
title: Popular Mining Lies / The Mining Grift
show_author: true
comments: true
date: 2025-05-26 04:00:00
---




### Summary

Mining has always been *perfect*.

This is in part because it is so **perfectly** designed.

But it's perfect in practice, too! Blocks are **always** found, roughly 1 per 10 minutes. Transactions have **never** been censored. There has **never** been a large reorg. Bitcoin's miners have never misbehaved -- ever.

So, why do people view the miners with such... hostility?

Or concern? Why do they *concern-troll*, so much? Why pay any attention at all?

### Miner's Supposed Crimes

Supposedly, miners did wrong on a few occasions:

1. The [blocksize war](https://old.reddit.com/r/Bitcoin/comments/5xg7f8/the_origins_of_the_blocksize_debate/) (siding with Jihan Wu and largeblockers).
2. Being slow to adopt the Segwit upgrade.
3. SegWit2x - a contentionus hard fork supported by 83% hashrate.
4. July 2015 -- glitched [upgrade to 0.9.5](https://bitcoin.org/en/alert/2015-07-04-spv-mining), resulting in [6 invalid blocks](https://www.coindesk.com/markets/2015/07/06/double-spending-risk-remains-after-july-4th-bitcoin-fork).
5. March 2013 -- glitched [upgrade to 0.8.0](https://en.bitcoin.it/wiki/BIP_0050), resulting in [a 24-block reorg](https://blog.citp.princeton.edu/2015/07/28/analyzing-the-2013-bitcoin-fork-centralized-decision-making-saved-the-day/).
6. Today -- "getting too big" -- by perhaps forming a 51% pool.

But, in fact, the miners are *innocent on all counts*. 


## Part 1 -- The Easier Ones

First I will mop up claims 2-5.

### A. Invalid Blocks

First, #5, the March 2013 incident -- involved miners *obediently* upgrading to 0.8.0 (as they were told to do by devs), even though devs had accidentally overlooked a mistake in the database lock system. Miners then *obediently* down-graded, to fix the problem -- (costing themselves roughly 600 BTC).

Second, #4, the July 2015 incident -- some lazy miners did indeed mine invalid blocks. However, *none* of these blocks were accepted by full nodes -- *ever*. Each block would have been worth 25 BTC, if it had been valid -- so each miner only managed to destroy 100% of their revenue, for no benefit.

### B. SegWit2x

Third, #3, SegWit2x -- it is true, that some large miners and pools, once signed a piece of paper in favor of SegWit2x.

But they *never* ran the SegWit2x software! In fact, at the 11th hour, right before the SegWit2x activation date, [ie, at the time when they had to actually switch to the software,] they *pre-emptively gave up*. This is because the fundamentals were way against them: [1] hashrate does not help you win a hard fork, and [2] even if a miner preferred the 2x-coins, they could get *more of those coins* by waiting and mining whichever coin had a higher market price (then selling this $ for 2x-coins). So, the whole SegWit2x strategy was terrible -- when they realized this, they all pulled out.

Frankly, it is evidence of the system *working perfectly*. There was some *cheap talk* -- which the wise could safely *ignore*. When push came to shove it was just empty words.

### C. SegWit Upgrade Controversy

Fourth, #2, slow to adopt SegWit -- this is true. But this event is a *combination of misunderstandings*.

* First, miners felt (wrongly) that by withholding SegWit, they could extract concessions from developers (this later proved to be false). Miners no longer believe this -- because it isn't true.

But how did miners come by this idea, in the first place?

That is the second misunderstanding:

* Back in 2012, the P2SH soft fork was programmed to activate on a certain day (Feb 1), if enough hashrate had upgraded. However, not enough hashrate had upgraded -- so the date had to be pushed back. And even after the official activation, some users (including miners) had not upgraded, producing invalid blocks occasionally. To avoid all this, the system was reworked, and -- for reasons of courtesy -- the threshold was made very high (95%). At the time, *no one* would have interpreted this as a "vote" -- because soft forks were *not* controversial. 

But why was it (mis)-interpreted as a vote?

And why was SegWit interpreted as *pro-smallblock*, in the first place!? It was itself a *mandatory blocksize increase* (from 1 MB to 4 MB)!

These questions takes us to *the blocksize war* -- itself a constellation of misunderstandings.


## Part 2 -- The Blocksize War

Many common believes about the blocksize war are wrong. 

The truth is: the blocksize war proved how *reliable* and *well-behaved* the miners are -- (not the reverse as is conventional wisdom).

### A. My Pristine Credentials

It's rarer (these days), but occasionally, someone tries to slander me, by saying: "Paul was a largeblocker! Paul was wrong on the blocksize war" -- blah blah blah.

That's not true. The misunderstanding probably is due to my many largeblocker friends, and associates -- including (proudly) Roger Ver. In any event, I'll take this moment to present the overwhelming evidence to the contrary, which includes:

* Oct 2016, (at Scaling III), [I proposed](https://www.youtube.com/watch?v=Gzg_u9gHc5Q&t=6575s) *shrinking* the L1 blocksize -- I am [still in favor](https://www.truthcoin.info/blog/sc-vision/) of this, [today](https://x.com/Truthcoin/status/1678793061642428416)! That's right, I have always been a Luke-Dashjr-style super-smallblocker.
* Dec 2016, I wrote ["Against the Hard Fork"](https://www.truthcoin.info/blog/against-the-hard-fork/) -- back then, all blocksize-increasers were pro-hardfork.
* After May 2017, there was [an important table](https://web.archive.org/web/20170810234850/https://en.bitcoin.it/wiki/Segwit_support) -- I was specifically *sought* for comment, and you can see that my entry is pro-SegWit, anti-Segwit2x -- just like the other small blockers.
* [Also] Back in Sept 2015, (before Scaling I, even), I wrote ["Measuring Decentralization"](https://www.truthcoin.info/blog/measuring-decentralization/) -- explaining how large blocks harm decentralization. I was the first, to formalize this argument!

My track record is *excellent*. My main mistakes have been: [1] assuming people would understand sidechains; [2] assuming people would be enthusiastic about sidechains; [3] assuming sidechains would quickly destroy Altcoins and help Bitcoin take over the entire world. *All those predictions* would have *come true* -- if Bitcoiners weren't (no offense), so stupid. (On this one topic.)

With that out of the way...

### B. The Lead-Up

...I'll now review the history.

In 2015, the blocksize war had heated up. In Aug, Mike Hearn [announced "BitcoinXT"](https://www.theguardian.com/technology/2015/aug/17/bitcoin-xt-alternative-cryptocurrency-chief-scientist) would hard fork -- Scaling I (Sept 13th 2015) was called as an emergency meeting. Even during Aug, the plan was to have a second conference, Scaling II (Dec 5th 2015), hot on its heels. The consensus after Scaling II, was to unite behind SegWit. This led to the Feb 21st ["Hong Kong Agreement"](https://medium.com/@bitcoinroundtable/bitcoin-roundtable-consensus-266d475a61ff) -- which had [a variety of interpretations](https://old.reddit.com/r/btc/comments/69w74o/just_a_reminder_about_the_text_of_the_hong_kong/) -- but which some felt "promised SegWit by April 1".

Scaling III was not until Oct 2016.

During this period (Aug_2015 - Oct_2016):

* SegWit still had not shipped. (It would ship at the hackathon immediately after Scaling III.)
* BTC rose steadily from $250 to $630, (+152%) -- but not enough to retake its all-time-high (of $1,077) -- set back in Dec 2013.
* In contrast, ETH skyrocketed more than 10x as much (+1,757%) from $0.70 to $13.00 -- hitting new all-time-highs continuously. 
* As a percentage of BTC's mktcap, Ethereum went from 4.2% straight up to 11.3% -- including a dramatic moment in May where it shot up to 15.5%.
* Note: Humans are more motivated by *envy* (than greed). It looked like Ethereum was having all the fun! While we [in BTC land] were so miserable.
* Personal attacks were being traded, across social media -- for example, [this](https://web.archive.org/web/20160827085159/https://www.reddit.com/r/btc/) and [this](https://web.archive.org/web/20160928105044/https://www.reddit.com/r/btc).
* BitcoinXT had been abandoned -- but "Bitcoin Unlimited" (and "Bitcoin Classic") were gaining steam -- threatening to hard fork Bitcoin Core.

Thus, an **anxiety** loomed over Scaling III.


### C. Scaling III

Let me continue to set the stage:

* People hadn't seen each other in a while. They didn't know the plan. Where was SegWit?
* People were nervous about what to do -- they wanted action. What was the plan for scaling? What was the plan to counter the rise of Ethereum, and maintain our market dominance?
* What if the blocksize dispute was just the first of many? Are we resolving disputes the right way? Does *everyone really agree*? If not, then maybe there *is* going to be a market for Altcoins, after all! 

[Pindar Wong](https://www.esf.edu.hk/internet-pioneer-pindar-wong/) -- (an early internet pioneer, seasoned professional, and veteran of the [IETF](https://www.internetsociety.org/board-of-trustees/minutes/36/) protocol wars) -- was active in Scaling I and II. But now he had bequeathed the conference to the young and inexperienced Matt Corallo (23 years old[^n]) -- a co-founder of Blockstream (the premier smallblocker organization).

[^n]: This is a guess of mine -- based on seeing him in person, and [this podcast](https://btcpodcasting.com/@anitaposch/episodes/matt-corallo/) which says he got into Bitcoin at 18 in 2011. 

When guests arrived, from all around the world, [*this*](https://web.archive.org/web/20161007145733/https://scalingbitcoin.org/event/milan2016#schedule) was the program they picked up, on Day 1:

![image](/images/scaling-3-program-sheet.png)

Basically none of it was about scaling.

See for yourself:

![image](/images/scaling-3-program-sheet-notated.png)

I myself gave the **only** Day 1 talk, that was on topic. My idea is still the best -- and probably *only* way of scaling Bitcoin.

Although Taproot gave us Schnorr signatures (in Nov 2021), it did not give us "signature aggregation" (ie, 99% of the scaling benefit -- mentioned in Pieter's talk on Day 2). That work was left to a later soft fork -- which hasn't yet occurred (and now, probably will never occur).

Covenants was later taken up by Jeremy Rubin -- of course. But there has been no progress toward activating them. Probably it will take 10 years! 

The other talks were basically irrelevant. Certainly they did nothing to alleviate the *stress and anxiety* felt by so many.

### D. The Accidental SegWit Blockade

Upon viewing the program, one miner was so angry, he immediately rebooked his flight (back to China) and left.

Others stayed, for the whole conference -- but on the whole, it was not worth the wait!

I don't remember if the guy who left immediately was the ViaBTC guy. But -- [twitter](https://x.com/ViaBTC/status/785423172770365440) and [reddit](https://old.reddit.com/r/btc/comments/56rbod/viabtc_switch_to_bitcoin_unlimited_vote_for_2mb/) evidence proves -- by 6 AM on Oct 10th, ViaBTC had switched from Bitcoin Core, to Bitcoin Unlimited.

![images](/images/via-btc-bu.png)

ViaBTC was about 9%-10% of the hashrate at the time.

Now -- let me remind you -- the 95% hashrate activation threshold was still in use at the time.

And -- on this exact day -- developers were hard at work, trying to finally ship SegWit (after months of effort).

So, obviously, the developers took this as a huge insult.

My guess is -- the ViaBTC guy probably *didn't know anything* about the 95% threshold. He was just angry and wanted to *do something*.

However -- the developers had now been "triggered". They were pissed off about this.

And the rest was history! The miners (and largeblockers) now thought: "we found something, that can piss them off!". And so they ran with it. Bitcoin Unlimited eventually got 55% hashrate (I think) -- I found [one WayBack snapshot with them at 33% (beating SegWit)](https://web.archive.org/web/20170318125435/https://coin.dance/blocks).

And this is the explanation for it all! That's why developers hate the miners -- even though miners have never done anything wrong, ever!


### E. The Aftermath [of the Blocksize War], Interpreted Properly

Even the aftermath is misinterpreted.

It is interpreted completely backwards!

#### i. The Conventional Wisdom

The conventional interpretation is:

* "miners lost"
* "miners don't control bitcoin, as we saw during the scaling war"
* "we, the little node runners, defeated *the big corporations* and miners"

#### ii. The Truth

But the truths revealed by the blocksize war, are much more modest:

1. "the hard fork, is very unlikely to work"
2. "largeblocks are not as popular as smallblocks"
3. "a 2x scaling improvement is not really worth the trouble of a hardfork"
4. "BCH was not a good idea [even if largeblocks were]"

#### iii. The Details

First, I wrote ["Against the Hard Fork"](https://www.truthcoin.info/blog/against-the-hard-fork/), back in 2016. I later wrote [this](https://www.truthcoin.info/blog/mahf-and-replay/), [this](https://www.truthcoin.info/blog/garp/), and [this](https://www.truthcoin.info/blog/imex/), about the practical difficulties involved in pulling off a hard fork. The pro-hardfork people are rarely interested in this sober analysis -- instead they are champing at the bit, they want to launch the new coin and get on with building a new community and competing for greatness! Who can blame them. But, every hard fork has so far failed. BCH is today less than half-a-percent of BTC. The other coins [Bitcoin Gold, Bitcoin Diamond] are frivolities.

Second, various techniques were used to measure support for Large Blocks. One was ["fork futures"](https://www.truthcoin.info/blog/fork-futures/)...

![images](/images/fork-futures-2017.jpg)

...(tweet [here](https://x.com/Truthcoin/status/931348354545614848)) which put support for SegWit2x at about 11%. When the prices materialized (upon the launch of BCH), these were indeed the prices! (Although, admittedly, the price was pretty volatile overall.) But, it did hover around 11% on average, fo

Why was support only 11%? Well, at the time, *most people* didn't want to introduce the chaos of hard forks, just for a 2x benefit. Most people were optimistic about lightning, and wanted to give it a try -- let developers cook some stuff up. Necessity was the mother of invention.

Third, the 2x improvement would not have permanently solved the problem. We would have to hardfork again, in the future. This begged some questions: [1] "why not remove the *whole* limit, immediately?", and (if not) [2] "are we going to hardfork, over and over again?". Will there be a committee that answers these questions? What if the committee is incompetent, or malicious?

Although BSV would later bite-the-bullet, and remove the limit entirely -- at the time, no one advocated this. Gavin Andresen himself, said...

![images](/images/gavin-quotes-lost.png)

Although, those quotes (and whole threads) have since been deleted. This was a very contentious period, and /r/bitcoin mods would often delete whole threads, if they leaned largeblocker-ish. Interestingly, though, the AI "perplexity.ai" still "remembers" the quotes, somehow. These quotes match my memory.

Fourth, and finally: BCH was poorly executed:

![images](/images/the-bch-mistakes.png)

Above: a table of BCH Mistakes, as [I tweeted here](https://x.com/Truthcoin/status/1557189048623681537).

Furthermore, for anything with network effects, there is really only room for *two* "serious" projects. One leader, and one opposition (it is exactly the same, as the American two-party system). As [I tweeted here](https://x.com/Truthcoin/status/1556369912695758862). The leader is BTC and the opposition is ETH -- leaving no room for BCH.

#### iv. Conclusion

So -- the largeblockers were sunk, by their many mistakes, before the "war" could really beging. They basically destroyed their own side, immediately.

And so -- the story of "miners attacking Bitcoin" during the blocksize war, is false. Even the largeblockers themselves, never really got their attack going. Some mining pools were frustrated, and offered up their opinion, at various times -- this hardly counts as an "attack". No transactions were censored, no blocks were reorged -- nothing bad happened, at all.

#### v. In Fact...

In fact, this whole episode is further evidence of **friendly miners**.

Because -- if miners wanted to attack, they **could easily** have increased the blocksize, via a mandatory extension block [soft fork]. SegWit was one such example!! And -- with a soft fork, 83% **could** easily have gotten their way.

But they did not!

#### vi. Furthermore...

Furthermore, when Taproot was finally ready for activation -- miners jumped to activate it quickly.

Developers were actually *dragging their feet*, on it -- and getting nowhere. They were afraid to get involved, (literally) with activation. Finally, "speedy trial" was proposed -- and the miners rushed to be helpful and supportive.

Because miners are so perfect, in every way, miners will even **courteously absorb** your inane criticisms. At the risk of off-topic metaphor, miners resemble *fathers of a household*. Supposedly, more money is spent on Mother's Day than Father's Day. Fathers, are also criticized more than mothers. This is because men just "suck it up" -- life is unfair, but fathers just deal with it. Why complain? Like some crybaby? Men just suck up the negativity, like a sponge -- for the good of society. This is basically how the miners are. If you want a punching bag -- they are all for it. Like a true friend, they're down for anything.

The problem is: this attitude is hostile to the truth.



## Part 2. The Grift!

So -- if mining is perfect, why the complaints?

Who is complaining? Are they lying? And why?

### A. Cashing In on The Bullshit

Virtue signaling, of course.

And it's big money, baby:

1. Aug 2022 -- [Foundry donates 1 BTC to StratumV2](https://bitcoinmagazine.com/business/foundry-digital-donates-1-btc-to-fund-bitcoin-mining-pools), to help "decentralize mining".
2. Oct 2022 -- [BitMEX, Foundry, Galaxy Digital [enormous companies] etc "support" StratumV2 working group](https://bitcoinmagazine.com/business/spiral-braiins-launch-working-group-for-stratum-v2), to help "decentralize mining".
2. Nov 2023 -- [$6.2 Million raised for OCEAN](https://cointelegraph.com/news/jack-dorsey-raise-decentralize), to "decentralize mining"
3. Jan 2025 -- [HRF grants 7 BTC (in part) for StratumV2](https://www.cryptopolitan.com/human-rights-foundation-hrf-7-btc-20-project/), to "decentralize mining"
4. Apr 2025 -- [Tether (HUGE company) to assign Hashrate to OCEAN](https://bitcoinnews.com/mining/tether-hash-power-ocean-mining-pool/), to help "decentralize mining"
5. May 2025 -- [OpenSats awards grant to P2Pool](https://opensats.org/blog/elevent-wave-of-bitcoin-grants)

"Virtue signaling" (in general) is dishonest -- because the speaker has **duped themselves**. They think that *they really are* serving a noble cause, to help "decentralize mining". Even though they are actually doing it [1] for a paycheck, and/or [2] to look good.

Of course, *the intent* is admirable. But there is a well-known road, to Hell, which is paved with good intentions.


### B. Drowning In Bullshit

All this nonsense, is a distraction to us Serious People.

The deluded people *present themselves* as sincere -- leading to wasted time.

For example, this **time vampire** is everywhere these days:

![images](/images/time-vampire.png)

![images](/images/time-vampire-2.png)


You see? "petty and immature personal attacks" (referring to me) -- and "organization providing important infrastructure" -- referring to OCEAN /himself.

But OCEAN is a shit idea. It is not "important infrastructure".

But *it wastes time* to find that out -- four days ago, [Pieter Wuille](https://x.com/fluffypony/status/1925266011801968915) figured out *the true extent* of this man's time-wastefulness.

Anyway -- that's the issue. **There is a huge incentive to lie** about mining, so that you can be **the savior**.

The murkier these terms are defined, the better -- that helps, to make it a better boogeyman. Any genuine menace, can be measured and understood -- and eventually defeated. But *something vague*, will be around forever. Hence [my attempt to measure mining centralization](https://www.truthcoin.info/blog/mirage-miner-centralization/) (back in Jan 2017) ended in failure.


## Part 3. My Submission to Bitcoin Magazine

### Background

Because of my heterodox views, Aaron van Wirdum (the Editor-in-Chief of Bitcoin Magazine) sought my opinion for their ["Mining" issue](https://store.bitcoinmagazine.com/products/bitcoin-magazine-issue-36). Which they printed! I'm right at the end -- giving "the other side". (I got the last word.)

I am reprinting it in full, here:

Written Jan 2025; Published March (?) 2025;

by Paul Sztorc, CEO LayerTwoLabs, Author BIPs 300/301

### "The Fraud of Miner Centralization"

If you want to trick good people into doing bad things, then it helps to pick a misleading name. For example, the USA "PATRIOT" Act was so-named to cast its critics as unpatriotic. "North Korea" is officially named "The Democratic People's Republic of Korea," despite (and, in fact, *because of*) being none of those three things. In Orwell's 1984, the Ministry of Truth exists solely to destroy the truth, the Ministry of Peace exists solely to destroy peace, etc. It is with this in mind that we must turn to one of the longest-lasting and pure-ist bullshit scams in all of Bitcoin's history: Miner Centralization.

Peter Todd, Matt Corallo, some Blockstreamers, a few failed miners (who can't win on merit), and some self-important academics -- these are the few people who prop up this fake idea. Like the "patriot" act, they hold up the word "centralization", and hope you will automatically assume that: [1] something real is being discussed, [2] it is definitely a bad thing (of course), and finally [3] the entire Bitcoin community already agrees that it is bad. That is how stupid they think you are. And an easy mark! For --so they think-- you will now take out your wallet, and fund their SV2 project, or Ocean, or consulting (or their other bullshit schemes).

Before I demolish the fraud idea of Miner Centralization, let me provide some true background information about Mining:

1) Why does the mining process exists at all? Because a centralized repository is not a reliable monetary database. That failed idea was tried, (with DigiCash, Liberty Reserve, e-gold, etc), and it didn't work.
2) Does the difficulty adjustment algorithm accept excuses? No -- it is pure accountability. Every two weeks, the bottom half are fired. Age, race, religion, "centralization", ethnicity, sexual orientation, etc -- these are are ignored. That's what it means to be a meritocracy: no whining.
3) If there is any txn censorship, then these transactions build up in the mempool, as a reward for anyone who will include them. It is as if Censors cut a check to Uncensors.
4) What if someone gets 100% hashrate forever? Forever can be a long time. As fee-pressure builds in the mempool, the uncensored block(s) will eventually be worth more, than all profit the 100%-miner expects to earn, ever, with their pro-censorship strategy. At that point they will either give up, or be out-mined.

In other words, we do not need to obtain a "decentralization permit" from the Department of Matt Corallo, in order to mine. Revenue maximization is correct. Cost minimization is correct.

Now, with that out of the way, we can begin the enormous task of unraveling the fraud that is "Mining Centralization".

First, like all fake ideas, it has no fixed definition. Sometimes it means: ">50% hashrate controlled by one pool". Other times it means: "the Chinese company BitMain makes the best (highest-quality, lowest-cost) ASIC chips, and I don't like meritocracy because I am racist against Chinese people". Next it meant: "hey, what if one group bought up >50% of the physical mining chips, what then? have you ever thought of that??". To the stratumV2 people, it means something like: "pools do not allow their customers to construct their own block templates (ie, choose which transactions are in the blocks they mine)", which in practice translates to: "my pool is working hard to make me more money, for free -- hey, instead can they allow me to ruin the whole pool, for everyone, for no reason? After all, I contribute 0.0001% of the hashrate of this pool, I should be allowed to destroy the whole pool (and the pool's brand, and reputation, which I had no part in making) because I am a retard".

Sadly, I was not given enough space to tackle all these frauds. But we can tackle one: **stratumv2**. After all, whenever the phrase "mining centralization" is heard, a chorus of mindless Pavlovian dogs replies: "stratum v2".

StratumV2 focuses on the following problem (which by the way, has never happened): you connect to a pool -- you mine there -- after a block is found, it turns out that some txns were not included, and so you didn't get as much money! Bad pool! Pre-SV2 (ie, right now) the solution would be to *switch pools upon detecting the fraud*. The *threat of losing customers* keeps the pools in line, and forces them to behave. Once we have SV2, the solution is instead to do this every block: first, all individual ASIC-owners decide which txns they want to include, and each builds their own aspirational block (called the "block template"); second, they send it to the pool; third the pool scans their template to accept/reject it; and finally you are allowed to "mine your own template". Thus, you are warned of pool-based censorship, *before the censored block* has been found -- ie, 10 minutes earlier.

That tiny microscopic advantage, must be set against SV2's enormous disadvantages. First, SV2 is more work. It must be installed and configured; miners must actually select txns (all day every day) to include in blocks, and must negotiate every job. Second, "job negotiation" is an insignificant aspect of the pool-hasher relationship. Pools only pay, *after* the Hasher's earnings exceed a threshold (0.001 BTC or so) -- until then, the Pool keeps the Hasher's money. This alone is roughly 100x more significant than a 10-minute early warning of slightly-less-than-preferable txn fee collection. Third, by shifting responsibility away from pools, we lose the ability to *blame* pools for bad blocks. Pools can hide behind SV2, and instead blame their hashers. This paradoxically makes censorship easier in the long run, because it is easier to scorched-earth destroy a misbehaving pool, than it is to track down a misbehaving hasher and persuade them to stop censoring (especially since they may not even exist).

Although "mining centralization" is a fake issue, I will close, with some suggestions for improving *competitiveness among pools* (which is real).

First, we should publish high-quality, high-performance, open-source pool software. Our "OpenPool" should obsessively maximize miner revenue (ie, it should be more like MARA's "slipstream", and not at all like OCEAN pool). Second, we should build a "pool hopper" technology that monitors pools for hashprice, and automatically directs hashrate to the most competitive pool(s). Once it is doing that, it can easily pull double-duty by scanning pools for misbehavior (censorship and reorgs) -- if all known pools are censoring, it can automatically trigger the creation of a new pool (and switch people to it). Finally, we should activate Bip300, because (among other things) it can lower the pool payment threshold by 10x or even 100x (by creating a hashrate-secured L2 for smaller frequent payments). These three steps make it easier to detect if a pool is misbehaving, and to do something about it.




## Part 4 -- Conclusion

My criticisms haven't yet killed-off the spectre of "mining centralization".

(Because people are still talking about it.)

Unfortunately for me, I *actually* know, what is best for Bitcoin and Bitcoin Miners. But -- if I talk about *that*, it lands me in the cross-hairs of the virtue-signalers.

The better thing to do, is describe *The Ideal*. Which I will do in [the next post](https://www.truthcoin.info/blog/ideal-mining/).

---