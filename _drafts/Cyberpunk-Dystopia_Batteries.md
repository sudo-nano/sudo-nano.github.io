---
layout: post
title: "Batteries are maintenance items - How to Not Live in a Cyberpunk Dystopia #01"
date: 2024-01-21 16:00:00 -0700
tags: politics right-to-repair cyberpunk electronics
category: drafts
category: Cyberpunk Dystopia
hidden: true
--- 

## Introduction

This is the second post in a series about what we can do to make real life less 
of a cyberpunk dystopia. The first post is 
[here.](https://sudo-nano.github.io/posts/Cyberpunk-Dystopia-00/) 
This post is targeted towards a general audience. No prior knowledge is required. 
If something is unclear, please refer to the footnotes or [contact me to ask for 
clarification.](https://sudo-nano.github.io/about/)

Portable electronics, because of their newness, exist in a sort of cultural limbo: 
They are completely pervasive in everyday life, yet we have little to no generational 
knowledge about their care and maintenance. 
This is in part because they've only existed for about one generation, but in equal 
part by the intention of manufacturers through planned obsolescence.[^1] 
In contrast to something like cars, where maintenance practices are well-known and 
parts are intended to be replaced by a user or mechanic, many portable electronics 
are designed so that the battery is unserviceable. 
Most often seen in phones, e-readers, wireless headphones, and thin laptops, it's 
usually the case that either the device is not meant to be opened for any maintenance 
at all, and/or the battery is installed in such a way that removing it could be unsafe.
This wasteful design is similar in principle to throwing out your car instead of
changing its oil, because the manufacturer has made it so that you must cut into
your engine to change the oil.

Their incentive to do this is the aforementioned planned obsolescence, where manufacturers 
force consumers to prematurely buy a new device at the cost of increased electronic 
waste (sometimes abbreviated e-waste). Besides the obvious detriment of manufacturers 
wringing more money out of consumers for shorter device lifetimes, e-waste is more 
harmful to people and the environment than traditional garbage. 

> Electronic scrap components, such as CPUs, contain potentially harmful materials 
> such as lead, cadmium, beryllium, or brominated flame retardants. Recycling and 
> disposal of e-waste may involve significant risk to the health of workers and 
> their communities.[^2] ([Wikipedia](https://en.wikipedia.org/wiki/Electronic_waste#Definition))

Making batteries easily replaceable to mitigate these issues is quite easy. 
All a manufacturer has to do is
1. Connect the battery with a connector rather than soldering it directly to the board
2. Secure the battery in a way allowing removal without damaging the battery (as damaged batteries can start a fire)
3. Construct the phone so that the battery can be accessed easily

In fact, this used to be the standard for smartphones. Older Samsung flagship phones 
such as the Samsung Galaxy 5 had removable batteries. In the 10 years since its 
release, manufacturers have realized that charging consumers to service their batteries 
is much more profitable. 

To explore just how possible it is to have replaceable batteries in consumer electronics, 
we'll cover the basics of how batteries work and what kinds are in your devices. 

## Battery Basics

### How does a battery work? 
Batteries, at their most basic, perform a chemical reaction to generate electricity. 
What this reaction is, as well as whether it's reversible, depend on the type of battery. 
Nearly all electronics with rechargeable batteries use lithium-ion batteries, which
utilize dissolved lithium to perform a reversible reaction to store or release charge. 

Lithium batteries are notable for their high power density, meaning smaller batteries can 
store lots of energy, and high discharge rate, meaning they can release their power 
quickly. Usually, a battery is optimized for one of the above, not both. 
Lithium batteries can also be dangerous because their electrolyte, the solution
in which the metal is dissolved, is flammable. This means damaged lithium batteries
can catch fire and explode violently, something that other types of batteries (like 
disposable alkaline AA batteries or lead-acid car batteries) don't do. 




Footnotes:

[^1]: **Planned obsolescence** (also called built-in obsolescence or premature obsolescence) is a policy of planning or designing a product with an artificially limited useful life or a purposely frail design, so that it becomes obsolete after a certain pre-determined period of time upon which it decrementally functions or suddenly ceases to function, or might be perceived as unfashionable. ([Wikipedia](https://en.wikipedia.org/wiki/Planned_obsolescence))

[^2]: Perkins, Devin N, Marie-Noel Brune Drisse, Tapiwa Nxele, Peter D. Sly. 2014. "E-Waste: A Global Hazard". *Annals of Global Health*. [https://doi.org/10.1016%2Fj.resconrec.2008.03.002](https://doi.org/10.1016%2Fj.resconrec.2008.03.002) (Citation carried over from Wikipedia blockquote)
