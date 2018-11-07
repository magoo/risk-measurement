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
You are likely surrounded by a variety of factors that compose your ability to influence a risk.

- Your time and resources available to contribute.
- The skillsets you can contribute to a problem.
- An short lived opportunity to mitigate a risk.

As such, you might find yourself with many available strategies that have varying limitations associated with them.

Here is an example scenario:

.. admonition:: Scenario
  :class: warning

  *The vault will be robbed during overnight hours, in Q2, resulting in $1M loss or greater.*

In selecting engineering tasks that risk, our limitations as engineers may contain our ability to influence the likelihoods *or* impacts that compose the risk.

This goes against definitions of risk attempt to track the *Expected Value* of a risk, which demand that both factors are calculated.

.. note::
  The Expected Value of risk is equal to the product of its likelihood and impact. For example, a 50% likelihood of a $10 loss within a year has an expected value of $5 annually.

However, we *may not want to measure both*!

In our example vault was in a bank, the "losses" may be obvious. But what if artwork is in the vault? What about a softer subject, like, reputation? For instance, you may try to reduce the overnight holdings of the bank vault (impact). You may install a thicker vault to prevent robbery (likelihood). It's common to be limited to solutions that focus on one component of risk and not the other.

Both of these impact the expected value of a loss. You can still work on these independent factors and trust that an expected value is being influenced positively.

In some cases, an organization may be *very intentionally* increasing one factor or another. For instance, a business may be trying to collect as much artwork as possible, and limiting this operation may be counterintuitive to the business.

The world being as it is, the expected value of a risk is a desirable thing to measure, if it is reasonable to do so. We can trust that efforts to mitigate a risk may reduce the Expected Value of a loss, even if we don't have the full picture measured.

Conclusion
----------
As engineers, we must work on estimations of well defined likelihoods or impacts. We do not always need to measure both. First, we need to measure the targets of our efforts.

We can focus and target these areas of risk by defining them as :doc:`scenarios </risk/scenarios>`.
