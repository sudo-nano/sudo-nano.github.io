---
layout: post
title: "Hacking Tools Don't Exist"
date: 2024-04-22 16:00:00 -0700
tags: politics right-to-repair cyberpunk electronics hacking
category: drafts
hidden: true
--- 

## Outline (delete this later)
- There's no such thing as hacking tools, only tools useful for hacking.
- Any tool useful for hacking is also useful for research, development, and
diagnostics, therefore banning one is always a net negative.
- Technology is inherently neutral
- A tool becomes a "hacking tool" when it does something politically unfavorable
- Anyone calling for the banning of a "hacking tool" is clueless 
- Actual enforcement of hacking tool bans only exists to make examples out of
public figures 
- Banning "hacking tools" is a clear step into anti-intellectualism
- Mention flipper zero fearmongering
- MAC address spoofing became a standard enabled-by-default feature on many devices recently for privacy purposes.

Part of Apple's developer terms that really annoyed me: 
> (e) You will not, through use of the Apple Software, Apple Certificates, Apple Services or otherwise, create any Covered Product, Corresponding Product, or other code or program that would: (1) disable, hack or otherwise interfere with the Security Solution, or any security, digital signing, digital rights management, verification or authentication mechanisms implemented in or by iOS, iPadOS, macOS, tvOS, visionOS, watchOS, the Apple Software, or any Services, or other Apple software or technology, or enable others to do so (except to the extent expressly permitted by Apple in writing); or (2) violate the security, integrity, or availability of any user, network, computer or communications system;

## Introduction: The Hacker Mindset
In an age where the pervasiveness of computers is rapidly outpacing tech 
literacy, it's quite easy to feel like computers are magic. 

Being a hacker is, more than anything, about deep curiosity and a desire to know
how things work. A key part of figuring out how things work is differentiating
between *what they intend to do* and *what they actually do.* 
Most systems try to keep the inner workings hidden from the users, but we can
glean some interesting information about them in edge cases where systems fail.
For example, Portland's Tri-Met public transit system intends to give you useful
data on how long it'll be until the bus arrives. However, sometimes it says the
bus is 3 minutes away, and then you wait 15 minutes, and it still says 3 minutes.
At this point, the average person would probably say "fuck it, I'm getting a 
taxi/rideshare." However, I noticed that the bus has been in the same place for
the whole time, and that place was two stops before mine. The time since last
update showed that fresh location data was still coming in. From this, we
can deduce that Tri-Met's countdown is probably based solely on the distance
from the bus to you, and does not account for the bus' speed. 

This is an interesting but ultimately harmless deduction. Special failure modes
in other applications reveal more sinister software defects. If you put 
incorrect or invalid data into a web form, the form will usually tell you so.
Sometimes, if you put in certain special characters, you'll get a weird server
side error instead of the normal one. This can indicate a failure of
**input sanitization:** some of your input is inadvertently being run as code, 
which should have been prevented. Depending on the exact nature of the system,
you may be able to exploit that sanitization failure to reveal secret information, 
or to log in as someone whose password you don't have. This is how SQL injection,
one of the most notorious vulnerability categories, functions.


## Footnotes
