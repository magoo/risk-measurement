---
title : "Standards for \"In-The-Wild\""
date: 2020-10-06T08:47:36+00:00
lastmod: 2020-10-06T08:47:36+00:00
draft: false
images: []
menu:
  forecasts:
    parent: "intro"
---

This document guides a forecaster towards judgement of a vulnerability or exploit's "in the wild" status. This term is used with many definitions and is not well standardized.

The intent is to act as a more stable target for forecasting and is not intending on being more than that. Keep using "in the wild" however you want, this is simply judgement criteria for forecasters and a specific use case.

## An in the wild *vulnerability*.
- The knowledge necessary to exploit a vulnerability can be demonstrated as "known" by an individual.
- This largely is proven by a "proof of concept" which would need to be observed.
- A proof of concept can be observed, but you would need to trust that the PoC is exploiting the vulnerability.
- Some PoC's might not actually be useful enough to graduate to "in the wild" exploitation.

## An in the wild *exploit*.
- This does not include lab environments, red teams, academic research, presentations, etc.
- This includes unauthorized victims.
- Honeypots and honeyclients, or observable attempts to attack unauthorized victims tend to meet this definition.
- Single, confirmed instances of the above, count as "in the wild".
- There need not be vulnerable targets for an exploit to count as "in the wild". IE, if an exploit is being attempted across the internet with the attacker's fingers crossed, and no one is exploited, the exploit is still in the wild. For instance, CVE-2018-11776 did not have many misconfigured systems to exploit, but exploits were still seen in the wild.

## An in the wild *malware sample*.
- This generally means that samples are collected from victim systems or en route or waiting for victim systems.
- This can, again, be found from a honeypot environment.
- This does not count proof of concept malware or malware built as an example sample.
- Single instances count. For instance, if a targeted attack uses a specific piece of malware in a controlled state, like an airgapped victim, this is still in the wild.

## An in the wild *worm*.

> Added 12-20-2021 and collecting feedback

First, a *worm* must also be an in the wild *malware sample*.

A worm has fully autonomous discovery and exploitation (propagation) and propagates autonomously from its operator (C&C). A "partial" worm only has a subset while a "full" worm is described by the whole set.

1. **Autonomous Discovery**: Scanning is a classic, strict example, whereas using Google SERPs or a social platform would be a more loose interpretation. In theory, you could stop a worm by modifying the underlying platform, but this is unlikely on the internet and more likely on a application platform.
2. **Autonomous Exploitation**: An infected system can infect other systems without external dependencies. (A central exploit server)
3. **Autonomous from Command and Control**: Continues to propagate without access to the operator, or continues operation even when infrastructure is taken over.

Example of full worms: [Blaster](https://en.wikipedia.org/wiki/Blaster_(computer_worm)) and [Sasser](https://en.wikipedia.org/wiki/Sasser_(computer_worm)), [Code Red](https://en.wikipedia.org/wiki/Code_Red_(computer_worm)), [Samy Worm](https://en.wikipedia.org/wiki/Samy_(computer_worm)), and [Stuxnet](https://en.wikipedia.org/wiki/Stuxnet).

Worms may be indiscriminate (or not) with target selection and this should be included in a scenario if desired. For example, the Stuxnet worm discriminated against multiple qualifiers to limit its spread (d), whereas Blaster had none.