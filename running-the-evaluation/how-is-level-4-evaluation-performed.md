---
description: A Quick Primer on Impact Evaluation Methods
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
    - /broken/spaces/NdqczEOrO06puTzbj8Wy/pages/AFlY5GiRC66jsYKV1dHL
---

# How is Level 4 evaluation performed?

Once it is the right time and resources are in place, you must choose a method. At its core, an impact evaluation compares outcomes between groups that differ only in exposure to the intervention—that is, treatment versus control. There are several ways to achieve or approximate this:

{% hint style="info" icon="1" %}
### **Randomized Controlled Trials**

This method assigns a sufficiently large number of units (e.g., individuals, schools, clinics) at random to receive the intervention, while others are excluded (or often assigned to a waitlist). Randomization, along with sufficient sample size, ensures groups are comparable on average, except for whether they receive the intervention. Sometimes, politics, ethics, or other constraints will make it less feasible to randomize, so we can turn to other methods. Other times, conducting a randomized evaluation is easier politically and more ethical; context and resources will determine that.
{% endhint %}

{% hint style="info" icon="2" %}
### **Propensity score matching**

This approach requires a large dataset covering both participants and non-participants, with a clear indicator of treatment. It uses statistical techniques to match treated units with similar untreated ones based on observable characteristics. Because it relies only on what is observed, robustness declines when unobservable differences are likely to matter.
{% endhint %}

{% hint style="info" icon="3" %}
### **Difference-in-Differences**

This method relies on the assumption that treated and untreated (comparison) groups would have followed parallel trends in outcomes, but does not have the luxury of random assignment to force that to be so by design. By comparing differences before and after the intervention, impact can be estimated. Key is to try to understand why the comparison group was not treated and whether that reason is masking—i.e., predicting—a likely difference in trends that they may experience compared to the likely trend of those treated had the treated not been treated.
{% endhint %}

{% hint style="info" icon="4" %}
### **Regression discontinuity design**

This approach uses a cutoff, comparing people (or other treatment units) just below it to those just above. For example, if students below a threshold receive remedial education, impact is estimated by comparing students near the cutoff on either side. Valid implementation requires that the cutoff itself does not directly affect outcomes (e.g., it reflects budget constraints, not pedagogy) and that there are many observations close to the threshold, since differences grow farther from it.
{% endhint %}

### Key design considerations for AI-specific impact evaluations

Across impact evaluation methods, there are distinct challenges emerging for the impact evaluation of AI products, and some merit special attention.

<a href="key-design-considerations-for-ai-specific-impact-evaluations.md" class="button primary">Read more -></a>

### Common Pitfalls to avoid

There are several common pitfalls that can undermine even well-designed studies. First, studies are often underpowered when assuming 100% of people will use the AI. In reality, uptake is often low; plan for a larger sample size than you think you need. Second, there is the "black box" problem: if the AI evolves mid-study without version tracking, you won't know _which_ version of the product caused the impact. Additionally, there is the tension between transparency and adaptability, considering a Pre-Analysis Plan to define how you will handle product changes before the study begins.

<a href="common-pitfalls-to-avoid.md" class="button primary">Read more -></a>

### Addressing challenges with process evaluations

Use process evaluation to gain insights into the mechanisms when the intervention does not produce the expected development outcomes. Process evaluation can also help you find the enabling factors that will be important when you scale up.

<a href="process-evaluation-why-arent-outcomes-changing.md" class="button primary">Read more -></a>

<details>

<summary><i class="fa-book">:book:</i> Further reading</summary>

These are very basic introductions. For more on methods as well as a step-by-step guide to impact evaluation planning – including sampling, power calculations, and analysis – we strongly recommend:

* [Impact Evaluation in Practice](https://openknowledge.worldbank.org/server/api/core/bitstreams/4659ef23-61ff-5df7-9b4e-89fda12b074d/content) (Gertler et al., World Bank)
* [Running Randomized Evaluations](https://press.princeton.edu/books/paperback/9780691159270/running-randomized-evaluations) (Glennerster & Takavarasha)

In the following section, we do not replicate that guidance. Instead, we focus on what is _distinctive_ when evaluating AI-based products in the development sector.

</details>

{% hint style="success" icon="star" %}
**Note:** **This playbook can be used directly with AI tools like Claude, ChatGPT, and NotebookLM.**\
[_**Explore how**_**&#x20;>**](https://app.gitbook.com/s/Ec5nQAw37GGYw1m7rYdO/additional-resources/using-the-playbook-with-ai-tools)
{% endhint %}

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-4-impact-evaluation%2Fhow-is-level-4-evaluation-performed" %}

</details>
