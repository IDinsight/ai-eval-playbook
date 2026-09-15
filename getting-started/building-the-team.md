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
      https://app.gitbook.com/s/pbloAUUbQhacfW14WRJm/overview/building-blocks-for-genai-evaluation/building-the-team
---

# Building the Team

Success in the development sector depends on breaking down silos. A great GenAI product isn't just "built by engineers" and "checked by researchers"; it is the result of a cross-functional dance.

In this section, we outline roles by level, how they collaborate, the tools they use, and how teams align goals with evaluation outcomes. You’ll find:

* Role Definitions: Who leads which level of evaluation (from model performance to long-term impact).
* Collaboration Best Practices: How to pair technical staff with domain experts early to ensure "accuracy" aligns with "human need."
* Shared Language: Tools for creating a unified vocabulary to avoid the "jargon trap."

Only some of the roles will need to be permanent or in-house, while others may be temporary or external. In addition to the assigned roles, we recommend a review of all stages by domain experts as well as persons with used experience of the intervention’s topic.

<table data-header-hidden="false" data-header-sticky><thead><tr><th width="195.2578125">Area of Expertise</th><th width="199.37890625">Roles in Evaluation</th><th>Responsibilities</th></tr></thead><tbody><tr><td><p>Engineers</p><p>(AI, Backend/Data, MLOps)</p></td><td><p><strong>Lead:</strong> Level 1</p><p><strong>Support:</strong> Level 2, Level 3, Level 4</p></td><td>Orchestrate prompts, knowledge bases and other components of a modern AI system; Create/maintain benchmark datasets and set up automated metrics/human judges/LLM judges to run offline and online tests; Track and improve model performance; Perform error analysis and ensure data quality; Build and fine-tune models if necessary; ensure relevance and safety; log outputs for downstream use. Domain-specific inputs (e.g., educators for tutor bots) are also essential.</td></tr><tr><td>Product Managers</td><td><p><strong>Lead:</strong> Level 2</p><p><strong>Support:</strong> Level 1, Level 3</p></td><td>Integrate AI into workflows; define product metrics, maintain shared dashboards; design/implement experiments in collaboration with Domain Experts and User Researchers and track outcomes of A/B tests; manage product versions and releases; align product metrics with user behavior research.</td></tr><tr><td>Data Scientists</td><td><strong>Support:</strong> Level 2, Level 3, Level 4</td><td>Analyze data from Level 2, including definition of metrics. Contribute to both routine monitoring and analysis of A/B tests.</td></tr><tr><td>User researchers (can include behavioral/psychological scientists)</td><td><p><strong>Lead:</strong> Level 3</p><p><strong>Support:</strong> Level 2, Level 4</p></td><td>Measure user outcomes (cognitive, affective, and behavioral) and run A/B tests on these outcomes; run surveys and interviews; co-design metrics with end users; and integrate qualitative insights from interviews, focus groups, and direct observation with Level 2 product metrics.</td></tr><tr><td>Social scientists</td><td><strong>Lead:</strong> Level 4</td><td>Evaluate long-term outcomes (e.g., learning, health, income); define theory of change; run impact evaluations</td></tr><tr><td>Domain Experts</td><td><strong>Support:</strong> Level 1, Level 2, Level 3, Level 4</td><td>Help to define rubrics for Level 1, and validate Level 1 metrics. Support definition of Level 2 and Level 4 metrics and their real-world relevance. Contribute to the theory of change.</td></tr></tbody></table>

{% hint style="warning" icon="circle-info" %}
In small teams, individuals may span multiple levels, but all four perspectives must be represented. Engineers may collect user feedback but still need behavioral or domain input; product managers should understand model metrics, and researchers should look at product analytics. The team should jointly define what “enough evaluation” means at each stage—later in the Playbook, we outline a set of Minimum Viable Evaluations.
{% endhint %}

<details>

<summary><strong>Best practices for cross-level collaboration</strong></summary>

{% hint style="info" icon="star-sharp" %}
### Look Beyond Your Slices of Evaluation

Each team member should understand how their work shapes other evaluation levels. Engineers should look beyond benchmarks to user experience, and data scientists analyzing engagement (Level 2) can gain insight from behavioral experts (Level 3). Regular cross-functional check-ins anchored in the user journey help surface these links and prevent tunnel vision.
{% endhint %}

{% hint style="info" icon="user-group" %}
### Pair Engineers with Domain Experts Early

Involve domain experts in Level 1 from the outset. Engineers need their input to define success beyond technical metrics, ensuring model evaluation reflects real user needs.
{% endhint %}

{% hint style="info" icon="user-crown" %}
### Identify a Cross-Functional Lead

Product managers (or cross-functional leads) should connect roles, coordinate timelines, run experiments, and translate insights into decisions. A clear evaluation plan spanning Levels 1–4 keeps teams aligned on goals and evidence.
{% endhint %}

{% hint style="info" icon="head-side-speak" %}
### Use a Shared Evaluation Language

Adopt a shared vocabulary across levels (e.g., Level 1 accuracy, Level 2 engagement, Level 3 learning gains, Level 4 outcomes). Explain jargon as needed and document tests and lessons in a shared space to build alignment, shared goals, and avoid rework.
{% endhint %}

{% hint style="info" icon="people-carry-box" %}
### Use Tools that Support Collaboration

* **Evaluation pipeline**: An automated evaluation pipeline for your AI system can help identify cases where it currently fails and track its behavior as you make improvements
* **Dashboards & Data Pipelines**: Centralized, annotated dashboards can ensure that key metrics are accessible to all.
* **Experimentation Platform**: Use lightweight tools (e.g., Evidential to run and track experiments collaboratively).
* **Project & Knowledge Tools**: Keep tasks visible, foster quick feedback, and hold regular debriefs for deeper insights.
{% endhint %}

</details>

***

{% hint style="success" icon="star" %}
**Note: This playbook can be used directly with AI tools like Claude, ChatGPT, and NotebookLM.** \
[_**Explore how**_**&#x20;>**](../additional-resources/using-the-playbook-with-ai-tools.md)
{% endhint %}

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-1-model-evaluation%2Foverview" %}

</details>
