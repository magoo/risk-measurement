.. highlight:: None

Measurement
===========
We often use instruments to measure things. For instance, a ruler to measure the size of a table. However, we rely on estimation when instruments do not exist for our area of measurement.

Ultimately, it is well understood that all forms of measurement are, in essence, an approximation_. This is well discussed both in philosophy and more practically in `international standards`_.

.. _approximation: https://plato.stanford.edu/entries/measurement-science/
.. _international standards: https://en.wikipedia.org/wiki/Joint_Committee_for_Guides_in_Metrology

As an example, any weight scale you might own is likely calibrated to an approximation of many intermediary approximations to a "`international prototype`_" stored in an underground vault in France.

.. _international prototype: https://www.bipm.org/en/bipm/mass/ipk/

In risk, we are concerned with future events and their impacts. No instrument exists that can *directly* measure future events. As a result, we often find ourselves approximating the most likely outcome by understanding past events or reference classes.

An estimation of a likelihood is typically called forecast.

As the role of information becomes more prevalent in a forecast, we can reduce (but never eliminate) our uncertainty in a given scenario.

The primary feature of this documentation is to make all concepts of "risk" subject to quantitative techniques, and forecasting is one of these important methods.

Some thoughts on definitions:
-----------------------------
By sticking to principles (See: :ref:`principles`), this documentation is opinionated on the usage of some risk language. *Estimations* are a form of approximation for any unknown value. A *forecast* is a an estimation of a value that doesn't exist yet. An estimate is not necessarily a forecast, but a forecast is an estimate.

There are grey areas for these terms. For instance, an unknown quantity may also be a future value. These will be worked out as this documentation as opportunities to simplify may arise. The authors are already aware of industry conflicting definitions.

A *prediction* does not necessarily mean a "100% belief", but should probably be avoided as it can be interpreted poorly.

.. _forecasting:

Forecasting
===========
Forecasting is a disciplined practice to estimate the likelihoods and impacts of future events. It is a subject matter with over a half-century of multidisciplinary research into risk, decision making, and predictions.

Every day, you forecast things related to your basic needs. Choosing what time you wake up in the morning is a forecast of how much time you'll need to prepare for the day. Peeking out your window is a forecast of the weather and informs a decision about clothes to wear. Examples are infinite.

You'll notice that you can seek information to support these forecasts, outside of relying on your expertise or intuition. Sometimes this data is readily available, sometimes it is not.

Forecasting is relied on in either case. Even when a meteorologist is presented with significant data about a ten day forecast, it is common for them to make a personal estimate based on that data instead of using it directly.

With forecasting, we do our best to approximate values that best represent our intuition. We stick to methods that improve our forecasting skills, and defend ourselves against well known forms of cognitive bias. As subject matter experts of the risks care about, we can create risk data that is highly leveraged by quantitative methods.

When culturally supported and invested in, groups of engineers can attack large risks methodically.

.. _calibration:

Calibration
-----------
Forecasts often include a value of "confidence" associated with them. For instance, "*I am 50% sure it will rain tomorrow.*" would indicate that the forecaster will be historically wrong in half of the instances where they've made a *50%* claim.

If someone is *99%* certain, their track record would be incorrect one in one hundred cases.

.. note::
  This makes the values of *0%* and *100%* very special, as they would indicate that the forecaster expects a perfect track record.

  You do not know anyone with a perfect prediction track record.

Volumes of research show that humans are poorly calibrated without training and practice. An uncalibrated individual may frequently use the phrase "*I'm 90% sure*" and display a track record of being far worse, as an example.

Research shows that individuals can be very easily calibrated with minimal training, and regular practice supports this as well. (See: `Tetlock <https://github.com/magoo/forecast-documentation/blob/master/READING.md#philip-tetlocks-prediction-research>`_)

.. _keeping score:

Keeping Score
-------------
Forecasts that include their associated confidence can make use of the `Brier Score`_ to record accuracy over time. This is simply calculated as the "Squared Error".

.. _Brier Score: https://en.wikipedia.org/wiki/Brier_score

The Good Judgement Open has an `accessible definition`_ of the Brier Score: ::

  The Brier score is the squared error of a probabilistic forecast.
  To calculate it, we divide your forecast by 100 so that your probabilities
  range between 0 (0%) and 1 (100%). Then, we code reality as either 0 (if the
  event did not happen) or 1 (if the event did happen). For each answer option,
  we take the difference between your forecast and the correct answer, square
  the differences, and add them all together. For a yes/no question where you
  forecasted 70% and the event happened, your score would be (1 – 0.7)2 + (0 – 0.3)2 = 0.18.
  For a question with three possible outcomes (A, B, C) where you forecasted
  A = 60%, B = 10%, C = 30% and A occurred, your score would be
  (1 – 0.6)2 + (0 – 0.1)2 + (0 – 0.3)2 = 0.26. The best (lowest) possible
  Brier score is 0, and the worst (highest) possible Brier score is 2.

.. _accessible definition: https://www.gjopen.com/faq

An average Brier score is useful for tracking the reliability of a forecaster. It can be tracked by certain topics, panels, individuals, etc.

For instance, let's take a batch of some pretty good weather predictions.

========  ==================  =========             ============  =========== =======================
Forecast  % Rain              % No Rain             Outcome       Brier Score Brier Score (Work)
========  ==================  =========             ============  =========== =======================
1         0.99                0.01                  Rain          0.0002      (1-.99)^2+(0-.01)^2
2         0.8                 0.2                   Rain          0.08        (1-.8)^2+(0-.2)^2
3         0.334               0.666                 No Rain       0.223112    (0-.334)^2 + (1-.666)^2
4         0.01                0.99                  No Rain       0.0002      (0-.01)^2 + (1-.99)^2
5         0.95                0.05                  Rain          0.005       (1-.95)^2 + (0-.05)^2
========  ==================  =========             ============  =========== =======================

This table shows an average Brier Score of ``0.0617024``. If we observed this forecast score from our local meteorologist, we'd be pleased and consider this forecast source *useful*. Let's put together a table of pretty terrible weather forecasts for comparison.

========  ==================  =========             ============  =========== =======================
Forecast  % Rain              % No Rain             Outcome       Brier Score Brier Score (Work)
========  ==================  =========             ============  =========== =======================
1         0.1	                0.9	                  1             1.62	      (1-.01)^2+(0-.9)^2
2         0.04                0.96                  1             1.8432      (1-.04)^2+(0-.96)^2
3         0.77                0.23                  0             1.1858      (0-.77)^2+(1-.23)^2
4         0.88                0.12                  0             1.5488      (0-.88)^2+(1-.12)^2
5         0.2	                0.8	                  1             1.28        (1-.2)^2+(0-.8)^2
========  ==================  =========             ============  =========== =======================

This table shows an average brier score of ``1.49556``. Any reasonable individual would consider those forecasts *not useful*.

Industry will vary on what a "useful" threshold for a forecast source would be. For instance, a Brier Score measuring forecasts about parts that explode will be very different from a risk forecast about missed project deadlines.

However, all industries can agree that reduction of a Brier Score over time is a good thing, and is a useful engineering metric that can be targeted over time.

.. _Types of Forecasts:

Types of Forecasts
------------------
A scenario can prompt for several types of answers to create a forecast. Depending on the risk you are hoping to measure, you may want to prompt an expert for a different type of answer.

Yes or No
~~~~~~~~~
The simplest type of forecast asks an expert for their belief of a binary outcome. For instance:

**Scenario** ::

  Will it rain tomorrow?

**Outcome** ::

  (Yes / No)

A forecaster may express themselves by saying Yes: 60%, No: 40%, if they believe it's more likely that not to rain. Or for instance, Yes: 0.01%, No: 99.99% if the forecaster lives in the desert.


Over / Under
~~~~~~~~~~~~
To include some aspect of "impact" in a risk, you can bake an over / under value into the scenario.

**Scenario** ::

  Will there be more than **three inches** of rainfall tomorrow? (Yes / No)

**Outcome** ::

  (Yes / No)

This is similar to the previous forecast, but instead adds a numeric condition that must be met. This is useful when investigating the likelihood that some risk will meet a threshold or tolerance level you need to better understand. For instance, there may be a legal reason to close down schools with a certain height of snow, or maybe a certain amount of losses that your insurance couldn't cover.

Confidence Intervals
~~~~~~~~~~~~~~~~~~~~
A confidence interval represents a range of possible values, and also includes a percentage belief that the outcome will fall into it. A forecaster would then expand their range of values to increase their expression of uncertainty, and an engineer's efforts would widen or narrow this range. For example:

**Scenario** ::

  Police have responded to a protest at City Hall.

**Outcome** ::

  (# of arrests, 70% confidence)

A forecaster may answer this with an interval of 5-10 arrests. If, for instance, they were asked for a more aggressive forecast (say, 70%), they may answer a more narrow range that results in a higher rate of being wrong. An example of a 60% confidence forecast for the same question could be 2-7 arrests, and so on.

A visual example of a percentage belief that an unknown value will end up within this range when revealed.::


                                70% Certainty

                                      │
                                      │
                                      │
                                      │
                                      │
                                      ▼
                              5              10
                              ▽──────────────▽

 ◀─────────────────────────────────────────────────────────────────────▶
  ... -3 -2 -1 0  1  2  3  4  5  6  7  8  9  10  11  12  13  14  15 ...

To summarize, a forecaster would provide:

- An interval (min-max)
- A percentage belief the outcome lies within.

A scenario can also demand the percentage belief beforehand.

Probability Distributions
~~~~~~~~~~~~~~~~~~~~~~~~~
Some forecasts may include many outcomes. For instance:

**Scenario** ::

  Our potential customer has made a decision regarding their request for business.

This could be answered with multiple options, like (A: Us, B: Competitor 1, C: Competitor 2, D, Competitor 3, E: No Decision / Walkout.)

**Outcome** ::

  % Likelihood
  A: Us
  B: Competitor 1
  C: Competitor 2
  D: Competitor 3
  E: No Decision / Walkout / Other

Skills
------

Divide and Choose
~~~~~~~~~~~~~~~~~
Divide and choose is a mental heuristic to determine if odds are fair or not. It is similar to the children's "fairness" concept where one child slices a piece of cake, and another child chooses the slice they'd like.

This method prevents the first child from slicing unevenly and taking the larger piece.

This equates to forecasting, where instead of assigning "fair odds" for an event, a forecaster assigns an extreme likelihood to a scenario in pursuit of a stronger accuracy score.

As forecasting can often be related to gambling or a decision market, it can appear advantageous to "win" a forecast and aggressively assign likelihood to one option or another. A goal of forecasting is to assign "fair odds" that represent the whole uncertainty associated with an event or value, instead of strong accuracy scores.

Strategies and incentives to maximize accuracy scores over calibration can hinder this approach, as it is not meant to be "gamified".

Principle of Indifference
~~~~~~~~~~~~~~~~~~~~~~~~~
The `principle of indifference`_ is a rule of thumb that divides a likelihood across all of its options. For instance, 50/50% or 25/25/25/25%.

When faced with these odds, a forecaster may find themselves disagreeing with them. If this is the case, it's likely that the forecaster has opinions they may express numerically.

.. _principle of indifference: https://en.wikipedia.org/wiki/Principle_of_indifference

The Absurdity Test
~~~~~~~~~~~~~~~~~~
The absurdity test assigns extreme and irrationally formed likelihoods or values to a forecast, testing the opinions of a forecaster. For instance, "A small child can eat between zero and one million pies in a sitting."

When faced with such a test, a forecaster may be encouraged to start making a forecast *less* absurd. For instance "Well, a child can at least eat half of a pie, and maybe up to five pies, in extraordinary circumstances."

This form of test has been used as an interview prompt in psychological research since the 1900's.

Reference Class
~~~~~~~~~~~~~~~
When data is not available to study a risk, alternative data may suffice as a reference. For instance, the history of reversals in the Supreme Court may inform a type of case that may be considered unprecedented.

Further Reading
~~~~~~~~~~~~~~~
See :ref:`Measurement / Approximation`, :ref:`Forecasting research`
