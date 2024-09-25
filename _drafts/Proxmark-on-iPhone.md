---
layout: post
title: "Building Iceman's Proxmark on iPhone"
date: 2024-09-19 16:00:00 -0700
tags: politics right-to-repair cyberpunk electronics
category: drafts
hidden: true
--- 
This article is intended for an audience that u

## Introduction
With the latest release of Iceman's proxmark3 software coming out, the discovery
of the manufacturer backdoor in Fudan static encrypted nonce MIFARE classic
credentials, and my college installing new key lockboxes that support RFID, I 
started wondering if I could run the proxmark client on my phone. 

## Packages
git 
ca-certificates 
build-essential -> alpine-sdk
pkg-config \
libreadline-dev -> readline-dev
gcc-arm-none-eabi 
libnewlib-dev 
qtbase5-dev \
libbz2-dev -> bzip2-dev
liblz4-dev -> lz4-dev
libbluetooth-dev 
libpython3-dev 
libssl-dev 
libgd-dev

`gcompat` is necessary because Alpine linux is `musl`-based while the proxmark software is based on `glibc`. 

`bsd-compat-headers`, `musl-dev`, and `linux-headers` are also necessary.

## Footnotes
