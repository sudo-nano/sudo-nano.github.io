---
layout: post
title: "Glean is Almost Good"
date: 2025-02-26 16:00:00 -0700
tags: software accessibility
category: drafts
hidden: true
--- 

> Full disclosure: I receive access to Glean for free as part of my accommodations
> for ADHD at my college.
{: .prompt-tip}

## Introduction
Glean is an online study tool that claims to reduce stress, improve confidence,
and improve grades. 
Full disclosure: I receive free access to their service as part of accommodations
for ADHD at my college.
Its primary feature is audio recording in a way that lets students set custom
markers with notes at specific points in the lecture.
According to Glean, this is what makes their service better than competitors
that only offer full transcripts or full recordings. 
I agree with their assessment. Searchable transcripts are great, but seeing
my own select notes at a glance is much more useful.
The cumbersome nature of scrubbing through full audio recordings has 
prevented me from properly utilizing other audio-based accessibility tools in 
the past.
They still provide the transcript as a fallback, which makes it a strict
improvement over other services.

## Missing Quality of Life Features
Glean is, unfortunately, missing quite a lot of fairly obvious quality of life
features. 
In order to draw equations, you must use the scribble tool. 
This tool is frankly unusable on a laptop trackpad.
Not only is drawing any moderately complicated equation way too slow for real
time use, the friction required to click and drag on a trackpad makes it a
painful experience.
In my case, it's literally painful, because doing that inflames my repetitive
strain injury. 
As for what they should do instead, using LaTeX seems like a no-brainer.
Other popular note taking and study programs (Logseq, Obsidian, Anki) integrate
LaTeX using either KaTeX or MathJax, two popular javascript libraries that
provide easy and lightweight TeX rendering.

Another thoroughly underdeveloped feature is the search function.
It allows you to search your notes and the transcripts of transcribed events,
but it lacks any sort of granularity. 
There is no way to search only within a folder of events.
If you have multiple classes that use lots of similar terminology, you'll have
to trawl through the global search results in order to find what you're looking
for.

These friction points were immediately obvious to me upon using Glean, and 
they give me serious doubts about the maturity of their product.
It's unclear whether these features needed more time in the oven or whether
they were purposefully skipped in order to save development time, but either
way I'd like to see improvement.

## Trendy-Startup-itis
Glean suffers from what I call trendy-startup-itis: the website design is pretty,
the CSS stylesheet is immaculate, but the service itself is not thoroughly 
fleshed out underneath its pretty paint job. 

Searching the help database reveals its sparseness.
Attempting to find useful documentation on what the event and transcript search 
function does and doesn't support is maddening. 
Each query helplessly replies with 
a plethora of unrelated help pages rather than admit that it doesn't have
any related to my search, a trend that has become all too common on new
websites. It suggests a company that cares more about keeping up appearances
than clearly defining what is and isn't in the scope of their feature set. 

## The Duct Tape Machine
Examining the help pages and using the service, it becomes quite clear that
Glean has made significant sacrifices to allow it to become a web app for 
easy cross-platform compatibility. While all-platform support is an admirable
goal, Glean suffers massively from these sacrifices and fails to fully 
capitalize on the gains made from them. 

The documentation has [an entire page](https://help.glean.co/article/31-why-private-browsing-is-potentially-a-very-bad-thing)
on why you shouldn't use it in incognito mode. 
In short, audio recordings are saved in your browser's storage until they're
uploaded to the cloud. 
Incognito mode poses several problems for this: First, it limits the amount of
storage that a site is allowed to use. 
That means your recording may not be saved if you run out of space 
while recording.
Second, it erases all site data when you close the window. 
That means if you close the window before it's done uploading the recording to
the cloud, it gets erased forever.
The same thing can happen if you clear your site data in regular browsing before
the upload is finished.
The fact that the primary feature of this service is so easily screwed up is
really poor design, and could have been prevented if this was a real app 
instead of a web app. 






## Footnotes
