---
title: Unlimited Blocksize (BSV) and the Data Availability Problem
show_author: true
comments: true
date: 2025-04-30 05:00:00
---


### Summary

I will review the case against unlimited L1 blocksizes, focusing on the BSV-community's mis-emphasis on SPV.

Finally, I will apply this argument to other L2s (such as rollups and SNARKs). And conclude by explaining why Drivechain is superior.

I discuss these ideas in [my appearance on CoinGeek](https://www.youtube.com/live/n29r-eWA6Zo) (April 29, 2025).


### A. Intro

Imagine we need to put *The Lord of the Rings* trilogy "on the blockchain".

Which blockchain, should we use? BTC or BSV?

Well, BTC has a 4 MB blocksize limit. LotR [is 176 GB](https://old.reddit.com/r/criterion/comments/zt4l7t/malcolm_x_4k_might_have_the_largest_file_size_for/). So LotR won't fit "on" BTC... right? We have to use BSV.

Wrong.

I could put 10,000 copies of LotR "on" the BTC blockchain, right now. Or even a million copies. Or a million unique movies. There's no limit.

It would be different, if I wanted to put LotR "in" the BTC blockchain.

"On" and "in" make all the difference.


### B. Something for Nothing

If we want to eat -- then someone has to farm (or ranch).

If we want safety -- then someone has to stand guard.

Young children do not think this way. They want to eat candy all day -- without worrying about nutrition or stomachaches. They want to play all the time -- without earning money. They want clean clothes -- but they don't want to do laundry. They want a roof over their head; but they don't want to work construction.

Everything is about -- them! them! them! -- and rarely (if ever) do they give a thought, to how their behavior affects the people around them.

Unfortunately this is a metaphor for BSV.

BSVers believe that they have a bold, brilliant, new idea. But when you look under the hood, all you find is the [childish] belief "something for nothing".


### C. What BSV-ers Get Right

The BSV community is correct about a few things:

1. Bitcoin Core (the organization) is dysfunctional and a distraction. They are about 100 IQ points beneath Satoshi Nakamoto. They are pretentious, political, corrupt and corruptible. What little they have accomplished, has mostly been a failure. If BTC fails, they will suffer little -- they will find some other job.
2. Many other BTC-ers are also useless. It is easy to write a "Bitcoin" book, or sell a "Bitcoin" conference -- (or call yourself "Bitcoin" Core). Thus, they hitch their wagon to a strong horse. But Bitcoin (ie, Satoshi's idea) is mostly succeeding **despite** these people (not because of them). Satoshi is the engine of the train, BTC personalities are the caboose.
3. Lightning Network doesn't work. Disgracefully, some BTC-ers still pretend that it does work. Many of these work at Lightning startups, and/or have equity that will be worth a lot less, once Lightning is revealed to be a sham. Many bright programmers invested years building expertise/reputation in Lighting -- a complete malinvestment. Now they don't want to admit it. Then we might not be invited to the cool parties!
4. The fear of "regular blocksize increases" was overemphasized, in comparison to the fear of "cultural death spiral and no real users". We should test the Bitcoin software with higher blocksizes, so see how far the performance can be pushed. We should not accept the "boogyman" of an expensive node -- we should study it with numbers. (As I argued [back in 2015](https://www.truthcoin.info/blog/measuring-decentralization/).)
5. Today, the world's transactions are computerized (by VISA, Venmo, etc), and these networks *do* manage to process a large number of transactions, without bursting into flames. So we should be more open-minded to the idea of our network processing billions of transactions (in some way, eventually, at least in part). We shouldn't be so defeatist.
6. BTC has mostly abandoned its "users", and is instead distracted by "number go up". This is putting the cart before the horse -- and a mistake. Instead we should focus on users -- we should have billions of users, each paying a small txn fee.
7. SPV mode is a brilliant idea; we should emphasize it more. One day, perhaps 8 billion people will have their own SPV node, but only a tiny minority will run their own node. (However, BSV-ers misinterpret SPV, as I will explain below.)
8. A small node with no hashpower, does very little to protect "the network". (But -- it does *very very much*, to protect its owner's incoming funds. So BSV-ers are wrong about that part.)

Unfortunately, no matter how right you are, one single mistake can ruin your project. Imagine a new airplane design that is cheaper, faster, safer, better in every way. There's just one problem -- it doesn't fly. Well, that one mistake ruins the project.

The BSV mistake is today called "the data availability problem" -- ie, cost of maintaining one's mandatory data.

Among the BSV-ers themselves, the mistake comes in two flavors:

1. Regarding blockchain data as simultaneously **mandatory** and **optional**.
2. Misinterpreting **free-riding** as **literally free**.

In order to explain these, I will need to introduce some background information.


### D. Missing Data

If you look at the BSV code, you will find [these lines](https://github.com/bitcoin-sv/bitcoin-sv/blob/86eb5e8bdf5573c3cd844a1d81bd4fb151b909e0/src/validation.cpp#L4323-L4324).

![image](/images/bsv-smoking-gun.png)

"Missing data" is treated the same as "invalid data". Data is only tagged as "valid" if you [first] **obtain it**, and [second] run it through the validation functions.

(Every blockchain does this, not just BSV.)

This is supported by the Bitcoin whitepaper, which says...

![image](/images/every-byte.png)

...every byte that is *in* the blockchain, must be sent around to all the nodes. It must be processed.

As the final paragraph notes, even **old blocks** must be served to new nodes. If a node is *brand new*, it requests the *entire* blockchain history.

You can see why. If any block is missing (or invalid), then the sync will halt. It will stop, at precisely *one block earlier* than the missing block.

The whole point of the node, is to filter out double-spends. It cannot do that unless it knows who-spent-what.

### E. Blockchain Service Cost

Let us define **blockchain service cost** (BSC) as: "the cost of following the steps in Part 5 of the whitepaper".

In Bitcoin (BTC), this cost goes by many names. I would regard it as CONOP (the cost of node option); Bitcoin Core would regard it as the "cost of IBD" [initial block download], or the "cost of syncing a node". You could also call it the "cost of checking for double-spends"; or the "data availability problem mitigation cost".

BitcoinSV says "only miners are nodes". They regard small nodes (of low hashrate or zero-hashrate) as illegitimate. They are wrong -- but for now, it doesn't matter. After all, each new miner must follow the steps in Part 5 of the whitepaper, before producing new blocks. So, each new miner must pay the BSC.

To repeat, blockchain service cost (BSC) is: "the cost of processing [obtaining + validating + storing + serving], all of the bytes in the blockchain".

### F. Mandatory vs Optional Bytes

I will call these bytes the **mandatory bytes**.

These are the bytes "in" the blockchain. Every node has this exact set of bytes. All bytes were collected into txns. All txn were scanned. All are valid. None are double-spends. All are sitting on our hard disk. All will be provided, upon request.

In contrast, **optional bytes** are not in the blockchain. But some reference to them may be. For example, the Bitcoin Whitepaper has SHA-256 hash...

    B1674191A88EC5CDD733E4240A81803105DC412D6C6708D53AB94FC248F4F553

...which I could put into an OP Return.

These 32 bytes (in the OP Return), are mandatory bytes. They are in a txn. They will be stored by every node, forever.

But the whitepaper itself (184,292 bytes), is not "in" the blockchain. It consists of optional bytes.

This is still quite useful. Like Niel Armstrong on the moon, you plant a flag in the timeline -- no one can place it earlier than you. Your mandatory bytes are anchored in the past, which is evidence that you (at least) had the optional bytes.

This concept is essential to L2s, such as the Lightning Network. To "join" the L2, you need mandatory bytes. In Lightning, you join via a channel-open txn, which spends L1 outputs to a single 2-of-2 multisig output on L1. (To "leave" the L2, you use a channel-close txn, which spends from that output back to two individual L1 outputs.) Once the channel is open and ready to use, you merely refer to it -- these are optional bytes. A long list of sequential LN transactions, all refer to the same mandatory bytes. But these bytes are not found on L1 -- they are not processed by L1 nodes. They are optional, and only the two LN counterparties have them.


### G. Who pays?

Mandatory bytes are a great deal for *the requestor*.

We can ask for the data, whenever we want -- a nearby node will always give it to us! For free!

However, they're a bad deal for *the provider*. Providers must store all this data, and serve it back, whenever asked -- forever.

The situation resembles that of a taxpayer-funded library. The library agrees to store, and archive -- *anything* that is sent there. The library will even photocopy books, and mail them out, to whomever requests one. It's a great deal for the *readers* at the library. But the librarians are overworked -- the taxpayer must foot an ever-higher bill.

Because the blockchain is always growing, the *cumulative bytes* will increase forever, implying a higher and higher cost. This is like the library filling up, with everyone's cat pictures, and selfies, and tweets, and other junk. All adding to the archive.


### H. The Misinterpretation of SPV

#### i. What Is SPV

"SPV" is an **ingenious*** part of Satoshi's design.

Thanks to SPV, even if you do not run a full node, Bitcoin has these amazing properties:

1. Regular users can validate *all the proof-of-work*, of the entire chain (ie, the part that miners spent all their money on), with just 4.4 MB per year. (Which is basically nothing.)
2. A hostile full node cannot lie to you, about the contents of a block. If it says that XYZ is in Block A, then you know that XYZ is really in there.
3. It allows regular users to easily identify the block at the "tip" of the chain (ie, the most recent block).

However, SPV cannot do everything. For example:

1. It cannot force a hostile node to talk to you, in the first place.
2. It cannot create new nodes.
3. The data it shows you, may be a double-spend. (You have indirect evidence that it is not, since miners are building on it. But no other evidence.)
4. It will not help the network recover from a situation where some block data has gone missing (from everyone).

SPV is not a magic wand that erases all costs. It is a technique for free-riding, on someone else's node. It allows a casual user, to trust someone else's large server.

#### ii. Problem 1: Missing Data Source

But -- first of all -- that server has to actually be there. If there is no server, then the SPV node cannot ask it anything -- and then SPV is useless.

One OG-BSVer (digitsu) in the YouTube comments section, disagrees:

    He's wrong about SPV. SPV nodes never need to know
    the contents of the blocks. They only freeride in
    so far as trusting the node network to tell them
    about txn validity. They only need to keep track
    of their OWN coins. They trust a node to tell them
    if something is double spent. They never ask for
    block contents to try to determine it themselves.

This is typical of the BSV's misunderstanding of SPV.

First, notice him *mostly agreeing* with me. SPV nodes don't have block data. SPV nodes don't validate; they must "trust a node to tell them if something is double-spent".

SPV only tracks "your OWN coins" -- I agree. (In contrast, a full node tracks *all* coins.)

But -- how did we get these coins, in the first place? From someone else.

And those transactions are the ones we care about -- the **incoming coins** (coins paid to us). In contrast, the *outgoing coins* -- if we purchase a car with Bitcoin -- are *the recipient's* problem. We want to drive away with the car -- they want the coins. (And finally, any coins paid from-us-to-ourselves, aren't very problematic.) A full node can tell us if our *incoming coins* are valid -- an SPV-node cannot. If our incoming-coin-txn is a double-spend (or if it is descended from an invalid or missing txn), the SPV won't be able to warn us.

My guess is that digitsu is trying to say, something like: "Alice can pay Bob, even if both of them use SPV. Alice's SPV-node has her UTXOs, and so it can just copy this information over to Bob's SPV-node. Thus, they can transact without leaving the SPV-world."

But that is not strictly true, because [1] the Alice-to-Bob transaction will need to be included in a block (so it must be broadcast around the full node network); and [2] Bob needs a [Merkle Proof](https://bitcoin.stackexchange.com/questions/99164/how-does-a-merkle-proof-differ-from-the-merkle-tree) that his incoming-coin-txn was included. Only a "full node" (ie, a node which has the whole block) can make this proof.


#### iii. Problem 2: Novocaine

Second, SPV disaligns incentives. 

Imagine a family Netflix account -- where the father pays the monthly bill, the kids use his username/password for free. The father is like a node (and, in BSV-land, a miner). His kids are like SPV nodes -- free riders. The kids tell their classmates, at school, the Dad's Netflix password.

Again -- this is fantastic, for the classmates. They get to watch all the Netflix they want, without paying. And -- correspondingly -- it is a bad deal for Netflix.

Since the children are not paying the monthly bill, they will not care how expensive it is (nor if it starts to increase, nor how high it eventually goes). Also, they will give out the Dad's password to anyone who asks, hoping to glean additional popularity at school (at no cost to themselves). Being naive and superficial, the children will not stop to consider the long-run effect that their actions will have on the dynamics of the situation. Only *adults* understand complex topics such as *foresight*, maintenance, a healthy interest in the welfare of neighbors, "an ounce of prevention, is worth a pound of cure", "pay now or pay later", a "ticking time bomb", etc. 

That is exactly what is dangerous about SPV -- it is the novocaine that dulls the pain of running a full node. It masks the problem, instead of solving it. It fosters an attitude of *procrastination* -- and a culture of dependence [on others], and resignation [to one's fate]. Like any painkiller, it is addictive. It must easier to ignore a problem, than solve it. And drug addicts often become better-and-better at ignoring their real problems (making them worse, of course) and turning instead, more-and-more, to the easy fix.

#### iv. The Ratio

Each full node can easily support very many SPV nodes.

A network that is [99.99%-SPV, 00.01%-fullNode] is perfectly viable. The parasite/host ratio is not the problem. (The problem is the health of the host.)

By the way -- the dogma that "everyone must run a full node", is false. Luke Dashjr's rule-of-thumb that "if less than 80% of the network is running a full node, then Bitcoin dies" is hyperbole and (as far as I can tell) nonsense. A full node helps you, in a few ways, including: [1] it helps you receive coins from an untrustworthy sender (since your node will measure txn-validity and confirmations); [2] it enhances your privacy, since you never have to ask anyone about your coins (since you ask *the network*, about *all* of the coins); [3] it backs up the whole blockchain, so at least you have a copy (even if all other copies are destroyed, you can single-handedly regenerate the whole bitcoin network). If a node doesn't solve a problem for you -- then don't run it.

#### v. Conclusion

SPV is a wonderful technique, but it does **nothing** to **solve** the underlying problem of mandatory data. Instead, it makes life easier for those who are **ignoring** this problem, and burying their heads in the sand. In that way, it makes the underlying problem much **worse**.


### I. Free-Riding on Miners

#### i. The BSV Plan

BSV-ers think that **the miners** are an ideal group to free-ride off of.

And they are right!

First of all, miner's costs (and revenues) are very high. They are so high, that the costs of running a node (even a very large one) are insignificant by comparison. If 8 billion people use Bitcoin every day (paying a small fee), the revenues will be [X00 Billion USD per year](https://www.truthcoin.info/blog/all-world-txns/). In contrast, a 1 GB node costs [less than $500/month](https://www.truthcoin.info/blog/thunder/#appendix-1-usd-cost-of-1-gb-blocksize-node), to maintain. It's a microscopic rounding error.

Second of all, Satoshi's difficulty adjustment algorithm will reimbursing miners if fixed costs increase. If each miner has one node, and the node cost rises, then some miners will tend to go bankrupt, fewer hashes will be hashed, the difficulty will adjust downward, and mining will *increase* in profitability, to compensate. It's exactly the same as when the difficulty adjusts upwards to drain miners of their excess profits. (In that case, the BTC price rises -- miners get more revenue, *temporarily*, but more mining equipment is turned on, more hashes are calculated, and the difficulty adjusts upwards. Miners end up with a smaller slice of a bigger pie -- but the same total pie as before.) Equilibrium profits are always zero in mining. Mining is mostly immune to changes in cost, and revenue. Miners compete against rival miners. A 99-th percentile miner will do quite well, a 15-th percentile miner will lose money, a 50-th percentile miner will about breakeven.

The BSV-ers understand mining pretty well.

But they do **not** understand free-riding.


#### ii. The Problem With Free-Riding

Every "free rider" strategy has the same problem: everyone wants to free-ride; no one wants to provide the ride.

Why pay a cost, just to get equal treatment? Especially if everyone around us is not paying -- we don't want to be singled out as the only sucker. But if everyone free-rides, then no one provides the ride. Instead of a stable and reliable equilibrium, we have permanent dissatisfaction and turmoil.

With BSV mining, the story could unravel like this. At first, everyone is a CPU miner and everyone runs a node (cost: just $40/month). Eventually, as the network grows, the node costs rise (to $160/month). At this higher cost, smaller casual miners drop out, and only larger professional miners remain. Time passes -- more users -- node costs continue to rise (say, $800/month). Eventually, the large miners think: "well, actually I mine with a pool -- I don't even use my node for anything". So, they stop their nodes. The top 20 pools still run a node (but individual SHA-256 hashers do not).

BSV continues to attract more and more users. In 2030, we hit hyper-bitcoin-sv-ization -- every transaction on Earth is in the L1 chain. This is [roughly 9 trillion txns per year](https://www.truthcoin.info/blog/all-world-txns/), requiring an L1 blocksize of about 25 GB per 10 min. This node (scaling up [these numbers](https://www.truthcoin.info/blog/thunder/#appendix-1-usd-cost-of-1-gb-blocksize-node)) costs about $170,000 upfront, and $9,700 per month.  

But those numbers are too conservative. They are from my own "thunder" model, which assumed 13 geographically distributed chains, each with a *blocksize limit*, and a targeted $0.10 transaction fee, and networks specialized for payments. The [BSV website](https://bsvblockchain.org/), in contrast, promises no blocksize limit, micropayments, and "teranodes". Twitter promises 86 B txn/day, today, (which is 3.4x higher than my eventual 2030 hyperbitcoinization figure), and fees of "less than a penny per transaction".

![image](/images/bsv-micropayments.png)

With all that in mind, BSV is sure to get *much more usage*, than mere global payments. BSV won't just replace VISA and Mastercard -- it will replace Dropbox (perhaps). And maybe AWS and Netflix and YouTube.After all, BSV promises free distributed storage to everyone. To account for all this, we could conservatively estimate that node costs would rise roughly 10x higher: $2.0 M upfront, and $100,000 per month maintenance.

At this point, the 3 smallest pools get together, and say: "Why should we each pay $100k per month? We only need one node, among the three of us". They start a node-providing service, and spin it off into its own company (like Ethereum's Infura). It runs one node, and sells API access. The larger pools realize that this is a viable business (for now), so the #1 pool and #2 pool each spin off their own "node-providing service" company. Thus, there are only three such companies -- to which everyone subscribes. These are the only three nodes on Earth -- with 3 billion subscribers each. The top 20 mining pools subscribe (to one or the other), the individual SHA-256 hashers just outsource the work to their pool.

#### iii. What do we make of this outcome?

First, notice the inevitability of "separating miner from node". The BSV idea, that "all miners are nodes", is false. (We played along with it, until now, to be charitable -- but now it is revealed as the nonsense it is.) To mine, you *must* talk to *some* node -- but it need not be yours (and it need not be a "mining node"). Miners can use SPV just like anyone else. You do NOT need a full copy of the blockchain, in order to mine -- miners can *themselves* be SPV free-riders. For example, they could be free-riding off of another mining node. 

Second, notice that we now live in a world where 8 billion people are on novacaine (SPV). Almost no one feels the pain of increased node costs (which are high) -- only three people. This will inevitably lead to conflicts-of-interest between nodes and users: Users will want to keep dumping tons of stuff into the chain, for free; and the three providers will want to [somehow] impose smaller-and-smaller blocksize limits. They may try to shift data outside the chain in other ways, such as centralized "L2s" (similar to Coinbase's BASE), which are entirely controlled by them (and optimized by them). As with Blockstream's Liquid, they will also skim the txn-fee revenues for themselves -- leeching it away from the L1 miners. This is a recipe for conflict. It also breeds *secrecy* -- since the large problems (affecting the survival and viability of the whole network) are felt by just a few specialists, and not billions of users.

Third, some people are more optimistic than others. Who starts up these "node-providing service" companies? The *most optimistic CEOs*, for that business model. Who funds these companies? The *most optimistic* investors. This lays out the very real possibility that the *only three nodes*, in the world, will be run by precisely *the three most delusional people* with respect to the long-run economic viability of their business operations.

#### iv. The Sins of the Father

    for I, the LORD your God, am a jealous God,
    punishing the children for the sin of the parents
    to the third and fourth generation
    -Exodus 20:5

So far, we have only been considering the *steady state* node cost. This is the cost of an *already running node*.

Instead, we should consider the *cost of starting up a new node* (which is more relevant).

The blocksize is a flow (ie, bytes per 10 min), the accumulated chain data is a stock (ie, bytes). 

As the monthly cost rises, the *new entrance cost* will rise even faster. Not only must new nodes keep up with *today's* inflow of data, but they must process *the entire historical backlog* -- from Day 1 up until the present moment.

![images](/images/chain-stock-to-flow.png)

So, the moment when existing nodes throw in the towel (and quit, since running a node is too expensive), is precisely the moment when *existing nodes have the largest advantage*, over new entrants. This is a recipe for a system which *appears* healthy and stable -- but which suddenly collapses in a black swan.

Today, in BTC, initial block download (ie, the syncing of a brand new node) takes just 0-2 days. Two days is a very small percentage of a 30-day month, so there is not that much difference between "monthly" node cost (in steady-state); and "new node from scratch" cost. However, as blocksizes grow, the *accumulated past blockchain history* grows at a faster and faster rate; thus the difference between initial sync and monthly maintenance grows larger.

On top of all that, we have to consider that the "node runners" might be *different people*, over time.

On [day 1], the node runners [of day 1] pay [the node costs of day 1].

On [day 2], the node runners [of day 2] pay [the node costs of day 1] + [the node costs of day 2].

On [day 3], the node runners [of day 3] pay [the node costs of day 1] + [the node costs of day 2] + [the node costs of day 3].

This leads to a situation where *my bad behavior*, today, must be paid for by countless future *other people*. And on and on.

Obviously this is a recipe for conflict and misaligned incentives.

#### v. The Business Model

Any business model can fail.

New startups are tried every day -- more than 95% fail. Hundreds of businesses go bankrupt every day. We can't *guarantee* that a given pattern of economic activity will be viable forever.

Perhaps running a node will be "profitable", perhaps not. If it is today, then perhaps it won't be tomorrow.

To answer these questions, we would have to make projections of: how much revenue the node-providers can expect to take in (and for what, and from whom); what their competitors will be (other nodes, AWS, DropBox, etc); the impact of free-riders (both on us, and on our competitors -- who may have a more "managed" way of dealing with them).

No one knows for sure.

But what we do know is -- if the chain gets too expensive, and the node providers quit, (and no one shoulders the burden of starting a new node service), then the whole network dies. All of the SPV nodes stop working (they have no one to talk to). Miners do not know what to put in the next block. If they somehow make a block anyway, then does it contain double-spends? No one knows -- no one has any way of knowing. Because the only way is to check this new block against the txn data of all previous blocks -- but that is exactly the economic activity that has now become too expensive. 

If the network runs into trouble, then perhaps miners will vertically integrate, hoping to save the network (and the source of their revenues)? The fundamental problem would still remain -- would node service costs *always* be lower than mining revenues? There is no guarantee of that. Furthermore, the integrated miners would always be at a disadvantage -- other miners could free-ride off of their node, and out compete them. It really is just "free riding all the way down".

In any event, BSV cannot afford to be indifferent to node costs. They may rise to infinity (which no one can pay), or they may merely be above node-revenues, or above mining revenues. It is lazy to design something with a ticking time bomb.



### J. SPV Trumps BSV

BSV-ers *defend* their unlimited L1 blocksize, as follows...

![images](/images/spv-the-wrong-defense.png)

...not realizing that this argument is a Dunce Cap.

First, let's review the latter part: "you don't need to download the whole blockchain thanks to SPV". Yes, SPV allows you to free-ride. But not *everyone* can free-ride. And -- if we want to be a parasite, then we must pick a healthy host. It is precisely *because* we are an SPV-parasite, that we *must* inquire about the *full* nodes (the non-SPV) that we will be mooching off of. Their health is our health. (Not the other way around.) And, in general, when choosing a coin (or any long term investment), we must be comfortable with the eventual fate, of all the participants in the venture.

But actually -- the problem with this argument is its first part: "the merits of BSV vs BTC".

Because, "thanks to SPV", there is no difference.

In SPV mode, there is no difference between BSV and BTC. You can pack an unlimited amount of data "on" BTC, if you merely hash it all beforehand (this will always reduce its total size to 32 bytes, no matter how large its initial size). That is how you would put *Lord of the Rings* on BTC. Admittedly, your data is not backed up, on any BTC full nodes -- but you have it. And you can give it to your friends. (They can check its hash against the BTC txn.) You may label these nodes, (which have the 176 GB of video data), "LotR nodes", if you want. Furthermore, you can label the "regular" Bitcoin Core BTC full nodes (which lack the LotR data) as "LotR SPV nodes".

In the same way, you can backup LotR to the BSV blockchain. If you do, then every BSV full node will have a copy of the 176 GB. Every BSV full node (every miner) will be an "LotR node". They will all be obligated to save the data, and even serve it back to you upon request. Furthermore, 100% of the SPV nodes, will be "LotR SPV nodes". It is fundamentally the exact same situation, in both BTC and BSV -- some nodes have the data, some do not. The only difference is, in BSV many full nodes are *coerced* into storing data they would prefer to ignore.

But this coercion, *is* BSV. It is the only difference, between BSV and BTC -- an increase in "mandatory bytes". Other than that, BTC and BSV are the same.

SPV nodes are non-coerced. They are not obligated to store any chain data (except the trivial headers). If two SPV nodes meet, both are equally blind. Neither can help the other find their lost data (or any data). Suppose the first node put LotR on-chain [last week]; and the second node put the Star Wars trilogy on-chain [last year]. If they deleted their video files, then they'll have to download them again, from someone who has them. Not each other. 

So in that sense, "BSV in SPV mode" is just exactly equal to "BTC". In other words: a chain where fewer of the bytes are mandatory. And if both of them are "in pure SPV mode" (as in the above paragraph), then they are exactly equal to each other. Both contain nothing. And both have no blocksize limit.


### K. The Data Availability Problem

zkSNARKs are *enormously* powerful compression techniques. Nearly magical.

But their applicability to blockchain and cryptocurrencies is (alas) very limited. Satoshi's SPV mode (invented back in 2008), is *still much better*.

For example, a few years ago, my friend Robin Linus (co-founder of ZeroSync [a zkSNARK company], and creator of BitVM) was walking with me in the streets of Amsterdam. He told me that they had a new zkSNARK prover, which could sync the headers of Bitcoin. This of course was not very impressive -- but one day (he said) they would improve it, so you could prove the validity of the whole chain. That way -- you would know you were on a *valid* chain, without syncing a whole full node. You'd only need the prover. He asked me what I thought of this. 

I said: "Well, compare it to the SPV mode we already have. Imagine if we lived in a world, where people were constantly syncing the BTC headers (which are tiny), and there were frequent forks in that header chain -- and one side of the fork contained invalid content, the other side had valid content -- and people were always being tricked, into going onto the wrong side. *ahem* In that world, it would be very useful. But of course that never happens -- these days, there are basically no reorgs or orphaned blocks. And, faking the headers would take an enormous amount of proof of work -- no one would do it. And, if you were going to do that, you would probably just make both sides valid, and basically do a 51% attack. So, actually, Satoshi's original SPV mode -- is better. From the headers, we basically already know that the chain is valid -- and if someone is willing to attack those, they can just 51% attack."

He agreed.

The *core problem*, of blockchain scaling, is the "Missing Data" problem I outlined in Part E. If you "compress" this data away, then it just becomes missing data. (If you are going to do that, then you might as well just throw the data away, use SPV, because it will be ultra-compressed.) This is called the **data availability problem**. You can't check for double-spends, unless you know who-spent-what.

A looming curse hangs over the "mandatory bytes" in the blockchain -- the curse of *our responsibility*. It is like we run a vast orphanage, full of innocent children who all need food (and deserve food). It is natural to want to have our cake and eat it too -- on one hand, love having kids, but on the other, just leave for a pack of cigarettes and never come back. If only we could have everything at once! That is the desire at the heart of BSV.


### L. BTC vs BSV vs Drivechain

To solve the data availability problem, we need to know **who is willing** to be *responsible* for **what data**.

BTC "solves" this via the blocksize limit of 1 MB (now 4 MB). BTC says: *everyone* is responsible for *4 MB / 10 min*. The current chain size is 750 GB -- this is already too much, for casual users. (Even a behemoth game like [Call of Duty is only 150 GB](https://gamerant.com/pc-games-file-size-hd-space-biggest-huge/).) Also, at roughly 2500 txns per 10 minutes, it is *overkill* for a settlement network. Nonetheless, BTC tries to "split the difference" and achieve a compromise. BTC also puts a premium on "keeping the community together" (ie, not hard-forking). The downside of that, is [stasis and complacency](https://www.truthcoin.info/blog/precedence-ossification/#part-3-problems-with-todays-ossifiers).

BSV has no blocksize limit -- and it piles everything into its L1 chain. As a result, their users have access to abundant, cheap block space -- but their Nodes languish under the burden of maintaining all this data.

That does not mean BSV is necessarily wrong. Nor does it mean that BSV is doomed. (And, even if doomed, it might still have been a useful science experiment.) But it is a cop out. It weasels out of answering the question -- like a child getting a "2+2" test question, and writing down "a number" as their answer. Drawing the line is difficult -- you have to justify the number you chose. So instead, in BSV there is no line. There is no "scaling in layers"; there is no "feedback loop" to bring the limit down, if validation costs rise excessively. 

Drivechain is more flexible. Users produce new L2 chains whenever they want, and opt-in to them a la carte. Each L2 has its own blocksize limit -- but the *ensemble* of chains, altogether has no limit. If one chain becomes too expensive, and dies, it will not bring down the others. That is the Drivechain idea.


### M. The Same Mistake, From Different Sides

#### i. The Error

Ironically, Drivechain is sometimes [misunderstood (by Peter Todd for example) as a "blocksize increase"](https://www.youtube.com/watch?v=KDZi-vtD0qg&pp=ygUwdGFiY29uZiBkcml2ZWNoYWluIGRlYmF0ZSBwZXRlciB0b2RkIHBhdWwgc3p0b3Jj).

Peter is just as wrong as the BSV-ers, and for basically the same reason: he mixes up required bytes and optional bytes.

Peter believes that there is a *second way* which bytes can become mandatory: if all "viable miners" find it in their economic interest to obtain them. Again -- this is similar to BSV: BSV says that *we don't need to care* about full node costs, since miners will pick up the tab for us -- Peter says that *we must care*, about even the *non-L1-node* mining costs, since all Bitcoiners share the same mining network.

Peter is wrong. We do *not* care about mining costs -- only node costs. We only care about the "L1 Blockchain Service Cost" (Part E, above). We want the cost of running an L1 full node to be low -- since that is the cost of examining the L1 blockchain for "errors" (ie, invalid txns and double-spends). The data in the blockchain is special -- for that reason. Thus, Satoshi solved the double-spend problem.

#### ii. Some Asides

By the way -- using Peter's logic, *every mining cost* is a blocksize increase. (After all, you could simply re-label "ASICs" as "mandatory L2 bytes" -- and "buying ASICs" as "running a merged-mined ASIC-acquisition node".) This leads to funny conclusions such as: "ASICs are a blocksize increase" (since every viable miner must obtain them), and "ERCOT demand management tax credits are a blocksize increase" (if these are profitable enough to become widely attractive). In our debate, I asked Peter: "is every upward difficulty adjustment a blocksize increase" (since those always increase miner costs), and he evaded the question. That is because Peter knows that "removing upward difficulty adjustments" from Bitcoin is equal to "removing proof-of-work" from Bitcoin. Peter is deeply confused as to what proof-of-work *is* -- it is the translation of miner revenue into double-spend protection on L1. This is also called "the security budget", and "the cost of continually 51%-attacking the network". They are all the same number -- and we want it to be high. A high security budget means many happy users, large mining revenues, large mining costs, high network difficulty, high hashrate-security, high 51-attack cost. Drivechain is good *because* it amplifies miner revenues -- leading to additional hashrate. Since Peter started out by mixing-up good and bad (on the question "is more proof of work good?"), it is no surprise he mistakenly concludes that Drivechain is bad.

By the way, again -- Peter also happens to be literally wrong, about how Drivechain works. Thanks to blind merged mining, the mandatory L2 bytes are *not* mandatory for L1 miners. L1 miners collect all the L2 fees, whether they run an L2 node or not. Again -- Peter is wrong in the same way that the BSV people are wrong. BSV people say that their network will never die, no matter how high its node costs get -- Peter says that even if the L2 network *is already dead*, it will still impose higher full node costs on L1 nodes. Obviously that is not true. If the largeblock L2 network doesn't have any full nodes, then it just dies off -- no more revenue, no more costs. So it cannot have any harmful effect on Bitcoin, or anything else -- since it no longer exists. However, if it does exist, then it has at least two full nodes. Blind Merged Mining allows *miners* to safely free-ride off of these two L2-full nodes -- without running an L2-full node themselves. And it is not "free-riding" -- the full nodes compete with each other, to extract a tiny premium for assembling the block. BSV uses wishful thinking to guarantee block-assembly in perpetuity -- Drivechain says "either someone is assembling this block, or not -- either way we're fine".

Peter is wrong for other reasons as well. We only care about the node costs *on the networks we participate in*. For example, a Bitcoiner -- who never uses the Solana altcoin -- shouldn't care about the *Solana* node cost. He doesn't use Solana! And so -- if a new L2-drivechain came to Bitcoin, then *users of Bitcoin L1 ONLY* should not care about its node costs -- even if these are very high. Everyone starts out as a non-user, and must voluntarily opt-in (just as you must opt-into the Lightning Network). (This is exactly why the *cost of running a Lightning Node* is *not* considered a blocksize increase -- because it isn't. It is also why *only miners* would/should care about mining costs -- only miners are "running a node" of the "mining" L2.) Furthermore, people are heterogeneous -- (some are wealthier than others, for example). So, some would care more about node costs (in general), others less. Etc etc.

#### iii. The Simple Truth

But all of that is a distraction. Here's the truth: **Node costs are not mining costs. Node costs are node costs.** BSV is wrong, to say that node costs will always be offset by miner-revenues. They are unrelated. And Peter Todd is wrong, to say that new miner-revenues will always increase node costs. They are unrelated. It is just a mix-up -- a mistake. Pure and simple.


### N. Data Availability at Scale

Imagine all of the financial transactions in the world, today.

Someone has to process all of that data!

Unlike BSV, it is not piled all into one system. We have VISA, WeChat, Venmo, Swift -- all separate.

Also unlike BSV, it is arranged into *layers*. Credit card companies (and phone apps), each have an account at a commercial bank. Commercial banks, each have an account at the Central Bank. And the central banks, each have an account at the Bank of International Settlements. It is hierarchical, and pyramidal.

It is also customizable: those who prefer Venmo can use Venmo -- those who prefer WeChat can use WeChat -- those who prefer paper checks, can use paper checks.

It is also dynamic: "ING Direct" launched in the USA in 2000, as the first "online only" bank (that I heard of) -- no brick-and-mortar locations, but lower fees and higher APY on deposits. If you were computer-savvy, it was great choice! Before 2011, I had never seen a QR-code in my life. New "fintech" companies come into business (and go out of business) all the time.

BTC alone, cannot scale to the required size (nor the required *structure*, *differentiation*, and *dynamism*). BSV, likewise, cannot *break* itself into independent, differentiated subsystems (nor can it contain its ever-increasing L1 node costs).

However, as [I have explained elsewhere](https://www.truthcoin.info/blog/thunder/), "BTC + Drivechain" is able to accomplish all this. This is because it places the emphasis on *data availability* -- and on *voluntarily joining* an L2 group (because that group solves a problem for its users) -- and on *competition* among L2s. (Regrettably, Lightning is now hard at work, installing an anti-competitive culture into BTC.)


