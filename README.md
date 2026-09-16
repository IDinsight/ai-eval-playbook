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
  actions:
    visible: true
  anchors:
    visible: true
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pbloAUUbQhacfW14WRJm/linkages-across-levels/overview
---

# Linkage across levels

There are several ways to link the four levels as you develop and evaluate an AI solution. These cross-level linkages are essential for tracing how changes in your model system, product, solution, and/or program affect outcomes—whether intentional or not. Consideration of risks and data protection requirements should also be done in a wholistic manner that cuts across the levels. Key practices include:

* **Developing Level 1-3** metrics at each stage of the user funnel;
* **Defining a single set of identifiers** that links data collected at each level (e.g. a user ID, session, and model/product version)
* **Ensuring product managers, data scientists, and user researchers cooperate** across levels to manage risks and provide continuity and context while iterating on product features.

Here are a few other actions you can take to link your evaluations across levels:

{% hint style="info" icon="1" %}
**Use critical metrics from one evaluation level as guardrails for others** so engagement optimizations don’t undermine “North Star” outcomes. Similarly, use metrics from one stage of the funnel as guardrails for other stages. For example, optimizing a bot for low latency (L1) while targeting student learning (L4) creates trade-offs: added latency may improve chain-of-thought correctness but reduce engagement and learning. If feasible, do not track L1 without L3 and L4 guardrails; North Star metrics propagate trade-offs across L1–L4, requiring deliberate weighting and interpretation.

<details>

<summary><i class="fa-book">:book:</i> Further reading</summary>

A more sophisticated—but less mature—option is multi-objective optimization, which optimizes an AI solution across multiple goals at once (e.g., cost, latency, safety). These [techniques](https://arxiv.org/pdf/2502.18635) are still new and under development.

</details>
{% endhint %}

{% hint style="info" icon="2" %}
**Level 2 engagement metrics must be evaluated in tandem with Levels 1 and 3.** Ideally, as your Level 1 metrics improve and the AI system becomes more reliable, your Level 2 engagement metrics should also improve. However, technical performance does not always guarantee user adoption, so it is critical to monitor AI system metrics and product analytics in tandem, to ensure that engineering “improvements” actually translate into a better user experience.

In this playbook, Level 2 evaluation focuses exclusively on the digital traces users leave within the product. It does not include qualitative interviews or surveys that probe user beliefs and moods; these activities will fall under the domain of Level 3 evaluation. Level 3 is also where we track many of the metrics used to **monitor harm** (e.g., anxiety, addiction). This is why we must evaluate Levels 2 and 3 in tandem.

As your product evolves, remember to refine and revalidate your Level 2 metrics, to better capture the nuance of the user experience. Metrics that record meaningful interactions are more valuable than raw event counts.
{% endhint %}

{% hint style="info" icon="3" %}
**Identify a product manager to “own” the North Star metric.** They are responsible for shaping the roadmap by balancing engineering and design trade-offs across all levels. This person ensures design choices—such as adding UI friction for specialized users—stay aligned with the overall goal, even if they look sub-optimal in one level’s metrics in isolation.
{% endhint %}

{% hint style="info" icon="4" %}
**Conduct routine multi-level risk assessments and failure-mode analyses.** When conducting error analysis, flag aberrant behavior at any level—for example, benchmark drift (Level 1) or user gaming (Level 3)—then assess whether it is detectable in the data produced at that level or other levels. Combine these insights with user research to predict fixes: issues appearing in Level 1 metrics near the top of the funnel often require AI system changes (e.g., knowledge base updates, prompt engineering), while downstream failures may require new product features or broader solution/intervention changes.
{% endhint %}

{% hint style="info" icon="5" %}
**User research** should sit alongside each evaluation level to interpret log data. Its depth varies by level: interviews to design golden datasets (L1), workflow observation to develop hypotheses (L2), and cognitive interviewing to inform survey design (L3–L4).
{% endhint %}

{% hint style="success" icon="star" %}
**Note:** **This playbook can be used directly with AI tools like Claude, ChatGPT, and NotebookLM.**\
[_**Explore how**_**&#x20;>**](https://app.gitbook.com/s/Ec5nQAw37GGYw1m7rYdO/additional-resources/using-the-playbook-with-ai-tools)
{% endhint %}

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=linkages-across-levels%2Foverview" %}

</details>
