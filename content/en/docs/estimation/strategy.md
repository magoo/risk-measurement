---
title: "Strategy"
date: 2021-10-26T13:12:14-07:00
draft: false
menu:
  docs:
    parent: "estimation"
---

Estimation is a skill that benefits from approximation strategies. These mental models will help support common problems in risk modeling, elicitation, and forecasting. They're also useful as elicitation techniques when trying to draw out numeric estimates from an expert.

### Divide and Choose

Divide and choose is a mental heuristic to determine if odds are fair or
not. It is similar to the children\'s \"fairness\" concept:

1. One child slices a piece of cake
2. Another child chooses the slice they\'d like.

Of course, this method prevents the first child from slicing unevenly and taking
the larger piece and forces them to behave impartially to the outcome. Being partial would result in them receiving a smaller slice.

The ability to impartially estimate odds is crucial to forecasting and decision making. Opportunities for advantageous decision making arise when rewards are not congruent with the odds, but the ability to see these impartially can be difficult.

In summary - what odds would you apply to a situation, where you would be comfortable taking either side fo the bet?

### Principle of Indifference

The [principle of
indifference](https://en.wikipedia.org/wiki/Principle_of_indifference)
is a rule of thumb that divides probability across all of its options.
For instance, two outcomes at 50/50% or four outcomes at 25/25/25/25% respectively.

This principle is similar to the [uniform distribution](docs/estimation/distributions).

When faced with a scenario with four outcomes, this principle suggests starting with 25% forecasted probabilities for each of outcome and continuing a study from there. Assuming there is no available information to suggest one outcome over another, this would be the most efficient default strategy to avoid error.

During [elicitation](/docs/estimation/expert-elicitation), an expert may immediately disagree with these odds. They may find themselves confronting information about their beliefs for each scenario and debating an indifferent strategy. Afterward, it\'s likely that the forecaster has opinions they can more easily express numerically: _this should be higher_ or _that must be lower_. 

### The Absurdity Test

An absurdity test would assigns extreme and irrationally formed likelihoods
or values to a forecast, testing the opinions of a forecaster. For
instance, \"A small child can eat between zero and one million pies in a
sitting.\"

When faced with such a test, a forecaster may be encouraged to start
making a forecast *less* absurd. For instance \"Well, a child can at
least eat half of a pie, and maybe up to five pies, in extraordinary
circumstances.\"

This form of test has been used as an interview prompt in psychological
research since the [1900s](https://www.google.com/books/edition/The_Journal_of_Philosophy_Psychology_and/-zWCoyAWHjMC?hl=en&gbpv=1&dq=%22absurdity+test%22&pg=PA415&printsec=frontcover).

## Inside and Outside Views
An outside view looks at a specific situation as a frequently occurring pattern with a base rate. An inside view inspects why a specific situation is an exception from the norm. Balancing these views can offer a rational approach to understanding the probability of an event occurring.

[Tetlock's](https://g.co/kgs/npHyBC) [books](https://g.co/kgs/TTFNFR) heavily visit the concept of inside and outside views. Let's assume we are measuring how often we'll suffer a major data breach.

**Outside View:** How often do companies in my sector suffer major data breaches?
**Inside View:** What makes my company different than the rest?

An outside view may help regulate any instinct to panic over your risk findings. An inside view gives you the opportunity to compare them to how often they may be compromised in the wild. 