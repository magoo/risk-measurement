Tutorials
=========
The following tutorials are quantitative risk methods with the least amount of rigor. (See :ref:`rigor`)

Low rigor measurements are still useful for day to day, "back of envelope" risk modeling with low cost and effort. They can easily be expanded upon as requirements expand.

As an organization becomes involved with extraordinary risk, it would take efforts to bolster these methods with the methods described in the documentation.

Risk Analysis
-------------
In this example, we are concerned with a single risk. First, we develop a :doc:`scenario </risk/scenarios>`.

.. admonition:: Scenario
  :class: warning

  A bank robber attempts robbery to one of our tellers next quarter. (Yes / No)

This meets the criteria of a scenario by including an observable event, and includes a specific timeframe.

The observable judgement criteria could be the bank's security team, or the creation of a police report.

The forecaster who is asked to measure the risk would then assign a likelihood to "Yes" or "No".

As an example, we'll say that the forecaster believes that "Yes" has a likelihood of 5%, which would estimate an occurrence of every five years.

That is an example of risk analysis done quickly and simply.

Risk Assessment
---------------
In this example, we are concerned with gathering, and comparing more than one risk.

In our example, lets say that we are assessing the risks involved with our CEO getting a virus on their laptop based on their request for an assessment.

In this case we will use two similar scenarios, and we'll just have to pretend that these were all the scenarios found in a risk discovery effort.

We develop two :doc:`scenario </risk/scenarios>`.

.. admonition:: Scenario
  :class: warning

  A: A malicious insider employee infects our CEO's laptop with a virus next quarter. (Yes / No)

.. admonition:: Scenario
  :class: warning

  B: A malicious website infects our CEO's laptop with a virus next quarter. (Yes / No)

We have two scenarios with similar outcomes (The CEO gets a virus), but differing threats (A malicious insider or a malicious website). Both share a similar timeframe.

We would perform a Risk Analysis on both of these scenarios. Given that they are similar, a forecaster would likely rely on useful data for both.

As an example, let's say the forecaster believes that Scenario A has a "Yes" likelihood of 1%, while Scenario B has a likelihood of 35%.

This example would indicate that the forecaster believes Scenario B (a malicious website) to occur about annually, while an insider employee would occur once every twenty years.

Under the assumption that the "virus" is equally bad in both cases, we can numerically compare both of these risks.

Risk Management
---------------
In this example we are concerned with mitigating our risks over time, with our efforts and resources.

Let's use our first scenario from Risk Analysis again. In that example, our forecaster assigned a 5% likelihood to the following scenario:

.. admonition:: Scenario
  :class: warning

  A bank robber attempts robbery to one of our tellers next quarter. (Yes / No)

Imagine if the bank wasn't OK with this level of risk to their employees, and decided to invest in a mitigation, like an armed guard near the tellers. Maybe they make this decision because other banks in the area don't have an armed guard, making them the least attractive target.

Assume that this information is valuable to the forecaster. Given that no other substantial information has changed regarding the risk, they would forecast again next quarter, let's say at 3%, a reduction of 2% from the original 5%.

If these assumptions weren't correct, and for some reason this mitigation increased risks in the mind of the forecaster, then it would also
