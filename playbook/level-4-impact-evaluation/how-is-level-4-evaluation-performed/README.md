# How is Level 4 evaluation performed?&#x20;

Performing a Level 4 evaluation requires rigorous experimental or quasi-experimental designs to isolate the effect of the AI from other external factors.

#### 1. Choosing Your Methodology

At its core, impact evaluation compares a Treatment Group (those using the AI) to a Control/Comparison Group (those who are not).

| **Method**                | **Best Used When...**                                                                                                  |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| RCTs                      | You have a large sample and can randomly assign access to ensure groups are identical.                                 |
| Propensity Score Matching | You have a large dataset of users and non-users and need to statistically "match" them based on similar traits.        |
| Quasi-Experimental        | Randomization isn't possible, but you can compare trends before and after the intervention between two similar groups. |
| Regression Discontinuity  | The intervention is delivered based on a strict numeric cutoff (e.g., test scores or income level).                    |

<a href="a-quick-primer-on-impact-evaluation-methods.md" class="button primary">Read more -></a>

***

#### 2. High-Level Steps for AI Impact Evaluation

**Step A: Select the Right Counterfactual**

You must define what "the world without the AI" looks like. In AI evaluations, the comparison isn't always "nothing"—it might be a static chatbot, a human teacher, or a traditional paper-based process.

**Step B: Account for "Product Dynamism"**

Unlike a static pill or a physical textbook, AI products change constantly. To maintain scientific rigour:

* **Tag Versions:** Log exactly which model version every user interacts with.
* **Maintain a Hold-out Group:** Keep a small group on the "baseline" version of the AI to see if updates actually improve outcomes.
* **Coordinate with Tech:** Ensure the engineering roadmap doesn't accidentally "break" the evaluation design.

**Step C: Measure True Outcomes, Not Proxies**

Ensure the evaluation measures actual welfare or capability gains.

* **Avoid Gaming:** Don't use tests that users can pass simply by repeating AI-generated answers.
* **Use Validated Tools:** Rely on industry-standard assessments or administrative data (e.g., health records, employment rates).

**Step D: Manage Spillovers and Attrition**

AI tools are easily shared, which creates a risk of "contamination" (the control group getting access to the AI).

* **Cluster Randomization:** Randomize by village or school rather than by individual to prevent sharing.
* **Monitor Drop-outs:** Use Level 2 (Usage) and Level 3 (Behavior) data to see who stops using the tool and why, as high attrition can ruin your statistical power.



<a href="key-design-considerations-for-ai-specific-impact-evaluations.md" class="button primary">Read more -></a>

***

#### 3. Common Pitfalls

* **Underpowered Studies:** Assuming 100% of people will use the AI. In reality, uptake is often low; plan for a larger sample size than you think you need.
* **The "Black Box" Problem:** If the AI evolves mid-study without version tracking, you won't know _which_ version of the product caused the impact.
* **Transparency vs. Adaptability:** Use a Pre-Analysis Plan to define how you will handle product changes before the study begins.



<a href="common-pitfalls-to-avoid.md" class="button primary">Read more -></a>

{% embed url="https://tally.so/r/A788l0?originPage=level-4-impact-evaluation%2Fhow-is-level-4-evaluation-performed" %}
{% endembed %}
