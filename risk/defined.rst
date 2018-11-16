Problems
========
The term "risk" is problematic and this documentation favors the :doc:`scenario </risk/scenarios>` instead.

That said, it is still important to understand the complexity of "risk" to effectively use this documentation.

Understanding these complexities improves our ability to create scenarios that better represent our intentions than trying to argue for a specific "risk" definition.

We'll discuss the varying uses of the term, and the varying goals we have concerning risk.

`Sven Ove Hansson`_ describes risk with many definitions:

  1. An unwanted event which may or may not occur.
  2. The cause of an unwanted event which may or may not occur.
  3. The probability of an unwanted event which may or may not occur.
  4. The statistical expectation value of an unwanted event which may or may not occur.
  5. The fact that a decision is made under conditions of known probabilities (“decision under risk” as opposed to “decision under uncertainty”)

.. _Sven Ove Hansson:  https://plato.stanford.edu/archives/fall2018/entries/risk/

It is not difficult to find other uses in the wild!

  - The lack of obvious mitigations ("*Driving without a seatbelt is a risk*")
  - An amount of property at stake ("*We have too much risk in volatile investments*")
  - General expressions of fear. ("*This feels pretty risky...*")

There are obviously consistent themes involved with all of these definitions. They all relate, somehow, to the likelihood of a future event, or the impact of a future event, or both.

Risk in practice
----------------
You are likely surrounded by a variety of factors that compose or limit your ability to influence a risk.

- Your time and resources available.
- The skillsets you can contribute to a problem.
- A short lived opportunity to mitigate a risk.
- You, or your team's role in the mitigation

As such, you might find yourself with many available strategies that have limitations associated with them. Or, you may be simply asked to use a specific strategy arbitrarily.

Here is an example scenario:

.. admonition:: Scenario
  :class: warning

  *The vault will be robbed during overnight hours, in Q2, resulting in $1M loss or greater.*

We face limitations as engineers that may hinder our ability to influence the either the likelihoods *or* impacts that compose a risk.

This goes against definitions of risk that attempt to strictly track the *Expected Value* of a risk, which demand that both factors are calculated.

.. note::
  The Expected Value of risk is equal to the product of its likelihood and impact. For example, a 50% likelihood of a $10 loss within a year has an expected value of $5 annually.

A fully rational approach to mitigating this risk would be to explore options that reduce the Expected Value of this risk.

However, in reality, we may not be operating in a fully quantified environment. For instance, we might be the company that manufactures the walls of the vault. We don't get to know what will be stored inside of our vaults, but we do know how likely a certain type of drill would pierce the vault, given a certain amount of time.

Alternatively, we may be in charge of customer use of the vault. Maybe this allows us to estimate the value of what is stored in the vault, but aren't tasked with understanding the likelihood of it being stolen.

Indeed, many people involved with risk will need their own measurement tooling before Expected Value can be considered.

There are plenty of examples where engineers will not be calculating the full Expected Value of losses, but this does not limit their measurement opportunity to help inform this value. It's important to recognize that an engineer may be surfacing specific details for future management, and that these values are useful.

These sorts of measurement limitations are common in engineering. This documentation serves as guidance towards risk measurement in more practical situations so that they can be useful with broader risk management situations where expected values become useful while informing a broad picture of risk, and the decision making associated with it.

The world being as it is, the Expected Value of a risk is a desirable thing to measure, but it is unreasonable to think that all participants in risk mitigation will be fully concerned with it. Instead, we can trust that efforts to mitigate a risk may reduce the Expected Value of a loss, even if an engineer doesn't have the full picture measured.

Conclusion
----------
As engineers, we must work to influence the likelihoods and impacts associated with a well defined future event. We do not always need to measure both, but we'd like to eventually. First, we need to measure that our individual efforts are making a difference.

We can focus and target these areas of risk by defining them as :doc:`scenarios </risk/scenarios>`.

Further Reading
~~~~~~~~~~~~~~~
See :ref:`Defining Risk`
