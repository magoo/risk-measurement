.. highlight:: none

Scenarios
=========

We use **scenarios** to specifically define future events that we'd like to measure. This must happen before we forecast its outcomes. (See :ref:`Forecasting`)

In our discussion about :doc:`risk </risk/defined>` we discussed the *likelihood* and *impact* of a future event.

A point of failure in measurement is ambiguity about a risk problem being solved. A group of very smart people can spin in circles discussing a risk if they don't pin a specific outcome down first.

To do this, we explicitly define a risk with a *scenario*, which is an unambiguous statement about a future value or event. These statements should make the author sweat.

A scenario can have multiple *outcomes* to be estimated. For instance, an explosion may have costs, a loss of life, and periods of time before normalcy can be regained. That would be a single scenario with three outcomes to be estimated.

.. note::
  Read up on `The Clarity Test`_ to better understand the specificity a good scenario, or outcome, should meet.

.. _The Clarity Test: https://en.wikipedia.org/wiki/Clarity_test

Here's a batch of examples:

**Scenario** ::

    The house burns down next quarter.

**Scenario** ::

  An earthquake has destroyed one of the three critical bridges this year.

**Scenario** ::

  We are named in a headline lawsuit in a major publication within the next three months.

You may have heard of this format for a risk before!

It should be familiar because many industries advocate for the `tabletop scenario`_ as a way to encourage brainstorming and better understanding of risks.

.. _tabletop scenario: https://www.ready.gov/business/testing/exercises

The scenarios we create are closely related with these activities. They can easily be explored in a tabletop environment.

Always include a specific timeframe.
------------------------------------
We must include a specific timeframe with our scenarios. A risk can be viewed completely differently if it described as something happening tomorrow, or within the next ten years. Discussing scenarios without specific timeframes will cause communication and prioritization issues.

View scenarios as a hierarchy.
------------------------------
A scenario has ties to the `Fault Tree`_ and `Tree diagram`_, whereas higher level outcomes at the top of a tree aggregate the likelihoods of more specific events at the branches of a tree.

A specific example, a meltdown event at a nuclear facility is a scenario we'd like to avoid.

**Scenario A** ::

  A core damage event releases nuclear material into the environment this year.

This scenario could be caused by a variety of issues that are far less vague and more specific. For instance, the following **Scenario B** caused **Scenario A**, just mentioned above, in the Fukishima disaster.

**Scenario B** ::

  A tsunami has flooded the power station and caused a loss of pressure in cooling systems,
  resulting in core damage and a release of nuclear material into the environment this year.

This is described as "decomposition" of a risk. It is a form of flexibility in scenario building. With this flexibility, one could target broad failures, or more narrow ones, by being more or less precise with language . The former **Scenario A** would include the likelihood of many possible root causes that could cause a core damage event. The latter **Scenario B** is more narrowly dependent on factors like the weather and the resiliency of cooling systems.

.. _Fault tree: https://en.wikipedia.org/wiki/Fault_tree_analysis

.. _Tree diagram: https://en.wikipedia.org/wiki/Tree_diagram_(probability_theory)

In :doc:`Enterprise </enterprise/index>` this aspect of scenarios-informing-scenarios is used to inform larger organizational approaches to risk.

A principle of scenario building (see: :ref:`Limitation`) is to assume that unknown scenarios may occur. Erring towards upward investment in a hierarchy of scenarios helps defend against "unknown" branches. The initiating events that create complex problems can sometimes not be predicted, and assuming large forms of failure can help prevent disaster.

We can use this flexibility to model risks and measure them. We can decompose a risk with greater resource and available effort, but not so much that we lose sight of our risks and become vulnerable to uncertainty that was not accounted for.

Outcomes and Judgments
----------------------------------
One issue in forecasting is deciding on the criteria that "closes" a forecast. For instance:

**Scenario** ::

  The Cubs win the World Series in 2020.

**Outcome** ::

  % Likelihood of Yes / No

This scenario is simple to judge, as you would likely respect the judgment of Major League Baseball to judge the outcome. Multiple outcomes can be mentioned as well. For instance:

**Outcome** ::

  90% Confidence interval of margin of victory (in runs scored)

**Outcome** ::

  % Likelihood the game went into extra innings (Yes / No)

It's perfectly OK to measure multiple types of outcomes related to a scenario, or have them expand upon the scenario with conditional circumstances ("Given that these condition occur...").

.. hint::
  You can estimate multiple types of outcomes or values. See: :ref:`Types of Forecasts`

It is important to identify how a scenario will be judged, if this is not obvious. The "judge" becomes part of the  forecast, and may influence the certainty of the forecasters if poorly chosen.

The judges that are selected to evaluate outcomes should be considered for their objectiveness to the outcome, and their lack of incentives to manipulate an outcome. In casual or workplace settings, it can be as simple as designating a team or individual to pass judgment on an outcome.

Judges could be given criteria on which to judge upon. For instance: "Judges will observe official MLB scorecards 24 hours after competition".

If there is concern that a Black Swan may invalidate the forecast, it is best to make sure the forecastable outcomes include "other" circumstances. For instance "The Cubs Win / The Cubs Lose / Other". This would allow you to factor in Wrigley Field exploding, a sudden players strike, or other unknowns.

Additionally, decisions can reverse. Having a scenario that mitigates the flip-flopping of an outcome will help specify forecasts. For instance, a headline that "The MLB has ruled against the Cubs in a cheating investigation, retracting their title". A specific scenario may dictate that the MLB's official stance 24 hours after competition matters. Or, a week, or a month, or a year, etc.

This sort of specificity with long timeframes has an operational impact. You won't get data until they officially "expire", and would only be left with preliminary judgment until the scenario expires and data is confirmed.

The reliability of judgment can also be bolstered to decision makers if included in whistleblowing policy or professional codes of conduct. (See: :ref:`whistleblowing`)

Higher quality judgment should *always* be desired by engineers. Back-of-napkin risk assessment, with the lowest standard rigor (See: :ref:`Rigor`), are generally self-judged, but will likely need greater rigor for organizational decision making.

Further Reading
~~~~~~~~~~~~~~~
See :ref:`Specific Scenarios`
