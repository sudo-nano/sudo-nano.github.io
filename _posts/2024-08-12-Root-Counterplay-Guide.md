---
layout: post
title: "Root Counterplay Guide"
date: 2024-08-12 23:30:00 -0700
tags: board-game root living-document
hidden: false
--- 
## Introduction 
This document is a guide on how to counter the various factions in the 
asymmetric strategy board game Root. It details their means of scaling, merson[^1] 
deployment, and win conditions, as well as how you can best 
prevent fulfillment of those those win conditions.

This guide is for those of intermediate familiarity with strategy board games 
and basic familiarity with the rules of Root. General strategy game terms such 
as "action economy", 
"board presence", and "engine" will not be explained. Some Root specific rules
terminology will also not be explained, but the rules are [available online
here.](https://root.seiyria.com/)

This is a living document, which means it will receive updates as new 
information is gained and strategies are tested. All updates will be recorded
in the change log. Contributions are welcome, and can be made by [submitting a 
pull request here.](https://github.com/sudo-nano/sudo-nano.github.io)

## Change Log
### 2024-08-12
- Created Underground Duchy section
- Created Woodland Alliance section 
- Created Corvid Conspiracy section 
- Created Lord of Hundreds section
- Created Lizard Cult section (unfinished)

## Underground Duchy 
### What do they do?
The Underground Duchy has a heavy board presence. They have the ability to 
deploy massive numbers of meeple, which is hampered only by their initially slow 
recruitment. They start with a poor action economy, but scale rapidly by swaying 
nobles, as well as building citadels and markets. Swaying nobles allows 
incredibly good action economy, building citadels allows rapid recruitment, 
and building markets allows greater procurement and cycling of cards.

### How to Sabotage
The moles require a few rounds to ramp up. If you know the person playing them 
will be a threat, they're relatively easy to kneecap by attacking within the 
first three rounds, before they get everything going. If they're smart, they'll 
hole up in a few defensible clearings from the start, which makes things more 
difficult. 


## Woodland Alliance
### What do they do?
The Woodland Alliance[^2] has the lightest board presence of any faction. They 
deploy very few meeple, but mainly ramp up by accumulating followers and placing 
**sympathy** tokens. These sympathy tokens are key to their development. Even 
though they're placed undefended, you're incentivized not to destroy them. Each 
token you destroy requires you to select a card from your hand matching the suit 
of the clearing, and give it to the Alliance. If you have no matching cards, 
they get to view your hand and select a card of their choice. Either way, it 
gets added to their supporters.

This makes fighting the Woodland Alliance annoying and expensive. The 
alternative, however, is more expensive. 
If a clearing has a sympathy token, the Woodland 
Alliance player can pay two matching supporters to **revolt**, which will: 
- Destroy all enemy pieces in the clearing
- Deploy a number of Alliance meeple equal to the number of matching clearings 
with sympathy tokens 
- Place a matching **base** that allows them to directly deploy warriors
- Add warriors to the office box, increasing their action economy

Additionally, the number of victory points that they score by placing each 
sympathy will increase with the number of sympathy tokens currently placed.

### How to Sabotage
**Bases** are what allow the Woodland Alliance to directly deploy units. 
Most importantly, placing sympathy tokens usually requires spending at least
one supporter. Once they get meeple on the board, they can take the *organize*
action to remove a merson and replace them with a sympathy. 
This is a critical piece of the Woodland engine, because it allows them to make
a net supporter profit when someone destroys their sympathy.

Removing a base exacts a steep price from them.
If you destroy a base, they must discard all matching supporters and remove half 
of their officers (rounded up). They also lose the base as a deployment point 
for meeple.

Because of the Corvids' ability to deploy **snare plots**, they're uniquely 
suited to handicap bases. If the Corvids were to flip a snare in the same 
clearing as a base, and then remove all Alliance meeple from that clearing, the
base would be worse than useless until the snare is removed. The Alliance would
be unable to deploy meeple there due to the snare, and also unable to revolt in
that suit because of the existing base. While marching in from elsewhere to 
destroy a snare is easy for heavy factions, the extremely light presence of the
Alliance makes this very expensive for them. 


## Corvid Conspiracy 
### What do they do?
The Corvid Conspiracy has a light board presence. They have the ability to 
deploy **plots**, special tokens that have one of four functions: 

- Bomb: When flipped, remove all enemy pieces in its clearing.
- Snare: While face up, enemy pieces cannot be placed in or moved from its clearing. 
- Extortion: When flipped, take a random card from each player who has any 
pieces in its clearing. *While face up, you draw an extra card in evening.*
- Raid: When removed, place one warrior in each adjacent clearing. 

Tokens are always deployed face down. Facedown tokens allow the crows to deal an 
extra hit per defending battle. Tokens can be flipped face up during the Crows' 
birdsong phase if a crow is present in the clearing. 

### How to Sabotage
Facedown plots are their primary method of exerting pressure, especially because 
other players don't know what the plot is. Facedown plots can be **exposed**: 
You can reveal a card of a matching suit and make a guess about which plot it 
is. If you're right, the facedown plot is removed. 

If you have the extra action economy, you can attempt exposure and guess what 
you think is most likely. However, the most economic way to deal with plots is 
to guess whether the plot is a *Raid*. If it is, it will be **exposed** and
disappear, giving you one VP. If it's not, you can safely destroy move in meeple
and destroy it, knowing that it won't spawn more crows. 

A slightly more advanced application of this strategy involves guessing what you
think would be most harmful, not most likely. If your guess is right, it's 
removed. If your guess is wrong, you are assured that the worst case will not
come to pass, and can decide whether it's even worth engaging with the plot. 


## Lord of Hundreds
### What does it do?
The Lord of the Hundreds holds iron-fisted control over clearings. Completely 
controlling clearings is the only way for them to score VP, and their toolkit
is designed around doing so. 
The first and foremost of these is **mob tokens**. During evening, the Lord 
can spend a card to place a mob token in a matching clearing that has a Hundreds 
warrior. At the beginning of each of their turns, *every enemy token (excluding 
warriors) in clearings with a mob token are destroyed.* 

The reason the Hundreds needs such strong board control is that they can only 
score victory points from clearings that they control *which have no other 
factions' pieces.*

### How to Sabotage
Like the Woodland Alliance, the Lord of Hundreds is expensive to fight, but the
alternative is letting them win. You can fight the Hundreds primarily by 
destroying mob tokens and keeping warriors in their clearings.

#### Preventing Victory Points
Because the Hundreds can't score from clearings with enemy pieces in them, you 
can waste a lot of their time and actions by keeping the minimum number of 
warriors in their clearings necessary to prevent them from scoring. 
<!-- Editor's note: what is the minimum number? -->
This is best done by heavy factions that can afford the losses.

#### Preventing Recruiting
The Hundreds rely on the warlord for recruiting. They can only recruit in the 
clearing where the warlord is, and the Recruit action is before the Anoint 
(replace warlord) action, so \textbf{killing the warlord prevents them from 
Recruiting for one turn}. (Note that any Strongholds will also produce warriors, 
but only one per turn.

Enlisting the assistance of the Crows to prevent the movement of Hundreds 
warriors is also very helpful, as their Snare Plots, Bomb Plots, and Raid Plots 
can be a great deterrent. This can be combined with the help of the Woodland 
Alliance's Sympathy tokens to require the Hundreds to pay cards when entering 
clearings.[^3]

#### Preventing Mobs
Preventing effective deployment of mobs is something that benefits all players 
at the table except the Hundreds. Consider preemptively coordinating with the 
other players at the beginning of the game to cordon off the spread of Mobs. 
This is best done by building a perimeter of warriors around the Hundreds, so 
that they can destroy any newly-formed Mobs that appear along the border. 

The Crows are especially good at this because of their ability to place Snare 
Plots. When revealed, they prevent any new non-Crow pieces from being placed in 
the clearing (but doesn't prevent warriors from moving into it), so *the 
Hundreds aren't allowed to place any mob tokens in clearings with face-up 
Snares.*

#### Addendum: Opinions on Game Design
The Lord of Hundreds has the unique effect of changing the objective of the 
other players. Not within the rules, but informally. If the Lord is
present, and the other players don't cooperate to handicap them, it will prove
an easy victory for the Lord. 

Their balancing is such that they can win most 1v1 faction matchups easily, 
unless the other player is experienced in dealing with them. However, they can 
be quickly dispatched by the cooperation of a heavy faction with any other 
faction, especially when one of them is able to deploy warriors flexibly and 
without prior building placement as a prerequisite.[^4]

## Lizard Cult
> This section is incomplete. 
{: .prompt-warning}

### What do they do?
The Lizard Cult is unconventional in its engine and action economy. 

### How to Sabotage
Destroying gardens is one of the most effective ways to mess up the Lizards' plans. 
Unfortunately, destroying gardens is not as straightforward of a countermeasure as 
something like destroying the Moles' buildings. Because destroying Lizard meeple in battle 
effectively feeds them actions, attacks on gardens must be calculated so that they 
destroy the fewest possible meeple in battle. 


## Footnotes
[^1]: Merson is a portmanteau of "mini person". The plural is meeple, as in "mini people".

[^2]: Colloquially called the Toasts, because their meeple resemble bread slices.

[^3]: I'm a big fan of the "Maginot Line" strategy, where the Crows and the Toasts collaborate to make clearings with **sympathy** and **snare plots** to render the area difficult to pass. It requires players passing through to pay a card tax to the Toasts, then destroy the snare. 

[^4]: The moles are included in this description, because they can deploy on the same turn they place a burrow. 
