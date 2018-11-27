Tutorials
=========
The following tutorials are quantitative risk methods with the least amount of rigor.

All risk measurement must start somewhere, and this tutorial represents the earliest examples of scenario measurement. (See :doc:`/risk/scenarios`)

These example scenarios and their forecasts are similar to using your shoe to measure "one foot". Low rigor measurements are still useful for day to day, "back of envelope" risk modeling with low cost and effort. They can easily be expanded upon as requirements demand more rigor. (See :ref:`rigor`)

.. _Risk Analysis:

Risk Analysis
-------------
In this example, we are concerned with a single risk. First, we develop a :doc:`scenario </risk/scenarios>`.

Scenario
  A bank robber threatens a teller next quarter.

Outcome
  ``% Likelihood of Yes / No:``

This meets the criteria of a scenario by including an observable event ("A bank robber threatens a teller"), and includes a specific timeframe ("Next Quarter"). Without either of these, we lose our ability to quantify risk.

The observable judgment criteria could be established by bank's security team declaring the incident, or maybe the creation of a police report. We would just need to trust that our criteria would offer us a stable, observable event.

The forecaster who is asked to measure the risk would then assign a likelihood to "Yes" or "No". (See: :ref:`forecasting`)

As an example, we'll say that the forecaster believes that "Yes" has a likelihood of ``5%``, which would estimate an occurrence of every five years.

This documentation does not dictate how they arrive at an estimation of ``5%``, but we could assume that perhaps they are drawing upon experience, perhaps have law enforcement or industry data, or maybe are comparing to how often *any crime at all* happens at the bank, and further specifying from there. If the rigor of this information gathering needed to be improved, requirements could be added to the process. (See: :ref:`Rigor`)

That is an example of risk analysis done quickly and simply.

Risk Assessment
---------------
In this example, we are concerned with gathering, and comparing more than one risk.

In our example, let's say that a CEO has asked us to assess the risks that they will become infected with a virus on their laptop. For sake of an example, let's say that after extensive brainstorming, we came up with only two possible scenarios.

We develop two :doc:`scenarios </risk/scenarios>`:

Scenario A
  A malicious insider employee infects our CEO's laptop with a virus next quarter.

Scenario B
  A malicious website infects our CEO's laptop with a virus next quarter.

Outcome (A, B)
  ``% Likelihood of Yes / No:``

We have two scenarios with similar outcomes (The CEO gets a virus), but differing threats (A malicious insider or a malicious website). Both share a similar timeframe.

We would perform a :ref:`Risk Analysis` on both of these scenarios. Given that they are similar, a forecaster would likely rely on some useful data that informs both forecasts.

As an example, let's say the forecaster believes that Scenario A has a "Yes" likelihood of ``1%`` (and "No" of ``99%``), while Scenario B has a likelihood of Yes of ``35%`` (and "No" of ``65%``).

Those likelihoods, would indicate that the forecaster believes Scenario B (a malicious website) to occur a bit more than annually (every 2.8 quarters), while an insider employee would occur once every twenty five years (every 100 quarters).

Under the assumption that the "virus" is equally bad in both cases, we can numerically compare both of these risks, and focus efforts on the more likely scenario.

Risk Management
---------------
In this example we are concerned with mitigating our risks over time, with our efforts and resources.

Let's use our first scenario from Risk Analysis again. In that example, our forecaster assigned a 5% likelihood to the following scenario:

Scenario
  A bank robber threatens a teller next quarter.

Outcome
  ``% Likelihood of Yes / No:`` Yes 5%

Imagine if the bank wasn't OK with this level of risk to their employees, and decided to invest in a mitigation, like an armed guard near the tellers. Maybe they make this decision because other banks in the area don't have an armed guard, making the guarded bank the least attractive target.

Assume that this information is valuable to the forecaster. Given that no other substantial information has changed regarding the risk, they would forecast again next quarter, let's say at 3%, a reduction of 2% from the original 5%.

If these assumptions weren't correct, and for some reason this mitigation increased risks in the mind of the forecaster, then it would reflect itself with an increasing likelihood in the measurement.
