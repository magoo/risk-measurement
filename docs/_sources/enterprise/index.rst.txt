Organizing Risks
================
Instead of focusing on a single individual, this section of documentation focuses on how a group of individuals would mitigate a risk in unison.

From the :doc:`principles </principles>` of this documentation, a single engineer working in isolation should be capable of measuring risk. They would do this by creating scenarios that describe their risks and forecasting its outcomes.

Organizations are likely to have lots of varying activities in flight that generate wildly different forms of risk. Let's take for instance, a rocket ship. Entirely different organizations and skillsets may be building the rocket, the hull, and the electronics used by astronauts.

Despite the variance in all of these disciplines, we still need to measure the likelihood that a "mission to mars" will succeed without failure.

One of the first concepts to understand when discussing large efforts around risk is the concept of "rigor" as it applies to risk measurement.

.. _rigor:

Rigor
=====


The expectation of "rigor" in measurement.
------------------------------------------
Carl Sagan once said "Extraordinary claims require extraordinary evidence". For us, extraordinary decisions follow the same principle.

A decision to launch a rocket ship is not one to be taken lightly, nor would you expect it to be the sole decision of a single individual.

Leadership can require that a "Launch" decision meet certain requirements that defend it against negligence, cognitive error, corruption, imaginative failures, or gaps of evidence. Some examples will be listed here, and extrapolated in the continuing documentation:

- Risks are decomposed into a register by the individuals mitigating them.
- Forecasts are gathered by individuals who have been calibration trained.
- Forecasters have a determined track record with Brier scores meeting a specific threshold. (See: :ref:`keeping score`)
- Historical data was sought out and modeled with frequentist approaches to inform forecasting.
- Measurement of "unknown" factors were a part of forecasts.
- A panel of individuals were relied on instead of a single individual.
- The panel included outside expertise.
- Monte Carlo and uncertainty modeling was available to experts.

Requiring effective forecasters.
------------------------------------------
After a certain amount of practice or calibration training, a decision maker can exclude forecasters with regularly poor calibration, or not meeting a threshold Brier Score. (See: :ref:`keeping score`)

.. _whistleblowing:

Whistleblowing and Complaints.
------------------------------------
Some industries have created, and enforce, whistleblower regulation to protect channels that would surface risks or other failures. (See: `NRC Whistleblower Protection`_)

.. _NRC Whistleblower protection: https://www.nrc.gov/insp-gen/whistleblower.html

Decision makers knowing that these channels exist which could question the integrity of risk measurement may find greater certainty in the information brought to them when issues are not surfaced.

The quality of these channels can also be measured, and if distrust of these channels exists, it can also be mitigated.

Decomposition of risk into a register.
------------------------------------------
Given our familiarity with :doc:`scenarios </risk/scenarios>`, we understand that a natural hierarchy forms as we add conditions to a scenario.

For instance, "My house burns down tomorrow" is inherently more likely than "My house burns down tomorrow due to a grease fire". The former scenario inherently includes the conditions of the second scenario.

This aspect of scenario building is important for a chief decision maker who may decide to "Go!" a space launch. They'll need to be informed by the likelihoods of failure in several areas that could cause the mission to fail, like a rocket explosion, a hull failure, or an failure in electonic life support systems.

This can be simply modeled with simple "OR" logic operations in a spreadsheet. Visually: ::

                         ┌─────────────────────┐
                         │   Mission Success   │
                         └─────────────────────┘
                                    │
             ┌──────────────────────┼──────────────────────┐
             │                      │                      │
             ▼                      ▼                      ▼
  ┌─────────────────────┐┌─────────────────────┐┌─────────────────────┐
  │   Rocket Failure    ││     Hull Breach     ││ Electronic Failure  │
  └─────────────────────┘└─────────────────────┘└─────────────────────┘

Thus, these three example issues would be three scenarios:

- "The mission has failed due to a rocket failure. (Yes / No)"
- "The mission has failed due to a hull compromise. (Yes / No)"
- "The mission has failed due to an electronic failure. (Yes / No)"

As aerospace engineers approach a launch date, they could forecast outcomes based on proposed dates. These dates may allow for more or less testing, training, discovery of issues, etc. ::

  ┌────────────────────┐┌────────────────────┐┌────────────────────┐
  │     JAN Launch     ││     FEB Launch     ││     MAR Launch     │
  └────────────────────┘└────────────────────┘└────────────────────┘
  ┌────────────────────┐┌────────────────────┐┌────────────────────┐
  │Rocket Failure: 1%  ││Rocket Failure: .1% ││Rocket Failure: .01%│
  └────────────────────┘└────────────────────┘└────────────────────┘
  ┌────────────────────┐┌────────────────────┐┌────────────────────┐
  │Hull Breach: 1%     ││Hull Breach: .1%    ││Hull Breach: .01%   │
  └────────────────────┘└────────────────────┘└────────────────────┘
  ┌────────────────────┐┌────────────────────┐┌────────────────────┐
  │Elctrc Failure: 1%  ││Elctrc Failure: .1% ││Elctrc Failure: .01%│
  └────────────────────┘└────────────────────┘└────────────────────┘

A simple model like the above is relying on three independent probabilities which cannot be directly added. They are instead calculated with the `Inclusion / Exclusion Principle`_, however we can more easily estimate these values in a practical working environment using Monte Carlo software.

With either approach, we would have a likelihood of mission failure of about ``~2.9%`` in January, ``~0.29%`` in February, and ``~0.029%`` in March.

Proof of work
  Using the inclusion and exclusion principle, we estimate a total failure of any one of these issues causing the mission to fail.

  ``(.01 + .01 + .01) - (.01 * .01) - (.01 * .01) - (.01 * .01) + (.01 * .01 * .01) = 0.029701``

This is far easier to reproduce with a Monte Carlo simulation, which may require writing code or using statistics software, which this documentation will not cover.

.. _Inclusion / Exclusion Principle: https://en.wikipedia.org/wiki/Inclusion%E2%80%93exclusion_principle

With an approach like this, we can start to decompose a high level failure statement like "Mission Failure" into multiple areas of mitigation effort, or the discovery of new risks that influence failure.

This sort of delegation of risk can help decouple the prescription of risk mitigations from measurement. It allows the engineers focused on "rocket failure" to achieve their highest levels of certainty by any means, as opposed to following a prescribed checklist mandated by a leadership team.

.. _monte carlo:

The Monte Carlo simulation
------------------------------------------
To properly estimate the likelihood of mission success for January, February, or March, you would likely use a Monte Carlo simulation. A Monte Carlo approach to this problem depends on randomized trials to estimate outcomes.

Let's estimate the likelihood of any failure in January. If *any* condition (Rocket, hull, or electric failure) occurs, the entire mission fails. In pseudocode: ::

  rocket_failure = rand()
  hull_breach = rand()
  electric_failure = rand()

  failure = OR(rocket_failure < .01, hull_breach < .01, electric_failure < .01)

Each value would be the result of a `rand()` value. Run many thousands of times, you would find the average result of *failure*. We'd see a ``2.9%`` chance of mission failure in January, because it would be the average likelihood of three independent conditions with 1% likelihoods each.

As models become more complex, Monte Carlo tools allow for cheap models and estimation without attempting to "solve" for risk mathematically. Monte Carlo methods are a powerful tool to critically inspect assumptions about risk, help build models that support all known context about a risk, and introduce uncertainty for values that don't behave predictably.

Most importantly, the complex interactions between risks can be considered in Monte Carlo models. For instance, as the stresses increase for a ```hull_breach``, the likelihood of an ``electric_failure`` may increase as well, even before a ``hull_breach`` condition is met. Major disasters are known for having several root causes with complicated, deeply coupled interactions with complex systems, and Monte Carlo modeling helps capture these interactions.

Quarterly estimations of a risk might be common in a business setting. If there is a belief that a scenario could occur with a specific quarterly likelihood, it could help estimate an annual likelihood as well, and vice versa.

That said, a scenario with a 5% chance of occurring in a quarter may have a ~19% chance of occurring in a year, as there are four quarters in a year and four opportunities to occur during the year.

==================================  ==============================
Quarterly likelihood of Occurrence  Estimated Annual Occurrence (Monte Carlo)
==================================  ==============================
0.25%                               ~1.00%
0.5%                                ~1.99%
1%                                  ~3.94%
3%                                  ~11%
5%                                  ~19%
13%                                 ~41%
25%                                 ~69%
50%                                 ~94%
99%                                 ~100%
==================================  ==============================

These can be directly calculated with the `principle of inclusion / exclusion`_, but is generally easier to model risk with monte carlo methods.

.. _principle of inclusion / exclusion: https://en.wikipedia.org/wiki/Inclusion%E2%80%93exclusion_principle



Panels of Forecasters
------------------------------------------
Groups of forecasters seem to benefit from the "Wisdom of Crowds" effect, and research has suggested that simple averages across multiple perspectives will have a debiasing effect on a forecast and generally improve effectiveness.

This is seen in practice with `ensemble forecasting`_ in meteorolgy.

Philip Tetlock's research into forecasting teams suggests that diversity in perspective also improves the effectiveness of forecasts.

.. _ensemble forecasting: https://en.wikipedia.org/wiki/Ensemble_forecasting

There does not need to be much to the elicitation of experts on a panel, but there are more formal approaches of panel estimations like the `Delphi Method`_.

.. _Delphi Method: https://www.rand.org/topics/delphi-method.html

Panels also reduce the risk of bias towards defensive decision making, as a single individual may not even be identified in the decision as the sole actor to go forward with a decision.

Protecting against a low quality risk assessment.
--------------------------------------------------
You may want to apply efforts to measure the significance of remaining scenarios that were never identified.

It is highly likely that other scenarios may cause a space mission to fail, outside of the three we identified. To ensure that assessment of risk was thoroughly exhaustive, we can sample for how likely "unknown" events may cause an event.

As an example, outside of a rocket failure, hull breach, or electronics failure... one could imagine a variety of reasons that a mission may not succeed.

Within the risk register, another node can be added: ::

                         ┌─────────────────────┐
                         │   Mission Success   │
                         └─────────────────────┘
                                    │
             ┌──────────────────────┼──────────────────────┬───────────────┐
             │                      │                      │               │
             ▼                      ▼                      ▼               ▼
  ┌─────────────────────┐┌─────────────────────┐┌─────────────────────┐┌───────┐
  │   Rocket Failure    ││     Hull Breach     ││ Electronic Failure  ││   ?   │
  └─────────────────────┘└─────────────────────┘└─────────────────────┘└───────┘

If there the *other* ("?") category has an undesirable value to leadership, it may call for more rigorous risk assessment methods to identify further scenarios to measure.

An anonymous panel may be necessary in cases where individuals feel uncomfortable surfacing a previously un-measured risk.

Decision Standards
==================

An organization can create "levels" of rigor associated with important risks. Here are some example thoughts on organizing the appropriate amount of rigor for a decision.

These "levels" do not belong to any standard in particular - instead, they show how decision making effort can be wrapped into a requirement.

.. note::
  For a real-world example, see `NASA-STD-7009`_

.. _NASA-STD-7009: https://standards.nasa.gov/standard/nasa/nasa-std-7009

Level Zero
  A single individual estimate.

Level One
  A estimate from a single individual who has received risk training, with reasonable access to reference classes or specific historical data.

Level Two
  In addition to previous levels, this estimation is from an individual who is calibration trained (See: :ref:`calibration`) and has maintained a Brier score under *.4*. (See :ref:`keeping score`)

Level Three
  In addition to previous levels, a panel of three or more calibrated individuals were involved with this estimation.

Level Four
  In addition to previous levels, an external expert was involved with the estimation.

Such levels can be created that map to an organizations necessary decisions, depending on the decision making resources available and the stakes involved with the decision.

Further Reading
---------------

See :ref:`Expert Groups`, :ref:`Cognitive Error`, :ref:`Industry`
