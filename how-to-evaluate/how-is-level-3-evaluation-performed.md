---
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
---

# How is Level 3 evaluation performed?



**The full workflow includes:**

{% stepper %}
{% step %}
#### Generate hypotheses based on a theory of change

Based on the theory of change, define intermediate cognitive, affective, or behavioral outcomes that are plausibly linked to your targeted social impact. Validate these via qualitative methods (e.g., user interviews) as well as quantitative research or reviews of the academic literature.
{% endstep %}

{% step %}
#### Identify outcome metrics

There are three potential ways to identify outcome metrics. First, you can analyze interaction data to construct metrics that reflect psychologically and behaviorally meaningful user interaction. Second, you can collect primary data. Often, the most direct way to gauge users' thoughts, feelings, knowledge, and behaviors is simply to ask them: short surveys can capture self-reported changes and subjective experiences, while longer surveys, interviews, quizzes, or observer reports can measure psychological well-being, behavioral frequency, and attitudinal shifts over time. Third, you can analyze conversation logs. For instance, you can use Natural Language Processing (NLP) methods to mine actual conversation logs or written outputs for signals of cognitive or emotional change.

<a href="descriptive-analysis.md" class="button primary">Read more -></a>
{% endstep %}

{% step %}
#### Define guardrail metrics and measure potential harm

As you reach Level 3 evaluations, you are not just measuring if your product is working; you want to measure if it is causing harm. While Level 2 metrics track usage, Level 3 is your opportunity to use direct interviews and surveys to track unintended consequences.

<a href="defining-guardrail-metrics-measuring-potential-harm.md" class="button primary">Read more -></a>
{% endstep %}

{% step %}
#### Consider constructing proxies for long-term development outcomes

We expect Level 3 metrics to materialize more quickly than Level 4 evaluation outcomes. In principle, short-term Level 3 indicators can be used in A/B testing to rapidly design and test product improvements. However, it is unlikely that any one Level 3 metric is fully predictive of Level 4 outcomes. Therefore, we propose constructing a "Surrogate Index", consisting of Level 2 and Level 3 metrics, to serve as a proxy for longer-term Level 4 outcomes. The validity of this index can be assessed in Level 4 evaluations (e.g., in RCTs), following the framework proposed by [Athey, Chetty, Imbens, and Kang (2025)](https://academic.oup.com/restud/advance-article/doi/10.1093/restud/rdaf087/8268796?guestAccessKey=). Although this approach relies on very strong assumptions of unconfoundedness, surrogacy, and comparability, we encourage the continued collection of indicators to capture the links between the intervention, its adoption, underlying mechanisms, and ultimate development outcomes.
{% endstep %}

{% step %}
#### Consider conducting experiments to improve the selected key metrics and running process evaluations

After identifying intermediate outcomes that serve as early indicators of the development outcome of interest, the next step is to run experiments to assess how product changes influence Level 3 outcomes. The evaluation methods remain the same as in Level 2, but are applied to a different set of outcomes (e.g., A/B testing: Feature A vs. Feature B; multi-armed bandits: performance-based adaptive allocation; holdout testing: e.g., AI vs. non-AI). We also recommend running process evaluations to gain an understanding on why and when Level 3 metrics are not changing.

<a href="why-arent-thoughts-feelings-and-behavior-changing.md" class="button primary">Read more -></a>
{% endstep %}
{% endstepper %}

As sensitive data, collecting information on user thoughts and feelings carries significant legal and ethical responsibilities. Because using GenAI models often involves sending data to third-party model providers (e.g., OpenAI, Google, Anthropic), it is also important to scrutinize whether their data governance and privacy and safety policies align with these responsibilities.&#x20;

<a href="https://eval.playbook.org.ai/level-linkages/linkage-across-levels/data-protection" class="button primary">Read more -></a>



***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-3-user-evaluation%2Fhow-is-level-3-evaluation-performed" %}

</details>
