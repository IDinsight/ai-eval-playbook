# Linkages Across Levels

There are several ways to link the four levels as you develop and evaluate an AI solution. These cross-level linkages are essential for tracing how changes in your model system, product, solution, and/or program affect outcomes—whether intentional or not. Key practices include:

* Developing Level 1-3 metrics at each stage of the user funnel;&#x20;
* Defining a single set of identifiers that links data collected at each level (e.g. a user ID, session, and model/product version)
* Ensuring product managers, data scientists, and user researchers cooperate across levels to provide continuity and context while iterating on product features.

Here are a few other actions you can take to link your evaluations across levels:

1. **Use critical metrics from one evaluation level as guardrails for others** so engagement optimizations don’t undermine “North Star” outcomes. Similarly, use metrics from one stage of the funnel as guardrails for other stages. For example, optimizing a bot for low latency (L1) while targeting student learning (L4) creates trade-offs: added latency may improve chain-of-thought correctness but reduce engagement and learning. If feasible, do not track L1 without L3 and L4 guardrails; North Star metrics propagate trade-offs across L1–L4, requiring deliberate weighting and interpretation.

{% hint style="info" %}
A more sophisticated—but less mature—option is multi-objective optimization, which optimizes an AI solution across multiple goals at once (e.g., cost, latency, safety). These [techniques](https://arxiv.org/pdf/2502.18635) are still new and under development.
{% endhint %}

2. **Identify a product manager to “own” the North Star metric.** They are responsible for shaping the roadmap by balancing engineering and design trade-offs across all levels. This person ensures design choices—such as adding UI friction for specialized users—stay aligned with the overall goal, even if they look sub-optimal in one level’s metrics in isolation.
3.  **Conduct routine multi-level risk assessments and failure-mode analyses.** When conducting error analysis, flag aberrant behavior at any level—for example, benchmark drift (Level 1) or user gaming (Level 3)—then assess whether it is detectable in the data produced at that level or other levels. Combine these insights with user research to predict fixes: issues appearing in Level 1 metrics near the top of the funnel often require AI system changes (e.g., knowledge base updates, prompt engineering), while downstream failures may require new product features or broader solution/intervention changes.



User research should sit alongside each evaluation level to interpret log data. Its depth varies by level: interviews to design golden datasets (L1), workflow observation to develop hypotheses (L2), and cognitive interviewing to inform survey design (L3–L4).

