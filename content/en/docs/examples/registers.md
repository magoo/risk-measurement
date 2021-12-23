---
title: "Registers"
description: "Reviewing multiple risks in a single place."
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "examples"
weight: 110
toc: true
---

Many risks can be compared quantitatively so long as they share a measurement.

Let's compare a bunch of vulnerabilities we are treating as risks. We assume we have `VULN-0` to `VULN-9`. If we have a common group of forecasts for all of them, we can sort and manage them as you'd expect.

|  Vulnerability (1 year)      | Exploited? | (Exploited) Dislosable? | Headline? |
| ------ | ---------------------- | ------------------------------- | ------------------------------- |
| VULN-0 | 2.00%                  | 5.00%                           | 5.00%                           |
| VULN-1 | 3.00%                  | 1.00%                           | 1.00%                           |
| VULN-2 | 1.00%                  | 1.00%                           | 1.00%                           |
| VULN-3 | 2.00%                  | 70.00%                          | 1.00%                           |
| VULN-4 | 30.00%                 | 10.00%                          | 40.00%                          |
| VULN-5 | 10.00%                 | 1.00%                           | 5.00%                           |
| VULN-6 | 6.00%                  | 14.00%                          | 10.00%                          |
| VULN-7 | 1.00%                  | 100.00%                         | 5.00%                           |
| VULN-8 | 15.00%                 | 15.00%                          | 1.00%                           |
| VULN-9 | 2.00%                  | 25.00%                          | 1.00%                           |

Register approaches are _extremely_ cumbersome if direct elicitation is required for every entry. 

The layout may convince you that a fixing-from-the-top-down approach is the obvious one, and that we should discover _all the risks_, elicit forecasts for _all the risks_ and register _all the risks_. Of course, this is not the right way to go.

Actual [decisions](/simple-risk/docs/intro/decisions) involving these risks will always include non-registered factors. Engineers might not have a clear mitigation in mind. There may be costs we haven't enumerated. Maybe delays are involved with some of the risks we'd prefer mitigating.

A risk register will not lay plans in front of us, so care should be applied in efforts to tie everything into a register.

However, there are ways to make registers more efficient.

## Lens Models
A lens model is a technique that could help populate a risk register more effiently. It allows the creation of a statistical model that captures expert opinion (or plural from a panel) on a few select predictors and outputs a register of probabilities to prioritize from. An example of this is here: [AWS Risk Model](https://magoo.github.io/model-risk-aws/)


## Statistical models 

Third party vulnerabilities are well covered with a method like [EPSS](https://www.kennaresearch.com/tools/epss-calculator/) which is promising for register based approaches. These are useful when a corpus of data is available and closely relevant to the target scenario you are forecasting. These approaches lose value in first party vulnerability risk areas or more obscure software without openly available vulnerability data.
