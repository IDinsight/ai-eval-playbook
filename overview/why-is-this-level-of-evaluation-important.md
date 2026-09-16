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
---

# Who is most involved in this level of evaluation?

<table><thead><tr><th valign="top">Execute</th><th valign="top">Support</th></tr></thead><tbody><tr><td valign="top"><p><i class="fa-square-code">:square-code:</i> <strong>AI Engineers</strong></p><p><i class="fa-flask-vial">:flask-vial:</i> <strong>ML Researchers</strong></p></td><td valign="top"><p><i class="fa-graduation-cap">:graduation-cap:</i> <strong>Domain Experts</strong></p><p><i class="fa-house">:house:</i> <strong>Product Owners</strong></p><p><i class="fa-magnifying-glass">:magnifying-glass:</i> <strong>User Researchers</strong></p></td></tr><tr><td valign="top">Your engineering team will be driving the process from driving technical development (e.g. implementing metrics and setting up automated evaluation pipelines) and working together with domain experts to finalise the rubrics and developing the golden dataset.</td><td valign="top">Domain experts and product owners must support the engineering team as product owners by deciding the rubrics, validating if the metrics proposed measure those rubrics accurately and helping inform the design of the golden dataset.</td></tr></tbody></table>

***

#### Key Motivation

In high-stakes sectors like health, education, and agriculture, misalignment isn't just a bug—it’s a safety risk. Level 1 evaluation is important because:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><h4><i class="fa-circle-o">:circle-o:</i></h4></td><td><strong>Mitigating Hallucinations</strong></td><td>Verifies that fluent-sounding responses are actually factually grounded.</td></tr><tr><td><h4><i class="fa-database">:database:</i></h4></td><td><strong>Contextual Accuracy</strong></td><td>Ensures the system uses your proprietary data or local context (e.g., specific soil types) rather than generic internet data.</td></tr><tr><td><h4><i class="fa-hand">:hand:</i></h4></td><td><strong>Harm Prevention</strong></td><td>Identifies potential biases or unsafe advice before they reach vulnerable populations.</td></tr><tr><td><h4><i class="fa-sack-dollar">:sack-dollar:</i></h4></td><td><strong>Cost Efficiency</strong></td><td>Catching a misaligned system during development is significantly cheaper than fixing a deployed product that users have already lost trust in.</td></tr></tbody></table>

***

#### Why is this level of evaluation important?

Level 1 evaluations focus on the AI system that form the “smarts” of your product. And while these AI systems are powerful, they have inherent blind spots. Large language models (LLMs) like GPT, Claude and Gemini do not understand content in the way humans do. Given an input, they generate output by predicting the next word in a sequence. Their predictions mimic the data used in model training—usually a vast collection of information published to the internet, including textbooks and computer code, as well as misinformation, unverified claims, and conspiracy theories. This is why they can appear fluent and convincing while remaining inaccurate, irrelevant, or harmful—a phenomenon known as hallucination.

Because of the way they are trained, AI models face several limitations:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><h4><i class="fa-globe-pointer">:globe-pointer:</i></h4></td><td><strong>Static Knowledge</strong></td><td>Used alone, they cannot access real-time information (e.g., current weather in a rural village) so are limited to the training data they have received.</td></tr><tr><td><h4><i class="fa-folders">:folders:</i></h4></td><td><strong>Limited Context</strong></td><td>The model will not have access to personal information or your proprietary documents unless explicitly engineered to do so. As a result, models may lack the context to generate actionable, personalized, or even accurate outputs for a given task.</td></tr><tr><td><h4><i class="fa-person-chalkboard">:person-chalkboard:</i></h4></td><td><strong>Instruction Following</strong></td><td>Models may struggle to adhere to complex instructions or fail to follow constraints consistently, leading to results that do not fully meet expected criteria.</td></tr><tr><td><h4><i class="fa-not-equal">:not-equal:</i></h4></td><td><strong>Task Mismatch</strong></td><td>AI models are not the right “tool” for every task; for example, they may confidently make errors in math calculations which are trivial for a calculator. Understanding where they shine and augmenting them with capabilities they lack is key to using them well.</td></tr></tbody></table>

Product developers can often address these limitations, but it requires a structured, continuous evaluation process: a set of iterative workflows to verify that the AI system is useful, accurate, and safe; and that it reliably exhibits desirable behaviors and characteristics. For instance, an effective AI tutor will follow pedagogical best practices – like withholding answers to encourage self-directed learning, or gauging a student’s abilities to better tailor instruction.

Level 1 evaluation verifies that the AI system performs reliably and is appropriate to the context. This is non-negotiable in sectors like education, health, and agriculture, where misalignment or unverified claims can cause real-world harm to vulnerable users. We recommend starting early with Level 1 evaluation, to prevent wasted effort and time.

You can begin by engaging key stakeholders, including users and domain experts, to define success criteria and a continuous evaluation strategy. This allows you to shape system behavior throughout the development process, and to avoid the high costs (and delays) of fixing a misaligned system after it has already been built.

{% hint style="warning" icon="circle-info" %}
**Note: Low-resource languages**

Most LLMs are trained on digitized text in just a handful of languages, predominantly English. Yet they are used in contexts where users speak ”low-resource” languages, such as Kannada or Hikuyu. These languages may be spoken by tens of millions of people, but there is relatively less digitized text (and even fewer labeled datasets) available to train foundation models. As a result, LLM queries in these languages may result in higher rates of hallucination or other failure modes. In contrast, “high-resource” languages like English or Hindi have far more internet and digital data available, leading to stronger performance. To improve the performance of an AI system operating in “low-resource” languages, you may want to design your systems to first translate the user’s input from their language to a high-resource one, generate the AI response in a high-resource foundation model, then translate the answer back, so the user receives guidance in the language they prefer.
{% endhint %}

{% include "../.gitbook/includes/note-this-playbook-can-be-....md" %}

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-1-model-evaluation%2Foverview%2Fwhy-is-this-level-of-evaluation-important" %}

</details>
