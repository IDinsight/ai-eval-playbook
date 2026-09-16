---
description: Do users with access to the product improve development outcomes?
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/c8kIjQckFMmOgTGk4tcQ/level-4-impact-evaluation/overview
---

# What is Impact Evaluation

Impact evaluation (IE) provides strong evidence for understanding causal social impact. While Level 3 measures shifts in thoughts and feelings, Level 4 measures the ultimate results: improved crop yields, higher test scores, or better health outcomes. By using a counterfactual—comparing those who use your product to a similar group that does not—you can isolate the true impact of your AI intervention from the "noise" of a messy world.

{% hint style="warning" icon="circle-info" %}
**Level 4 is typically pursued once Levels 1–3 show consistent, promising evidence**. The framework is a guideline to shape to your own purpose and methodology, not a definitive instruction — but rushing into an impact evaluation before the product is mature risks measuring a moving target.
{% endhint %}

***

#### Core Concept: The Counterfactual

To know if your AI tool works, you must estimate what would have happened to the same people _without_ it. We do this by creating a comparison group.

<table data-header-hidden="false" data-header-sticky><thead><tr><th valign="top">Method</th><th valign="top">How it Works</th><th valign="top">Best Used When...</th></tr></thead><tbody><tr><td valign="top"><strong>Randomized Control Trials</strong></td><td valign="top">Randomly assign users to "Treatment" or "Control."</td><td valign="top">You have a large sample and high control over rollout.</td></tr><tr><td valign="top"><strong>Propensity Score Matching</strong></td><td valign="top">Pair "Treatment" and "Control" units that look statistically similar on observed traits</td><td valign="top">You have a large dataset of users and non-users and need to statistically "match" them based on similar traits.</td></tr><tr><td valign="top"><strong>Difference-in-Differences</strong></td><td valign="top">Compare groups that follow "parallel trends" over time.</td><td valign="top">Randomization is not feasible or ethical.</td></tr><tr><td valign="top"><strong>Regression Discontinuity</strong></td><td valign="top">Compare people just above/below a specific cutoff (e.g., test scores).</td><td valign="top">The intervention is delivered based on a strict numeric cutoff (e.g., test scores or income level).</td></tr></tbody></table>

Interventions in the development sector aim to improve the quality of people’s lives. Impact evaluations measure the effects of the intervention on outcomes such as mortality, learning outcomes, and earnings. The main issue these evaluations face is that the world is a messy place: as an intervention is being implemented, many other things are happening that would make a simple before-and-after comparison an insufficient way to judge program effectiveness.

To address this, we consider the counterfactual: what would have happened to the same people in the absence of the intervention. Because we cannot observe both realities at once (the same people with and without the intervention), we estimate the counterfactual using a comparison group that is as similar as possible to the group that received the intervention. It represents what would have happened without the program. Comparing outcomes across these groups helps us isolate the intervention’s impact.

There are a number of ways to estimate or measure the counterfactual. The most straightforward approach is usually a randomized controlled trial (RCT). In an RCT, participants are randomly assigned to one or more treatment groups that receive an intervention (or variants of it) and a comparison group that does not. Researchers then measure outcomes across groups. Well-designed randomized evaluations enable credible, and are less-prone-to-bias estimates of causal impact—that is, which changes in participants’ lives can be attributed to the program. Other techniques for the counterfactual construction include propensity score matching, difference in differences, and regression discontinuity designs. These are discussed further below, but in general require more technical econometric expertise and contextual knowledge in order to execute well.

### **When to Start?**

Do not rush into an Impact Evaluation. You are ready for Level 4 when:

* ✅ Level 1–3 evidence is consistent.
* ✅ Scale-up is being considered by major partners.
* ✅ You have the technical bandwidth to coordinate with independent researchers.

{% hint style="success" icon="star" %}
**Note:** **This playbook can be used directly with AI tools like Claude, ChatGPT, and NotebookLM.** \
[_**Explore how**_**&#x20;>**](https://app.gitbook.com/s/Ec5nQAw37GGYw1m7rYdO/additional-resources/using-the-playbook-with-ai-tools)
{% endhint %}

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-4-impact-evaluation%2Foverview" %}

</details>
