---
title: "Breach Impact"
description: "Measuring the impact from a breach."
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "examples"
weight: 110
toc: true
---

We may be asked what the impact would be if we suffered a breach. The following questions are useful to ask when thinking through a model.

- [x] Did we discover this breach? Are we talking about response costs?
- [x] Are we talking about costs from an undiscovered breach?
  - IP theft / Corporate espionage / competitive threats
- [x] Do we strictly mean financial costs?
  - Or measurements in engineering hours, days offline, etc
- [x] Are we counting costs imposed to others (imposed risk)?
- [x] Are we also speculating on legal costs?
- [x] Are we talking about operational costs?
- [x] Do sales and growth from reputation hits and future business losses count?

## Example forecasts

- _There's a 30% chance we'd have to pay a fine to a regulator_
- _If the breach accessed a host in production, 85% chance we'd disclose to a regulator_.
- _If the breach accessed a dev host, a 15% chance we'd disclose to a regulator_

## Example intervals

- _A fine to a regulator would be between $100K and $300M_ (95%)
- _The total costs of our breach would land between $500K-$80M_ (90%)
- _We'd spend between 5 and 200 engineer days on incident response._ (95%)
- _There could be zero newspaper headlines, or up to 10_ (70%)
- _Our customer churn would be between 5-12% the month after public disclosure._ (75%)

## Example distributions
- _A legal settlement would follow a lognormal distribution with an average of $1M and a 5% chance of exceeding $100M_
- _A legal settlement would follow a pareto distribution with an average of $1M and a 5% chance of exceeding $100M_
- _A legal settlement would follow a zipf's distribution with an average of $1M and a 5% chance of exceeding $100M_.
