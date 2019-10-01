Key Performance Indicator
===============================
KPIs are selected by leadership. They represent a leadership opinion that the values they elevate will correlate with some notion of *success*.

The hope is that an organization will increasingly adopt behavior that favorably influences these KPIs.

KPI as an organizational metric
-------------------------------
An engineering organization will engage in activities that discover risk :doc:`scenarios </risk/scenarios>` and mitigate them.

The difficulty is that completely different engineering disciplines may be engaged in preventing similar outcomes. These organizations may think that their efforts should be measured and managed differently than one another.

This is true. However, varying disciplines will still contribute to some notions of risk. For instance, a team focused on software errors and a physical security team at a datacenter may both concerned with the confidentiality of data.

Both organizations may track incidents with a qualifier like SEV_  or P0_. Should either of them see a failure putting the confidentiality of data at risk, both of them may declare a ``SEV0`` for instance.

.. _SEV: https://response.pagerduty.com/before/severity_levels/

.. _P0: https://blogs.msdn.microsoft.com/willy-peter_schaub/2009/10/22/getting-your-priorities-right-p0-p1-p2/

During a retrospective analysis, both would be judged as a failure to assure confidentiality.

An organization with consistent incident management can have multiple risk organizations contribute to the :ref:`decomposition <decomposition>` of a single, probabilistic measure. A failure can occur in organizations with differing subject matter and ultimately result in the same undesirable scenario.

Protecting a KPI from cultural toxicity
---------------------------------------
KPIs are subject to `organizational toxicity`_ whether they are objectively measurable or approximated through expert elicitation. An organization should avoid "risk" being overly valued as the individual performance measure.

.. _organizational toxicity : https://en.wikipedia.org/wiki/Goodhart%27s_law

Instead, a performance management focus on the completion of activities that measure, discover, and mitigate risk is more attractive for performance assessment. These contributions should be viewed independently of the risk measure.

Otherwise, the measurement methods themselves may be manipulated in an attempt to eliminate risk artificially.

An organization that aspires to have a reliable measure of risk will see efforts to :ref:`reliably forecast <keeping score>` risk while simultaneously reducing it.
