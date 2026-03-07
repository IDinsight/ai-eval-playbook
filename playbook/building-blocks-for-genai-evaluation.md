# Building Blocks for GenAI Evaluation

Whether evaluating a GenAI tutor or a clinical decision support tool, reusable building blocks often apply across all four evaluation levels. When implemented well, they shift teams from static design to repeatable, delivery-embedded practices that support continuous improvement. There are five key building blocks:

## 1. The Foundation: Start with formative research, a theory of change, and subgroup identification

GenAI products—such as math tutors or clinical decision support—operate within larger systems. A government AI tutor, for instance, depends on teacher training, devices, and incentives. If outcomes fall short, the cause may be the model (level 1) or program delivery. Understanding the full system is essential.

<div data-full-width="true"><img src="https://docs.google.com/drawings/d/1sA3i252ExADWRjOrn6nw_l3KirUDyx03QkG1eUD-xUzbc8WPX1_RBTjB3f3FZ4oXp-jMFQVi23RrkJfSBdy4PGvFB0UcvSJ_tZHuiXcCvBYiwmVl/image?parent=18du_LUMPGGu4pZQ1nZ-pKoEwu2zlzmQhFLYwX-A-ix0&#x26;rev=90&#x26;drawingRevisionAccessToken=bNVlK9CLHzEQcA&#x26;h=400&#x26;w=400&#x26;ac=1" alt="Figure 2. Unit of AI evaluation across systems"></div>

Formative research helps organizations define the context and system in which a GenAI product operates (Figure 2). At the center is the AI system, which includes multiple components—one of which is a foundation model (e.g. GPT-5, Claude Opus 4.5, Gemini 3). Foundation models are trained on large datasets to learn patterns and generate new outputs—text, images, code, or audio—that resemble their training data. In this playbook, however, the AI system extends beyond the model itself to include prompts, knowledge bases, and other elements of the broader AI pipeline.

In global development, AI models typically sit within an AI product, such as a direct-to-consumer health chatbot delivered via WhatsApp. That product is deployed through an intervention, program, or social service—for example, an onboarding session onto the WhatsApp product for expectant mothers during prenatal screening visits. These interventions, in turn, exist within a broader delivery system, such as a country’s public health system that funds and supports prenatal care and onboarding.

Formative research is early-stage work conducted before or during design to understand the problem, the users, and the delivery system. Its goal is not to prove impact, but to inform decisions. It typically uses qualitative and mixed methods—interviews, observations, usability tests, surveys, and rapid pilots—to reveal how people actually behave, not how we expect them to.

Formative research can help form a Theory of Change (TOC). A TOCmaps hypothesized causal pathways from inputs (e.g., training, products, information) to a human development “North Star” outcome (e.g., literacy, mortality, yields). It traces how inputs move through activities to outputs, produce short-term outcomes, and ultimately generate social impact. The figure below shows a TOC for a skills development intervention.

<div data-full-width="true"><img src=".gitbook/assets/unknown (5).png" alt="Figure 3. An example theory of change of a skills development intervention"></div>

From an evaluation standpoint, a TOC explains how earlier-stage Level 1–3 variables—AI system performance, user engagement, and user mindsets—are expected to drive the medium-term outcome or impact of interest. By making the end-to-end flow from inputs to impacts explicit, a TOC helps motivate the design of the intervention, product, and AI workflow.

Formative research and a TOC also help define the target population: the people or institutions (e.g., schools, health clinics) the intervention aims to benefit. Crucially, this population is heterogeneous—clinics vary in capacity, schools in remoteness, individuals in wealth and gender. Such variation can cause the TOC to operate differently across subgroups and, in some cases, justify multiple parallel TOCs.

For evaluation, this creates subgroups of interest. Subgroups such as gender or rural populations should be monitored at every evaluation level to detect unequal effectiveness. Under a “minimum viable evaluation” approach—doing only what is needed to mitigate serious risks—you can define a broad initial population while focusing on those least able to benefit. Teams can then iteratively design and evaluate for priority groups, such as rural, low-capacity clinics in a health assistant intervention or low-income indigenous girls in a tutoring program. Track outcomes for these subgroups and adjust the AI workflow, product, or intervention so they benefit.

An alternative is to start with a diverse target population and, as segments fail to engage or benefit, stop targeting them. Teams must carefully assess why these users are not a priority and explicitly justify their exclusion.

## 2. The user funnel: track the journey across Levels 1-4

One of the most useful tools for developing GenAI products is a user funnel: a structured map of how people move through a product and program, from first exposure to long-term impact. A comprehensive funnel does more than describe usage—it creates a shared framework for tracking the user journey from discovery to impact. It surfaces weak points to guide improvements and provides a common anchor for the four levels of evaluation.

To build a funnel, start with the program’s TOC. The funnel is essentially a user-centric theory of change: it captures user inputs—typically behaviors or resources the user controls - in response to the intervention. It can also track intervention elements the product team controls and varies, based on factors like cost or impact.

Funnel design is usually bottom-up. Start with the final development outcome, or “North Star” metric (Level 4), such as, improved learning outcomes, better health, or higher crop yields. Then work backward to break the journey into specific user stages

{% stepper %}
{% step %}
### Recruitment

The beneficiary is identified and enters the program. (Level 2)
{% endstep %}

{% step %}
### Onboarding

The user is introduced to the AI product and completes initial setup. (Level 2)
{% endstep %}

{% step %}
### Engagement

The user begins actively interacting with the AI product (Level 2).
{% endstep %}

{% step %}
### Retention

The user continues engaging with the AI product over time, rather than dropping off (Level 2). Level 1 evaluation may continue as needed to monitor model behavior.
{% endstep %}

{% step %}
### Proximal Outcome

The user demonstrates near-term cognitive or behavioral change (Level 3). Level 1 evaluation may continue as needed to monitor model behavior.
{% endstep %}

{% step %}
### Development Outcome

The user achieves the desired long-term result (Level 4).
{% endstep %}
{% endstepper %}

Your objective as a product team is to convert users from each stage to the next, minimizing user drop-off along the funnel. For each stage, teams should clearly define:

* What the program does to bring users into that stage (i.e., program inputs).
* What the user must do to count as having entered the stage (i.e., user input).
* The metric that confirms entry into the stage (e.g., login rate, session length, quiz completion)
* Target metric values and transition rates between stages.
* Costs associated with moving a user through a given stage.
* DRIs (Directly Responsible Individuals) tasked with maintaining or improving the performance of each metric, at each stage of the funnel.

This structure turns a theory of change into a measurable, cost-aware product design tool. It lets teams track performance over time, identify user drop-offs or failure points, and test whether user behavior aligns with intended outcomes. It also gives funders and evaluators clear signals of where progress is occurring and where it is stalling.

{% hint style="warning" %}
**The Engagement Trap**

In the development sector, high engagement is necessary but not sufficient. A commercial app optimizes for "time on device" (ad revenue). A development app must optimize for "Time to Success."<br>

**Action**: Always pair engagement metrics with negative metrics (e.g., doom-scrolling, repeated confusion) to ensure you aren't optimizing for unwanted behavior.
{% endhint %}

{% hint style="info" %}
**Accounting for subgroups in a user funnel**

A user funnel is not only useful for overall program performance; it can also identify the types of users who are not progressing to the next stage. This creates an opportunity to design features or customizations to help these subgroups advance—or to decide, deliberately, that they are not the target users and update upstream targeting criteria accordingly. Careful user research should inform this determination.
{% endhint %}

At each level of evaluation, you will define and track an array of metrics – from generic benchmarks that are broadly adopted by an industry, to specific metrics used only to improve your product. You can imagine your inventory of metrics as a pyramid:

![Figure 4. Relationship between contextualized metrics and generic metrics](https://docs.google.com/drawings/d/1z5JXdj-D-_bWHPbjO4UHfY0xrVOFMxGZkiBx9eEuz9oYZsTDe-qDSt8NKL5ndLFrZCA56OP3POAoNmJS-lnOIdMcKonb6BVyW-N5LDIV-sKHuIzc/image?parent=18du_LUMPGGu4pZQ1nZ-pKoEwu2zlzmQhFLYwX-A-ix0\&rev=94\&drawingRevisionAccessToken=wdWu7kkD8vN5dA\&h=222\&w=381\&ac=1)

Metrics at the top of the hierarchy are often widely used industry or academic benchmarks for well-defined tasks. Examples include Accuracy for translation or speech recognition (Level 1), daily active users (DAU) for digital products (Level 2), user information recall (Level 3), and household income or consumption (Level 4). These metrics enable comparisons across foundation models, product classes, or development solutions.

At the bottom of the hierarchy are contextual metrics. These are often most useful for product improvement but rarely support cross-product comparison. For a mental health app, examples include percentage of emergency situations that were missed in LLM-driven message triage(Level 1), time spent improving mental health rather than DAU (Level 2), daily self-reported stress (Level 3), or a validated generalized anxiety disorder scale for the target population (Level 4).

At each stage of the user funnel, consider capturing a range of Level 1–4 metrics. This allows you to trace how changes propagate through the full user journey. For example, adjusting the AI system may shift translation accuracy (Level 1) without affecting engagement (Level 2), yet still alter user understanding and behavior, reducing Level 3 and 4 outcomes.

“Minimum Viable Evaluation” (MVE) means collecting only the data (through logs, surveys, analysis) needed to get started. Begin with the North Star metric, then define the smallest set of upstream metrics and targets required to observe it. Eliminate anything not essential.. Here are examples of MVE metrics you might consider:

* Accuracy[^1], [response completeness](#user-content-fn-2)[^2], or latency[^3] (<i class="fa-gear-code">:gear-code:</i> Level 1, note[^4])
* Number of daily active users, session duration, timestamps (<i class="fa-box-isometric">:box-isometric:</i> Level 2)
* User satisfaction or comprehension of content (<i class="fa-user">:user:</i> Level 3)

We also recommend defining data quality requirements and target values for each MVE metric. Critically, to track users across evaluation levels and funnel stages, you will need a simple set of identifiers that can be captured in log data and surveys, including:

* "User ID" : a unique identifier for each user;
* "Event": defined as a timestamped user engagement, within a specific session, for a given AI system configuration and/or product version (e.g. a user’s prompt correction); and
* "Action", which is the user’s choice or input as they navigate a product journey (e.g. copying the system’s final output at the end of a session).

In some cases, you may need multiple nested funnels to capture the full user experience with an AI product. These funnels and their metrics can also be linked across all framework levels; the final [Linkages Across Levels](the-4-level-framework/linkages-across-levels.md) section discusses this in more detail.

## 3. ETL pipelines: Build and tracking metrics

A well-designed evaluation framework is only as good as the data infrastructure that supports it. At the heart of that infrastructure is a robust ETL pipeline – a system that extracts, transforms, and loads data to power consistent, reliable measurement of user funnel metrics (also known as program indicators):

* **Extract**: Collect data from various sources – chat logs, product telemetry, survey tools, third-party APIs, or even spreadsheets.
* **Transform**: Clean, standardize, and reshape the raw data into a usable format. This could involve timestamp alignment, anonymization, session stitching, or deriving new funnel metrics like time-on-task or trust indicators.
* **Load**: Make the transformed data available from centralized storage (like a data warehouse or analytics dashboard) so teams can access it for analysis, visualization, or modeling.

AI products—especially GenAI—generate large volumes of complex, unstructured data. Without a clear ETL pipeline, turning this data into actionable metrics at scale is slow and unreliable. For example, a product supporting adolescent mental health might collect:

* **Model-level outputs** (<i class="fa-gear-code">:gear-code:</i> Level 1): response quality, hallucination rate, representative failure cases.
* **Engagement logs** (<i class="fa-box-isometric">:box-isometric:</i> Level 2): sessions per user, conversation length, feature use.
* **Behavioral indicators** (<i class="fa-user">:user:</i> Level 3): changes in sentiment or self-reported stress levels.
* **Outcome data** (<i class="fa-chart-column">:chart-column:</i> Level 4): improvement in standardized well-being scores over time.

To make sense of this, teams should build a data pipeline that integrates core datasets into a warehouse—AI system logs, product analytics, user surveys, and outcomes data—and translate them into consistent indicators across evaluation levels. Teams should also track data lineage in the warehouse so indicators are interpreted correctly.

## 4. Hypothesis targeting: Address weak links

Once a user funnel and robust ETL pipeline are in place, the next challenge is diagnosing why metrics underperform. Start by identifying major drop-offs: if users do not engage, they are unlikely to benefit. Then investigate what drives the drop-off, using targeted hypotheses.

Rather than relying on intuition, teams should ask specific, testable questions about drop-offs and mechanisms. This approach bridges product management, UX research, and behavioral science, keeping evaluation disciplined despite nonlinear development.

Evaluation should not dictate what teams build; it should clarify what needs to be understood and changed. For instance, if engagement drops after onboarding, evaluators can surface competing hypotheses—unclear value, interface overload, or mistrust of AI responses—each informing targeted metrics or experiments, often co-designed with product, UX, and behavioral science leads. In this way, evaluation is generative: not just judging performance, but helping teams ask better questions, faster.

## 5. Experimentation: Test with rigor and speed

Once hypotheses are set, experimentation tests them. For lightweight changes (e.g., prompts or onboarding), evaluation datasets and A/B tests (through tools like [Evidential](https://www.google.com/url?q=https://docs.evidential.dev/welcome/\&sa=D\&source=editors\&ust=1770879886900619\&usg=AOvVaw1aqbit6aXwhPbGgXxpO9xK)) are often fastest and cheapest. For deeper behavioral or policy questions, teams may use staggered rollouts, holdouts, or—when justified—full RCTs informed by L1–3 data. The aim is consistent: produce credible causal evidence on what improves user outcomes, turning evaluation into a decision tool.

Throughout experimentation, maintain version control by logging every change to the AI system, product features, wrap-around services, and delivery manuals. This often-overlooked practice is foundational: it helps align stakeholders when updates are needed and enables accurate interpretation of shifts in evaluation data at every level.

{% hint style="info" %}
To support these building blocks, The Agency Fund is developing a suite of practical playbooks to complement the GenAI Evaluation Playbook, focused on user funnels, user research, product design, and experimentation. Each playbook offers actionable guidance and tools to help teams move from insight to impact with speed and discipline.
{% endhint %}

[^1]: **Accuracy** refers to the proportion of system outputs that are correct according to a task-specific ground truth or expert-validated rubric.

[^2]: **Response completeness** refers to the extent to which a system’s reply covers all required informational components of the user’s query (as specified by a task-level checklist or rubric).

[^3]: **Response latency** refers to the time elapsed between a user message and the system’s response.

[^4]: For Level-1 (L1) “minimum viable evaluation” (MVE) metrics, acceptable thresholds should be explicitly specified to support go/no-go deployment decisions (e.g., ≥70% accuracy for emergency-intent detection in a health chatbot may be considered minimally launchable, whereas performance below this threshold would not meet MVE criteria).
