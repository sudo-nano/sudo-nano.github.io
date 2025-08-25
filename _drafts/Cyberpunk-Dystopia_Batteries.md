---
layout: post
title: "Batteries are maintenance items - How to Not Live in a Cyberpunk Dystopia #02"
date: 2024-01-21 16:00:00 -0700
tags: politics right-to-repair cyberpunk electronics
category: drafts
category: Cyberpunk Dystopia
hidden: true
--- 

This is post #02 in a series about what we can do to make real life less 
of a cyberpunk dystopia. The first post is 
[here.](https://sudo-nano.github.io/posts/Cyberpunk-Dystopia-00/) 
This post is targeted towards a general audience. No prior knowledge is required. 
If something is unclear, please refer to the footnotes or 
[ask me for clarification.](https://sudo-nano.github.io/about/)
I don't bite, unless you want me to.


## Introduction

Portable electronics, because of their newness, exist in a sort of cultural 
limbo: 
They're completely pervasive in everyday life, yet we have little to no 
generational knowledge about their care and maintenance. 
This is in part because they've only existed for about one generation, but in 
equal part by the design of manufacturers through planned obsolescence.
In this post, we'll cover how batteries work, which ones are in your devices,
why we need replaceable batteries, and how getting there is well within our 
reach.

## Battery Basics

### How does a battery work? 
Batteries, at their most basic, perform a chemical reaction to generate 
electricity. 
The chemicals involved in this reaction, as well as whether it's reversible, 
depend on the type of battery. 
In rechargeable batteries, such as nickel-cadmium (often abbreviated Ni-Cd)
and lithium-ion batteries, this reaction is reversible.[^dislit]
In non-rechargeable batteries, such as alkaline batteries
(AA, AAA, C, D, 9V, and most button batteries), the reaction is not reversible.

Lithium batteries are notable for their high power density, meaning smaller 
batteries can store lots of energy, and high discharge rate, meaning they can 
release their power quickly. 
The trade off is that their electrolyte, the solution in which the reaction takes
place, is flammable. This means damaged lithium 
batteries can catch fire and explode violently, something that other types of 
batteries (like disposable alkaline AA batteries or lead-acid car batteries) don't do.
Different types of lithium-ion batteries are optimized for different applications.
Lithium-polymer batteries, which look like a capri sun and live in devices like your
phone, are optimized for power density. People often abbreviate these as LiPo.

<img src="{{site.url}}/assets/cyberpunk_dystopia/lipo.jpg" alt="A small rectangular silver battery, with printing that says LiPo battery 3.7V LP401522 100mAh Made in China.">
*Figure 1: A small 3.7V 100mAh LiPo*

There's not a lot of space in your 
portable electronics, so most of them try to pack as much power in as possible, 
with the trade off that you can't discharge it all at once unless you want your
phone to do its best Galaxy Note 7 impression.
On the other hand, standard size cylindrical cells, such as 18650s and 21700s,
are optimized for higher *discharge rates.* That means they can let out more
of their power at once. Consumer devices rarely have you handle individual cells
directly,
but most people have handled battery packs with these inside. They power portable 
devices with higher current demands. Drills, older laptops, and high-end lightsabers
tend to use 18650s. Even larger devices, like ebikes and electric cars, use hundreds
of 21700s stuck together into a single massive battery pack.

<img src="{{site.url}}/assets/cyberpunk_dystopia/18650.jpg" alt="A cylindrical blue 18650 battery with a ">
*Figure 2: An 18650 battery*

### How do batteries age?
Over time and recharge cycles, batteries degrade. 
Their capacity and maximum current output decrease as the battery degrades.
You've probably noticed capacity degradation when your phone or laptop don't
last as long between charges.
Decreases in maximum current output are harder to notice, and are
only obvious on devices that perform mechanical work. For example, you may
notice that your drill doesn't output as much torque when used with older
battery packs.
On your drill, that's not much of a problem. Just go to your local hardware
store and buy a new battery. 
When the battery on your phone gets old, you have to take it into the shop
so someone can peel apart your computer sandwich and insert a new battery.
You *can* do this at home, but it requires phone-specific repair tools
and sometimes soldering equipment.
That sucks! Replacing your car battery at home can be done with some basic
tools, why not your phone? We'll get to that in the next section.

## How did we get here? 

### Planned Obsolescence
> **planned obsolescence** (noun)
> (also called built-in obsolescence or premature obsolescence) a policy of planning or designing a product with an artificially limited useful life or a purposely frail design, so that it becomes obsolete after a certain pre-determined period of time upon which it decrementally functions or suddenly ceases to function, or might be perceived as unfashionable. ([Wikipedia](https://en.wikipedia.org/wiki/Planned_obsolescence))

In contrast to something like cars, where maintenance practices are well-known 
and parts are intended to be replaced by a user or mechanic, many portable 
electronics are designed so that the battery is unserviceable. 
This is most often seen in phones, e-readers, wireless headphones, and thin laptops.
Often, the device is not meant to be opened for any 
maintenance at all, or the battery is installed in such a way that removing 
it could be unsafe. For example, Apple's airpods are 
[among the least repairable](https://www.vice.com/en/article/airpods-are-a-tragedy/)
products out there. They're glued together, and there's no safe way to open them
without risking puncturing the battery and starting a fire. 
iFixit, a website dedicated to teaching users how to repair their own devices,
[rates them 0/10](https://www.ifixit.com/Device/AirPods) on repairability.
This wasteful design is similar in principle to throwing out your car instead of
changing its oil, because the manufacturer has made it so you must cut into
your engine to change the oil.

Their incentive to do this is nothing but profit.
The sooner your device's battery life becomes unreasonably short, the sooner you
have to buy a new one. 

Besides the obvious detriment of manufacturers 
wringing more money out of consumers for shorter device lifetimes, e-waste is more 
harmful to people and the environment than traditional garbage. 

> Electronic scrap components, such as CPUs, contain potentially harmful materials 
> such as lead, cadmium, beryllium, or brominated flame retardants. Recycling and 
> disposal of e-waste may involve significant risk to the health of workers and 
> their communities.[^2] ([Wikipedia](https://en.wikipedia.org/wiki/Electronic_waste#Definition))

## How do we get out of here?
### The Road is Already Paved
Making batteries easily replaceable to mitigate these issues is not necessarily easy, but
it's well known how to do it, and it's no harder than design challenges that these companies
face every day.
All a manufacturer has to do is
1. Connect the battery with a connector rather than soldering it directly to the board
2. Secure the battery in a way that allows removal without damaging the battery
3. Construct the device so that the battery can be accessed easily

This used to be the standard for smartphones. Older Samsung flagship 
phones such as the Samsung Galaxy 5 had removable batteries. 
In the 10 years since its release, manufacturers have realized that charging 
consumers to service their batteries is much more profitable. 
[This Mashable article](https://mashable.com/article/why-phones-cant-have-removable-batteries-anymore)
claims that removable batteries are never coming back, because people prefer having 
water and dust resistance to having removable batteries. Hidden in this article is
a false dichotomy: you can have both! The [Fairphone 5](https://shop.fairphone.com/fairphone-5)
proves it, being a fully modular and repairable phone with a removable battery while
still achieving an IP55 rating.[^3]

While the Fairphone doesn't quite achieve the full immersion protection that many
flagship phones have these days, this problem was solved long ago by Yaesu, a
company that makes amateur radio equipment. Their VX line of handheld radios 
are ruggedized
and fully submersible, while having easily replaceable batteries that can be
swapped in seconds. These have been around so long that two of the 3 models from this 
line are now discontinued. I have a VX-8DR, and I clipped it to my belt
so I could play radio while surfing in Hawaii. That's how waterproof it is.
Companies that manufacture phones,
who have orders of magnitude more money than Yaesu, can surely figure it out.
They most definitely could have researched thinner waterproof connectors by now
if they wanted to, so let's say it like it is: they chose not to do it.

### Standard Sized Lithium Cells for Big Boi Projects

For devices that draw more current than LiPo batteries can supply, we have standard
size cylindrical lithium cells. The most common of these are the 18650 and its larger
sibling the 21700. These are already ubiquitous, but in less consumer facing ways
than alkaline batteries. 18650s are often used as one or two cells in compact hobbyist
electronics, such as in high quality toy lightsabers and powerful flashlights.
21700s are also used in these applications, but more often are spot welded together
into larger battery packs for high power applications like drill batteries and electric
vehicles. Electric scooters and electric cars are both poweredby these, but in different
cell arrangements. Your incompatible drill batteries are all the same on the inside! 
Drill battery incompatibility has always been bullshit, but power tool companies love
the brand lock-in.

Hobbyists have been living in a beautiful world of semi-standardized interchangeable
batteries for some time now, and there's very little reason this can't be the case for
all electronics. I want to live in that world.

## Appendix: Terminology Pedantry
Coming from my amateur radio background, I typically make the distinction
between *portable* and *mobile.* Portable typically means something that can be
moved and set up in another location, but not used while in transit. 
Mobile typically means something can be operated while moving, like a transceiver
in a car. Since this post is targeted towards the layperson, and there are very few
battery powered consumer electronics that cannot be used in transit, I've thrown
out that distinction to ensure it doesn't confuse new readers.

## Footnotes
[^dislit]: There also exist disposable lithium batteries. These are mostly 3V coin cells, but in the past few years disposable lithium AA and AAA batteries have entered the market.

[^1]: **Planned obsolescence** (also called built-in obsolescence or premature obsolescence) is a policy of planning or designing a product with an artificially limited useful life or a purposely frail design, so that it becomes obsolete after a certain pre-determined period of time upon which it decrementally functions or suddenly ceases to function, or might be perceived as unfashionable. ([Wikipedia](https://en.wikipedia.org/wiki/Planned_obsolescence))

[^2]: Perkins, Devin N, Marie-Noel Brune Drisse, Tapiwa Nxele, Peter D. Sly. 2014. "E-Waste: A Global Hazard". *Annals of Global Health*. [https://doi.org/10.1016%2Fj.resconrec.2008.03.002](https://doi.org/10.1016%2Fj.resconrec.2008.03.002) (Citation carried over from Wikipedia blockquote)

[^3]: IP stands for ingress protection. The first number is a dust protection rating. A 5 in dust protection means that a small amount can get in, but not enough to interfere with the function of the device. The second number is a liquid protection rating. A 5 in liquid protection indicates protection against "water jets", but not immersion. Basically, it can get more than rained on and still walk away.
