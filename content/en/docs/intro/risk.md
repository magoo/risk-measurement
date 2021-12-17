---
title: "Risk"

date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "intro"
weight: 130
toc: true
---

This section includes conceptual discussion to support your intuition around risk. A grasp of risk concepts will improve your ability to comprehend risk problems as well as articulate them to others.

## Language
This documentation mostly cares about quantitative risk, which has a strict definition (See Math below). However, the term _risk_ has lots of useful interpretations. Miscommunication with others is common without clarifying what you are measuring. 

[Sven Ove Hansson](https://plato.stanford.edu/archives/fall2018/entries/risk/)
describes risk with many definitions:

 1.  An unwanted event which may or may not occur.
 2.  The cause of an unwanted event which may or may not occur.
 3.  The probability of an unwanted event which may or may not occur.
 4.  The statistical expectation value of an unwanted event which may or may not occur.
 5.  The fact that a decision is made under conditions of known probabilities.
 
 For example, playing russian roulette (1/8 odds) compared to walking through a _literally_ haunted house (👻).

There are obviously more uses of the word _risk_.

 -   The lack of obvious mitigations (*Driving without a seatbelt is a risk*)
 -   An amount of property at stake (*I have nothing to lose to the stock market!*)
 -   General expressions of fear. (*This feels pretty risky...*)

There are obviously consistent themes involved with all of these
definitions. They all relate, somehow, to the likelihood of a future
event, or the impact of a future event, or both.

Be careful to spot different interpretations when discussing risk with others; You may think you're talking about the same thing, when in fact, you're talking past one another.

## Math

Traditional risk is represented as the following

```none
r = p * i
```

The equation can be described as a scenario. 

- `r` is Risk, or sometimes described as the **Expected Value**.
- `p` is a **Probability** involved with the scenario.
- `i` is an **Impact**.

Quantitative risk is composed from the product of how *probable* an undesireable event is, and the probable impacts that would result. 

We _very often_ focus on smaller components of this equation. Practical cybersecurity blue team work is full of examples where we make assumptions about a scenario or impact. "Assume Breach" is one of them, which you've likely heard of. Sometimes we assume a breach has already occurred, and work to mitigate downstream impact. Then, we may switch gears and patch a vulnerability that could cause that same breach to begin with.

This leaves us finding ourselves applying many hours understanding the probability of a scenario of an occurring... while we make assumptions about impact. Or vice versa. This is why understanding the whole equation is necessary for understanding how everyone contributes to the reduction of risk.

However, actual risk measurement work can be creative and flexible depending on our areas of interest.

### Expected Value
Let's say our scenario states how much risk a museum's assets ($500M) a museum has to a fire (1% odds) next year.

`risk = $500M * 1%`

The expected value (`r`) of losses would be $1M. If this scenario were simulated hundreds of thousands of times... the _average loss_ would also be about $1M... the same value we would expect. So, the name "expected value" is quite helpfully chosen! 

The expected value is useful in comparison with the expected value of other risks. You can compare the expected value of risks and prioritize them. 

Also, mitigation costs can also be explored in comparison to the reduction of expected value. If a mitigation is more expensive than the reduction of a risk - it may not worth mitigating.

Explained similarly: The expected value of coming up heads on a coin flip is 50%, which can either be calculated or simulated.


### Probability
The probability (`p`) of an event could come from a variety of places. Let's use an example scenario of a fire taking place at a chosen museum next year.

Where would we gather a probability of this happening for use in analysis? The answer takes some creativity and some resourcefulness. There may be statistical data on fires at museums you could manually collect. Maybe the insurance company provides their estimate based on claims data. Perhaps risk managing employees at the museum perfomed a study and were [elicited](/docs/estimation/expert-elicitation) for a probability.

You'll notice from these examples that probability is _subjective_! Even if we were to statistically calculate a likelihood from a useful dataset, it would still be up to us (the subject) to choose this indirect measurement as representative of a future probability. Accepting this data allows this data to suggest furture performance, when we already know that past results do not guarantee future performance. 

Probability used this way is considered a _measure of evidence or belief_, rather than a certification of future outcomes.

Probabilities must follow the [probability axioms](https://en.wikipedia.org/wiki/Probability_axioms). You'll find more formal definitions elsewhere, but they're explained here for context in risk modeling.

**First axiom**:  A probability has to be a non-negative real number.
- It's not possible to be _infinity percent sure_ of something, right?
- Similarly, you can't be -5% sure, either.

**Second axiom**: All of the events in the sampled space must equal 1. 
- Assume we're predicting the winner of the Super Bowl. The combined odds of all of the candidates must equal one (`100%`). Since there's two teams involved, the sum of each victory probability must equal `100%`.
- If you're estimating some percentage of a system being exploited, then the other half must sum to 1. `5% Yes + 95% No = 100% `
- So, all potential outcomes in an experiment must equal one.
- Or looked at the other way around: All possible outcomes must divvy up (and exhaust) the `100%` odds. No leftovers!

**Third axiom**: For all events in a sampled space that are mutually exclusive, the result of their sum should equal their union. 

In more simple english, imagine a deck of cards. There are no "Kings" that are "Queens", because the face cards are mutually exclusive. No card is both a King and a Queen. 

So, the odds of a card being a King (1 in 13) can be added to the odds of being a Queen (also, 1 in 13) safely (2 in 13 odds of being a King OR Queen)

However, the odds of being a Heart and a King are not mutually exclusive, because they intersect with the King of Hearts which is simultanously both cards. 

So, you cannot cleanly add the odds of being a King (1 in 13) with the odds of being a Heart (1 in 4), because there is a single card that could be both. 16 cards would meet the criteria of being a King or a Heart in reality. If you broke this rule and treated them as mutually exclusive, you might count the King of Hearts twice, or not at all. This is a failure of quantitative risk modeling.

{{< alert icon="🚨" >}}
This axiom creates problems in real world risk measurement. Keep reading!
{{< /alert >}}

Enforcing this axiom (or ignoring it) creates weaknesses in probabilistic risk assessments. This property is something we work against in making broad risk models. 

In cyber security: We often make models that treat events as mutually exclusive when they are not. As an example: 

While it is _unlikely_ that an spearphishing APT group might work with an insider, these are not mutually exclusive events, and it's certainly not outside the realm of possibility that it could occur. 

We are easily suprised by what we see in the wild because it breaks our models, but our models may still be applicable as a proxy to organize efforts around them.

However, we will always operate with models (quantitative or not) and cannot escape them. Quantitative modeling is clear on where they can be improved and corrected, which is where it beats qualitative methods. Qualitative methods might have benefits covering complex scenarios, but may not have the same measurement capability. 

### Impact
Impact `i` represents losses. It could be as simple as a `i = 1` to represent an all or nothing event, like death. Or, it could the value of a bank account, the passengers on a plane... or from our previous example: The value of all art in a museum. 

However, impact is another probabilistic value with varying results. This will be covered in [distributions](/docs/risk/distributions). Here, let's consider the behavior of some cybersecurity impacts:

- The absurd variance involved in breach costs
- An under-the-radar incident compared to sustained headlines in the press
- Prolonged civil litigation, versus a quick settlement
- The amount of customers that may, or may not, churn from an incident.
- The amount of time fixing a vulnerability.

When impact is a simple value-at-rest, like a bank account... it can simply be represented by that value. When impact behaves probabilistically, we can resort to writing code as a [monte carlo](/docs/risk/monte-carlo) simulation.

It's OK to _assume_ that a scenario will take place and focus on studying its impact, just like it's OK to assume that an incident is bad enough to warrant a study of its causes.

## Risk in practice

While `r = p * i` is foundational to risk measurement, it is not always the focus of our studies. We focus more practically on certain aspects of risk due to our interests or limitations. We are often surrounded by factors that shape our ability to influence a risk.

-   Your time and resources available.
-   The skillsets you can contribute to a problem.
-   A short lived opportunity to mitigate a risk.
-   You, or your team\'s role in the mitigation

As such, you might find yourself with many available strategies that
have limitations associated with them. Or, you may be simply asked to
use a specific strategy arbitrarily.

Here is an example scenario:

{{< alert >}}
*The vault will be robbed during overnight hours, in Q2, resulting in
\$1M loss or greater.*
{{< /alert >}}

We face limitations as engineers that may hinder our ability to
influence either the likelihoods *or* impacts that compose a risk.

This limits the ability of engineers to influence risk when using
definitions of risk that attempt to strictly track the *Expected Value*
of a risk, since the Expected Value requires that both factors are
calculated.

{{< alert icon="👉">}}
The Expected Value of risk is equal to the product of its likelihood and
impact. For example, a 50% likelihood of a \$10 loss within a year has
an expected value of \$5 annually.
{{< /alert >}}

A fully rational approach to mitigating this risk would be to explore
options that reduce the Expected Value of this risk.

However, in reality, we may not be operating in a fully quantified
environment. For instance, we might be the company that manufactures the
walls of the vault. We don\'t get to know what will be stored inside of
our vaults, but we do know how likely a certain type of drill would
pierce the vault, given a certain amount of time.

Alternatively, we may be in charge of customer use of the vault. Maybe
this allows us to estimate the value of what is stored in the vault, but
aren\'t tasked with understanding the likelihood of it being stolen.

Indeed, many people involved with risk will need their own measurement
tooling before Expected Value can be considered.

There are plenty of examples where engineers will not be calculating the
full Expected Value of losses, but this does not limit their measurement
opportunity to help inform this value. It\'s important to recognize that
an engineer may be surfacing specific details for future management, and
that these values are useful.

These sorts of measurement limitations are common in engineering. This
documentation serves as guidance towards risk measurement in more
practical situations so that they can be useful with broader risk
management situations where expected values become useful while
informing a broad picture of risk, and the decision making associated
with it.

The world being as it is, the Expected Value of a risk is a desirable
thing to measure, but it is unreasonable to think that all participants
in risk mitigation will be fully concerned with it. Instead, we can
trust that efforts to mitigate a risk may reduce the Expected Value of a
loss, even if an engineer doesn\'t have the full picture measured.

## Uncertainty and Risk
_Uncertainty_ is a term that often comes up in risk measurement, and is often used interchangeably with probability. For example, the probability of some scenario occuring can be described as the uncertainty involved with that scenario.

However, there are interpretations of risk that distinguish risk from uncertainty, as [Knightian Uncertainty](https://en.wikipedia.org/wiki/Knightian_uncertainty). 

This interpretation of risk could certainly do us a favor and use different terminology. Nonetheless, the lessons drawn from this interpretation are important enough to cover for cybersecurity risk. It's important to note that very well read minds disagree with whether Knightian risk actually exists, but it is still a good model for discussing the information surrounding a scenario.

Through this lens, you can view a _risk_ as something that is deeply susceptible to measurement, and _uncertainty_ as something that is not. 

**Knightian Risk**

A game of [Russian roulette](https://en.wikipedia.org/wiki/Russian_roulette) can be considered a _Knightian risk_. Your odds are right there in the chamber; A six shooter has a 5 in 6 odds of survival, and 1 in 6 odds of ruin. Also, you can inspect the gun itself for flaws. A player can perform industrial radiography on the revolver and check for manufacturing flaws, and do the same with the bullet. Similar models can be tested for jams or other malfunctions. All said, Russian roulette can be a very well understood system to a potential player. However, knowing this system does not make the odds any favorable - it is still likely to be about 1 in 6, unless new information is found. Adding more resources and science to the study of the game does not make the game any more or less safe. 

**Knightian Uncertainty**

Spending the night in a _literally_ haunted house is an example of _Knightian Uncertainty_. You'd be unfamiliar with the houses inner-hauntings. You'd not have about previous victims who have survived a night in the house. Perhaps you only have some evidence of a terrifying event that took place that earned its reputation.

While this is a humorous example, you can tell that scientific approaches are more difficult in this scenario, not cost efficient, or not invented yet. Until the scooby-doo crew comes in and reveals the inner workings of the haunted house, A rigorously studied probability is not available to make a decision about whether to stay in a haunted house or not. Someone could, perhaps, make a forecast about a life-or-death scenario within the house, but it will likely have a lot of noise between different individuals making the forecast as there is likely no statistical anchor between them.

### Knightian application to Cyber-Security
A useful interpretation of Knightian risk for cybersecurity is to discuss how much inspection or research is available for a certain scenario. There are obviously areas of cybersecurity that are deeply covered with measurement opportunities: audits, detection, logging, red teaming and all sorts of other analysis. These can be viewed as efforts that moves risks farther on a spectrum from _unknown_ to _known_, and are more abundant in networks and areas that we control, or are well resourced.

However, there are risks that do not have similar opportunities. These risks are more difficult to transition into more _knowable_ problems. For instance:

- The security of your vendors may only be understood through a questionnaire. 
- The machinations of your adversaries intentions may never be fully known.
- After an acquisition, the possibility of an existing breach can't be fully eliminated.

Even well traveled, open source, and heavily tested code can have [risks](https://googleprojectzero.blogspot.com/2021/12/this-shouldnt-have-happened.html), so this is not to say that either side of Knightian interpretation is preferrable. Rather, we should be sensitive to the amount of study that has occurred behind the risks we are making decisions about, and value opportunities to measure risks that are hard to reach.

Decision making should take into account the understanding of risks that lack appropriate study, versus well studied risks. See [Decision Standards](/docs/enterprise/decision-standards) for thoughts on incorporating this level of rigor into a decision.