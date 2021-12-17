---
title: "Decisions"
date: 2021-10-26T13:11:58-07:00
draft: false
menu:
  docs:
    parent: "intro"
---

Decisions are _subjective_. This documentation is about making quantitative risk measurements. These measurements will not make decision making an _objective_ process. We are still [bounded by rationality](https://en.wikipedia.org/wiki/Bounded_rationality). Risk based measurements will only be a subset of all information available for a decision. 

This documentation can only offer methods to improve the quality of risk based measurements for those decisions, and offer commentary on decision processes themselves.

## Data driven decisions

Often discussed is the _data driven_ decision. We may be subject to unconscious bias if we seek and collect data before structuring the criteria we are making a decision with.

Rather, we can pursue decisions as follows:

1. Identify the problem.
2. Set goalposts.
3. Collect measurements.

For instance, we'll examime a typical IT endpoint security problem at some large engineering organizations.

**The Problem:**
> Engineers are removing mobile device management software from their laptops, and in some cases, changing settings that violate policy or accumulating vulnerabilities we cannot track and mitigate. They're also out of scope for our detection efforts - we can't _see_ them.

Yikes! But, do we take action immediately? That's the decision we have to make. There's a lot of security work to do, what says that this is the first item to attend to?

Let's set some criteria that dictates at what point we begin taking action - now, or later.

**The Goalposts:**

Let's pretend we have thought on the issue, and determined some break points where the problem is too severe to ignore any longer.

> When more than 2% of engineering laptops become unmanaged, we'll treat it like an incident and start enforcing a policy that denies them access to production and prioritize it over other work items.

Now we have taken note of what types of action we would make before we're [biased](/docs/risk/bias) with the data we've collected.

**The Measurement:**
> OK. Since you've asked, we've identified at least 5% of engineering laptops are connecting to the bastion environment without their hostnames appearing in MDM. 

This exceeds the goalposts we set. We can make the decision to begin enforcing the policy without being accused of having made a decision without regard for the data.

## The McNamara Fallacy
This documentation is focused on quantitative risk, but warns of narrow mindedness in its usage. An overly focused attititude towards quantitative reasoning is sometimes referred to as the [McNamara Fallacy](https://en.wikipedia.org/wiki/McNamara_fallacy). Individuals who reject information that hasn't yet been quantified are vulnerable to this sort of failure. Qualitative analysis is still valuable.

Metrics are gathered because they've met some level of accessibility. A unavailable metric or quantified measurement is not necessarily less important - there may be resource constraints in acquiring them.

Leadership roles should be familiar with decision making under risk: Even with risk measurements, a total picture should be considered. 