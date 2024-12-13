 
    Rationale re: covenants support wiki
    Paul Sztorc
    12 Dec 2024


### Table of Contents

Part 1 -- Three Important Facts
Part 2 -- My Assessment of these Proposals

### Part 1. Three Important Facts

#### 1) Soft forks do not require consensus.

There is no reason for us to form a table on "covenant opcodes" -- or any other soft forks. We may as well form a table on pull request #31449 (which is a refactor), or #31457 (which is a test).

Why is my point of view so different? Because I am more knowledgeable. I wrote a soft fork, back in 2015 -- I wrote presentations on soft fork risks (one is 5 hours long), in 2016. In late 2016 I wrote technical blog posts about soft fork theory -- and again in 2017, and 2018. (In 2009-2016, Bitcoin averaged 2 soft forks per year.) 

Soft forks --especially the *OP code* soft forks debated here-- all carry zero risk. This is because they are [1] opt-in, and [2] reversible. The whole point of a soft fork, is that old nodes do not have to upgrade -- they are opt in. 

The easiest way to see why a soft fork is reversible, is just to imagine that OP NOP 7 has been claimed (as "CTV" for example), via soft fork. Previously, nop7 always returned "true" -- but now it will occasionally return "false" (if the CTV rules are broken). Let me be clear: to restore nop7 to its former state, is a HARD FORK. But, we can do something else: forbid any transaction from ever utilizing nop7 -- this is a soft fork.

For this reason alone, soft forks carry **no risk whatsoever**. They are the same as any pull request -- such as #9049, a mere test. However, in that pull request, Matt Corallo inadvertently introduced an inflation bug -- CVE-2018-17144 . 

I certainly do not say this to embarrass Matt Corallo, who I see as mostly the victim of bad luck. (With enough pull requests, one is bound to contain a bug eventually.)

The pull request idea (to save 600 millionths of a second), was a good one -- and the inflation bug would have (had it been exploited) hard forked the network. This is why it is essential that people run **old versions** of Bitcoin Core -- the exact opposite of what Luke Dashjr (for example) mistakenly believes.

So in that sense I am pro-ossification: people should run old nodes -- and old nodes should generally prevail over new nodes.

However, the ossification people are uneducated on these matters. They do not know (for example) the difference between a hard and soft fork -- eliminating their credibility on this issue.

But, really, for those people who *do know* the difference between a hard and soft fork -- this whole table is pointless, anyway. All the soft forks in the table, should activate, in the very next version of Bitcoin Core.

So, given that it is a huge mistake, why are we now doing it?

#### 2) This entire process is a disgusting venue for corruption

For a variety of historical reasons, the soft fork has mistakenly become a political football. This has led to trillions of dollars in lost Bitcoin value (and may be one of the worst events in the history of civilization), so I may as well take a few paragraphs to try to explain it now.

Two of the big events are: Satoshi concealing his identity, and CSW suing Bitcoin developers.

The details are not important -- what is important, is: no one wants to "take responsibility" for the Bitcoin project. In one sense, this enhances Bitcoin's decentralization -- no one can be jailed, in retribution for Bitcoin's success.

In a different sense, the lack of responsibility is more similar to a group of adults who refuse to "take responsibility" for a crying infant, who has been left out in the cold to die. In this sense it is shameful and disgusting. "After all", they say, "Craig is also out there in the cold, he might get us". In other words: everyone is a coward -- vile and corrupt, and therefore unwilling to do the right thing.

Ava Chow (for example), has stated explicitly, that it is the policy of Bitcoin Core, to "never merge anything if it is even slightly controversial on Twitter". This strategy has an obvious defect: it is quite easy to generate fake controversy on Twitter. Ava has further stated (in public on twitter) that Craig's lawsuits are one reason they avoid touching soft forks. This has the same problem: lawyers may sue, **until** a soft fork **is** merged. Really it's the same thing: either you do what's best for Bitcoin (the virtuous option), or you let the terrorists win (the cowardly option we are now taking).

Ava went on to say: "we will not let anyone know, that their idea has been rejected -- instead, we will just not talk about it". They are true to their word. APO (at the far right of the table), has the bizarre property that it was coded up many years ago, by beloved developers, to help upgrade the beloved Lightning Network, and yet its authors refuse to discuss activation -- so it just doesn't activate. The same happened with Taproot -- the developers who created it, simply refused to discuss it. (Eventually it was activated by Speedy Trial -- Core having nothing to do with it.) Countless soft forks, have simply been ignored out of existence.

Each time this happens, the anxiety surrounding the next soft fork increases. It is like a Pass/Fail exam, that gets harder and how. Now, in 2024, it is like winning the Nobel Prize -- when in reality it should be: nothing.

We can belabor the history that brought us to this point, or we can do the right thing, and: end all soft fork controversy.

#### 3) The Gatekeepers and Saboteurs

An improvement in Bitcoin technology, would be a disaster for many people:

1. First, obviously, Bitcoin's enemies would suffer. The better Bitcoin becomes, the worse off they are. Anyone who hates freedom, and believes that people are unreasonable and must be corralled into a jail and told what to do. They will smile to learn that a decentralized rabble cannot reliably get anything done.

2. Second, many tech startups have raised millions of dollars, on a project that works "on Bitcoin without a soft fork". As if this were something to celebrate - instead of lament. Their fortunes improve, if Bitcoin remains dysfunctional. 

3. The lightning network was originally a good idea (I wrote some LN tech myself, in 2016). But if Bitcoin functionality improves, LN will not be able to compete with newer, better ideas such as Thunder/13-13 and Ark (both presented at OP NEXT).

4. Anyone who loves custody, or custodial solutions. Op vault, and improved multisig -- these directly compete with BitGo (for example). There are multiple billion-dollar companies that can be replaced, with an op code. The op code is superior because it is more cypherpunk, more private, more reliable, etc.

5. All Altcoiners -- these people would love nothing more, than to see Bitcoin remain dysfunctional. This gives cover to their scam projects.

6. Anyone who (for whatever reason) criticized any soft forks, or the software development process. They will look like fools, if soft forks start activating again. This category includes many cynical opportunists, who formed their opinion during the 2018-2024 period. For example Michael Saylor has been telling people that if Bitcoin soft forks, then Bitcoin will be "deemed a security" and will be no different from Ethereum. This is quite an ignorant point of view, but held by many people. It also includes Peter Todd and shinobi, who have mistakenly criticized my Bip300 soft fork. These people will be (to some extent) revealed as frauds, if the Bitcoin development process contradicts their past statements.

7. Past authors of soft fork. It is natural to want to enhance your own prestige, by pulling the ladder up behind you. *Before* you gain entry to a school, you want it to be easy to get in -- but after you graduate, you hope that the school only takes the very best.

8. Current authors of a soft fork. In the mistaken view (of the table), that unfortunately now prevails -- only one soft fork can be done at a time. Supposedly, we must pick the one that is best, from among the group. Therefore, anyone who has authored a soft fork, has an incentive to bash the others, so as to hopefully secure their place in line. For example, CAT and CTV seem to have evolved some kind of rivalry, along these lines.

These people have an incentive, to fight the pro-softfork philosophy.

Are we going to let them get away with it? Probably.

#### Drivechain Comment

In fact, the whole covenants table is a kind of "controlled opposition", since it does not include the best soft fork of them all, BIP300. I had already built, back in 2020-2021, [working software (with a GUI)](https://www.youtube.com/watch?v=N33iJK2FdpE) using BIP300 that:

1. enabled planetary scale (to 8 billion daily users), and
2. cloned the zCash altcoin (for zk-snark privacy).

This is many years ahead, of anything that could possibly be built, using any of the opcodes in the table. Especially since the non-mined L2s are not viable in the long run (see [my OP NEXT presentation](https://www.youtube.com/watch?v=ImUCulfr1cE)).

However, as time passes, more and more people agree with my view. (Because it is correct.)


## Part 2. The Actual Proposals

### OP Vault

OP Vault is my favorite.

Vaults are very important, for protecting Bitcoin's core store-of-value use case.

Jameson Lopp has compiled a list of known physical attacks against Bitcoiners: people being tortured (or killed) for their private keys. First, this is horrible.

https://github.com/jlopp/physical-bitcoin-attacks/blob/master/README.md

But second, and even more importantly: every time that the perpetrator gets away with the coins, copycats are emboldened. All of us become less safe. And our project (to replace the banks) is revealed for the sham it is.

It is possible to simulate vaults, in various ways, but the application-specific op codes are best, in my view. 

### CTV and CAT

CAT:

* is mere string concatenation
* is fewer than 20 lines of code
* was already in Bitcoin Core
* was already *removed* from Bitcoin Core (via soft fork)

Plus, it allows Bitcoin to compute Merkle Trees. The Stark-researchers are interested in it (for some reason).

I see CAT as a canary-in-the-coal mine. If CAT cannot activate, then it proves that [probably] no soft fork can activate. It would demonstrate that politics has triumphed over reason. In this world, BTC will become a kind of "Starship Heavy Booster", and pave the way for some other coin to (eventually) take over.

CTV:

* Enables some vaults
* Enables the beginning of a shift from LN to ARK
* Is pretty simple, saying "you must spend to this TxID"
* Incredibly passionate, and dishonest critics -- so it must do something right

It is another canary in the coal mine.

I have been at a few different Bitcoin events where CTV has come up (since it has been around for many years now). A common remark is: "the problem is not with CTV, the problem is with Jeremy". This disgusting remark proves how corrupt and anti-meritocratic the whole process is -- if CTV does not get some vindication, then it proves that we choose our ideas, for reasons other than how good they are.

In my view, we have a choice: [1] do what is best for the Bitcoin user (and the Bitcoin miner), OR [2] do what is best for our own political bullshit games.

If we choose the latter, then we are no different from the Federal Reserve -- and we will be replaced. Just as BTC aims to replace them. (Everyone who is paying attention, will be able to +100,000% ROI a 2nd time, BTC will be defeated and go to $0. Just something to think about.)

Jeremy was years ahead, of everyone, on "covenants". He tried to activate them, years ago -- and was run out of town. He quit both CTV, and Bitcoin development. Now, years later, people have finally caught up to him. They *finally* see the value of CTV (et al)... but now, they want to second guess the maestro's opinion, a second time??

As far as I'm concerned, if you didn't support CTV back in 2019, then I'm really not interested in your opinion of it now. I'll just ask Jeremy what the right answer is -- he already knows today, what you'll be saying in 6 years.


### CSFS + PairCommit + InternalKey

Well... they don't really do much, do they?

They are very simple ingredients.

PairCommit seems to be an attempt to do OP CAT, while not doing CAT itself, for some reason. I actually strongly support this, in principle. (It saves a byte on the wire! Why not?) But I cannot shake how deranged it feels. So I demoted it to Weak. "Better than nothing".

### TX_Hash

Sorry to say this, but when I see TX_Hash I just see a kind of attempt to defraud and/or plagiarize Jeremy Rubin.

How can people feel differently about the two?

Once, I had dinner at a table that included Robin Linus, Burak, and his friends. That is the only time in my entire life I ever heard anyone bring up TX_Hash. That is the only time I heard "CTV is good but it cannot do the stuff people really want to do".

As far as I know, they are right. But the "Deficient" label reads: "Okay with the idea, but considers it to have insufficient community support", and I felt compelled to use it somewhere.

Honestly, the labels are terrible, especially when they ask me to make an assessment of "community support".

### APO

There's nothing wrong with APO -- as an opcode. So we should activate it. And we should have activated it many years ago.

The reason I gave it "Weak", is because Bitcoin is being vampirically drained of life, by the accursed Lightning Network. APO (sort of) gives hope to Lightning, when instead it would be better for us all, if that hope were extinguished. (That is also why I snuck a "Weak" into LNhance.)

A second reason to opposite APO, is ironically because of how old it is. This may set the precedent that opcode-softforks should "wait in line" -- wait many, many years before activating. What a dreadful thought!

### CCV

I've never heard of this before. As you might guess, I didn't particularly feel compelled to look into it.