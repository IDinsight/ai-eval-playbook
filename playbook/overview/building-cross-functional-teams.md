# Building Cross-Functional Teams

Building effective GenAI evaluation is a team sport. No single role spans all four levels; success depends on cross-functional teams where responsibilities are clear and complementary. Leading tech teams pair AI engineers, data scientists, user researchers, outcome scientists, and product managers, with strong cross-disciplinary communication and minimal jargon. Adopting this model in the development sector reduces silos and ensures gains at one level translate to others. Below, we outline roles by level, how they collaborate, the tools they use, and how teams align goals with evaluation outcomes.

## Team roles by evaluation level

<table data-full-width="false"><thead><tr><th width="160.48828125">Evaluation Level</th><th width="242.734375">Lead Roles</th><th width="221.21484375">Support Roles</th><th width="324.33984375">Core Responsibilities</th></tr></thead><tbody><tr><td><i class="fa-gear-code">:gear-code:</i> Level 1 – Model</td><td><ul><li>AI Engineers/ML Researchers</li></ul></td><td><ul><li>Domain Experts</li><li>Product Owners</li><li>User Researchers</li></ul></td><td>Orchestrate prompts, knowledge bases and other components of a modern AI system; Create/maintain benchmark datasets and set up automated metrics/human judges/LLM judges to run offline and online tests; Track and improve model performance; Perform error analysis and ensure data quality; Build and fine-tune models if necessary; ensure relevance and safety; log outputs for downstream use. Domain-specific inputs (e.g., educators for tutor bots) are also essential.</td></tr><tr><td><i class="fa-box-isometric">:box-isometric:</i> Level 2 – Product</td><td><ul><li>Product Managers</li></ul></td><td><ul><li>Data Scientists</li><li>Data Engineers</li><li>Software Engineers</li><li>Domain Experts</li></ul></td><td>Integrate AI into workflows; track engagement through A/B tests; maintain shared dashboards; align usage data with user behavior and product design.</td></tr><tr><td><i class="fa-user">:user:</i> Level 3 – User</td><td><ul><li>User Researchers</li></ul></td><td><ul><li>Data Scientists</li><li>Data Engineers</li><li>Domain experts</li></ul></td><td>Measure user outcomes (cognitive, affective, and behavioral) and run A/B tests on these outcomes; run surveys and interviews; co-design metrics with end users; and integrate qualitative insights with usage data.</td></tr><tr><td><i class="fa-chart-column">:chart-column:</i> Level 4 – Impact</td><td><ul><li>Policy Researchers</li><li>Economists</li><li>Data Scientists</li></ul></td><td><ul><li>AI Engineers</li></ul></td><td>Evaluate long-term outcomes (e.g., learning, health, income); define theory of change; run impact evaluations</td></tr></tbody></table>



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
