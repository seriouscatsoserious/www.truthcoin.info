---
title: Ideal Mining (EDAC Pools)
show_author: true
comments: true
date: 2025-05-26 02:00:00
---




### Summary

The optimal solution for **mining decentralization** is (what I call) "EDAC Pools".

These are pools which are:

| EDAC          | Description       |
|-------------|-----------------------------------------|
| Efficient   | Not wasting any money/resources.        |
| Detachable  | Can easily switch pools (ie, "detach"). |
| Accountable | Any mistakes are noticed.               |
| Competitive | It is easy to compare (and rank) pools. |

### Motivation

In [the previous post](https://www.truthcoin.info/blog/popular-mining-lies/), I detailed how "Mining Centralization" is a **fake** topic -- and it is. There is no problem [with mining], and (therefore) no solution.

Nonethless, we must purge Bitcoin of the **grifters**. People selling a fix to what isn't broken. And the best way to do that, is to just *Elaborate the Ideal*.

We will make mining *slightly more Perfect*. That way, anyone who proposes [something else], will automatically be discredited. Since their thing will be clearly worse.




## Part 1 -- A Review of Pools

Some people *lament* the very existence of pools -- seeing them as a nuisance.

That's a big mistake. Pools are essential for **small** miners and for *decentralization*. They are essential to Bitcoin.


### A. Review of the Variance Problem

By basic arithmetic, a 10-minute blocktime implies [1008] blocks per week; and [4320] per month.

Thus -- by definition -- if you have (1/4320)-th hashrate, you will find 1 block a month.

However, you have a **variance problem**. Hitting a block is statistically random. Sometimes, you will hit many blocks quickly -- other times you will go 130 or 150 days, without hitting a block. You can use [this simple calculator](/images/simple-mining-simulator.xlsx)) to see for yourself -- if you operate for 2 years total, there is *usually* at least one 90-day "bad luck" streak -- and quite common to have a 120-day streak [or even 150 days].

And -- this unlucky 120-day streak, could be during your *first* 120 days. You could hit 4 months of bad luck off the bat. That is unacceptable for a new, small miner. Imagine -- they do everything right, and still get ruined by bad luck! Many "profitable miners" (on average), will thus be scared away. They will be defeated by their small scale.

Furthermore, this risk is hard to insure. An insurance company can easily be defrauded -- since it is inherently based on luck. The hashers can secretly mine somewhere else (or solo mine), then claim to have bad luck -- submitting a claim to the insurance company and collecting. There is no easy way for the insurance company to detect this fraud -- the managerial controls it would theoretically require, are so strong that they would imply de-facto vertical integration (ie -- not insurance). Plus, vertical integration would mean consolidation -- ie, that the small miners are now becoming "large". (That's what we didn't want in the first place.)

Luckily, we have pools! Pools convert this into an *immediate*, consistent payout. This is perfect!

Now, all of that (above) is well-known in Bitcoin. 

But one implication of it, is consistently overlooked!


### B. The Sheer Inevitability of Pools

The example above, involved a hypothetical miner with (1/4320)-th hashrate.

First of all -- that's a lot of hashrate! Today, it would be 0.2039 exahash. A single [BitMain S21](https://shop.bitmain.com/product/detail?pid=00020250126221803633lzm03UGa06A1) is 500 TH/s, so we would need 408 of those, at total cost 5.63 million USD (with coupon). This does not include *any* electricity costs -- just the single, upfront ASIC cost. (Quite the barrier to entry!)

But, more importantly...

It is **a fraction**. So, as Bitcoin grows, the "(1/4320)-th hashrate" figure will **also grow**.

And the Bitcoin network must grow. If Bitcoin remained very small -- for example, if it were only used by 4000 people (as back in the year 2009), then -- sure -- everyone could mine (and each of them could hit one block a month). But that outcome is itself centralized. A mere 4000 users, and 8 billion non-users?! Instead, we need Bitcoin to grow. It must *aspire to have* 8 billion users. And -- even if all 8 billion users *wanted to mine*, (and many won't) -- and even if they all had *exactly equal* hashrate (which will never happen), then...

...they'd each have (1/8-billion)-th the network hashrate. Each would hit a block (on average), once per *80 billion minutes* [10 minutes each], ie 152,102 years.

That is obviously absurd.

Yet -- it is also the *ideal*, preached by the "mining decentralization" crowd. After all -- everyone mines, everyone is equal, there are no pools. Perfect!

It is a mark of how un-serious these people are, that they don't do this basic arithmetic. They have no serious idea of what Bitcoin should look like. 

If they did, they would see that *L2s* and *payment aggregation* are essential.


### C. Scaling Mining = Scaling Bitcoin

Let's take the "8 billion miners" example, more seriously.

We can now see that [1] the *Bitcoin scalabililty problem* and [2] the "mining centralization" problem -- are linked.

To solve mining centralization, there must be a way to pay 8 billion miners, once per 10 minutes. (Because, that is the only way, of having all 8 billion people mine at once, without each of them being crushed [or discouraged] by the variance problem.)

At first, that might sound impossibly difficult. However, it is actually *a smaller* version, of the question: "how can 8 billion people use Bitcoin everyday, for transactions".

The second question is basically "how to scale bitcoin". I have already [solved it via drivechain](https://www.truthcoin.info/blog/thunder/), for which software is [already available](https://layertwolabs.com/download).

Furthermore...


### D. Onboarding Directly to L2

Some "Bitcoin L2s" (such as the Lightning Network) require that **each user** first onboard, from the L1 to the L2, by broadcasting an L1 transaction. Such L2s are not viable. They are not viable in general -- and they are not viable for mining either.

But Drivechain is not such an L2. Drivechain allows new users to onboard, directly to the L2. They can even stay on the L2, forever, if they wish.

If instead, they want to "drop" from L2 to L1, then they can do this -- provided there are L1 bytes availible.

(That is yet another big misunderstanding. Every L2, has it's exit limited by L1. Contrary to popular belief, it is impossible for *any* L2 to give 8 billion users the ability to "unilateral exit" the L2. It has nothing to do with the L2s themselves, instead it is because 8 billion *new* UTXOs [ie, new users] do NOT fit on L1 -- unless their exit is "spread out", over a period of decades[^1]. So, *that itself* is a nonsensical criterion. It is nonsense re: L2s, and re: "mining centralization" and everything else. It is yet another example of people failing to do arithmetic, and failling to take their own ideas seriously.)

[^1]: The math is the same. 8 billion people, needing perhaps 300 bytes of an effective-sized 2.25 MB block -- so, 1.06 million blocks are required. At 4320 blocks per month, that comes to 247 months total (20 years).

Direct payment via L2, is a *requirement*, if you want 8 billion miners.

Of course, everyone would rather have an L1 UTXO (vs an L2 UTXO) -- all other things being equal. But they won't be equal. Everyone *can't fit* on L1. The L1 fee-rates, will always tend to be higher, than L2 -- making small payments uneconomical, and (therefore) changing the minimum viable payment size.

(In fact, all pools today, *already* solve this problem, by onboarding their hashers to a **custodial** L2 -- themselves. A hasher, must earn a minimum amount of money [kept at the pool, meanwhile]. When they earn enough, they can "request" a pay out. Thus, you see that L2s are inevitable.)


### E. The Safest L2 for Miners

Drivechain is secured by hashrate (ie, by miners).

That makes it a pretty comfortable way for miners to get paid. Of course, they [like everyone] would rather be paid on L1 (see above), but -- if they must be paid via L2 [and they must] -- then they would rather be paid on an L2, that *they themselves* secure. That's almost as good, as L1.

On top of that, the [security model for Drivechain](https://www.drivechain.info/blog/fees/), is unchanged by the existence of a 51% pool. In contrast, the Lightning Network security model changes drastically, if there is a 51% miner. In that way, the lightning network may *encourage* a 51% pool to form. Drivechain may *discourage* a 51% pool to form.

For these reasons, I believe Bip300 L2 payments to be *de facto required* for mining decentralization.


## Part 2. The Benefits of PPS

Of all the [payout methods](https://en.bitcoin.it/wiki/Comparison_of_mining_pools), PPS (and its variants) has been winning -- deservedly so, since it is the best.

### A. Review

All pools construct a parallel version of the Bitcoin network, where the difficulty is *much lower*. It is easy to hit blocks there (even for tiny miners). This solves the variance problem. On the pool, these blocks are called "shares".

PPS is "pay per share", where the pool pays its hasher, for each share they hit.

### B. PPS vs Proportional

PPS shifts *multiple types of risk* to the pool operator. For example, imagine a pool is paying $20 per share, but then the price of Bitcoin crashes -99% -- but the pool-operator is asleep. They keep paying $20 per share. Miners would switch to this pool, draining the pool's banking account (since the pool is overpaying for BTC, now worth 99% less than it was yesterday). A second example: imagine the pool-operator anticipates that today's BTC transaction-fee revenues will be $5000 total. He sets a high PPS rate, to attract hashers. But, actually, the blocks mined today only total $2000 in txn-fee revenue. The pool-operator eats the loss. Finally, the pool-operator may expect to hit 20 blocks today -- they set a high PPS rate. But, they have bad luck, the whole pool only hits 14 blocks. It doesn't matter -- the pool-operator still has to pay everyone out, as promised.

The rival payout method (PPLNS, and its variants) works the opposite way. It [1] waits for the pool to hit a real Bitcoin block, and then [2] distributes the reward of that block proportionally, to all miners, based on who found more shares. It used to be called "proportional" (for that reason) and it has since split into many variants of its own. But the key points are [1] you are tied to the pool's fate -- if they are unlucky (and never hit a block), then you never get paid; [2] you don't get paid, *until* the pool hits a block (thus, you bear the "exchange rate fluctuation" risk, etc).[^2]

[^2]: You also suffer if your pool-mates utilize bad templates. OCEAN, for example, allows clients to choose "their own template". (This is to "limit spam", supposedly.) Imagine that Alice and Bob both mine at OCEAN -- Alice, however, prefers to mine *empty blocks*. When Alice hits a block, the entire pool -- Bob included -- will collect less money.

Some payouts distinguish between "the block subsidy" and "the transaction fees" -- to me this makes no difference. FPPS is equal to PPS, for my purposes. (In the future, there will be only fees, and zero block subsidy.)

The relevant distinction is the *duration* of the relationship. Under PPS, it is brief and standardized -- I pay you, immediately, X USD for 1 share. Under PPLNS, it is protracted and amorphous -- I am paid, at some point, f(X) USD, based on many factors (which fluctuate).

### C. Specialization of Labor

PPS forces the pool to make projections -- and take financial risk, that these projections may turn out to be inaccurate.

In that sense, it is worse for the pool.

But for the Hasher, it is better. They are freed from this burden.

Plus, they can shop around -- and pick whichever pool is the *most optimistic*. This might be the most *delusional* pool -- ie, with projections that are the most-wrong. But, to a Hasher under PPS, it makes no difference. A deal's a deal -- they get more money.

Projecting is difficult, and many Hashers would probably prefer to leave it to the professionals. This is called "specialization of labor". This way, Hashers can focus on [1] getting cheap power, [2] efficient setup/tear-down, [3] heating/cooling, [4] getting new ASICs. Under PPS, they automatically get the best numbers -- but they must pay a mining fee.

However, this "conversion", of a complex problem into a fee -- that is *itself* a net benefit to the Hasher. The Hasher can compare fees, (and choose the lowest), just as easily as he compared PPS rates (in order to choose the highest). Similarly, he can benefit from the Pool's "optimism" when setting an overly-low fee (or, perhaps in this case, it is the pools "nervousness" [about losing Hashers to another pool]).

So, in general, PPS makes it easier to compare one pool to another -- since you are just looking at some numbers to choose the highest (PPS rate) or lowest (fee rate).


### D. PPS + Drivechain

Drivechain improves PPS even further.

For one thing, it means that -- for both PPS and PPLNS -- *less money is kept in the pool's custody*. After all, L2 fees will be lower, smaller amounts of money can be transacted, scarce L1 bytes are not consumed. Therefore, Hashers can "cashout" much more frequently -- even if there are 1000x more Hashers, per pool.

But only under PPS, can this value get *really low* -- ie, to zero. Under PPLNS, you are not paid until the pool hits a block. But, under PPS, you could be paid *every 10 minutes* -- even if the pool does not hit that block. A payout is a payout -- just like any other Bitcoin transaction. 

Second, Drivechain helps a new PPS pool establish immediate credibility. A miner gets *immediate feedback* -- they sign up, they start hitting shares -- they start earning. Within a few moments, you'll know if the pool operator is legit or not.

Third, it also helps miners who are *switching among PPS pools*, for the same reason. Maybe a PPS pool has existed for 5 years -- but you've never used it. However, today you feel mistreated by your current pool -- you want to switch. Now, you can try out that rival pool, easily. You can even switch back and forth, all day!


## Part 3. The Ideal Mining Equilibrium

### A. Competition

Ideally, *competition* would keep pools well-behaved.

Each pool would wake up every morning, and think: "Hey -- I had better do the right thing -- because if I don't, all of my Hashers will leave me (!) and go down the street, to a rival Pool".

Thus, the question: "how can we Bitcoiners, best improve Bitcoin mining [and best improve mining decentralization]?" -- that question is actually equal to a second question: "how do we make it as easy as possible for Hashers to switch pools?".

As I've explained, this would involve:

* All pools use PPS.
* All pools use a one-dimensional fee.
* Drivechain activates, and is used for L2 payouts (from pools to hashers).

But we could improve it further...


### B. The "Pool-Hopper"

In theory, "PoolHopper" would be a new piece of software.

Instead of each Hasher pointing their hashrate *at a pool* -- they would **all** instead point it at their own instance of "Pool Hopper" (or "Hasher Advocate").

The Hopper would then: [1] look around at all the pools, [2] find the highest-paying pool, and [3] send all the Hasher's hashrate there.

This would force the pools to always: [1] charge the lowest fees possible, and [2] pay out the highest PPS rates possible.


### C. "OpenPool"

In theory, "OpenPool" would be an open-source mining pool.

Theoretically it is community-run -- with researchers around the world, making it high-performance and reliable. It should always maximize mining profits -- if we do a perfect job (satisfying miner's needs), then miners will never be tempted away (to other pool software). 

In this way, we'd all know what software all the pools were running -- because they would all run *the same* software. Ideally, pools become a simple, commoditized thing -- unremarkable.


### D. Balancing and Regenerating

In such a world, each pool only owns one thing: their brand.

They are basically an IP address and a name. Yet -- if their fees are low, and they maximize txn-fees, and they pay high PPS rates -- then they will gain hashrate over time. The hopper will send more and more hashrate its way.

In general, the hopper should always send *all its hashrate* to the most economically-rewarding pool. As a result, it may get a little schizophrenic. However, eventually, several pools will probably "tie" (ie, charge exactly the same low fees, etc). The Hopper can then divide the hashrate evenly among these few surviving pools.

In this world, it is very difficult for a pool to *censor transactions*. Because: each censored transaction, is $$ lost. And therefore, a censor-pool will find it hard to pay the optimal PPS rate (and charge the lowest fee). (In the same way, it is very difficult for these pools to *tolerate reorgs* -- since these are devastating to the revenue of a PPS pool [they *already paid* 100% full price, for block(s) which are now worth $0 to them].)

The Hopper should always be on the lookout for *new pools* -- these lack an established *brand* (so far), but they might have *the best rates*. Each Hasher can set their preferences in the app -- how willing are they to switch (ie, how much more $$ would they have to be offered). This would be the Hasher's "loyalty rate" -- and we would want them all to be *low*. (Maximum disloyalty -- maximum competitiveness -- minimum misbehavior among pools.)

In fact, if the Hopper wants -- it can *trigger* the creation of new pools. It has all the data, on each pool -- so it knows "the market". The Hopper can also be connected to a Bitcoin Node, and [in that way] learn about prevailing transaction fees (and mempools, and orphans and reorgs, etc).

### E. Ideal Mining

Thus, we have achieved the properties I laid out at the beginning of the article:

| EDAC          | Description       |
|-------------|-----------------------------------------|
| Efficient   | Not wasting any money/resources.        |
| Detachable  | Can easily switch pools (ie, "detach"). |
| Accountable | Any mistakes are noticed.               |
| Competitive | It is easy to compare (and rank) pools. |

This is a mining environment where (basically) no mistakes are made. And, if any mistakes are made, then the appropriate people suffer -- immediately -- and new competitors automatically take advantage of their mistakes (and replace them).

---


### Appendix (Added 6/6/2025) -- Capital Requirements for A New Pool

How much money does it take, to start a new pool from scratch?

After all, we want it to be easy to start a new pool. Yet -- under PPS, pools must start handing out $$ immediately, to their new hashers. So they need cash upfront. How much is needed?

Let's assume:

* There is currently one pool, "MonoPool", with 100% hashrate -- you want to start a new pool and capture that 100% for yourself.
* MonoPool charges 1% (of revenue).
* Bitcoin txn fee revenue (onchain + merged mined), is [640 B USD per year](https://www.truthcoin.info/blog/all-world-txns/) -- so, MonoPool collects 6.4 B $/year.
* MonoPool's other costs (employees, serves, domain name, software) -- are low. Less than $1 million per year.
* Therefore, MonoPool's *operating profit* is also 6.4 B $/year.
* Viability (as a pool), requires 30 days of working capital -- ie [640/12] = $530 million USD, total.

530 million USD?! Isn't that too much?? No one will ever be able to start a new pool, at those magnitudes!!

Well, actually, there are a few problems with our "toy" model.

First, our high number is driven *completely* by the success of Bitcoin. Successful Bitcoin = more txn fees. It is hard to preemptively amass "30 days worth of txn fees", if that number is high. But if instead, Bitcoin was not used by anyone -- and paid only $200 per month in txn fees, total. Then it would be easy to start a new pool -- it would be easy to front the $200 needed, to make sure we could pay miners for 30 days, even if we are unlucky.

Second, we ignored the *upside*. Admittedly, a single, one-time, upfront cash requirement, of $530 M, *is* a lot... if you get nothing in return. But, in the toy example above, we are getting *6.4 billion dollars per year, forever*. In fact, (in the toy model above), the setup is *always* of the form: "you supply 1 month of cash, upfront, and in return, you get *that amount* of cash, every month, in perpetuity". It is like planting a $20 tree, which grows a new $20 bill every month (including the first month). Since there are 12 months in a year, the IRR (annual) of this project is north of 1000%. So, actually: the bigger the better. People will be *lining up* to throw money into a project like this.

Of course, competition will bring *down* that 1% fee -- to something lower. It violates the economic "laws of physics", for a pool to make 6.4 billion USD in profit per year -- that's too high. Surely, a new pool would undercut that. This "Pool_2" would still front $530 M (to pay 30 days worth of expenses), but they would charge (for example) half as much (0.5%), and collect (after usurping the #1 pool) 3.2 billion USD per year, instead of 6.4. This process would repeat, driving the fee lower and lower. Eventually, it would reach some kind of equilibrium, where the pool must front $530 M in cash, but they collect *enough* money to make a decent Rate of Return.

So that's the point. The capital cost is (essentially) *free*. It is "paid for", by the stream of incoming fees. It is paid for by the net present value of the fee-profits you later obtain.

So, let's review.

First, the "capital requirements" number *follows* the "Bitcoin txn fees" number. It only becomes large and intimidating, *after* Bitcoin's txn fees rise. (It cannot "jump up" and be "stuck" at a high value, throwing the system into crisis.) We *want* Bitcoin to be a success -- we want "30 days worth of miner payouts" to be high -- we want a high security budget -- we want many happy users. So -- these complaints about high capital costs for pools, are really just complaints about *Bitcoin succeeding*.

Second, these capital costs come with *a benefit* attached -- the ability to charge 1% (or whatever the prevailing rate is) *of* the original fee-magnitude.

So, it is *not* a plutocracy -- in other words, it is NOT a scenario where the wealthiest do as they like, and the rest of us suffer. Instead, it is merely *specialization of labor* -- a few specialists have chosen to **shift a portion** of the annual fee revenue, into the present. In our toy example (above), that "portion" was [00.083%], ie [1% of (1/12)] the annual fee revenue. But that's all it is -- a mortgage on a house / a car loan / commercial paper. It is a shift of payments (across time), for mutual convenience.


---

### Footnotes
