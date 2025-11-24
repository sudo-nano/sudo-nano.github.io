---
layout: post
title: "Stylesheet Playground"
date: 2024-11-26 22:36:00 -0700
tags: meta web-development accessibility
hidden: true
--- 

This is a reference sheet (and testing zone) for all my custom CSS. Nice work
finding it, since it's not indexed! 

## Custom `abbr` pop up 

<abbr title="Problem Exists Between Chair and Keyboard">PEBCAK</abbr>

## Lancer Horus Text Distortion
> The Horus distortion text is flashy and eye-strainy, so I won't use it outside
> the testing page until I write an opt-in dialogue for the effects.
{: .prompt-warning}
<p class="horus--subtle">subtle distortion</p>

> Extreme eye strain warning for mousing over the below text!
{: .prompt-warning}
<code class="horus">EXTREME DISTORTION</code>

## TeX rendering via KaTeX
$$y = mx + b$$

$$x = \frac{-b \pm \sqrt{b^2 - 2ac}}{2a}$$

## Warning for images without alt text 
To help me with making this site more accessible, images without 
alt text will show up with a dashed red border. This should remind
me to add alt text to all images. Realistically the existence of
alt text shouldn't be an issue, because the default way of
embedding in markdown adds alt text, but it could be an issue if
raw img tags are inserted instead.

<img src="{{site.url}}/assets/cyberpunk_dystopia/18650.jpg">
## Footnotes
