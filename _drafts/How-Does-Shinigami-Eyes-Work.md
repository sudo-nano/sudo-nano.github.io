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
> moment regarding choice of data structures to go to waste.
{: .prompt-danger}

> This post is intended for audiences familiar with [asymptotic notation](https://en.wikipedia.org/wiki/Big_O_notation),
> otherwise known as "Big O" notation, as well as the concepts of keys and values
> in programming.
{: .prompt-tip}

## Introduction
Shinigami Eyes is a browser plugin for Firefox and Chrome that highlights 
social media users as trans-friendly or transphobic. It uses crowdsourced data, 
but the way in which the data is provided to end users is particularly interesting. 
It has to be pretty small, because people wouldn't download an extension that's
too massive. It needs to be quickly accessible, so that usernames can be checked
as a page loads without adding too much latency. The data structure the developer
chose for this is a **Bloom filter**, and I'll be covering the pros and cons of using
that particular data structure for this task. 

## What is a bloom filter?
A bloom filter is a data structure for maintaining **set membership**, basically
tracking whether a certain item is in a group or not. It functions similarly
to a **hash table**, but trades away the perfect (or near perfect) accuracy
of a hash table for massive space savings. In particular, false positives are
possible with a bloom filter, but false negatives are not. The false positive
probability and the exact space savings are dependent on the number of elements
relative to the size of the table. As the table fills up, false positives become
more likely. A larger table can be used to decrease the false positive probability,
at the cost of reduced space efficiency.

The way bloom filters actually work is that they are an array of $m$ bits, which
all start set to 0. It has $k$ different hash functions. To add an element to the
array, you put it through all the hash functions, and each function maps the
element to a bit in the array. 

## Footnotes

## References
