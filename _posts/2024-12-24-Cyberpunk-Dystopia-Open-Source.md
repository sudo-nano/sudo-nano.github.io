---
layout: post
title: "Critical Systems Must Be Open Source - How to Not Live in a Cyberpunk Dystopia #01"
date: 2024-12-24 20:40:00 -0000
tags: politics right-to-repair cyberpunk
category: Cyberpunk Dystopia
authors: [TheMagicalC, TuckerTwomey]
---
<!-- 
Editing Passes before completion: 2
Editing passes after completion:  2
-->
This is post #01 <!-- Edit this AND THE TITLE before posting -->
in a series about taking real, actionable steps to make real life less
of a cyberpunk dystopia. The premise of this series and the meaning of cyberpunk
dystopia are discussed
[in the first post.](https://sudo-nano.github.io/posts/Cyberpunk-Dystopia-00/)
This post is targeted towards a general audience. No prior knowledge is required.
If something is unclear, please refer to the footnotes or [contact me to ask for
clarification.](https://sudo-nano.github.io/about/)

> I always write out acronyms the first time they're used on each page, like this: \\
> `Problem Exists Between Chair and Keyboard (PEBCAK)` \\
> However, this article has *a lot* of acronyms, so I've added a new feature.
> Acronyms will now have alt text that can be viewed by putting your mouse over
> them, like so: <abbr title="Problem Exists Between Chair And Keyboard">PEBCAK</abbr>
{: .prompt-tip }

## Introduction
**Open source** is the idea of an object's design plans or software's source 
code being publicly available.
The terms for its use should also allow creation of derivative works, so that
people can improve upon it. 
For example, if Windows were open source, you would be able to create and
distribute an
alternate version (often called a "fork") where you remove Recall, the spyware
feature that nobody asked for. 
While there are many ideological reasons[^1] for supporting
open source hardware and software, this post will primarily cover the practical
reasons. Open source most often refers to software, but we will discuss both 
hardware and software.

"Critical systems" here means any systems whose failure is more likely than not
to cause serious injury (physical or otherwise) and/or loss of life. This definition
encompasses systems that would directly cause harm, such as killing a person via
failure of a medical device or autonomous vehicle. 
It also encompasses systems that would indirectly cause harm, such as the 
failure of a banking system preventing people from purchasing necessities, or 
supply chain failures preventing delivery of those necessities.

In my opinion, critical systems should be open source in order to promote
transparency and allow systems abandoned by the manufacturer to be maintained
by third parties. 

## Why Open Source?

Closed source (sometimes called proprietary) devices, have several problems:
1. They're nearly impossible to maintain if abandoned by the original developers.
(They become abandonware.)
2. Security research is severely hampered.
3. Accountability auditing, i.e. checking that a device works how the manufacturer says it does, is much harder.

Open source hardware and softare solves these problems in a variety of ways.

## Eliminating Abandonware
### What is abandonware?
**Abandonware** is hardware or software that is no longer being supported by the
manufacturer. For example, Windows XP's extended support by Microsoft was ended
on April 8, 2014. It no longer receives updates, with only a few rare exceptions
to patch the most serious security vulnerabilities.
Because Windows XP is no longer supported, most security vulnerabilities stay 
unpatched, so connecting Windows XP computers to the internet is not safe 
anymore.

### Losing compatibility with modern equipment
Another major consequence of abandonware is losing compatibility with current 
equipment.
As new hardware and software come out, existing devices must be updated to include
support for the new stuff. This happens on both the hardware and software level,
but tends to require more upkeep on the software level. For example,
older devices that only have dated interfaces like [FireWire](https://en.wikipedia.org/wiki/IEEE_1394)
or a [serial port](https://en.wikipedia.org/wiki/Serial_port) would
be difficult to connect to a modern device that only has USB. It could be done,
but would require an adapter that few places carry. These adapters are only available
because USB, most common serial interfaces, and FireWire are open standards: 
Their specifications are publicly available for free, so anyone can design a 
compatible device.

If your device uses
proprietary software, but the software is only compatible with an older OS like
Windows XP, then you're likely out of luck. There isn't anything as easy as a 
hardware adapter.
Unless you have an old machine running XP, or someone
has reverse engineered the software and built a new version that runs on your 
computer,
you have no way to use that device anymore. Reverse engineering by consumers is not something
that happens often, as it's time intensive and highly skilled work that few are willing
to do for free. In many cases, the EULA (End User License Agreement) or Terms of
Service (ToS) completely outlaw reverse engineering, allowing companies to sue people
who reverse engineer their equipment.[^2][^apple]

It's quite easy to see where this leads if these devices are controlling 
critical infrastructure.
If a piece of an old system dies, replacements are no longer available, and new
equipment isn't compatible, then you have to rip out the whole system and replace it at great expense. This will either lead to the intentional shutdown 
of critical systems while they are painstakingly rebuilt, or a dangerous 
condition where they continue running at reduced capacity.
The damage is multiplied if the system
maintainer in question is a municipal government or similar body that provides great benefit to citizens but operates on extremely thin margins.

When open source systems become unsupported, 3rd party maintainers step
in to make compatible replacement parts or continue development of the software.
Even if unofficial support is unacceptable to the company or government, it
provides a way to keep current systems running while an alternative is found.

### Planned obsolescence drives faster abandonment
Companies love the idea of forcing maintainers to prematurely purchase new 
systems, because it means maintainers have to give them more money.
Understandably, people who like their systems to work hate this. 
Corporations have historically hesitated to break compatibility, because 
intentionally sandbagging their own products generates bad PR. 
However, weak antitrust enforcement has allowed massive corporate mergers, 
creating market sectors governed by an **oligopoly.**

> **oligopoly** *(noun)* \\
> An economic condition in which a small number of sellers exert control over 
> the market of a commodity. ([Wiktionary](https://en.wiktionary.org/wiki/oligopoly]))

Under these conditions, customers have nowhere else to turn, and those 
companies are free to screw their customers
as hard as they want.[^3] There are no longer consequences for enacting planned
obsolescence to the extreme. 

<!-- Add section about medical hardware, including existing hardware and upcoming
such as Neuralink https://youtu.be/4Qz7rPxOExo?si=m9EjTLgu-t_hJCkC -->

### Example: Medical Hardware
Abandonware is not just a business problem. 
An increasing number of people are being uplifted by cutting edge medical
technology.
Bionic eyes enable blinded people to see again, pacemakers keep people's hearts 
pumping, and brain implants prevent dangerous seizures in epileptic 
patients. 
All of that can lose support at the whim of a corporation. It doesn't even need
to be intentional. 
Corporate insolvency can lead to inadvertent loss of support.
<!--
In fact, [this has already happened]
(https://futurism.com/neoscope/brain-implant-removed-consent) to the 
aforementioned epileptic patient, whose implant was removed *without her consent*
due to the company's financial failure. 
This is *unconscionably vile.*
-->
Improving people's quality of life is, in my opinion, the ultimate end.
No amount of money or claim to intellectual property could ever justify taking
that away from someone. 
The aforementioned bionic eyes 
[are now going blind](https://spectrum.ieee.org/bionic-eye-obsolete) 
because the company that supported them went under. <!-- Citation Needed -->
If the hardware and software for these devices was published, patients using
them would be able to maintain the devices themselves in order to keep their
vision. 
Critical medical equipment such as this should have its designs immediately
released into the public domain as part of bankruptcy proceedings.
Further, its intellectual property should be non-transferable when the company
is purchased, unless the purchasing company commits to maintaining its support.

## Assisting Security Research
<!--
Outline:
- Everyone benefits from security research
- Security research functions best as a preventative measure
- Touch on current state of security research
- Closed source means that security researchers can only do "black box" analysis
- "white box" analysis is more productive
- Open source exposes weak "security by obscurity"
-->

Security research involves discovering vulnerabilities in hardware or software,
informing the manufacturer, and allowing them to patch it before the researcher
discloses the details to the public.
Those not familiar with the process may wonder why you'd
*want* researchers to discover and publish vulnerabilities. 
The reason is that someone will discover it eventually, and we would rather 
have a researcher discover and disclose it responsibly before a malicious party 
can discover and exploit it. 
Well-resourced malicious parties, like intelligence services or organized 
criminal groups, stockpile exploits for use against their targets. 
Between these groups, there's a market for undisclosed vulnerabilities, 
referred to as 
zero-day vulnerabilities. Making it easier for legitimate security researchers to discover 
and disclose exploits will shrink exploit stockpiles and make their sale less profitable.

Unfortunately, not every company acts responsibly when a researcher
discloses a vulnerability to them. In 2008, security researchers reverse engineered 
the MIFARE Classic <abbr title="Radio Frequency IDentification">RFID</abbr>
credential[^4], which was at the time used for London's Oyster 
public transit cards. This revealed serious vulnerabilities in its cryptographic 
algorithm, demonstrating attacks that allow attackers to easily recover secret keys 
from the reader. NXP Semiconductors, the manufacturer of MIFARE Classic credentials, was sent an 
early notice so they could patch the vulnerabilities before publication of the
paper.[^5] Instead of fixing the
problem, NXP sued the university to prevent the researchers from publishing 
their paper. They requested an **injuction**, a court order that would
prevent publication of the research. 
The courts did not grant their injuction, and the research was published. 
This was an irresponsible prioritization of business interests over 
security, an attitude that any for-profit corporation has monetary incentive to take.[^shareholders]

The flaws in MIFARE Classic's cryptographic algorithm would have been glaringly
obvious upon mathematical examination. 
Had NXP open-sourced their algorithm, its weakness might have been spotted 
before it was widely adopted. 
Better yet, their anticipation 
of the scrutiny might have compelled them to design a more secure algorithm. 
MIFARE Classic was so popular at the time that it remains the most widely used 
RFID credential by pure inertia, despite having been broken repeatedly over the
past 14 years.[^mfc1][^mfc2][^mfc3][^mfc4]
In fact, the original draft of this post mentioned a 3rd party "static 
encrypted nonce"
variant that researchers had not yet cracked. During the writing of this post, 
researchers discovered a manufacturer backdoor hidden in the new variant.[^mfc_sen] 
Worse still, RFID credentials implement their cryptographic algorithms in
hardware, so these vulnerabilities cannot be patched except by replacing every
vulnerable credential in circulation. 

Coverage of security research often paints a dichotomy between the evil "black 
hat hacker" and the virtuous "white hat hacker". As with most dichotomies, 
reality is more complicated. 
Some paint the image that white hat hackers stay entirely 
within the law, but this is becoming much more difficult as companies employ 
aggressive 
intellectual property protection laws and 
<abbr title="End User License Agreements">EULAs</abbr> 
that make established research practices illegal. 
Any law that bans reverse-engineering is guilty of this, 
but the most egregious is the Digital Millenium Copyright Act (DMCA).[^6] 
It bans reverse engineering and bypassing of Digital Rights Management (DRM)
software and other software used to encrypt copyrighted media. 
Because of this, security research on proprietary software carries greater 
legal risks than ever, which wouldn't be an issue if the software
was open source.

## Accountability Auditing
<!--
Outline:
- Auditing claims about closed source software can only be done by reverse engineering 
- Reverse engineering is potentially illegal under the service's EULA or the DMCA 
- Are you starting to see a theme here with the DMCA
-->
When a product is advertised to contain some substance or meet some 
specification, it's usually pretty easy to verify that it does. 
Lab tests can ensure that your
food isn't full of lead,[^7] emissions tests can verify that your car meets 
environmental requirements, etc. When the product involves software, it becomes 
harder to verify, especially if the software isn't run on your personal 
computer.
Amazon can claim that their smart home devices don't spy on you, but unless you
have the personal expertise to inspect the electronics and software of the
device, you have no way to actually verify this claim. 

Even if you have the skills to verify this claim, there's a catch: 
Reverse engineering can run afoul of the 
<abbr title="Terms of Service">ToS</abbr>, 
<abbr title="End User License Agreement">EULA</abbr>, 
<abbr title="Digital Millenium Copyright Act">DMCA</abbr>, 
or Electronic Communication Privacy Act.
At this point, forbidding reverse engineering is standard boilerplate for any 
service. Here are some high profile examples: 

> You also may not reverse engineer or decompile our software or services, 
> attempt to do so, or assist anyone in doing so, unless you have our written 
> consent or applicable law permits it. ([Discord](https://discord.com/terms))

> You can’t modify, translate, create derivative works of, or reverse engineer 
> our products or their components. ([Instagram](https://help.instagram.com/581066165581870/))

If you want to verify that these services actually abide by their own privacy
policies, you legally can't! If you reverse engineer something
when the <abbr title="Terms of Service">ToS</abbr> or 
<abbr title="End User License Agreement">EULA</abbr> prohibit it, you may be 
civilly liable. (That's legal speak for "the company can sue the living 
daylights out of you.")

When fully contextualized, it becomes obvious how ridiculous this is. Often, 
these services send code to your browser. The code exists on your computer, and
yet is illegal to read. How ridiculous would it be for a car dealership to tell
you that it's illegal to do maintenance work on your own car? What if I sold you
a painting, but said it was illegal to get it verified as genuine rather than a
forgery? This is where we are in the tech space. The internet, in its infancy,
is not yet well regulated, and tech companies will take advantage of it until
we fix it.

### Aside: Algorithmic Decision Making
**Algorithmic decision making** is the use of a computer algorithm to make
decisions. 
These range from the algorithms that control which social media posts you see
to automated employment screening programs that can accept or reject you for a 
job. 
Use of algorithmic decision making has exploded in popularity, especially with
the recent Large Language Model (LLM) craze. 
Between the aforementioned automated employment screening and things like 
[United Health Care's alleged automatic denial algorithm](https://arstechnica.com/health/2023/11/ai-with-90-error-rate-forces-elderly-out-of-rehab-nursing-homes-suit-claims/), 
<!-- Citation Needed -->
computers are already making major decisions in people's lives. 
Most of these algorithms are completely opaque. 
Companies are not required to disclose how they work, since it's a "trade 
secret". 
It's difficult to know whether this algorithm is acting maliciously or 
discriminating against protected groups. 
Researchers can always use "black box analysis", where they treat the algorithm
as a "black box" with invisible insides, and only analyze the relationship
between the input and output. 
However, in the event of undesirable algorithmic behavior (which, I would like
to remind the reader, could involve someone losing their job or being killed by
an autonomous vehicle), black box analysis provides little insight into the root
cause. 
This is another extremely complex topic that requires its own article, which I
will write at a later date.
For now, my position is the following: 
- Computers cannot be held accountable, and thus must not make decisions. They should only serve to assist humans in making decisions. 
- Use of algorithmic decision making should require a huge, brightly colored disclosure banner. 
- Companies should be required to undergo annual testing to ensure that their algorithm is free of discrimination. 
- Companies found to be willfully using discriminatory algorithms should receive a legal injunction barring them from using algorithmic decision making.

## What can you do about it? 

### Policy Reform
A few reforms must be made to existing policy: 
- Anti-circumvention language must be removed from the <abbr title="Digital Millennium Copyright Act">DMCA</abbr>, since they prevent accountability auditing and right to repair.
- Ideally, anti-reverse engineering clauses should be made legally unenforceable. This is likely to face strong opposition, so it might work better to provide a specific exception for right to repair. 

Some new policies must be passed as well: 
- Right to repair bills that require parts to be made available 
- We need intellectual property law that allows IP for critical infrastructure to become public domain before the normal expiration period if abandoned
- Federal Anti-SLAPP laws need to be passed to prevent legal harassment by big corporations.

The gold standard would be a federal right to repair bill. I suspect that's a
long way off, but individual states are passing right to repair bills, so
there's hope. 
If you want it to happen faster, *call your representatives!* Call your senator
and representative, and call your state assembly members to get state right to
repair bills passed in as many states as possible. While calling may not seem
effective, very few people do it, so it makes your opinion stand out. 

Right to repair bills have already been passed in a few states. 
In March 2024, [Oregon passed a right to repair bill](https://www.theverge.com/2024/3/27/24097042/right-to-repair-law-oregon-sb1596-parts-pairing-tina-kotek-signed)
banning parts pairing, the practice of putting computers in parts so that a 
device can refuse to function when third party parts are installed. 
([Link to text of the law](https://olis.oregonlegislature.gov/liz/2024R1/Downloads/MeasureDocument/SB1596/Enrolled))
In October 2023, [California passed a law](https://www.theverge.com/23910066/right-to-repair-law-newsom-california-sb-244)
 requiring repair parts, tools, 
software, and documentation to be made available for 7 years for products priced
$100 or more.
Similar laws are in place in New York, Colorado, and Minnesota, according to
the above article from The Verge. 
Unfortunately, some of these laws have exceptions for some industries with 
strong anti-repair lobbies. 
[Oregon's bill has exceptions](https://www.ifixit.com/News/92144/oregon-just-struck-a-blow-to-parts-pairing-and-won-a-decade-of-repair-support)
for medical devices, farm equipment, anything that runs on an internal
combustion engine (ICE), and video game consoles. 
There's no logic involved in these carve-outs. 
If the goal was to exclude devices perceived as more frivolous, like game
consoles, then medical devices and farm equipment have no place on the list.
If the goal was to exclude devices that could injure someone if improperly 
repaired, such as medical equipment, farm equipment, and ICE vehicles, then
game consoles have no reason to be an exception. 
Still, Oregon's right to repair bill is the first to ban parts pairing, which
is a massive victory.


### Convince Decision Makers
Right to repair is good for businesses as well. Decision makers in corporate and
government positions should be made aware that repairable equipment reduces their long-term operating costs. 
In an age where shareholders pressure companies to
tear the wiring out of the walls in the name of increasing quarterly profits,
and then 
[cut costs by laying off 15% of the workforce](https://www.theverge.com/2024/8/1/24210656/intel-is-laying-off-over-10000-employees-and-will-cut-10-billion-in-costs),
Investing in equipment that will be maintained instead of thrown out keeps you 
ahead of the game. 

Decision makers negotiating for massive contracts have the leverage to ask
manufacturers for more durable and repairable hardware. Even if the manufacturer
can't improve the hardware for you during this contract cycle, expressing 
interest shows them they should be prioritizing it for the next cycle.


### Buy Repairable Hardware 
Experimental hardware becomes mainstream when it's popularized by *enthusiasts*:
hobbyists with the time to help developers work out the kinks. 
If you have the time, money, and expertise to try out experimental hardware, 
please do! 

- [Fairphone makes a modular repairable phone.](https://www.fairphone.com/) The entire phone is composed of user-replaceable modules, including the battery. 
- Fairphone also makes [earbuds with replaceable batteries!](https://shop.fairphone.com/fairbuds) These are especially exciting, because [AirPods are notoriously unrepairable.](https://www.ifixit.com/News/66194/apples-new-airpods-are-telling-users-to-replace-the-batteries-already-too-bad-thats-impossible)
- Framework makes a laptop composed of user-replaceable modules. Each of the ports on the side is also a module that can be swapped and customized. 

## Conclusion 
To live in a world that's person-first instead of profits-first, systems that
lives depend on must be open source in order to provide true accountability
and prevent quality of life regressions. 
Open-sourcing these systems also prevents for-profit planned obsolescense of
life saving equipment, a practice already being paid for in lives.
These problems are not hypothetical, they're already here, and people are
already working towards fixing them. 



## Footnotes

[^1]: [https://en.wikipedia.org/wiki/GNU_Manifesto](https://en.wikipedia.org/wiki/GNU_Manifesto)
[^2]: Regardless of whether the lawsuits actually have merit, having to fend them off can completely exhaust the money and resources of an individual or small group. This is especially true when the plaintiff (person filing the lawsuit) has a lot more money than the defendant. For more on this, read about [SLAPP lawsuits.](https://en.wikipedia.org/wiki/Strategic_lawsuit_against_public_participation) Some states have Anti-SLAPP laws, but the US has no federal anti-SLAPP laws. 
[^apple]: Apple has even leveraged intellectual property law to [make customs seize genuine parts](https://www.vice.com/en/article/dhs-seized-aftermarket-apple-laptop-batteries-from-independent-repair-expert-louis-rossman/) that were resold 3rd party, in order to prevent 3rd party repair. (This remains a footnote because thorough coverage of intellectual property law is outside the scope of this post. It will be covered in a subsequent post.)
[^3]: This statement applies primarily to the United States, which has fallen behind in antitrust enforcement and consumer protection laws since the Reagan administration.
[^4]: [Nohl et. al., "Reverse Engineering a Cryptographic RFID Tag."](https://www.cs.virginia.edu/~evans/pubs/usenix08/usenix08.pdf) USENIX Security Symposium. San Jose, CA. 31 July 2008.
[^5]: [https://www.secureidnews.com/news-item/nohl-nxp-making-terrible-decision/#](https://www.secureidnews.com/news-item/nohl-nxp-making-terrible-decision/#)

[^shareholders]: This is part of a broader trend of companies attempting to smite anything that has the smallest chance of displeasing shareholders. It's a symptom of late stage capitalism, which I intend to cover at an introductory level later in this series. 

[^6]: In-depth coverage of the DMCA is a complicated topic and deserving of its own article. It is the opinion of this blog that the DMCA allows for overly-aggressive policing of intellectual property in a way that is detrimental to the general public, however it does provide the essential function of protecting website hosters from liability for their users uploading copyrighted content.
[^mfc1]: [Garcia et. al., "Dismantling MIFARE Classic."](https://www.sos.cs.ru.nl/applications/rfid/2008-esorics.pdf)
[^mfc2]: [Garcia et. al., "Wirelessly Pickpocketing a Mifare Classic Card."](https://www.cs.umd.edu/~jkatz/security/downloads/Mifare3.pdf) 30th IEEE Symposium on Security and Privacy, 2009.
[^mfc3]: Koning Gans, Gerhard de. Outsmarting Smart Cards. [S.l., Nijmegen: s.n.]; UB Nijmegen [host], 2013.
[^mfc4]: Meijer, Carlo, and Roel Verdult. “Ciphertext-Only Cryptanalysis on Hardened Mifare Classic Cards.” In Proceedings of the 22nd ACM SIGSAC Conference on Computer and Communications Security, 18–30. Denver Colorado USA: ACM, 2015. https://doi.org/10.1145/2810103.2813641.

[^mfc_sen]: [Teuwen, Philippe. “MIFARE Classic: Exposing the Static Encrypted Nonce Variant,”](https://blog.quarkslab.com/mifare-classic-static-encrypted-nonce-and-backdoors.html) Quarkslab's Blog, 20 August 2024.
[^7]: Lead testing is a notable example because at-home test kits are usable by the layperson.


