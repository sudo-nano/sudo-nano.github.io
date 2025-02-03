---
layout: post
title: "How is Anaconda This Bad?"
date: 2025-02-02 21:32:00 -0800
tags: software python
--- 
> Normally, I try not to complain about things unless I'm also suggesting a solution.
> This post is literally just for me to complain about anaconda, the python
> environment manager. I suppose I am suggesting a solution, but the solution is
> uninstalling anaconda and using literally any other environment manager.
{: .prompt-warning}

## Upgrading from the old solver is sometimes impossible
A while ago, anaconda switched their slower environment solver to the much faster
one from `libmamba`. 
Along with some architecture changes, the anaconda blog 
[claims that conda is fast now.](https://www.anaconda.com/blog/conda-is-fast-now)
That's great, if you can update to the new solver. 
The problem is that the old solver is sometimes too slow to reasonably solve
the base environment in order to update to the new solver. 
Their documentation [shows how to work around this,](https://conda.github.io/conda-libmamba-solver/user-guide/faq/#install-older-conda)
but if the suggested workaround fails (as it did for me), you're pretty much
SOL unless you want to reinstall conda. 
Do yourself a favor, uninstall conda and replace it with something else.

## It interferes in places it shouldn't
### Breaks `clear` command on some arch systems
Anaconda has 
[a bug that's been open for nearly 10 years](https://github.com/ContinuumIO/anaconda-issues/issues/331#issuecomment-2622737645)
where they provide a `clear` binary with hardcoded `TERMINFO` that causes the 
command to just fail on some arch systems. 
As far as I can tell, the binary isn't even used for anything. 

### Interferes with `curl` certificate path
Just earlier today I was using `curl` to check whether I could use a certain
site for a project.[^1] 
It failed with a certificate error, citing some path to a `.pem` file. I
noticed `conda` in the path, and being already fed up with `conda` due to the
previous issue, said "fuck it" and uninstalled `conda`. 
Somehow, this solved the issue. 
While I'm normally a massive proponent of reporting bugs, the anaconda team's
response time to the last issue I mentioned does not inspire confidence that the
issue will be responded to within the decade. 

## Please use another environment manager 
### mamba
Mamba is just anaconda but rewritten in C++. It's way faster. Please use it
instead of sending more people to anaconda hell. 

Also, don't *install mamba via conda* like 
[this AI generated slop article](https://toxigon.com/conda-vs-mamba-speed-comparison) 
recommends. 
Installing package managers with package managers causes problems.
Incidentally, installing anaconda with `yay` may have played a part in my
problems above. 
This is, unfortunately, not an obvious thing to people installing anaconda, 
nor did anywhere I looked suggest checking this as a troubleshooting step.
I only learned about this piece of arcane wisdom from a friend.

### poetry
[Poetry](https://python-poetry.org/) is a python packaging and dependency manager.
Really, it's a whole system for managing your project. 
Dependencies are locked in and builds made reproducible using the `poetry.lock` file.
If you're using a Python project for scientific computing, please for the love
of god use `poetry` to package your software. 
Don't let people guess which combination of package versions is the only one 
that works after you've moved onto another job five years ago and they need to
move the in-house software to a new computer.

## Footnotes
[^1]: I was trying to see if I could fetch the angular position of the sun using `curl`, so that I could feed it into a cron job that would set my monitor brightness accordingly. You know, like a sane person. 
