---
title: "Mitigation"
description: "Measuring a mitigation's impact."
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "examples"
weight: 102
toc: true
---

Let's assume we found a vulnerability on a host named `build001`.

{{< alert icon="👉">}}
This example vulnerability was discussed **[here](/risk-measurement/docs/examples/vulnerability)**.
{{< /alert >}}

## The vuln
The vuln is bad. It's an RCE exposed to the internet, allowing for remote compromise _right now_. It's a feature of our CI/CD system, and is effectively a remotely accessible shell running as root.

There are complicating factors:

- Several partners companies remotely access `build001`
- The script console that offers a shell to the host is used regularly.
- No engineer currently owns this system.
- The whole system will be replaced with a new platform `build002` in 6mo, suggesting our efforts need to make sense in a short term.

This makes the job tough! Well, we can't _efficiently_ model each of these limitations in a reasonable time. We're here just to focus on risk, anyway.

This vulnerability was [previously measured](/risk-measurement/docs/examples/vulnerability) as follows:


- There's a `45%` chance that VULN-0 will be exploited within 30 days.
- (_If Exploited_) Incident response has a `60%` chance of requiring disclosure.
- An investigation has an `80%` chance of finding `build001` compromised.

Any possible mitigation has to have a positive effect on these measurments... but by how much?

## The target
Our role as the trusted and informed product security expert is to set some goalposts on what our mitigation should get us to. Let's do that now.

Previous work has already measured the vulnerability as-is with at having a `60%` chance of being involved in a disclosable incident. (see the [Vulnerability](/risk-measurement/docs/examples/vulnerability) example)

After a bunch of brainstorming, let's say we come up with the following goal:

{{< alert icon="📉">}}
Reduce the probability of a disclosable incident to 5% or lower within the next 30 days.
{{< /alert >}}

This number was arrived at based on the opinion of yourself, or your group, that _some method exists_ to hit this target. Now we just have to make those plans.

## The plans
Our quant efforts don't spit out plans, _we_ do. We've set these goalposts for ourselves, but we still require an achievable plan to get there. Let's assume the following plan is suggested by the team:

1. Bring `build001` down for maintenance and investigation.
2. Create a network ACL limited to partner access.
3. Reduce authorization in credentials on `build001`, bring back online.
4. Prioritize the migration off of `build001` and onto `build002`

This fix doesn't totally eliminate the vulnerability! As written, it's better described as a workaround. Should we push for this to be accepted as the plan?

Let's re-forecast our previous measurements, with a condition that our mitigations are put in place. Here's an example:

- There's a ~~`45%`~~ `5%` chance that VULN-0 will be exploited within 30 days.
- (_If Exploited_) Incident response has a ~~`60%`~~ `30%` chance of requiring disclosure.
- An investigation has an `80% (No Change)` chance of finding `build001` compromised.

Let's talk through these changes. 

Regardless of how they came upon these numbers: The team is expressing confidence that exploitation is less likely with network ACL's (going from `45%` to `5%`)

Next, A disclosure event seems less likely with the reduced credential footprint, (but not eliminated!), so the reduced forecast `60%` to `30%` is reasonable to see a reduction there. 

Last, there is **no change** in whether it is currently compromised or not. This makes sense, since new mitigations can't change whether it is compromised right now or not. 

## The decision
Now that the reasoning for these reductions are understood, we can make a decision on whether these risks are under our threshold. There's now a `5%` of exploitation in 30 days. If this happens, there's a `30%` chance it would result in a disclosable event. When worked out, this gives us `5% x 30% = 1.5%`, or a `1.5%` chance of a disclosable event which is well below the threshold we set for an acceptable decision.

Assuming the group agrees to the approach and the work, we have back-of-napkin'd our model of the risks that matter to us and met a target we are good with.