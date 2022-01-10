---
title: "Forecasting log4j worms"
description: ""
lead: ""
date: 2021-12-21T14:37:41-08:00
lastmod: 2021-12-21T14:37:41-08:00
draft: false
weight: 50
contributors: []
---

I organized an early forecast during the beginnings of the log4j (CVE-2021-44228) hysteria. Some links and early timeline are available [here](https://magoo.github.io/incident-tracking/2021-12-09-log4j) if you are reading this post in the future or aren't up to speed on this vulnerability.

This bug screamed uncertainty and motivated me to come out of hiding and get a forecast together. Our community was unfamiliar with a vulnerability like this and only caught everyone's attention after exploitation in Minecraft. The exploitation of this vulnerability is simple but not typical. 

Exploitation was in the wild before I could get an _[in the wild](https://magoo.medium.com/forecasting-bluekeep-5c25a8d5d681)_ forecast together. The next most interesting thing was [speculation](https://twitter.com/Laughing_Mantis/status/1470165580736987137) about whether this vulnerability would appear as a worm, which I gathered some folks up to take on with a panel forecast.

A meaningful forecast about a "worm" was complicated to pin down. Regardless, the process of getting the measurement together was helpful. It always seems to be! But future worm forecasting needs to be improved.

First, I'll describe what scenario we landed on and the measurement process. There are many areas for improvement, which I hope I can highlight with blog posts.  

Here's the scenario we picked:

> Will evidence of a worm spreading in the wild using CVE-2021-44228 (Log4Shell) for any stage of exploitation be found within 90 days?

![log4j-data](log4j-data.png)

We measured this with an [expert elicitation](/simple-risk/docs/estimation/expert-elicitation) approach, including twelve participants, and landed on a `65.58%` of occurrence. All are professionals in the security community with varying malware experience - some significant and some minor. Many of the participants were also busy with log4j response. They put their forecast in when coming up for air. 

As usual, the debate (the actual goal) was helpful for all of us. Let's talk a bit about the forecast process.

First, worms can use multiple means of exploitation. So we needed to be clear. Are we looking for a "full" worm that solely used CVE-2021-44228 to get around from victim to victim? 

Further, what if a worm solely uses this CVE for lateral movement within a network, and not initial exploitation?

Effective worms have historically used a handful of vulnerabilities to make themselves more widespread. But, some vulnerabilities allow for "full" worms that can roll off of a single vulnerability, penetrating networks and moving within them. So, is an existing worm that uses log4j in a minor role a "log4j worm"? We went for an inclusive approach to make a judgment (ultimately my role) easier.

Second, this vulnerability typically needs a malicious `ldap://` server, at least with the knowledge we had at the time of the forecast. Would a worm have to set up attack infrastructure with victims or have dedicated malicious servers? This impacts whether a worm is fully "autonomous" but might still propagate quickly. Again, we decided to be inclusive of SPOF `ldap://` attack hosts. This allowed dedicated attack hosts to be involved with the attack. You might see a trend in the forecast development by now. We'll cover it later.

Third, would a white-hat worm trigger this scenario? Yes, we decided not to be the judge if something is white or black hat and allowed it.

Lastly, would this have to be a brand new worm, or could this be added as a propagation method to an existing botnet? For instance, Mirai? Again, we decided on inclusivity.

All of these decisions to be inclusive of qualities of a "worm" all inherently add to the belief that "yes, evidence of a worm will appear." So, we ended up with a probable forecast at `65.5%`.

These exceptions show the need for improved demarcation on what a "worm" is for future forecasting.

A takeaway: We are less interested in "Will a worm appear?". Rather, we are interested in the size and impact a worm could have. 

What could have been more useful: 

- Exceeding victim thresholds from credible sources
- Discovery of a "full" worm 

I've drafted [some language](https://github.com/magoo/forecast-documentation/blob/master/IN-THE-WILD.md#an-in-the-wild-worm) that might be useful in the future for worm forecasting, and I'm happy to hear feedback that pokes holes in it. The details are in there, but it separates a "full" worm with a "partial" worm. 

A full worm is "pure": it shouldn't be reliant on any external infrastructure and be fully autonomous with discovery and exploitation. A partial worm can still exhibit some of these qualities and be something to be feared, but the definition starts to slip for forecasting purposes.  

A weird exception would be the kill switch domain in WannaCry, which would have been an external dependency that would technically force it into "partial" worm status. I'm unsure how to mitigate the language that excludes it from being a "full" worm, but I think it may have been a full worm without that kill switch. Later versions without the kill switch may have met the "full" definition. 

In any case, figuring out the language around "is it a worm" helps get us to more valuable information about victimization and impact. Hopefully, we can skip right to those forecasts if a future worm should appear.

If other known standards around "worm" language exist that would be useful in forecasting, please reach out. 

Lastly I'll conclude that _even allowing this inclusive definition of a worm_, I imagine most vulnerabilities would not measure as CVE-2021-44228 has, as most vulnerabilities are not wrapped up into active worms. So, this measurement would still be informative to me and have me take a second look at the vulnerability, assuming this measurement was all I had. 

***

This forecast has a couple possible binaries floating around that might trigger a `YES` on some of the technicalities in our language, but they're currently being refuted by active malware researchers. I'll be waiting until March to review and score this scenario unless a clear `YES` event happens. 

[Follow me](https://www.twitter.com/magoo) on Twitter for any updates. 