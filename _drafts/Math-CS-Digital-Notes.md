---
layout: post
title: "Digital Note Taking for Math and Computer Science"
date: 2024-04-22 16:00:00 -0700
tags: academics latex meta
category: drafts
hidden: true
--- 
<!-- Insert Audience Statement -->
Taking notes in math and computer science present some additional
challenges compared
to other topics. Both disciplines require a reasonable way to write equations, 
and computer science needs code syntax highlighting to maintain readability. 
Unfortunately, the existence of these features is not guaranteed in most word
processors. Across programs that have them, implementation is not standardized. 
In my four years of academia, these are the solutions that I've tried. 

## Baseline: Paper 
Paper, being the time-tested default for note taking, will be our baseline. 
Pros: 
- Versatile. Formatting is completely unrestricted. 
- No digital format compatibility issues 
- Hand drawing diagrams is easy 
- Writing equations is quick

Cons: 
- Syntax highlighting takes absolutely forever if you do it with colored pens, and is completely nonviable for live note taking
- Equation legibility gets pretty bad if your handwriting is messy
- No image insertion
- Turning in assignments digitally requires scanning

## LaTeX 
LaTeX, or more generally the TeX family of typesetting languages, are a staple
of modern academia. If you've ever seen a PDF and immediately noticed that it's
in the "research paper font", that font is *Computer Modern*, and it's the 
default font in LaTeX. 

TeX allows precise control of everything about your document. If you've never used a typesetting language before, specifying the formatting resembles 
programming. Every part of your document's formatting can be modified if you so
desire, which is a blessing and a curse. On one hand, you'll never have the 
classic Google Docs/Microsoft Word problem where you change your text slightly
and it shunts your image off to god knows where. 
On the other hand, it adds significant overhead when you want
to take uncomplicated notes. 

If you're entering Math or CS, chances are you'll be forced to learn LaTeX at
some point. Even if you hate typing raw LaTeX for entire documents, it's 
prudent to learn at least math mode. LaTeX math mode is the gold standard for
equation typesetting, and lots of other programs support inline LaTeX for just
this purpose. 

LaTeX supports language-specific syntax highlighting via a few 
different libraries. `minted` is the most commonly used. One significant drawback
of `minted` is that it freaks out if you have spaces in your file path.
That means your file name, and the name of every folder in the path to your file,
cannot have spaces. This is, in my opinion, a ridiculous problem to still be
having in 2025. I could have sworn there was a better syntax highlighting
library, but I was unable to find it for this post. `minted` is the most common,
and most guides use it. 

LaTeX also supports the `tikz` package for drawing vectorized diagrams.[^1]
`tikz` is extremely complicated to learm, but rendering high-res diagrams directly
into your PDFs makes a smoother compiling experience (and smaller file size)
than importing external bitmap images.

Pros: 
- Absolute control of formatting 
- Best-in-class equation rendering
- Compiles to PDF (easy to hand in digitally or send to friends)
- The sky is the limit when it comes to high resolution diagram rendering

Cons: 
- Lots of overhead, even for simple notes
- Extremely steep learning curve 
- Rendering diagrams is very complicated 

## Markdown

## Footnotes
[^1]: Vectorized images are mathematically defined using equations, rather than stored as an array of pixels. This means they have practically infinite resolution, and will never suffer from being weirdly blurry from aliasing if you resize them. Regular non-vector images are called bitmap images.
