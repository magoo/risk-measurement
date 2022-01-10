---
title: "New Product Review"
description: "Measuring risk of future products."
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

Let's imagine a new product. We'll discuss some hypothetical risk scenarios, and then discuss some estimations for them.


{{< alert icon="" >}}
**Scenario**:
We launch a feature that lets customers upload profile pictures. 
{{< /alert >}}

## Discussion 
This change allows "User Generated Content" or UGC onto a platorm. UGC can have multi-dimensional impacts.

Allowing new UGC into a product workflow creates many operational risks that will result during the lifetime of the product, as well as risks that would be infrequent but potentially devastating. For instance, a vulnerability in [image processing dependencies](https://imagetragick.com/). 

If we haven't launched the product yet, we can only speculate as to what may happen when we do. Rather than being the security expert who says *photo uploads are hella bad!*, we discuss the risks point by point and brainstorm mitigation options. Here are various studies we could engage in and [elicit estimates](/risk-measurement/docs/estimation/expert-elicitation) for:

## Interval Examples

- How many reports to NCMEC in the first 60 days? (Min-Max 75%)
- How many active CP/CSAM Investigations in the first 60 days? (Min-Max 75%)
- What increase in support tickets in the first 60 days? (Min-Max 75%)
- How many Image Codec SEVs in the first 60 days? (Min-Max 75%)
- How many Image Permission SEVs in the first 60 days? (Min-Max 75%)

## Scenario Examples
- Will an Image Code RCE SEV result in a disclosable incident in 365 days?
- Will negative newspaper headlines appear about this feature in the first 60 days?
- Will an adversary deletion SEV require us to restore from images from backups in the first 60 days?
- Will we have to contact law enforcement as a result of this product in the first 60 days?

## Distribution Examples
- How many reports to NCMEC in the first 60 days? (Pareto)
- How much storage in S3 will be occupied by this product? (Lognormal)