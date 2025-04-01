---
title: Precedence Ossification
show_author: true
comments: true
date: 2025-03-01 05:00:00
---

### Overview

Here I will contrast:

1. **Code Ossification** -- The belief that Bitcoin's software should CEASE to change, forever.
2. **Precedence Ossification** -- The belief that, in any dispute (between two Bitcoin nodes), the newer node should always DEFER to the older node.

The former is incorrect, and naive.
The latter is commonsense, and true.

In fact, the former view is so appalling -- so misguided in every way -- that I wonder: "Why even write an article about this? Isn't it obvious??". PO beats CO -- every time, in every way.

## Part 1. Primitive Superstitions -- The Motivation of this Article

But alas -- CO has become very popular.

![image](/images/black-cat.png)

Above: Superstitions, from [this page](https://meghines.wordpress.com/2020/07/10/superstition/).

For example, clearly **Michael Saylor** adopts CO -- or, he would, if he knew what we were talking about. The last time I spoke with him, he had no idea what any of these vocabulary words meant -- and didn't seem inclined to learn. Nonetheless, if Saylor carefully studied the issues (for a week or so), he'd come out saying: "if Bitcoin changes too much, it will be deemed a security, like Ethereum", and "Bitcoin is already a $300 trillion asset, the important thing is that we not screw that up", etc. At times like this, we should remind ourselves that Saylor is relatively new to Bitcoin, having joined [in 2020](https://en.wikipedia.org/wiki/Michael_J._Saylor) (many months after covid stimulus checks were announced, and three years after the blocksize war was over), and that he is [only up 32%](https://saylortracker.com/) on his Bitcoin investment -- making him one of the least successful Bitcoin investors of all time.[^1] 

[^1]: David Bailey [rightly stresses](https://x.com/DavidFBailey/status/1902135668945645627) that Saylor should get respect, for putting his money where his mouth is. Indeed. But many have done that. Erik Voorhees, in 2012 was asked "when he was going to cash out his Bitcoins", and famously replied: 'I did cash out. From the dollar.' Ultimately, Mr. Bailey's comment boils down to: "during 2020-2025, Saylor controlled more money than most Bitcoiners". Certainly, Saylor has less skin-in-the-game than many Bitcoiners, in my view.

But it is not just Saylor. A whole technical conference, **OP NEXT**, met in Boston in Nov 2024, to directly address the ossification topic. The main takeaway? ["Just Don't Break Bitcoin"](https://www.coindesk.com/tech/2024/11/12/just-dont-break-bitcoin-devs-debate-upgrading-tech-behind-top-crypto) -- the ultimate vapid platitude. As with Saylor, this view would be "Code Ossification", *if* the participants were sophisticated enough to have a view in the first place. Instead, "just don't break Teddy!", a child says, about their special toy, when they do not understand why it has to go through the airport luggage scanner. Should we even bother explaining? The child wouldn't understand any of the vocab words.

If you think I am being unfair, picking on the faceless "consensus view", then consider **Antoine Poinsot** -- a member of ChainCode Labs (an elite Bitcoin Dev organization, where many top minds fled after resigning from Blockstream), founder of a Bitcoin cybersecurity company, organizer of the BTC Azores tech conference (funded in part by [a $1.5 million OkCoin grant](https://www.bitcoininsider.org/article/184395/btc-azores-unstructured-conference-unstructured-protocol)), and author of Bitcoin Core's [official CVE disclosure policy](https://groups.google.com/g/bitcoindev/c/Q2ZGit2wF7w?pli=1). As of writing, his single [pinned Tweet](https://x.com/darosior) is [his longform piece](https://antoinep.com/posts/softforks/), which can be summarized as: "just don't break Bitcoin". Any code change might break Bitcoin, so the fewer code changes we make, the safer we are!

For what it's worth, I have traveled across Miami, NYC, CT, Nashville, Atlanta, Amsterdam, etc, attending Bitcoin conferences and meetups. The "don't break Bitcoin" is a popular view. I sometimes reply, "well, it's usually the people who don't know the difference between hard/soft fork, who say that", and invariably I hear: "oh, what is the difference?". (Thus confirming my suspicion that these views are based on ignorance.)

Before elaborating, I will explain a noteworthy Twitter exchange between Poinsot and myself -- because of how revealing it is. I wrote [a tweet expressing my disagreement](https://x.com/Truthcoin/status/1898443989365186819) with Poinsot's post, and [he replied](https://x.com/darosior/status/1898513368417198088), sarcastically: "when our source of truth won't be available, we'll just ask @Truthcoin for the state of the system. What could go wrong?". To him, the "source of truth" is the most important thing -- and I agree. What's interesting, is that I thought I made it clear in the *original* post (the one Poinsot is *replying to*), what to do in that situation. I *immediately* give a specific example, of a new source of truth that fails -- leading us to automatically revert to the old one. I even spell it out, saying "the legitimacy of past versions", is what protects Bitcoin. In other words, Poinsot's question (of "how to find the source of truth"), I had already answered: revert back to older and older nodes. If any nodes disagree, ever, then the oldest one prevails. (This is, in fact, the definition of "soft fork", as I have presented many times --including at [MIT 2023](https://www.drivechain.info/media/slides/mit-2023.pdf)). Yet, why repeat it? Poinsot missed it the first time. 


Now I will discuss ossification in some detail.
<!--
Pure CO (code ossification) would be: for the **software binary** not to change at all. (With the exception of CVEs). 

Currently we have nothing of the kind.
-->


## Part 2: The Benefits of Ossification

"Ossification" is when you RESIST the temptation, to yield to people's complaining.

In contrast, "Compliance" (in this context) is when you *give in* to people's complaining.

![no-whining](/images/no-whining.jpg)

Ossification helps ensure predictability, stability, and decentralization. In contrast, if things were changing all the time, we would need to know [1] what we were all changing to (and when, and how), [2] that the change won't "break Bitcoin", and [3] from *what origin* we obtain the details of the change (ie, how to find the new full node software, in the event of a dispute).

The pro-ossification arguments are very good, and very old. The arch-priest would be [the infamous Mircea Popescu](https://bitcoinmagazine.com/culture/mircea-popescu-bitcoin-philosopher-dead), saying (for example):

* ["The choice to stay away [from Bitcoin], whether voluntary or involuntary, whether deliberate or through omission, whether because you're poor or because you're stupid has already cost you, and will continue to cost you for the conceivable future."](http://trilema.com/2013/bitcoin-will-die/)
* ["you will lose your Bitcoins"](http://trilema.com/2015/if-you-go-on-a-bitcoin-fork-irrespective-which-scammer-proposes-it-you-will-lose-your-bitcoins/) -- re Hardforks / Blocksize war
* "you don't change Bitcoin; Bitcoin changes you" -- not sure if a real quote, but undoubtedly this "attitude" is attributed to MP.

I myself have written:

* [Measuring Decentralization](https://www.truthcoin.info/blog/measuring-decentralization/)
* [Against the Hard Fork](https://www.truthcoin.info/blog/against-the-hard-fork/)

We may elaborate the benefits of Ossification, as follows:

* If we are vulnerable to change, then we are also vulnerable to *harm*. In contrast, if we aren't being changed, then at least we know we aren't being harmed. 
* The whole **problem of Bitcoin** is the [**liberty reserve problem**](https://en.wikipedia.org/wiki/Liberty_Reserve). In other words, *how to keep the ledger alive* under adversarial conditions. (For more read [Aaron's excellent book](https://www.amazon.com/Genesis-Book-Projects-Inspired-Bitcoin/dp/B0CQLMQRH7).) In other words, "Bitcoin" is *the thing that United States federal prosecutors cannot affect* -- ie, that the US military cannot affect. So, being "un-affect-able" is part of its very nature. (See also the [Axiom of Resistance](https://github.com/libbitcoin/libbitcoin-system/wiki/Axiom-of-Resistance).)
* Banking is simple and autistic -- just add and subtract. (This simplicity, is part of what makes ossification possible.)
* The slippery slope -- if we change once, doesn't it become easier to change again? And, eventually the "bitcoin" system will not stand on any kind of principle. It will have some human "governance" process (and so will not be principled/autistic). Instead, it needs a [Schelling Fence](https://www.lesswrong.com/posts/Kbm6QnJv9dgWsPHQP/schelling-fences-on-slippery-slopes).
* Comparative advantage -- All of the big currencies out there today --both crypto and fiat-- are pliant (and com-pliant). Bitcoin should specialize, and be the unique "non-compliant" ossified option.

In general, Ossification is good. I would describe myself as pro-ossification...

...until recently.

## Part 3. Problems with Today's Ossifiers

Today's ossifiers have *ruined the "ossify" brand*.

They are naive, uninformed, self-contradictory, and generally embarrassing.

Let's discuss why.

### A. Infallibility

"Infallibility" refers to this idea: "Bitcoin (in its present form) cannot fail".

Infallibility is *assumed to be true*, by many Bitcoiners. Which is unfortunately, because it is obviously false, because:

* There is no way to foresee, all of the *good* ideas someone will come up with tomorrow. (After all, there was a day *before* you had ever heard of Bitcoin. Tomorrow could be that day, for a new "Better Bitcoin" idea.)
* There is no logical way to learn, today, what mistakes we have already made in BTC (or will make tomorrow), and what these will cost us.
* There are no infallible sources of wisdom, of any kind.
* (In contrast,) "wishful thinking" is a broad, common, overwhelming human delusion.

I have three quotes, to just remind us the perils of complacency and groupthink:

    "Organizations are permanently and randomly subject to decline
     and decay — no matter their institutional framework." 
    -Albert Hirschman
    
    "Monopolies don't innovate. The motto of any monopoly is: 'We
     don't care, because we don't have to.'"
    -Marc Andreessen
    
    "It is self-deception to think that the status quo is going to
     be satisfactory for everyone forever. It's already not
     satisfactory for a lot of people."
    -David Deutsch

And we should also consider -- the [Fall of Rome](https://en.wikipedia.org/wiki/Fall_of_the_Western_Roman_Empire) -- the [sinking of the "unsinkable" Titantic](https://en.wikipedia.org/wiki/Titanic) on its maiden voyage -- the [Star Wars Prequels](https://www.youtube.com/watch?v=xxf1c3fzDOU) -- the fall of Detroit from the wealthiest city in the world (1950s) into poverty -- Fyre Festival / Theranos seeming amazing (but mere frauds) -- Collapse of the Han Chinese dynasty after 400 years -- US housing Bubble -- etc -- numerous other factors I list [here](https://www.drivechain.info/misinformation/#8).

The irony is that **the biggest "change" to Bitcoin, would be if it *failed***. If Bitcoin is replaced by something else, then that would be a full 0% ossification.

Furthermore, the #1 way for Bitcoin to fail, would be *slow adoption*. Money has network effects -- people strongly prefer to use, what their friends are using. If Bitcoin is to survive, then it must meet a critical threshold of *relative popularity*. Bitcoin will go to $0, in a world where 8 billion people use Litecoin every day. There is only room for one cryptocurrency. Thus, *part* of survival itself (ie, part of ossification) is --paradoxically-- a "popularity contest". Bitcoin must be popular enough to survive -- if it is to ossify at all (let alone even a little bit).

### B. The Immaculate Conception

Tied to "infallibility", is the idea that Bitcoin has no viable competitors.

Hal Finney said, in May 2011:

        "Any successful replacement of the Bitcoin block chain
        will forever undermine the credibility of any successor.
        How is an investor to know that it won't happen again?".

Nowadays, this is translated as: "No Altcoin can ever surpass Bitcoin". And it is sometimes called "the immaculate conception".

Back in 2011, Hal was 100% correct.

But today things are very different. Namely, today there are *more ideas*, and *fewer of them* make it into the BTC project.

For example, in 2011 there was only one Altcoin. It was called Namecoin and it had a distinct, useful purpose. It was programmed by Satoshi himself, to *cooperate* with the BTC blockchain -- (Satoshi co-invented merged mining, just as he was co-inventing Namecoin itself). The 2nd Altcoin (Litecoin), would not arrive until Oct 2011 -- it was a carbon copy of BTC, with nothing new added at all. Thus, 100% of the innovation was on top of BTC, and the only competitor was [indeed] a cheap knockoff.

Today, there are tons of blockchains. There are many researchers -- and even identical protocols can have different parameters (such as blocksize). There is constant disagreement among devs, over what to add. As a result there is great **protocol heterogeneity**.

In Hal's day, Bitcoin was under constant development. During the 2009-2011 period, there were [7 soft forks and 1 hard fork](https://x.com/Truthcoin/status/1088934244762640384/photo/1); and during the 2011-2017 period, there were *10 soft forks and 1 hard fork*. Today, from 2017-2025, there has been just one soft fork [taproot]. In Hal's day, there was **near-zero** controversy over doing a soft fork (compared to today). In short, today there is **ossification**, which makes it difficult for any ideas (both good and bad) to make it into old protocols.

Hal's Bitcoin of 2011 was a constantly-changing, constantly improving piece of software, that was always tied for #1 in terms of its technical impressiveness. Hal would have assumed that this would continue. Thus, **given that the Bitcoin protocol is near the technical cutting edge** [why would it not be], then *why would anyone switch to a competing coin*? But this logic falls to pieces, once there are new coins that have significantly different tech. Indeed, Bitcoin led the way on DarkNet Markets, but now those same markets have [switched to Monero](https://x.com/DarkDotFail/status/1349640329578700800), due to a supported privacy tech (ring signatures). (This led Saylor to awkwardly admit that [maybe there is a 2nd best after all](https://www.youtube.com/watch?v=ccJ33hLaMF0).)

Hal was correct to say that a "flippening" [where an Alt overtakes BTC], would damage the credibility of the whole industry[^2]. But damaged does not mean destroyed. The credibility of our industry could fall, from 95% to 92%, as a result of a flippening. But investors would weigh this downside, against the upside of the new technical feature.

[^2]: The "credibility of our industry" is --alas-- very low. Hard to get much lower, as the result of a flippening!

In fact, we could rewrite Hal's argument backwards, if we wanted. We could say: "Any industry, where the #1 leader is lazy and complacent [and never improves], is a terrible place for the consumer! Mainstream consumers will shy away -- they will not adopt the coin, until they see a healthy environment of competition!" Not until a coin flips BTC, will the layperson realize that -- hey, *this* is the winning coin -- *this* new coin is the real deal. (So it is something of a circular argument.)


### C. Is it good to be bad? (No)

Saylor's conclusion re Monero ["you don't want to be that good"] is a prime example of "Infallibility". This perplexing statement embodies the complacency of the modern Bitcoiner -- ie, not only has Bitcoin *already won*, but also we need to *screw some things up*, intentionally -- we don't want to be too good!

It's like going to doctor Saylor for your annual checkup, and him breaking both of your legs -- all to help you, of course. (Help you be less intimidating to people! Plus you can use the handicap spot, now!)

Let us unpack this.

Saylor is correct in his belief that social life is not *additive*. For example, if you invite person A to your birthday party, then maybe B, C, and D won't want to come. In our case, if you invite the pro-privacy "Alice", to the Bitcoin party -- then [perhaps] the pro-government, pro-tax, pro-corporate, pro-mainstream people won't want to come. Saylor believes that adoption will be faster, if privacy tech is shunned.

That could be the case -- and it could not.

It could be the reverse. Mr. Saylor might *himself* be that odious houseguest who repels B, C, and D. After all, if I am correct in [my other theories and models](https://www.truthcoin.info/blog/all-world-txns/), then by promoting his brand of naive ossification, Saylor is:

* denying miners an enormous source of transaction fee revenues (to the tune of hundreds of billions USD per year),
* pushing a few "killer apps" (prediction markets, grey markets) toward other chains (Polymarket / Monero), even though they should all be on BTC,
* opening the door to complaints (both frivolous and justified), that BTC rejects innovation and lacks key features,

...all of which serves to drive users *away* from BTC. (And which undermines Hal's argument, opening the door to a competing "BetterBitcoin".)

In any event, Saylor's quest to halt technological progress is bound to fail. Devs are always going to dev -- and users are going to use software (if that software is useful). I myself figured out how to do ["soft forks without a soft fork"](https://bip300cusf.com/), and how to [add strong privacy to BTC as an optional L2](https://www.youtube.com/watch?v=N33iJK2FdpE). It requires zero changes to Bitcoin Core. To thwart this, Saylor would have to convince BTC miners to voluntarily forego these txn fees -- ie, to collect less $$ (in return for doing the same work).

Saylor is wrong in yet another way. He mistakenly divides the world into "compliant coins" vs "private coins" -- the compliant coins will [supposedly] get "institutional adoption" [ie, adopted by governments, corporations, ...], and have an advantage over the "private coins" (which are dirty). This ignores **cryptographic swaps** -- trading BTC for XMR, using only the blockchain (no names, no records) -- these swaps are very easy to do[^3]. In an extreme scenario --where govts crack down on XMR/USD trades, eg Saylor's line[^4]-- users would evade the ban by purchasing BTC instead [and then c-swapping it for Monero]. Eventually, the Bitcoin blockchain (and lightning network) would be the #1 way to get Monero -- the Bitcoin blockchain [and its cryptographic swaps] would be *The Glaring Flaw* in the government's misguided Monero crackdown program. So -- if governments are going to crack down on XMR, then they will have to crack down on Bitcoin as well. Thus, the supposed distinction between "compliant coins" and "private coins" does not exist.

[^3]: HTLCs are "Hash Time Locked Contracts" -- they are what power today's lightning network -- [or, they *would*, if LN worked](https://www.truthcoin.info/blog/lightning-limitations/#b-htlcs). They can easily be used to [swap BTC for other coins](https://bitcointalk.org/index.php?topic=193281.msg2058662#msg2058662). This has been known for more than 10 years, and is not controversial. Probably, this method is not quite as popular, because self-custody is difficult for people and the centralized [website-based] exchanges [such as Coinbase and Kraken] are making so much $$, they can advertise, acquire customers, etc. Every coin either already supports Sha256, or could easily -- and so every coin could easily support a Sha256-based HTLC -- they certainly would, at the drop of a hat, if push actually came to shove and this was the only way to get money in/out of the coin.

[^4]: I refer to ["you don't want the United States government to say 'Bitcoin is completely private'"](https://www.youtube.com/watch?v=ccJ33hLaMF0&t=72s).

Furthermore, "compliance" is a rejection of Proof-of-Work (and of the whole design of Bitcoin). Once we enter the "transparent" world [of corporations, custodians, EIN numbers, registered agents, domain names, brand equity, SOC reports, and mailing addresses] -- we have no need of PoW. A single ECDSA signature, from a known pubkey, has more than 100 million times the cryptographic firepower of any realistically achievable amount of PoW. The *whole comparative advantage of PoW* is that it is anonymous -- free entry and exit -- thermodynamic -- physics-based, not identity-based. In 2016, a wave of "blockchain, not bitcoin" companies sprung into existence, all hoping to cash in on "the technology behind Bitcoin" -- including Goldman Sachs (who were also [among the first to leave](https://nypost.com/2016/11/22/goldman-sachs-drops-out-of-controversial-r3-blockchain/)), [IBM](https://arstechnica.com/information-technology/2016/02/ibm-wants-to-move-blockchain-tech-beyond-bitcoin-and-money-transfer/), and [Microsoft](https://www.microsoft.com/en-us/industry/blog/financial-services/2016/03/14/azure-blockchain-as-a-service-update-6/). Nothing ever became of these efforts, because the SSL pubkey for "microsoft.com" already had more firepower than all the proof of work in the world. And the proof of work is the whole reason that the blockchain updates in discrete "blocks" -- drip by drip, instead of in a continuous stream. If we abandon proof of work, we will end up competing with Venmo and MasterCard -- and we will lose. An anonymous system of strangers, who are bound together only by the transaction fees they pay [and the digital network that aggregates and synchronizes their transactions], is the only viable path forward. (Back in 2016 this was common knowledge among all Bitcoiners[^5].)

[^5]: Two episodes of the 2016 podcast "Bitcoin Uncensored" come to mind. In one, Chris and Josh read aloud a suggestion for a mining company "where it only allows transactions that have done KYC/AML" -- there was a short pause, then they both laughed. "It's like they don't know what mining is for", they said. (They didn't even bother to explain the point.) Second, Chris and Josh were invited to speak at FSU (or some such place), someone asked a question like "Can we upgrade Bitcoin to do AML?", and Josh replied with a joke: "Bitcoin doesn't do AML - it does ML".

### D. Self-Contradiction / Obliviousness

Many ossifiers unwittingly harm their own cause. Like a Chinese finger trap, they want to pull their fingers loose, but they just tighten the trap. (Since they do not understand how the trap works.)

In the same way, some ossifiers *want* ossification [or, so they think] -- but their *actions* harm their own cause.

Their counterproductive actions, include:

* Fighting soft forks. Soft forks are pro-ossification. Soft forks are NOT a change to L1 protocol, since the old protocol survives intact. However, pro-ossification people such [Michael Saylor, react with absurd ignorance and hostility to soft forks](https://x.com/saylor/status/1697874866102325255).
* Failing to support sidechains. Sidechains allow everyone to get what they want -safely- on a Bitcoin L2. For example, a [largeblock sidechain](https://www.truthcoin.info/blog/thunder/) would have prevented the blocksize war. Instead, the largeblockers first (1) pushed for a hard fork [which is very anti-ossification], and (2) left the BTC community, with the direct aim of replacing BTC with a competing cryptocurrency (BCH). Both of those outcomes were anti-ossification, vs sidechains which would not have affected Bitcoin L1 at all.
* Neglect of the problem of "CVEs and Privileged Individuals" (next section) 
* Neglect of Code Rot, Refactoring, and Dependencies (section after that)

Eventually, they realize: they have no idea what they are talking about, no one is listening to them, they don't exactly know what to do (if anything). At this point, they fall back to "Code Ossification" -- which is itself a doomed and counterproductive idea, as I will now explain.


## Part 4. Core, CVEs, and Privileged Individuals

In Part 4 I will begin to demolish the misguided idea of Code Ossification.

### A. Bitcoin Core

The [official policy of Bitcoin Core](https://bitcoincore.org/en/lifecycle/) is:

    We aim to make a major release every 6-7 months.
    ...
    We generally maintain the current and previous major release. [only]

They will put out a new version twice a year -- regardless of what Saylor or Twitter or YouTube thinks. That's the reality. Look at the GitHub history -- you'll see that they stand by their words, 100%. 

Therefore, the Code Ossification movement is totally dead-on-arrival, already. It exists only on Twitter; and in the useless blather of the small-minded.

(That ought to be reason enough, to discard it -- but really, we're just getting started.)

### B. Accidental Severe Changes

In 2016, Matt Corallo [accidentally introduced](https://medium.com/@awemany/600-microseconds-b70f87b0b2a6) a *severe inflation bug* to Bitcoin.

Similarly, in March 2013, switching from BerkeleyDB to LevelDB [caused an unexpected hardfork](https://en.bitcoin.it/wiki/BIP_0050) (see [also](https://freedom-to-tinker.com/2015/07/28/analyzing-the-2013-bitcoin-fork-centralized-decision-making-saved-the-day/)). Thankfully, miners abandoned the hardfork immediately, so there was no permanent network split.

These events --in theory-- were very anti-ossification. They were hard forks (and -- the former violated the 21M coin limit).

But because they were accidental, there was no discussion. There were no "twitter hats" -- no t-shirts. No slogans. No podcasts. No campaign. No debate.

"Aha!", say the Naive Ossifiers, "You see? It is easier to change Bitcoin, than we thought! Bitcoin is vulnerable to change! We need to be extra-vigilant, to avoid changing it."

Yes -- we do need more vigilance. But it cannot take the form of: "hats, slogans, podcasts, tweets". That is not vigilance. It is insufficient.

Some of Ossifiers realize this -- leading them to *correctly* adopt the policy of **not upgrading one's node** unless absolutely necessary -- the "Frozen Binary". This is smart, and it is an essential part of *Precedence Ossification* (the good kind, see Part 6).

Unfortunately, it also *misleads* people, tricking them into adopting Code Ossification. People think "hey, if I shouldn't update my node unless absolutely necessary -- then *Bitcoin as a whole* shouldn't do that, either". It may sound reasonable at first glance, but upon deeper inspection this policy [of "Code Ossification"] is a disaster.

So -- now we meet the Ossifier's Achilles's Heel...

### C. CVEs

CVEs are emergency bugs.

They are very severe, and must be fixed quickly -- before the Bad Guys find out about them.

But -- more interestingly -- we also need Regular People to *upgrade* (ie, to install the "patch") **before we can tell them why**.

In this sense, CVEs represent a Black Box. There could always be a CVE, out there. It could have been introduced yesterday, or 5 years ago. It could have been introduced accidentally or on purpose.

Furthermore, the CVE is often **fixed covertly** -- to avoid alerting the Bad Guys to its presence. Thus, CVEs are secret in two ways: they appear randomly and unexpectedly, out of the mist -- and they are fixed with a lie. Only the **privileged individuals** know the truth about *why an upgrade is necessary*.

The inflation bug I mentioned above, was a CVE (of course). It was "CVE-2018–17144" -- (that is how such things are named).

Here is [the official Bitcoin Core Disclosure Policy](https://groups.google.com/g/bitcoindev/c/Q2ZGit2wF7w?pli=1), along with [some](https://x.com/alexbosworth/status/1809330440693809387) [commentary](https://bitcoinmagazine.com/technical/bitcoin-core-announces-new-security-disclosure-policy). It includes the quote:

    The project has historically done a poor job at publicly disclosing
    security-critical bugs, whether externally reported or found by
    contributors. This has led to a situation where a lot of users
    perceive Bitcoin Core as never having bugs. This perception is
    dangerous and, unfortunately, not accurate.

Hence the flaw in Code Ossification strategy: we cannot **permanently** stop upgrading, unfortunately. Because we can never be sure that our version is free of CVEs.

For this reason alone, CO is a dead end. But there are more reasons still!


## Part 5. Code Rot, Refactoring/Optimizations, and Dependencies

CO faces *a whole slew of practical problems* -- if you have never worked with computers, then these might surprise you.

### A. Code Rot

[Code Rot](https://www.overcomingbias.com/p/why-does-software-rothtml) refers to the idea that ["most all computer systems become gradually more fragile and harder to usefully modify over time, and eventually are replaced wholesale"](https://www.overcomingbias.com/p/what-makes-stuff-rothtml).

The great Bitcoin Engineer Jameson Lopp [wrote](https://www.forbes.com/sites/digital-assets/article/should-we-be-worried-about-bitcoin-ossification/) (on ossification):

    Even if this inevitable problem didn’t exist, one fundamental
    truth stays the same: unmaintained code rots.
    -Jameson Lopp

He also [said](https://www.youtube.com/watch?v=DQr3NIZf6DI) (rightly):

    We have to be wary of making changes to Bitcoin because there
    will always be unforeseen consequences. The flipside of that,
    that few people talk about, is that not making changes to
    Bitcoin also has unforeseen consequences.

Software exists *within* a wide variety of layers -- operating systems, device [family desktop vs laptop vs mobile vs client-server], platform, frontend, developer tools (ie, LLMs vs IDEs vs GitHub Actions vs hole-pushed cards), cultural knowledge of computers, the "stack" [AWS vs P2P vs Web 2.0], performance (and user expectations) -- all of these are in flux. As a result of this change, some parts of the software stack become easier to read/write/rewrite over time, and for other parts it is the reverse. Software "rot" refers to the gradual degradation of static code.

### B. Refactoring

[Refactoring](https://en.wikipedia.org/wiki/Code_refactoring) refers to the idea of *rewriting all the code from scratch*, just to make it do the exact same thing.

[Optimization](https://en.wikipedia.org/wiki/Program_optimization) when a refactor allows the software to run faster (or use less RAM, less CPU, less disk space, etc).

On one hand, Refactoring might *appear* to be pro-ossification. After all, the code does exactly what it did before, right? 

Except now, the code has been *passed over again* -- someone new has read it, thought about it, clarified it, debugged it, and freshly rewritten it.

In these ways, refactoring/optimization is actually a danger to ossification:

1. The new code may not behave *exactly* the same as the original code. (This was the case in the two examples at the beginning of this section -- both were optimizations.)
2. Because refactoring is so "boring" (and because it is considered a thankless "maintenance" chore) -- no one views it as a threat, and in fact doing this "janitorial" work may even earn you "brownie points" among the Bitcoin Core Maintainers. (See, you aren't breaking into the safe, you're helping sweep the floor!)
3. Refactoring --by its very nature-- touches an enormous number of lines of code. The goal of refactoring is to break ALL the code down and rewrite the WHOLE thing, into ever smaller and smaller pieces. So you can easily touch many lines of sacred code, and rewrite them yourself. You have an opportunity to understand all of the unit tests / test vectors (that will catch your own wrongdoing). If you introduce a severe bug on your 1st or 2nd draft -- everyone will forgive you. This will be treated as a mere "part of the job" of refactoring.

Refactoring is also pure hell, for newbies trying to *learn* the Bitcoin codebase -- since it is now always changing. Whole sections are moved around, and renamed. At one point, they [removed main.cpp](https://github.com/bitcoin/bitcoin/pull/9260) (from a C++ project). Any book, or guide to the Bitcoin code, will [become obsolete](https://bitcoin.stackexchange.com/questions/114125/where-does-the-main-cpp-moved-to-in-recent-versions) very rapidly. This leads to an insular priest class -- a monopolist guild, in which only a few are capable of understanding the Bitcoin codebase.

### C. Dependencies

If all that weren't bad enough, we also have to deal with [Dependencies](https://old.reddit.com/r/learnprogramming/comments/15sq6o6/can_someone_help_explain_software_dependencies/?rdt=35813).

Each program is a "stack" of sub-programs that were written by someone else, called "dependencies". For example, in the real world, when you "build a house from scratch", you aren't digging iron ore out of the ground, to forge your own screws. And you aren't cutting down your own trees to make 2x4 lumber. A house is "built" out of stuff that was *already invented/made by someone else*. Same with software.

Each of these "dependencies" has their own bugs, CVEs, refactoring, etc. A famous example was [Heartbleed](http://heartbleed.com/), in 2014 -- which led to [chaos and panic throughout the internet](https://www.coindesk.com/markets/2014/04/08/major-security-flaw-heartbleed-puts-critical-services-at-risk/).

Heartbleed affected Bitcoin Core, and [could theoretically have allowed hackers to steal people's BTC](https://bitcoin.org/en/alert/2014-04-11-heartbleed#how-serious-is-the-risk), if they did not "immediately upgrade" to 0.9.1. This would surely have humiliated any "ossifiers" -- but, back in 2014, there weren't any.

### D. Rolling Your Own Crypto

Bitcoin 0.12 [removed OpenSSL](https://bitcoincore.org/en/releases/0.12.0/#signature-validation-using-libsecp256k10) (ie, "libconsensus no longer depends on OpenSSL"), and replaced it with something that the Bitcoin Core Developers invented themselves, called "libsecp256k1".

Now -- I ask you: is that better?

Surely, it has the advantage that a bug in OpenSSL will not screw up Bitcoin. But it has the *disadvantage* that the library is now more obscure.

Before, we had the classic "strength in numbers" advantage of open source -- so called ["Linus's Law"](https://en.wikipedia.org/wiki/Linus%27s_law). Since the Heartbleed bug affected so many people, it was a bigger "event". Everyone had to fix it -- they had no choice. And they could safely copy the "mainstream" fix -- because they could be confident that anyone pushing a fraudulent fix, would also be caught by the mob. It was an ["eyes on the street"](https://thecityfix.com/blog/how-eyes-on-the-street-contribute-public-safety-nossa-cidade-priscila-pacheco-kichler/) scenario.

Now, with libsecp256k1, what will happen if there is a bug? Fewer people use it, so fewer people will be capable of fixing the bug -- or of understanding the fix. It is shrouded in a deeper mist -- with more reliance on the (now irreplaceable) Bitcoin Core Developers.

Ironically, the same elite developers used to swear by a mantra called "don't roll your own crypto". As [Andrew Poelstra wrote](https://download.wpsoftware.net/bitcoin/alts.pdf) in 2016:

    Why am I writing this document? Because when I first entered
    the world of cryptography, there were certain common-sense
    maxims ... For most people, these maxims could be summarized\
    simply as "don't roll your own crypto". Anyone who flouted
    this golden rule, without decades of schooling and experience,
    was rightly dismissed as a crank or a troll.

But, by ditching OpenSSL for libsecp256k1, we have certainly rolled our own crypto.

(Perhaps we have the requisite "decades of schooling and experience"?)

Either way -- this illustrates the perils of dependencies. Software has bugs -- and the software you write yourself, is probably *more likely* to have bugs, than software written by the wider Open Source Community. Pick your poison!

### E. Performance

A filing system that works for 10k emails, often fails at 100k emails.

In such cases, the software AND hardware are "ossified" -- they do not change. But one thing does change: the quantity of emails. It keeps piling up. *Regular*, expected use of a *popular*, **ossified** system -- leads to new problems and new requirements.

Usually the fix is simple. But usually the fix is also *unforseeable* -- we have to wait for circumstances to unfold, and then intelligently react.

I elaborate on this point in Appendix 1.

## Part 6: What We Should Do

### A. Precedence Ossification

**Precedence Ossification** is a flavor of ossification, that acknowledges the following background facts:

* Adversaries will try to attack Bitcoin, by sneaking it bad changes -- ossification is an excellent defense, against this attack.
* We cannot actually achieve ossification, unless we understand the underlying computer science.
* As *individuals*, we should avoid upgrading our software, if we can -- but *collectively* we cannot expect the whole system to stop changing. Some people will require new bugfixes, and new features. They will go elsewhere if they don't get them from us.
* The "frozen binary" (ie code ossification) is a doomed project because of:
* * CVEs [that we don't know about and will never know about],
* * Dependencies [upon which our software depends, but which we don't control],
* * User habits / expectations [such as the switch from mainframe to family desktop to mobile], 
* * Performance degradation / code rot over time [which is near-inevitable],
* * Developer habits [open source developers cannot helps themselves -- devs gonna dev]
* In the long run, the #1 best way to placate people [such as largeblockers, Altcoiners, LN devs, Covenant devs], is to give them *what they want*. If we support them, they will reciprocate -- if instead we antagonize them, they will try to destroy us. So, **if we can** give people what they want, in a safe way [ie, without harming other users], then we *should*. If we turn a blind eye to user-demand, (or worse -- kick talented and motivated people out of Bitcoin, and into competing projects), then our project falls in popularity, and may ultimately be replaced -- such a 'Death of Bitcoin' would be the ultimate anti-ossification.
* The whole reason the soft fork was invented, was that it allows for the peaceful coexistence of different protocols. We should be thankful that such a technique exists, and use it to its fullest potential -- not abuse it for political clout.
* It is always possible to find some idiot who will complain, about anything -- no matter how good it is, objectively. Some people make whole careers out of gate-keeping or cynicism. It is easier to complain, than build -- so, we should be prepared to ignore complainers, if they are not builders themselves, or if their complaints are bad, or if their motives are suspect. Therefore, a given soft fork can NEVER "have consensus" -- no idea ever will -- and we should NOT hold anything to an unmeetable standard.

It therefore advises, the following:

1. **Delay upgrading, personally**. -- Everyone should wait as long as they can, before upgrading (if at all) -- don't be the first through the door. Any new Bitcoin Core release could have a hidden bug. Let others be your Guinea Pig. Try to wait 6 months before upgrading.
2. **Old software outranks new.** -- If there is ever a disagreement among nodes (in the ChainActive, BestTip, UTXO set, etc), then the old node is considered correct and the new node is disregarded. Large exchanges (Kraken and Coinbase) and payment processors (BitPay, BitRefill) should always run several Bitcoin versions simultaneously -- ideally all of them, or one from each calendar year. In the event of any disagreement, just shut off the newest nodes and fall back to older nodes.
3. **Support soft forks.** -- Although we personally should avoid upgrading, we should expect the protocol to change -- always in backward compatible, opt-in and reversible ways. We should study the soft fork, and investigate [ways to make it even safer and easier](https://bip300cusf.com/cusf.pdf).
4. **Support P2P sidechains.** -- These are whole separate blockchains, where devs and users can do [almost] whatever they want. And yet they are also Bitcoin L2s. This is the ideal way to give people what they want, while keeping L1 ossified.
5. **Support competition.** -- It is perverse to expect everyone to agree -- in contrast, two adversaries are usually in a good position to criticize each other. Also, if we ever must have a hard fork, then do it openly -- with a completely new name. All Bitcoiners will receive coins on both sides of the fork, and the networks can have separate fates.

### B. What if we can't convince people?

Notoriously, it is difficult to convince people that they are wrong.

But -- therein lies an opportunity.

From 2011-2021, Bitcoin achieved a 50,000x return -- going from $1 to $50k -- possibly the greatest ROI in the history of capitalism. Why? Well, it was due to two ingredients: [1] Bitcoin was a good idea, and [2] most people, were, for a long time **slow learners**. If people were fast learners, the BTC price would have jumped straight from $0 to its final destination, quickly. But, instead, people were slow learners -- which is how you could buy a whole Bitcoin for $1 in 2011.

Instead of reasoning with the ossifiers, we could join them -- join them in killing the BTC project. We simply make a new "BetterBitcoin", and sell BTC for that. The ossifiers should be happy to buy more BTC (since, according to them, BTC cannot lose). We might then be in a position to dump on them, and get that juicy, once-in-a-lifetime 50,000x return... *a second time*.

Of course, this would be much harder than it sounds. There would be many perils, such as: [1] failing to build a critical mass of supporters, before attempting the switch, [2] mis-coordinating the switch (due to infighting or sabotage or poor communication), and finally [3] risk of BTC copying "BetterBitcoin" later, after seeing its benefits. I published [some thoughts](https://www.truthcoin.info/blog/imex/) on this problem, back in 2018.

Ossifiers may have unwittingly solved the IMEX problem. Ordinarily, if a project is in decline (or near-death), then the dire circumstances will automatically trigger a creative search for new ideas. However, if a critical mass of ossifiers have gathered, this creativity will be *unable to implement* the solution. The project will be protected to death.

This is not without historical precedent. In fact, it is the usual way large organizations die. The famous book "The Innovators Dilemma" is entirely about how organizations remain laser-focused on pleasing their current customers, neglecting the "disruptive" innovation (which inevitably forces them into eventual bankruptcy).

Many corporations, empires, and even whole civilizations have been destroyed, due to ossification:

    [Easter Islanders] developed a complex Stone Age civilization, which suddenly collapsed
    over a millennium later. By some accounts there was starvation, war and perhaps cannibalism.
    The population fell to a small fraction of what it had been, and their culture was lost.
    ...The prevailing theory is that the Easter Islanders brought disaster upon themselves,
    in part by chopping down the forest which had originally covered most of the island.
    They eliminated the most useful species of tree altogether.
    ... 
    Of the hundreds of statues on the island, built over the course of several centuries,
    fewer than half are at their intended destinations. The rest, including the largest,
    are in various stages of completion, with as many as 10% already in transit on specially
    built roads. Again there are conflicting explanations, but, according to the prevailing
    theory, it is because there was a large increase in the rate of statue-building just
    before it stopped for ever. In other words, as disaster loomed, the islanders diverted
    ever more effort not into addressing the problem – for they did not know how to do that –
    but into making ever more and bigger (but very rarely better) monuments to their ancestors.
    And what were those roads made of? Trees.
    -David Deutsch, The Beginning of Infinity

Thus, if ossification has death-gripped the project, then the correct thing to do is make an alternative and jump ship. The ossifiers will automatically kill off the old project, all by themselves.

----

### Conclusion

A new cycle of "softfork debates" is upon us.

Unfortunately, progress has been slower than normal -- due to ossifiers. Most of these ossifiers are ignorant (for example, they do not know the difference between a hard and soft fork), and many of them argue that Bitcoin would be *better off* if the software performed *worse* (on dimensions such as privacy). Ossifiers balk at Altcoins, and are proudly indifferent to Altcoin's usage statistics (including total fees paid per day) and their welcoming attitude. 

We should reject these misguided ideas -- and treat them as the *superstitions* that they are. Trump cannot solve the Ukraine-Russia war, by throwing salt over his left shoulder. The sooner we reject naive forms of ossification, the sooner we can proceed to the more productive *Precedence Ossification* (which is in fact, what Bitcoin had during its 2011-2017 period).


----



## Appendix 1: The Filing Cabinet Analogy

    ‘here, you see, it takes all the running
     you can do, to keep in the same place.'
     -The Red Queen, "Through the Looking Glass"

### A. Email

Many software applications become *slower* over time, even on the same hardware (ie "ossified" hardware).

One example is email clients, which routinely become slow and eventually unusable.

![image](/images/slow-thunderbird.png)

I will take a moment to explain *why* this slowdown is inevitable -- by analogy.

### B. Physical Files

Imagine you work in a dentist's office -- you handle the medical files, which are physical sheets of paper in folders.

Part of your job is to create, store, retrieve, and update these files. At first, the dentist only has 2 clients -- so you can just leave both folders on your desk. It is very "fast" and easy to find the right file -- one second. One day, however, the dentist has their 6th client -- no matter -- you tidy the desk up, barely fit all 6 folders on there. But it is no longer as "fast" to find a file -- it takes 3 seconds, on average. There are 3x as many files and it takes 3x longer. This is called "linearity".

Eventually, however, your boss has 30 clients. Now your desk becomes over-cluttered. Folders are on top of other folders -- some are buried at the bottom of a big pile. If patients call and ask to reschedule, you must first move stacks around as you search for their file. (Gone are the 2-file days when you knew immediately which folder to pick up.) Since folders are moving, you often cannot rely on your memory of where a folder "was" or "usually is", you frequently need to sift through 15 or so, opening each in turn to see if it is right, before getting lucky and hitting the one you need. (While the patient is on the phone, annoyed at the wait.) In this part of the analogy, the desk is called "RAM". The folder-quantity has increase by 5x, but --because you sometimes get unluckly-- it can often take 30 seconds or more, to retrieve a given file. This is called "non-linearity" or "super-linearity".

Eventually, you have a bright idea: stack the folders horizontally, on a nearby shelf. Plus -- you label each folder's tab, with the patient's name. Now your desk is free. And you can scan your eyes along the row of tabs to find the right folder. Your speed is back up! Not as fast as the old 2-file days, nor the 6-file days, but now 10 seconds is enough to locate and retrieve a given folder. Even better, when the dentist adds 30 more clients (a total of 60), your speed only suffers a little bit -- 15 seconds. Your eyeball moves pretty fast -- faster than moving folders around.

The dentist, however, is still adding clients. One day he has over 1,000. Things are even worse now, than they were in the good ole "cluttered desk" days of 30-clients. Now it takes at least 2 minutes to find any file. There are just too many names that your eyeball has to travel over.

Then -- you have a 2nd bright idea: sort the files, and keep them always in alphabetical order. Not bad! It still takes 15 seconds to retrieve a file, but that's much better than 120. Plus -- even though the dentist steadily adds more clients (four-thousand, five-thousand, ...) your time steadily increases, but never catastrophically. This phenomenon is sometimes called "log-n scaling".

But I'm afraid misfortune is right around the corner. Eventually the dentist has 10-million clients. Furthermore, many of these share names -- 2500+ are named "Mohammad", others have very common last names ("Smith", "Johnson", "Cooper", "Williams") and common first names. It is the "shelf" problem all over again!

Finally, you have a 3rd idea: sort by alphabetical last name; then sort any ties by date-of-birth. You've done it again! ...for now. It still takes quite a while to find any particular file -- 3 minutes or so. But at least it is possible. Thanks to your valiant efforts.

But now there's a new problem. Recently, a lot of new clients have arrived whose last name starts with "M". And there isn't quite enough space in the M-section to squeeze them all in. Annoyed, you decide to work late one week -- physically moving the 4.9 million N-Z files over, to make more space in the M-section. First you move the Z files, then the Y files, then the X... Finally the files are all moved, and you have enough space for the new Ms, plus many more. But then -- next month there are lots of new clients with last name "B". You almost cry, as you realize the A-section is against the wall of the fileroom, and cannot be moved. You must come in again, and move twice as many files, the C-Z sections -- nearly all of them. Just to keep the system you have going. And you will have to keep doing this, forever!

But you have a 4th idea -- when sorting the folders to fit the new B-clients, intentionally leave large frequent periodic gaps, so that there is always new space for inserting new folders! Now you've finally solved it...

But eventually...

(And on and on and on...)

### C. Why the Problem is Inevitable

The important part of the analogy is the *human creativity* and *novelty* involved in solving each performance issue.

Always: the *problem* was **new** and the solution was *new*, as well. The 1st solution involved a "second desk" (ie shelf) specialized for storage. The 2nd involved tagging the files with an index and sorting them. The 3rd involved keeping the name-tag unchanged, but tracking something new "identical names" and sorting within this category based on a previously-ignored piece of info in the file (the DoB). The 4th solution involved intentional "blankness" into the file-room -- a concept which, previously, would have been a pure waste of space for no reason.

None of those issues were complex. Each fix was simple. (Any idiot would realize the need to sort the files alphabetically.) But each fix was *novel*.

But how is this related to software?

### D. Premature Optimization

Maybe, "good programmers" are just smart enough to "do it the right way" from the beginning? No. That concept is called "premature optimization" and [Legendary Computer Scientist Donald Knuth](https://en.wikipedia.org/wiki/Donald_Knuth) has remarked that this practice is ["the root of all evil"](https://softwareengineering.stackexchange.com/questions/80084/is-premature-optimization-really-the-root-of-all-evil). In practice it is difficult to know *what the source of the slowdown will be*. Unlike a physical filing system, software is very complex (and users are complex, and the world is complex) -- it is hard to know what the software will be used for (or if it will be used at all). The smart thing is to release the software first, and then monitor it for problems. Some problems may automatically take care of themselves (via faster hardware, for example; or via consumer education / more reasonable user expectations), others may not. In this sense, the *require future changes* are **unforeseeable**.

The naive ossificationists, would reject ideas 1 through 4 in the example above. Relatedly, they would arrogantly reject Knuth's advice -- since they presume that not only is premature optimization good, but that Bitcoin has already completed this good process and it is now over.

### E. More to the Email Analogy

Email was original a "protocol" -- but since that protocol had unfixed flaws (ie "ossification"), none of us today run our own email server. We all use a third party service (such as Gmail) -- who is spying on us and reading all of our messages (and who can control our ability to login to any website).

See [Lopp's presentation on this topic](https://blog.lopp.net/death-of-decentralized-email/).

### F. Applicability to Bitcoin

The Bitcoin blockchain continues to add 1008 new blocks, per week -- roughly 130 GB of data each year. This data can never be deleted, and must be stored forever -- and *served* to other nodes, forever. (Hence the data availability problem and the blocksize war -- and [the](https://www.youtube.com/watch?v=Y6kibPzbrIc) [perennial](https://www.youtube.com/watch?v=CqNEQS80-h4) [debates](https://jrakibi.medium.com/major-improvement-of-initial-block-download-ibd-fcc2a5921e3f) over how to handle the problem.) A perfect example of shifting sands that produce Code Rot.

----
