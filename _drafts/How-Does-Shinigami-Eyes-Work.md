---
layout: post
title: "How does Shinigami Eyes work?"
date: 2025-04-22 16:00:00 -0700
tags: data-structures browser-addons programming
category: drafts
hidden: true
--- 
<!-- Insert audience statement -->
> This extension is involved in a bunch of absolutely radioactive drama, which
> is *not* what I'm here to comment on. I almost didn't cover the extension
> because of the drama, but ultimately I decided this was too good of a teachable
> moment to go to waste.
{: .prompt-danger}

> This post is intended for audiences familiar with [asymptotic notation](https://en.wikipedia.org/wiki/Big_O_notation),
> otherwise known as "Big O" notation. Readers should also know the concepts of keys and values
> in programming, and the general concepts of hash functions. 
{: .prompt-tip}

## Introduction
Shinigami Eyes is a browser plugin for Firefox and Chrome that highlights 
social media users as trans-friendly or transphobic. It uses crowdsourced data, 
but the way in which the data is provided to end users is particularly interesting. 
It has to be pretty small, because people wouldn't download an extension that's
too massive. It needs to be quickly accessible, so that usernames can be checked
as a page loads without adding too much latency. The data structure the developer
chose for this is a [Bloom filter](https://en.wikipedia.org/wiki/Bloom_filter), 
and I'll be covering the pros and cons of using
that particular data structure for this task. 

## What is a bloom filter?
This section is largely paraphrased from Wikipedia, with minor edits to
make the explanation more accessible to those unfamiliar with data structures.
Sections delving deeper into the specifics of hash functions have also been cut
for beginner accessibility.
The original version is quite good, and you are encouraged to read it. 

A bloom filter is a data structure for maintaining **set membership**, basically
tracking whether a certain item is in a group or not. It functions similarly
to a **hash table**, but trades away the perfect (or near perfect) accuracy
of a hash table for massive space savings. In particular, false positives are
possible with a bloom filter, but false negatives are not. The false positive
probability and the exact space savings are dependent on the number of elements
relative to the size of the table. As the table fills up, false positives become
more likely. A larger table can be used to decrease the false positive probability,
at the cost of reduced space efficiency.

The way bloom filters actually work is that they are an array of \(m\) bits, which
all start set to 0. It has $$k$$ different hash functions. To add an element to the
array, you put it through all the hash functions, and each function maps the
element to a bit in the array. We are, in effect, randomly selecting \(k\) bits 
of the array to set to 1 for any given element, in a way that is consistent 
between every time we input the same element.

When we want to check whether an item is present in a bloom filter, we put that
item through the hash functions, and check all of the bits that the hash functions
point to for that entry. If all of them are 1, then the element is in the bloom
filter. There's one issue: the more elements there are relative to the size of
the bloom filter, the higher the probability that other entries will have 
coincidentally set all the bits for a given element to 1 without that element
having actually been entered, producing a false positive. Since there is no
mechanism that sets 1s back to 0, false negatives are impossible.

## Is a bloom filter a good choice?
The suitability of a bloom filter for this task depends on your goals.
At the most basic of requirements, whatever you use for this addon must allow
you to check set membership. A list, binary tree, hash table, and bloom filter all achieve
this, but they're not equally good at it. Checking set membership in a list 
of size $$n$$ is $$O(n)$$. Checking using a hash table or bloom filter is $$O(1)$$.
Using a binary tree of size $$n$$ is $$O(\log n)$$. 

Lists and binary trees allow end users to view the keys (i.e. the usernames in the 
list), which is a benefit for transparency, but probably a drawback for drama avoidance.[^1]
Regardless of the transparency benefits, their performance is so outdone by hash tables
and bloom filters that they're immediately out of the running. While we have no way of
knowing exactly how many usernames are in the dataset, checking every username on every
page as it loads requires that the addon work extremely quickly to avoid slowing down the
page excessively.
<!-- TODO: Look at what patterns the addon is actually trying to match when it reads pages -->

## Footnotes

## References
