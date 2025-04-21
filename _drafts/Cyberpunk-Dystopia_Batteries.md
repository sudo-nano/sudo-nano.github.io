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
What this reaction is, as well as whether it's reversible, depend on the type of 
battery. 
Alkaline batteries, such as AA, AAA, C, and D batteries, are typically non-rechargeable.
Electronics with built-in rechargeable batteries use either lithium-ion batteries or
nickel-cadmium (often abbreviated Ni-Cd) batteries.
Lithium batteries utilize dissolved lithium to perform a reversible reaction to 
store or release charge. 
<!-- TODO: Find a citation for how lithium batteries work -->

Lithium batteries are notable for their high power density, meaning smaller 
batteries can store lots of energy, and high discharge rate, meaning they can 
release their power quickly. 
Usually, a battery is optimized for one of the above, not both. 
Lithium batteries can also be dangerous because their electrolyte, the solution
in which the metal is dissolved, is flammable. This means damaged lithium 
batteries can catch fire and explode violently, something that other types of 
batteries (like disposable alkaline AA batteries or lead-acid car batteries) don't do.

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
[rates them 0/10](https://www.ifixit.com/Device/AirPods) on repairability
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
swapped in seconds. These have been around so long that the VX-8 from this line 
is now discontinued. I have one, and I clipped it to my belt
so I could play radio while surfing in Hawaii. Companies that manufacture phones,
who have orders of magnitude more money than Yaesu, can surely figure it out.


### Standard Sized Lithium Cells for Big Boi Projects
Outline of this section:
- 18650s and 21700s are fantastic
- Manufacturers already know how fantastic they are, and routinely package these inside proprietary packs
- Drill battery incompatibility is bullshit, and they're already using these
- Hobbyists already use these (flashlights, lightsabers, EVs)

## Footnotes

[^1]: **Planned obsolescence** (also called built-in obsolescence or premature obsolescence) is a policy of planning or designing a product with an artificially limited useful life or a purposely frail design, so that it becomes obsolete after a certain pre-determined period of time upon which it decrementally functions or suddenly ceases to function, or might be perceived as unfashionable. ([Wikipedia](https://en.wikipedia.org/wiki/Planned_obsolescence))

[^2]: Perkins, Devin N, Marie-Noel Brune Drisse, Tapiwa Nxele, Peter D. Sly. 2014. "E-Waste: A Global Hazard". *Annals of Global Health*. [https://doi.org/10.1016%2Fj.resconrec.2008.03.002](https://doi.org/10.1016%2Fj.resconrec.2008.03.002) (Citation carried over from Wikipedia blockquote)

[^3]: IP stands for ingress protection. The first number is a dust protection rating. A 5 in dust protection means that a small amount can get in, but not enough to interfere with the function of the device. The second number is a liquid protection rating. A 5 here indicates protection against "water jets", but not immersion. Basically, it can get more than rained on and still walk away.
