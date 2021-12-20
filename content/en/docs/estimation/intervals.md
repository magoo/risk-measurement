---
title: "Intervals"
date: 2021-10-26T13:12:10-07:00
draft: false
weight: 104
menu:
  docs:
    parent: "estimation"
---

An interval estimate can be described as a range of values, plus the probability that an outcome will fall within them. More formally, these can be called probability intervals, or credible intervals.

Intervals can also be thought of as the values between two percentile values on a [distribution](/docs/estimation/distributions).

Here are the exact same statements with increasing formality. Each communicates an interval:

Here's a statement that _could_ be an interval with one more bit of information:
> _After a DDoS... we could be down from about a minute to seven days_

If we get a percentage from the individual, we can [elicit](/docs/estimation/expert-elicitation) an interval estimate.

> _There's a `90%` chance a DDoS causes downtime between 1 minute and 7 days._

Cool. An interval is just a pair of [percentile](/docs/estimation/percentiles) estimates. Knowing what is going on underneath, we can word these in a variety of different ways...

> _`5%` of DDoS downtime will be below 1 minute. `5%` will be above 7 days._

An interval should note what percentiles it represents. (For instance, `5%` and `95%`). It is generally assumed in this documentation that the interval is symmetric and represents the middle of the distribution you're discussing.

### More on Intervals

A [credible interval](https://en.wikipedia.org/wiki/Credible_interval)
represents a range of possible values, and also includes a percentage
belief (`confidence`) that the outcome will fall into it. 

Increasing your efforts to study a risk may change an interval estimate in a couple ways - by changing the interval or by changing the belief (probability) associated with it. 

The _size of the interval_ may change: This means the possible outcomes become wider. 

For example, there may be a 90% chance that 10-20 employee laptops are unencrypted. After some research, this may shrink to a 90% chance that 1-10 employee laptops are unencrypted. 

The _probability of the interval_: This means that the odds are different for the same possible outcomes.

For instance, a 90% chance of settlement costs between $10M-$100M dollars might reduce to 80% after some effort... but the interval you indicated ($10M-$100M) stays the same.

Here's a longer form example. An investigation has discovered an insider threat who was caught remotely accessing a co-worker's laptop. There's evidence to suggest they may have accessed more systems, but it's not definitive. 

Here is a scenario they propose:

{{<alert>}}
**Scenario** : Number of employee systems accessed by the insider within the last six months.
{{</alert>}}

An interval estimate could read as `A 95% chance of 5-10 employee owned systems`. Given this measurement from a security team, an incident command might allocate forensic resources to determine what may have been done.

A visual example of a percentage belief that an unknown value will end
up within this range when revealed:

``` none
                              95% Certainty

                                    │
                                    │
                                    │
                                    │
                                    │
                                    ▼
                            5              10
                            ▽──────────────▽

◀─────────────────────────────────────────────────────────────────────▶
... -3 -2 -1 0  1  2  3  4  5  6  7  8  9  10  11  12  13  14  15 ...
```

In summary, an interval estimate provides:

-   An interval (a lower and upper value representing a range of values)
-   A percentage belief that an outcome lies within that interval.