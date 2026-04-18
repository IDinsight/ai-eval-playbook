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
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pbloAUUbQhacfW14WRJm/level-1-model-evaluation/overview/what-is-the-minimum-viable-evaluation-for-level-1
---

# What is the Minimum Viable Evaluation for Level 1?



The earliest stage of AI development involves prototyping with offline evaluations. Here, we strongly recommend using notebooks (e.g. Jupyter notebooks, or Google Colab) to establish reproducible workflows instead of aiming to set up an automated pipeline from the start.

The goal of this step is to quickly analyze errors in the current configuration, make suitable changes, and test for resolution of issues. Working inside a notebook helps you access every component in one place—data, configs, models, metrics and any other intermediate steps like retrieval, tool calling—giving you full visibility into your existing system and a test bed for validating your experiments end-to-end.

Once you are ready to deploy a product to actual users, consider using an observability platform (like Langfuse or DeepEval) to automatically record traces as you iterate. This is important for understanding where your AI system is failing and why. But don’t let this delay your launch.

{% include "https://app.gitbook.com/s/c8kIjQckFMmOgTGk4tcQ/~/reusable/lwsl8FO9PoWvCTgiqdmI/" %}

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-1-model-evaluation%2Foverview%2Fwhat-is-the-minimum-viable-evaluation-for-level-1" %}

</details>
