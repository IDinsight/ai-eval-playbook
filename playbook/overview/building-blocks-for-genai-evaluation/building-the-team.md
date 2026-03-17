# Building the Team

To build a GenAI product for social impact, you need to start with the right team. Success depends on cross-functional teams where responsibilities are clear and complementary. Effective teams typically involve AI engineers, data engineers, data scientists, user researchers, social scientists, and product managers. They demonstrate strong cross-disciplinary communication and use minimal jargon. Adopting this model in the development sector reduces silos and ensures gains at one level of evaluation translate to the others. Only some of the roles will need to be permanent or in-house, while others may be temporary or external. Below, we outline roles by level, how they collaborate, the tools they use, and how teams align goals with evaluation outcomes. In addition to the assigned roles, we recommend a review of all stages by domain experts as well as persons with used experience of the intervention’s topic.

<table><thead><tr><th width="195.2578125">Area of Expertise</th><th width="199.37890625">Roles in Evaluation</th><th>Responsibilities</th></tr></thead><tbody><tr><td><p>Engineers </p><p>(AI, Backend/Data, MLOps)</p></td><td><p><strong>Lead:</strong> Level 1</p><p><strong>Support:</strong> Level 2, Level 3, Level 4</p></td><td>Orchestrate prompts, knowledge bases and other components of a modern AI system; Create/maintain benchmark datasets and set up automated metrics/human judges/LLM judges to run offline and online tests; Track and improve model performance; Perform error analysis and ensure data quality; Build and fine-tune models if necessary; ensure relevance and safety; log outputs for downstream use. Domain-specific inputs (e.g., educators for tutor bots) are also essential.</td></tr><tr><td>Product Managers</td><td><p><strong>Lead:</strong> Level 2</p><p><strong>Support:</strong> Level 1, Level 3</p></td><td>Integrate AI into workflows; define product metrics, maintain shared dashboards; design/implement experiments in collaboration with Domain Experts and User Researchers and track outcomes of A/B tests; manage product versions and releases; align product metrics with user behavior research.</td></tr><tr><td>Data Scientists</td><td><strong>Support:</strong> Level 2, Level 3, Level 4</td><td>Analyze data from Level 2, including definition of metrics. Contribute to both routine monitoring and analysis of A/B tests. </td></tr><tr><td>User researchers (can include behavioral/psychological scientists)</td><td><p><strong>Lead:</strong> Level 3</p><p><strong>Support:</strong> Level 2, Level 4</p></td><td>Measure user outcomes (cognitive, affective, and behavioral) and run A/B tests on these outcomes; run surveys and interviews; co-design metrics with end users; and integrate qualitative insights from interviews, focus groups, and direct observation with Level 2 product metrics.</td></tr><tr><td>Social scientists</td><td><strong>Lead:</strong> Level 4</td><td>Evaluate long-term outcomes (e.g., learning, health, income); define theory of change; run impact evaluations</td></tr><tr><td>Domain Experts</td><td><strong>Support:</strong> Level 1, Level 2</td><td>Help to define rubrics for Level 1, and validate Level 1 metrics. Support definition of Level 2 and Level 4 metrics and their real-world relevance. Contribute to the theory of change. </td></tr></tbody></table>

{% hint style="info" %}
In small teams, individuals may span multiple levels, but all four perspectives must be represented. Engineers may collect user feedback but still need behavioral or domain input; product managers should understand model metrics, and researchers should look at product analytics. The team should jointly define what “enough evaluation” means at each stage—later in the Playbook, we outline a set of Minimum Viable Evaluations.
{% endhint %}

## Best practices for cross-level collaboration

### Look Beyond Your Slices of Evaluation

Each team member should understand how their work shapes other evaluation levels. Engineers should look beyond benchmarks to user experience, and data scientists analyzing engagement (Level 2) can gain insight from behavioral experts (Level 3). Regular cross-functional check-ins anchored in the user journey help surface these links and prevent tunnel vision.

### Pair Engineers with Domain Experts Early

Involve domain experts in Level 1 from the outset. Engineers need their input to define success beyond technical metrics, ensuring model evaluation reflects real user needs.

### Identify a Cross-Functional Lead

Product managers (or cross-functional leads) should connect roles, coordinate timelines, run experiments, and translate insights into decisions. A clear evaluation plan spanning Levels 1–4 keeps teams aligned on goals and evidence.

### Use a Shared Evaluation Language

Adopt a shared vocabulary across levels (e.g., Level 1 accuracy, Level 2 engagement, Level 3 learning gains, Level 4 outcomes). Explain jargon as needed and document tests and lessons in a shared space to build alignment, shared goals, and avoid rework.

### Use Tools that Support Collaboration

* **Evaluation pipeline**: An automated evaluation pipeline for your AI system can help identify cases where it currently fails and track its behavior as you make improvements
* **Dashboards & Data Pipelines**: Centralized, annotated dashboards can ensure that key metrics are accessible to all.
* **Experimentation Platform**: Use lightweight tools (e.g., Evidential to run and track experiments collaboratively).
* **Project & Knowledge Tools**: Keep tasks visible, foster quick feedback, and hold regular debriefs for deeper insights.

{% hint style="info" %}
Besides the tooling described above, in the following sections of this introductory playbook, we’ll also share an initial overview of the key resources and tools available for each phase.
{% endhint %}
