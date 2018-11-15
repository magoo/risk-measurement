.. risk-rtd documentation master file, created by
   sphinx-quickstart on Mon Oct 22 13:10:32 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Simple Risk Measurement
=======================

:doc:`Simple Risk Measurement </index>` is written to help you measure complicated risks using a process that's simple enough to work out on the back of a napkin and powerful enough to organize a rocket launch.

.. note::
  In draft. Please send feedback to @magoo

If you are motivated by risk problems and are frustrated by how difficult they are to measure, you may find this documentation useful. Simple Risk Measurement can get you started towards a comprehensive and scientific approach to risk. It is designed to enhance subject matter experts who work with risk, especially those who mitigate complex risks on an ongoing basis.

See :doc:`risk </risk/defined>` to better understand the risk problem in engineering.

How does it work?
------------------------------------------
This approach is very simple to trivialize into a few steps. Once introduced into your industry, it will feel far more sophisticated.

1. **Define a risk scenario**: A well defined, undesirable future event that we want to measure.
2. **Gather the evidence**: We gather facts, reference classes, models, experiences, and opinions.
3. **Estimate the outcomes**: We estimate of the probabilities / impacts the scenario may have.
4. **Make a decision**: We make decisions with this information, and measure again if needed.
5. **Keep Score**: As outcomes occur, we check our work, improve our methods and reduce our uncertainty.

For example:
  ``The Cubs win the 2025 World Series (Yes / No)`` may be a future *scenario* you care about.

  You may gather *evidence* by reviewing historical baseball data, interviewing experts, or building statistical models. You would then *estimate* a likelihood based on that information, and make *decisions* based on that information.

  With little effort, for example and entertainment purposes, this author prepares a ``2.5% Yes`` forecast, based on a starting point of ``1/30`` teams in the MLB (``3%``). The author observes that other teams more often win the World Series, a World Series might not happen at all, and the author holds an irrational and indefensible belief in the `Curse of the Billy Goat`_ reducing this forecast further.

  With greater evidence, time, and additional expert opinions, this documentation suggests methods to make this forecast increasingly rigorous, *defending against cognitive bias* and introducing knowledge. This can result in a a more reliable value than an expert opinion that qualitatively states "They probably won't win in 2020" which can not be leveraged by scientific measurement or as an engineering approach.

.. _Curse of the Billy Goat: https://en.wikipedia.org/wiki/Curse_of_the_Billy_Goat

How does this help me?
------------------------------------------

You may be enthusiastic about some of the following risk problems:

Is a risk worth mitigating?
  We can gather quantitative data that informs decisions to invest in a mitigation, (or not).

Has a specific risk gotten better or worse?
  We can measure a risk over time and observe differences if it is being mitigated (or not).

Which mitigation option(s) should we choose?
  We can measure many mitigation options and compare them quantitatively.

How do we measure many risks?
  We can organize many risks that are being measured and use them to inform broader risks.

Have we spent enough time identifying new risks?
  We can measure if further risk assessments are likely to reveal new risks, (or not).

What doesn't this do?
---------------------
This method is *industry agnostic*. This creates very helpful limitations that, hopefully, improves its accessibility.

This documentation does not prescribe:

1. The evidence or statistical methods that must be organized for estimation.
2. The scenarios you should create for your risks.
3. The mitigations you should apply to your risks.

This method does prescribe creativity in your efforts, within a method that allows quantification.

There is always something to measure.

.. include:: toc.rst
