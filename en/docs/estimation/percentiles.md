---
title: "Percentiles"
description: ""
lead: ""
date: 2021-10-27T10:34:55-07:00
lastmod: 2021-10-27T10:34:55-07:00
draft: false
images: []
menu: 
  docs:
    parent: "estimation"
weight: 103
toc: true
---

A percentile estimate is a probability and value pulled from a [distribution](/docs/estimation/distributions). Some examples:

> The `90%` percentile of customer losses is `$1M`. 

This communicates a `90%` chance that future customer losses will be `$1M` or less. 

It also communicates a `10%` chance that losses will exceed $1 million. 

**The upside:** A percentile estimate is very simple to gather and communicate.

**The downside:** It won't communicate how the risk _behaves_. 

Stated differently: The possible outcomes might be normally distributed, exponential, uniform, or something else. This sort of intuition is not communicated from from a single percentile estimate. 

Some more examples of what a percentile estimate can sound like:

- We expect 95% of fraud claims to lie under $1M.
- The median (50% percentile) customer account value is $1K.
- 75% of our incidents last under 3 days to investigate.

Elicitation is quick and often understood. Though, a sole percentile estimate won't disclose other information about a risk (extreme values or underlying distributions).

For instance, let's say the 90% height in a group of people happens to be 6 foot 3. Knowing that height is normally distributed, we don't expect the remaining 10% of people to include any 20 foot giants. Rather, we expect the remaining 10% of people to be able to walk through a doorway.

However, a 90% percentile estimate of _regualtory settlements_ may be entirely different. Assume 90% of settlements are expected to be under $200 million for a business. Within that remaining 10% of possible settlements may be some extreme values in the [multiple billions](https://www.ftc.gov/news-events/press-releases/2019/07/ftc-imposes-5-billion-penalty-sweeping-new-privacy-restrictions).

The percentile itself does not communicate distributions of risk. Still, a percentile estimate is quick and useful especially if an audience is familiar with the underlying behavior of the risk.