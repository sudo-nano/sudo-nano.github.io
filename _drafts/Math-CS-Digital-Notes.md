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
- Syntax highlighting takes absolutely fucking forever if you do it with colored pens, and is completely nonviable for in-situ note taking
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
different libraries. `minted` is the most commonly used. 

Pros: 
- Absolute control of formatting 
- Best-in-class equation rendering
- Compiles to PDF (easy to hand in digitally or send to friends)
- The sky is the limit when it comes to high resolution diagram rendering

Cons: 
- Lots of overhead, even for simple notes
- Extremely steep learning curve 
- Rendering diagrams is very complicated 

## Footnotes
