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

During [elicitation](/simple-risk/docs/estimation/expert-elicitation), an expert may immediately disagree with these odds. They may find themselves confronting information about their beliefs for each scenario and debating an indifferent strategy. Afterward, it\'s likely that the forecaster has opinions they can more easily express numerically: _this should be higher_ or _that must be lower_. 

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

## Avoid the Availability Heuristic.
The [availability heuristic](https://en.wikipedia.org/wiki/Availability_heuristic) influences and biases a forecast due to a shortcut most thought processes take: _if you remember it, it must be important_. Keep in mind that the events in your memory do not represent all available data, nor does it represent the most important data necessary for a good forecast. It just happens to be your memory at the time.

For instance, a violent plane crash may bias people against flying, when flights are historically known to be very safe.

## Identify your stubborness.
The bias of [belief perseverance](https://en.wikipedia.org/wiki/Belief_perseverance) describes a belief you may have in spite of information that directly contradicts it. The causes of this bias are unclear. Your ability to suspend a belief as you explore opposing arguments is an important skill. It's also important to avoid bold and confident claims when you lack supporting evidence, or have not thoroughly explored an opposing side.

In once extreme case, psychologists joined a cult, and observed that its members clung to their beliefs even _after_ the world did not end on a given date.

> Festinger, Leon; et al. (1956). When Prophecy Fails. Minneapolis: University of Minnesota Press.

## CHAMPS KNOW
From research described [here](https://aiimpacts.org/evidence-on-good-forecasting-practices-from-the-good-judgment-project-an-accompanying-blog-post/), [here](http://journal.sjdm.org/16/16511/jdm16511.html), and [here](https://g.co/kgs/j4Y32n). 

|Letter   | Probabilistic Reasoning Principal   |
|:--:|:--:|
|  C |  Comparison classes|
|  H |  Hunt for the right information |
|  A | Adjust and update forecasts when appropriate  |
|  M |  Mathematical and statistical models |
|  P |  Post-mortem analysis |
|  S |  Select the right level of effort to devote to each question |
|    | Political Reasoning Principal  |
|  K |  Know the power players and their preferences|
|  N |  Norms and protocols of institutions |
|  O | Other perspectives should inform forecasts  |
|  W | Wildcards, accidents, and black swans |

### Comparison Classes ([link](https://en.wikipedia.org/wiki/Reference_class_forecasting))
Think through comparison classes to narrow in your forecast based on similar, comparable data.

1. Assume that your scenario is not entirely unique, and find comparables.
2. Identify what aspects of the scenario _do_ make it unique.
3. Explore the comparable scenarios and any data available, and determine how different they actually are by the estimating the value of those differences.

For instance: Estimating attendance at a performer's first headliner gig. Can you explore data from concerts at the same venue, type of music, or audience demographic? Maybe their previous, non-headline shows will give some basis for reasoning as well.

### Hunt for the right information
Immediately hunt for information that contradicts your gut feelings. Understand all nuance in the question statement. Be confident that you understand any nuance in the judgement criteria that may impact the outcome.

### Adjust and update forecasts when appropriate
If your scenario allows you to update a forecast over time, it will help. Not only is the progression of time a new source of information, but being able to "sleep on it" will allow you to apply critical thinking to a scenario with fresh perspective, or apply any other information you have gained.

### Mathematical and Statistical Models
When possible, bust out your spreadsheet and calculator and explore the historical data involved with your scenario. Understand the limitations of mechanical modeling, as well as your own subjective forecasting. You, as a forecaster, are subject to bias. However, a mechanical model might not see the data it needs to capture probability correctly.

### Post-Mortem Analysis
Value the "busted" forecasts! They are precious. What influenced a forecast that was ultimately incorrect? What reasoning was incorrect, or undervalued? What data would have valuable to have, in hindsight?

### Select the right level of effort to devote to each question
Very intentionally ask questions about the scenario. Decide which ones deserve your effort to research and answer them.

### Know the power players and their institutions
(Related to political forecasting)

### Norms and protocols of institutions
(Related to political forecasting)

### Other perspectives should inform forecasts
How would someone else look at this scenario? Would someone invested in this scenario view it differently? What about people invested in different outcomes, what questions or data would they rely on?

### Wildcards, accidents, and black swans
Always, always leave room for the complete shocker. Consider that we always view black swans as explainable events *after* they've punched us in the jaw. If you express certainty (0%/100%), you are likely opening yourself up for tragedy. The world is full of surprises, disappointment, accidents, and the unknown unknown.

## Online Training
Participation in something continuous like the [Good Judgement Open](https://www.gjopen.com/) will help keep forecasting skills sharp. Otherwise, varying levels of rigorous training below are available.

- [Good Judgement](https://good-judgment.thinkific.com/) (recommended)
- [Hubbard Research](https://www.hubbardresearch.com/shop/calibration-webinar-quantify-uncertainty/) (enterprise)
- [https://www.evidentmethod.com/training/](https://www.evidentmethod.com/training/) (free / enterprise)
- [http://confidence.success-equation.com/](http://confidence.success-equation.com/)

