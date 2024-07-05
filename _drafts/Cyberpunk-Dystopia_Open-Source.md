---
layout: post
title: "Critical Systems Must Be Open Source - How to Not Live in a Cyberpunk Dystopia #01"
date: 2024-01-24 16:00:00 -0700
tags: politics right-to-repair cyberpunk
category: drafts # Change this before publication
#category: Cyberpunk Dystopia
hidden: true # delete this before publication
authors: [TheMagicalC, TuckerTwomey]
---
This is post #01 <!-- Edit this AND THE TITLE before posting -->
in a series about what we can do to make real life less
of a cyberpunk dystopia. The first post is
[here.](https://sudo-nano.github.io/posts/Cyberpunk-Dystopia-00/)
This post is targeted towards a general audience. No prior knowledge is required.
If something is unclear, please refer to the footnotes or [contact me to ask for
clarification.](https://sudo-nano.github.io/about/)

## Introduction
**Open source** is the idea of an object's design plans or software's source code
being publicly available. While there are many ideological reasons[^1] for supporting
open source hardware and software, this post will primarily cover the practical
reasons. While open source most often refers to software, we will discuss both hardware
and software.

"Critical systems" here means any systems whose failure would more likely than not
to cause serious injury (physical or otherwise) and/or loss of life. This definition
encompasses systems that would cause direct harm, such as the failure of a medical
device or autonomous vehicles that would kill a person. It also encompasses systems that
would cause indirect harm, such as the failure of a banking system preventing people
from accessing money needed to purchase necessities, or supply chain failures
preventing delivery of those necessities.

## Why Open Source?

Closed source (sometimes called proprietary) devices, have several problems:
1. They're nearly impossible to maintain if abandoned by the original developers.
(They become abandonware.)
2. Security research is severely hampered.
3. Accountability auditing, i.e. checking that the devices work how the manufacturer
says they do, is much harder.

### Eliminating Abandonware
**Abandonware** is hardware or software that is no longer being supported by the
manufacturer. For example, Windows XP's extended support by Microsoft was ended
on April 8, 2014. It no longer receives updates, with only a few rare exceptions
to patch the most serious security vulnerabilities.
Because Windows XP is no longer supported, most security vulnerabilities stay unpatched,
so connecting Windows XP computers to the internet is not safe anymore.


Another major consequence of abandonware is losing compatibility with current equipment.
As new hardware and software come out, existing devices must be updated to include
support for the new stuff. This happens on both the hardware and software level,
but tends to require more upkeep on the software level. For example,
older devices that only have dated interfaces like [FireWire](https://en.wikipedia.org/wiki/IEEE_1394)
or a [serial port](https://en.wikipedia.org/wiki/Serial_port) would
be difficult to connect to a modern device that only has USB. It could be done,
but would require an adapter that few places carry. These adapters are only available
because USB, most common serial interfaces, and FireWire are open standards: Their
specifications are publicly available for free, so anyone can design a compatible device.
If your device uses
proprietary software, but the software is only compatible with an older OS like
Windows XP, then you're likely out of luck. There isn't anything as easy as a hardware
adapter.
Unless you have an old machine running XP, or someone
has reverse engineered the software and built a new version that runs on your computer,
you have no way to use that device anymore. Reverse engineering is not often something
you can rely on, as it's time intensive and highly skilled work that few are willing
to do for free. In many cases, the EULA (End User License Agreement) or Terms of
Service completely outlaw reverse engineering, allowing companies to sue people
who reverse engineer their equipment.[^2]

Reverse engineering is extremely time
intensive and highly skilled work. In many cases, the EULA (End User License Agreement)
or Terms of Service will outlaw reverse engineering, so even if it's viable, it's not legal.

It's quite easy to see where this leads if these devices are controlling critical infrastructure.
If a piece of an old system dies, replacements are no longer available, and new
equipment isn't compatible, then you have to rip out the whole system and replace
it at great expense. This will either lead to the intentional shutdown of critical
systems while they are painstakingly rebuilt, or a dangerous condition where they
are inoperable but users are not informed. The damage is multiplied if the system
maintainer in question is a municipal government or similar body that provides great
benefit to citizens but operates on extremely thin margins.

Companies love the idea of forcing maintainers to prematurely purchase new systems,
because it means maintainers have to give them more money.
Understandably, people who like their systems to work hate this. Corporations
have historically hesitated to break compatibility, because intentionally sandbagging
their own products generates bad PR. However, recent conglomeration
of companies due to weak antitrust enforcement means that their customers often
have nowhere else to turn, so those companies are free to screw their customers
as hard as they want.[^3]

Requiring critical systems to be open source means that if those systems are abandoned,
the people that use them can step in to maintain them, preventing otherwise
inevitable disruption of important infrastructure. It provides more reliable infrastructure
and a check against the tightening grip of capitalism.

<!-- Add section about medical hardware, including existing hardware and upcoming
such as Neuralink https://youtu.be/4Qz7rPxOExo?si=m9EjTLgu-t_hJCkC -->


### Assisting Security Research
<!--
Outline:
- Everyone benefits from security research
- Security research functions best as a preventative measure
- Touch on current state of security research
- Closed source means that security researchers can only do "black box" analysis
- "white box" analysis is more productive
- Open source exposes weak "security by obscurity"
-->

Security research most often involves discovering vulnerabilities in hardware or software,
informing the manufacturer, and allowing them to patch it before the researcher
discloses the details to the public.
Those not familiar with the process may wonder why one would
*want* researchers to discover and publish vulnerabilities. The reason is that someone
will discover it eventually, and we would rather have a researcher discover and
disclose it responsibly before a malicious party can discover and exploit it. 
Well-resourced malicious parties, like intelligence services or organized criminal 
groups, stockpile exploits (usually undisclosed ones) for use against their targets. 
Between these groups, there's a market for undisclosed (usually referred to as zero-day)
vulnerabilities. Making it easier for legitimate security researchers to discover 
exploits, and making it easier for them to publish without fear of legal consequences, 
will shrink stockpiles of exploits and make discovering exploits for sale less profitable.

Unfortunately, not every company acts responsibly when a researcher
discloses a vulnerability to them. In 2008, security researchers reverse engineered 
the MIFARE Classic RFID credential[^4], which was at the time used for London's Oyster 
public transit cards. This revealed serious vulnerabilities in its cryptographic 
algorithm, demonstrating attacks that allow attackers to easily recover secret keys 
from the reader. NXP, the manufacturer of MIFARE Classic credentials, was sent an 
early copy so that they could patch the vulnerabilities.[^5] Instead of doing so, NXP 
attempted to sue the university to prevent the researchers from publishing their 
paper. The courts did not grant their injuction, and the research was published. 
However, this response shows a concerning prioritization of business interests over 
security, an attitude that any for-profit corporation has monetary incentive to take.

The flaws in MIFARE Classic's cryptographic algorithm would have been glaringly
obvious upon mathematical examination. Had NXP open-sourced their algorithm, it might
not have been so widely adopted because of its weakness. Better yet, their anticipation 
of the scrutiny might have compelled them to design a more secure algorithm. 
At the time, MIFARE Classic was so widely used that we are still not rid of it. 
While there 
are variants that have been patched to fix the original vulnerabilities, original 
and completely exploitable versions are still circulating widely in the wild. 

Coverage of this sort of issue often paints a dichotomy between the evil "black hat
hacker" and the virtuous "white hat hacker". As with most dichotomies, reality
is more complicated. Some paint the image that white hat hackers stay entirely within
the law, but this is becoming much more difficult as companies employ aggressive 
intellectual protection laws and End User License Agreements (EULAs) that make established 
research practices illegal. Any law that bans reverse-engineering is guilty of this, 
but the most egregious is the Digital Millenium Copyright Act (DMCA).[^6] It bans 
reverse engineering and bypassing of Digital Rights Management (DRM) software and
other software used to encrypt copyrighted media. Because of this, security research 
on proprietary software carries greater legal risks than ever, something mitigated by
making software open source. 

### Accountability Auditing
<!--
Outline:
- Auditing claims caused by 
-->

## Footnotes

[^1]: [https://en.wikipedia.org/wiki/GNU_Manifesto](https://en.wikipedia.org/wiki/GNU_Manifesto)
[^2]: Regardless of whether the lawsuits actually have merit, having to fend them off can completely exhaust the money and resources of an individual or small group. This is especially true when the plaintiff (person filing the lawsuit) has lots of money, like Apple. For more on this, read about [SLAPP lawsuits.](https://en.wikipedia.org/wiki/Strategic_lawsuit_against_public_participation)
[^3]: This statement applies primarily to the United States, which has fallen behind in antitrust enforcement and consumer protection laws since the Reagan administration.
[^4]: [Garcia et al., “Dismantling MIFARE Classic.”](https://www.sos.cs.ru.nl/applications/rfid/2008-esorics.pdf)
[^5]: [https://www.secureidnews.com/news-item/nohl-nxp-making-terrible-decision/#](https://www.secureidnews.com/news-item/nohl-nxp-making-terrible-decision/#)
[^6]: In-depth coverage of the DMCA is a complicated topic and deserving of its own article. It is the opinion of this blog that the DMCA allows for overly-aggressive policing of intellectual property in a way that is detrimental to the general public, however it does provide the essential function of protecting website hosters from liability for their users uploading copyrighted content.

## Credits
