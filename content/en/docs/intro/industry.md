---
title: "Industry"

date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "intro"
weight: 130
toc: true
---

Cyber security is compared to other industries for its lack of rigorous and quantitative analysis of risk. **Simple Risk Measurement** focuses on _quantitative_ risk measurement to assist with this imbalance. While cyber security may lacks the forms of rigor found in other industries, this documentation also seeks to mitigate known weaknesses found in those approaches.

What makes other industries _quantitative_ about how they handle risk? How are we so different? Well, here are some examples, and we'll start with one you see all the time.

``` none
Will it rain tomorrow?
```

Of course, a meteorologist would give you a _forecast_ as a percentage. This would come from their subjective expertise as a meteorologist, supported by an enormous pile of modeled weather data to support their forecast.

Many industries follow similar principles. This means:

- Risks are structured as [scenarios](/simple-risk/docs/risk/scenarios).
- Reference class data is gathered as closely to the scenario as possible.
- [Forecasts](/simple-risk/docs/estimation/forecasting) are made with all available information. 
- [Decisions](/simple-risk/docs/intro/decisions/) are made. 
- Corrections are made when compare forecasts to reality.

Here are some industry examples which use different language, but with the same principles.

## Aerospace

The FAA has regulation about [space launches](govinfo.gov/content/pkg/FR-2016-07-20/pdf/2016-17083.pdf). All of their risk management effort directs towards a measurement for a simple event: **Expected Casualties** (`Ec`).

>For all launches, regardless of vehicle type, this final rule requires a single expected number of casualties (Ec) be calculated by aggregating the risk posed to the collective members of the public...

>This final rule also revises the acceptable risk threshold for launch from an Ec of 30 × 10E-6 for each hazard to an Ec of 1 × 10E-4 for all three hazards combined.

What does this mean in english?

``` none
How many casualties will result from a launch? 
```

## Nuclear Safety

The NRC (US) certifies nuclear reactors partially based on the completion of [Probabilistic Risk Analysis](https://www.nrc.gov/about-nrc/regulatory/risk-informed/pra.html). Nuclear is concerned with events that may result in core damage (Level 1 PRA), how these may leak radioactivity (Level 2 PRA), and how individuals would be put at risk from these exposures (Level 3 PRA). [Expert elicitation
techniques](https://www.standards.doe.gov/standards-documents/1200/1628-2013/@@images/file)
in nuclear risk measurement are
[common](https://www.nrc.gov/reading-rm/doc-collections/fact-sheets/probabilistic-risk-asses.html). 

- Will a tube in a steam generator rupture?
- Will there be health effects from resulting raditation leaks around a plant?
- How frequently will the core be damaged?

The nuclear industry relies on extensive [data
gathering](https://catalog.data.gov/dataset?q=organization:((nrc-gov)))
to inform estimation methods, and expert opinion is relied on when
adjustments need to be made for innovations without historic data.

## Environmental Safety

[Environmental impact organizations](https://www.epa.gov/osa/basic-information-about-scientific-coordination) use the [probabilistic risk assessment](https://www.epa.gov/sites/production/files/2014-11/documents/raf-pra-faq-final.pdf).

**Scenario:** The change in the mortality rate due to Fine Particles (PM2.5) decrease if we pass X regulation.

**Outcome:** `Credible Interval:` Reduction of .001 -.05% with 95% confidence.

The CSB [organizes investigations](https://www.csb.gov/investigations/)
that provide transparency into root causes informing probabilistic risk
approaches supported in EPA policies.

## Meteorology

The United States spends
[billions](https://en.wikipedia.org/wiki/Weather_forecasting) on weather
forecasting and its associated infrastructure.

**Scenario:** Will the east coast hurricane make landfall near our city before we
    can evacuate?

**Outcome:** `% Likelihood of Yes / No:` Yes with a likelihood of 50%.

NOAA and other global organizations build weather infrastructure that
makes operational forecasting possible. Meteorologists still make adjustments to their models when publishing forecasts based on known failures of their models, outages in data collection, or local familiarity.

## Intelligence Analysis

All forms of [intelligence gathering](https://en.wikipedia.org/wiki/List_of_intelligence_gathering_disciplines) ultimately desire to [inform decision making](https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/sherman-kent-and-the-board-of-national-estimates-collected-essays/4estimates.html).

**Scenario:**  Does the image taken by our satellite depict an adversary military aircraft?

**Outcome:**  `% Likelihood of Yes / No:` Yes with a likelihood of 70%.

Quantitative estimates are a foundational part of the National Intelligence Estimate process, and are used [globally by intelligence agencies](https://www.vice.com/en/article/kbz7gn/canadian-intelligence-agencies-are-actually-pretty-good-at-strategic-forecasting). Publicly accessible platforms have taken [similar approaches](https://www.predictit.org/) with [decision](https://www.gjopen.com/) [markets](https://augur.net/) accepting participation from large groups.