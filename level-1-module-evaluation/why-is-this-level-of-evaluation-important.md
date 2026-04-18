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

# Who is most involved in this level of evaluation?

{% include "https://app.gitbook.com/s/c8kIjQckFMmOgTGk4tcQ/~/reusable/mWShpDArkLJ7vuQiKjHe/" %}

## Why is this level of evaluation important?

Level 1 evaluations focus on the AI system (see [What is an AI system?](what-is-the-ai-system-being-evaluated.md)) that form the “smarts” of your product. And while these AI systems are powerful, they have inherent blind spots. Large language models (LLMs) like GPT, Claude and Gemini do not [understand](https://www.sciencenews.org/article/ai-large-language-model-understanding?utm_source%3Dchatgpt.com\&sa=D\&source=editors\&ust=1770879886919367\&usg=AOvVaw2IuQUzdG6HVftGYlMDjGer) content in the way humans do. Given an input, they generate output by predicting the next word in a sequence. Their predictions mimic the data used in model training—usually a vast collection of information published to the internet, including textbooks and computer code, as well as misinformation, unverified claims, and conspiracy theories. This is why they can appear fluent and convincing while remaining inaccurate, irrelevant, or harmful—a phenomenon known as hallucination.

Because of the way they are trained, AI models face several limitations:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="image">Cover image</th></tr></thead><tbody><tr><td><strong>Static Knowledge</strong></td><td>Used alone, they cannot access real-time information (e.g., current weather in a rural village) so are limited to the training data they have received.</td><td><a href="https://images.unsplash.com/photo-1584184200374-73d7f6c6a175?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxjb25jcmV0ZXxlbnwwfHx8fDE3NzI2NDAwMzB8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1584184200374-73d7f6c6a175?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxjb25jcmV0ZXxlbnwwfHx8fDE3NzI2NDAwMzB8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Limited Context</strong></td><td>The model will not have access to personal information or your proprietary documents unless explicitly engineered to do so. As a result, models may lack the context to generate actionable, personalized, or even accurate outputs for a given task.</td><td><a href="https://images.unsplash.com/photo-1586769852836-bc069f19e1b6?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxpbmZvcm1hdGlvbnxlbnwwfHx8fDE3NzI2NDAwNjh8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1586769852836-bc069f19e1b6?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxpbmZvcm1hdGlvbnxlbnwwfHx8fDE3NzI2NDAwNjh8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Instruction Following</strong></td><td>Models may struggle to adhere to complex instructions or fail to follow constraints consistently, leading to results that do not fully meet expected criteria.</td><td><a href="https://images.unsplash.com/photo-1508726096737-5ac7ca26345f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxvYmV5fGVufDB8fHx8MTc3MjY0MDA5OHww&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1508726096737-5ac7ca26345f?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxvYmV5fGVufDB8fHx8MTc3MjY0MDA5OHww&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr><tr><td><strong>Task Mismatch</strong></td><td>AI models are not the right “tool” for every task; for example, they may confidently make errors in math calculations which are trivial for a calculator. Understanding where they shine and augmenting them with capabilities they lack is key to using them well.</td><td><a href="https://images.unsplash.com/photo-1613905780946-26b73b6f6e11?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHx3cm9uZ3xlbnwwfHx8fDE3NzI2NDAxNDB8MA&#x26;ixlib=rb-4.1.0&#x26;q=85">https://images.unsplash.com/photo-1613905780946-26b73b6f6e11?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHx3cm9uZ3xlbnwwfHx8fDE3NzI2NDAxNDB8MA&#x26;ixlib=rb-4.1.0&#x26;q=85</a></td></tr></tbody></table>

Product developers can often address these limitations, but it requires a structured, continuous evaluation process: a set of iterative workflows to verify that the AI system is useful, accurate, and safe; and that it reliably exhibits desirable behaviors and characteristics. For instance, an effective AI tutor will follow pedagogical best practices – like withholding answers to encourage self-directed learning, or gauging a student’s abilities to better tailor instruction.

Level 1 evaluation verifies that the AI system performs reliably and is appropriate to the context. This is non-negotiable in sectors like education, health, and agriculture, where misalignment or unverified claims can cause real-world harm to vulnerable users. We recommend starting early with Level 1 evaluation, to prevent wasted effort and time.

You can begin by engaging key stakeholders, including users and domain experts, to define success criteria and a continuous evaluation strategy. This allows you to shape system behavior throughout the development process, and to avoid the high costs (and delays) of fixing a misaligned system after it has already been built.

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-1-model-evaluation%2Foverview%2Fwhy-is-this-level-of-evaluation-important" %}

</details>

