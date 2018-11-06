Scenarios
=========

In our discussion about :doc:`risk </risk/defined>` we discussed the *likelihood* and *impact* of a future event.

A point of failure in measurement is ambiguity about a risk problem being solved. A group of very smart people can spin in circles discussing a risk if they don't pin a specific outcome down first.

To do this, we explicitly define a risk with a *scenario*, which is an unambiguous statement about a future value or event. These statements should make the author sweat.

.. note::
  Read up on `The Clarity Test`_ to better understand the standard a good scenario should meet.

.. _The Clarity Test: https://en.wikipedia.org/wiki/Clarity_test

Here's a batch of examples:

.. admonition:: Scenario
  :class: warning

  The house burns down *next quarter*.

.. admonition:: Scenario
  :class: warning

  An earthquake has destroyed one of the three critical bridges *this year*.

.. admonition:: Scenario
  :class: warning

  We are named in a headline lawsuit in a major publication *within the next three months*.

You may have heard of this format for a risk before!

Many industries advocate for the *tabletop scenario* as a way to encourage brainstorming and better understanding of risks.

Scenarios are directly compatible with these activities, as they are simply scenarios without a timeframe. In a tabletop, you generally role play that a scenario has already happened.

Always include a specific timeframe.
------------------------------------
We must include a specific timeframe with our scenario if we want to forecast against it. A risk can be viewed completely differently if it described as something happening tomorrow, or within the next ten years.

View scenarios as a hierarchy.
------------------------------
A scenario has ties to `Fault tree analysis`_, whereas higher level outcomes (the top of a tree) relate to more specific events (the branches of a tree).

A specific example, a meltdown event at a nuclear facility is a scenario we'd like to avoid.

.. admonition:: Scenario
  :class: warning

  A core damage event releases nuclear material into the environment *this year*.

This scenario could be caused by a variety of issues that are far less vague and more specific.

.. admonition:: Scenario
  :class: warning

  A tsunami has flooded the power station and caused a loss of pressure in cooling systems, resulting in core damage and a release of nuclear material into the environment *this year*.

This is described as "decomposition" of a risk. It is a form of flexibility that allows you to be more or less specific and target more narrow measurement or wide view measurement. The former scenario would attract far more root causes that could cause a core damage event, while the latter scenario is highly dependent on factors like the weather and the resiliency of cooling systems.

.. _Fault tree analysis: https://en.wikipedia.org/wiki/Fault_tree_analysis

In :doc:`Enterprise </enterprise/index>` this aspect of scenarios-informing-scenarios is used to inform larger organizational approaches to risk.

Choosing your "judgement" criteria
----------------------------------
