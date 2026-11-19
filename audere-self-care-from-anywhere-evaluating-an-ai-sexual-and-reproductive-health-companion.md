# Audere -  Self-Care from Anywhere: evaluating an AI sexual and reproductive health companion

How Audere evaluated Self-Care from Anywhere, a WhatsApp-based AI companion for sexual and reproductive health and HIV care, across the playbook's four levels — and the design choices behind each evaluation.

**Sector:** Health | **Product maturity:** Scaling | **Impact Evidence:** Observational | **Evaluation window:** 2024–2026, ongoing | **Last updated:** November 2026

#### How the product is expected to create value

**If** people who lack regular access to healthcare get a private, always-available WhatsApp companion that discusses sexual and reproductive health and HIV prevention in a clinically appropriate, locally grounded way, **then** they seek out and connect to services — HIV testing, PrEP, PEP, ART, and related care — that they would not otherwise have reached, **because** a private conversation lowers the stigma and access barriers that keep people from raising these topics with a clinician in person.

#### At a glance

<table data-header-hidden><thead><tr><th width="201.30303955078125"></th><th></th></tr></thead><tbody><tr><td><strong>Organization</strong></td><td>Audere (501(c)(3) nonprofit, US, with a secondary entity in Africa). Core platform is proprietary; a mental health evaluation framework and taxonomy is being open-sourced with a consortium of contributors, funded by the Wellcome Trust with PATH as prime partner.</td></tr><tr><td><strong>What the tool does</strong></td><td>A closed-loop system for people lacking regular access to healthcare, currently focused on sexual and reproductive health and HIV, expanding into mental health and primary healthcare</td></tr><tr><td><strong>Primary user</strong></td><td>Individuals seeking care via WhatsApp (nurses and clinicians separately use a clinical portal for longitudinal client data and communication)</td></tr><tr><td><strong>Reach</strong></td><td>200,000+ users who have sent at least one message (as of October 2026); growing by roughly 25,000 a month toward a target of 1,000,000 by June 2027</td></tr><tr><td><strong>Delivery channel</strong></td><td>WhatsApp, with a separate clinical portal for nurse and clinician case management</td></tr><tr><td><strong>Service context</strong></td><td>Runs with ministries of health and implementing partners in South Africa, Zimbabwe, and, from late 2026, Mozambique. Users join on WhatsApp through QR codes or links promoted by peer ambassadors, clinic staff, call centres, and social media. The AI mostly extends existing services, adding private, 24/7 support between clinic visits. Diagnosis, treatment, and referrals stay with people.</td></tr></tbody></table>

#### Evaluation coverage

|                   | L1 Model                                                                                  | L2 Product                          | L3 User                                                                      | L4 Impact                                     |
| ----------------- | ----------------------------------------------------------------------------------------- | ----------------------------------- | ---------------------------------------------------------------------------- | --------------------------------------------- |
| **Depth**         | ● Substantive                                                                             | ● Substantive                       | ◐ Partial                                                                    | ◐ Partial                                     |
| **Evidence base** | 1,000 question and answer pairs; 2000+ real conversations; every live conversation scored | >200,000 users; 3 feature A/B tests | 244 free-form responses;  \~46,000 thumbs-up/down ratings;in-product surveys | 10,000-user feasibility study; 1 RCT approved |

***

## Level 1 — Model evaluation

> **Does the AI system perform as intended?** · [Level 1 →](https://eval.playbook.org.ai/model-behaviour/level-1-module-evaluation/overview)

**Decision problem.** Audere needed three things from evaluation: safety guardrails strong enough for sensitive sexual and reproductive health conversations, a way to choose the best model for each task in a system that routes work across several models, and monitoring that keeps running in the field.

**What they did.** Built a proprietary framework of about eight automated metrics led by clinical appropriateness — a composite of correctness, completeness, and harmfulness — scored by LLM judges calibrated against trained local labellers. It runs before launch and every quarter on a benchmark that includes more than 2,000 real multi-turn conversations, and continuously on every live conversation, with clinicians labelling a sample.

**What changed.** Evaluation results drive production directly: after each cycle, Audere's orchestrator re-selects the primary model for each task, with a fallback always from a different provider. An example of a recent discovery by the hybrid real-time field monitoring system: clinicians labelling a sample of live conversations escalated a people-pleasing bias in GPT-5.1, which was validating users' complaints about clinical staff — a pattern that could erode trust in the public health services the product exists to connect people to. The team rapidly iterated on the product in response, and revised the benchmarking dataset so future evaluations test for it. Issues like this can be missed by quarterly evaluation alone, which is why field monitoring matters beyond one-time evaluation.

<details>

<summary>How they did it — methods, datasets, and metric choices</summary>

**Rubric and metrics** _(playbook L1 steps 1–2)_

Approximately eight automated metrics: **clinical appropriateness** (correctness, completeness, and harmfulness) as the primary metric, alongside **empathy**, **stigma**, **persona adherence**, **local appropriateness**, **cost per token**, and **word count** (tracked because concise responses matter over WhatsApp). The metrics are continually augmented; the stigma metric is being refined to detect when a model agrees with criticism of the public health system. Each metric carries a pre-set numeric threshold, and results are reviewed as a team using a weighted approach across metrics. The same metrics are applied in quarterly evaluation and in continuous field monitoring.

The architecture also includes a context engine, a knowledge base, and a slang dictionary; the context engine was co-designed with local communities and Ministries of Health, so that responses are grounded in local health contexts.

**Golden dataset** _(playbook L1 step 3)_

The benchmark has grown from 1,000 question-and-answer pairs to also include more than 2,000 multi-turn conversations curated from actual user interactions, expanding gradually over the last year. Periodic evaluations run on a sample of the dataset sized for statistical significance rather than the whole set. It is stored in DynamoDB and labelled in an in-house tool.

Labelling is done in each country by contracted, trained local teams: clinicians and trained counselors label for accuracy, and a separate team of people with lived experience labels for stigma, tone, and empathy. The same set-up is live in South Africa and Zimbabwe. A clinician quality-control team checks the labels and escalates issues back to Audere.

**Scoring, error analysis, automation** _(playbook L1 steps 4–5)_

LLM-as-judge scoring draws on several candidate judge models, including Gemini 3 Flash Preview, GPT-OSS, Qwen 3, and Gemma 4. The best judge is chosen through regular judge evaluations against human-labelled data from Audere's hybrid review system, and different metrics may use different judges. Human labels serve as ground truth for tuning detectors, improving responses, and identifying gaps in the system.

**Continuous field monitoring.** Automated monitoring scores every live conversation, and human labellers review a sample; as it scales, Audere is moving to sampling live conversations. Every conversation is first translated into English, so programs can be analysed together, and all automated scoring and disclosure flagging run on the English translations, with a human labelling layer that checks the translations themselves. Audere has not compared judging in the original language against judging the translation. When a score falls below its threshold, the failure is categorised, assigned a severity, and filed automatically; failures are triaged, AI clinical and product leads review summaries weekly, and any potential patient-safety issue goes immediately to program clinicians for outreach. Fixes go into prompts, routing, or model choice, and the benchmark is updated so future evaluations test for the issue.

**Harm disclosures and escalation.** A safety framework looks for disclosures of harm — self-harm, gender-based violence, sex with a minor, violence, harassment, and others — and for other risk signals, including an HIV-positive test result, a mismatch between a user's reading and the computer-vision reading of an uploaded self-test, high vulnerability to HIV transmission, and depression, anxiety, and alcohol-use screening results. Disclosure flagging combines a major LLM provider's moderation API with Audere's own algorithms for suicide and self-harm and for gender-based violence and sexual assault, built to augment the API after it proved noisy and missed real disclosures. Flagging runs on every message, in real time, 24 hours a day. When a potentially harmful situation is detected, a priority task with a summary of the conversation appears instantly in the clinical portal, and at the same moment the AI responds with support and local crisis-line numbers matched to the type of harm. The clinical team works weekdays, 8am to 4pm; flags raised outside those hours are picked up the next working day, while the AI keeps supporting the user and checks in later. Audere is working with the ministry of health and implementing partners on evening and weekend cover. From September 2025 to October 2026, the framework flagged 16,554 conversations across 12,830 unique clients for self-harm, each routed to the clinical portal for review. Since April 2026, when a new gender-based violence flag replaced one that was over-flagging, it has flagged 3,426 conversations across 2,886 clients.

**What stays with people.** The AI does not diagnose, and it does not replace contact with nurses, clinicians, or other people; for clinicians, it provides decision support, and clinicians still decide the care plan. People review flagged disclosures and reach out where needed; make referrals and appointments; carry out testing, diagnosis, and treatment, including confirmatory testing and prescribing; counsel users who need or ask for a person; and label and quality-check the AI's outputs.

**Red-teaming** _(playbook L1 step 6)_

Two internal sessions a week try to break the system, and a paid external partner team in South Africa runs weekly red-teaming sessions to identify faults. The GPT-5.1 bias, however, was found through field monitoring: clinicians labelling a sample of live conversations escalated it.

**Alternatives considered, and tools**

**MLflow** was tried first for both the evaluation harness and the labelling tool, and dropped for both: it did not meet Audere's needs for data ingestion and ease of metric tuning, so both were built in-house. The orchestrator assigns models to four tasks — conversation, structured data extraction, summarisation, and judging — and **fallback models always come from a different provider** than the primary, so one vendor's outage cannot take the system down. For Northern Ndebele, **a fine-tuned GPT-4o model and Google Translate serve as primary and fallback**. Audere assessed having the AI work directly in the original language, but chose to **translate every conversation into English first**: it was more scalable to new languages and serves the downstream processes that depend on the conversations. Field monitoring has also led Audere to switch translation models based on how they perform in the field. Full inventory in the Tools section below.

</details>

***

## Level 2 — Product evaluation

> **Does the overall product engage and retain users?** · [Level 2 →](https://eval.playbook.org.ai/product-analytics/level-2-product-evaluation/overview)

**Decision problem.** Were users getting what they came for — a connection to care, or an answer that got them unblocked? Consumer products drive engagement for its own sake, because attention earns revenue; a health product pays for every conversation, so Audere aims for only as much engagement as a user needs to meet their goal and, ideally, to take up and stay in care.

**What they did.** Tracks a funnel covering engagement and connections to care, and runs A/B tests: three on product features, including an ongoing five-way voice-note test in a program of about 30,000 clients, and many more on nudges.

**What changed.** Personalised nudges raised engagement by about 10 percent; together with reminders — a feature users requested, prompting medication pickups and clinic appointments — they bring people back, alongside acute health needs. Drop-off analyses now feed product improvements.

<details>

<summary>How they did it — instrumentation and changes made</summary>

**Metrics and instrumentation**

Sixty percent of users have a conversation of more than two messages, against a pre-set threshold of 50%; about 30 percent meet a higher engagement tier, sharing meaningful personal information or returning for multiple sessions. Engagement follows a weekly cycle, falling at weekends and rising on weekdays. The funnel also tracks connections to care. Telemetry runs on Plotly and psql.

In the Aimee study (see Level 4), 9,310 of the 9,958 people who initiated contact enrolled (93.5%); within this cohort, 80.9% sent at least five messages and 58.6% returned on at least two distinct days.

Users also rate answers with a thumbs up or down — about 46,000 ratings between September 2025 and October 2026 — and complaints they make to the AI companion or to a nurse about the product not working are pulled from conversations. Every product goes through usability studies, and ongoing partnerships with the University of Cape Town, Wits, the University of Washington, Stanford, Harvard, and others evaluate new features, functionality, and feasibility across populations.

As the platform scaled, the cost of delivering the service fell from about $3.00 to roughly $1.00 per user per year, and to about $0.75 among female sex workers in Zimbabwe, whose conversations are more directed. Audere treats evaluation as part of the product rather than a separate activity: this per-user cost includes safety, ongoing evaluation, and monitoring — field monitoring, at about $0.05 per user per year, is part of it.

**Experimentation approach** _(playbook L2, methods for experimentation)_

Three product-feature A/B tests to date, run on an Audere-built platform with results visible through Plotly dashboards, plus many more on nudge messaging, timing, and engagement. Sample size varies by experiment. The team generally picks a specific product to test in, and sometimes varies features across products. The voice-note experiment is an ongoing five-way test, with new users randomly assigned to groups, in a smaller program of about 30,000 clients.

**Why users weren't engaging** _(playbook L2, why aren't users engaging?)_

Once a program reaches a certain stage, the team analyses drop-off: why people leave — they got what they needed, they did not get the right help, or other reasons — where in the funnel they leave and what preceded it, to find friction in the product, and whether people achieved their own goal and how that contributed to care uptake and retention. Engagement is read alongside those goals rather than in isolation.

**Changes made**

Personalised nudges, tested through the A/B platform, consistently increased engagement by about 10 percent. A reminders feature, added at users' request, prompts medication pickups and refills and clinic appointments at intervals before the event, on the day, and afterwards, when it asks whether the user made it. Voice notes were added because users kept trying to send them and asked for them in co-design sessions.

**Alternatives considered, and tools**

**Evidential** was considered for A/B test analysis and may be revisited as Audere scales; cost was a factor, as with other tools. Audere's monitoring and evaluation system has run since mid-2024, before Evidential and similar tools existed, drawing on in-house expertise that mapped out the metrics from the start.

</details>

***

## Level 3 — User evaluation

> **Does the product change users' thoughts, feelings, knowledge and behavior towards the development outcome?** · [Level 3 →](https://eval.playbook.org.ai/user-experience/level-3-user-evaluation/overview)

**Decision problem.** Were conversations changing what users thought and did — and could a conversation leave someone worse off?&#x20;

**What they did.** Combines in-product feedback, partner-run sessions, and signals from conversations: how topics users raise evolve, and references to service referrals extracted automatically.

**What changed.** Weekly whole-team data reviews drive rapid improvements where the model's guidance falls short, and regular analysis shows whether people are reaching the intended outcomes. The surveys added a view of what _is_ working, alongside criticism the reviews had also caught.

<details>

<summary>How they did it — measures and findings</summary>

**Outcome metrics** _(playbook L3, identify outcome metrics)_

The team tracks the topics clients discuss and how those topic areas evolve over time, and is developing trust indicators and leading indicators — kinds of engagement that correlate with later care uptake and retention, which are trailing indicators.

**Guardrail metrics and harm** _(playbook L3, guardrail metrics)_

Audere's safety framework, which flags disclosures of harm and escalates them to clinicians, is described under Level 1. At the user level, periodic deep dives into drop-off can zoom in specifically on distressing conversations, including through topic extraction.

**Methods and instruments**

Once users have engaged a certain amount, they receive a six-question survey with a free-form feedback option; this is live in two of Audere's four programs. Between September 2025 and October 2026, 244 clients provided free-form feedback and users gave about 46,000 thumbs-up or thumbs-down ratings, alongside external surveys.

A structured-data-extraction schema built into the system extracts 140+ discrete data elements from conversations — including references to service referrals for HIV and gender-based violence — feeding impact measurement, product metrics, and safety together.

**Findings** _(playbook L3, why aren't thoughts and behavior changing?)_

The survey responses carried more positive feedback than the team expected, alongside constructive feedback. That gave a view of what is working, not only what is going wrong. The constructive points were also caught by the weekly data reviews, though the team does not assume both sources will always agree, and continues to use both. Because users kept raising anxiety and depression, Audere added screeners for both, with clinician escalation flags.

**Alternatives considered, and tools**

No alternative approach to measuring user-level change has been considered and set aside; the team describes this as an area it is continually looking to improve.

</details>

***

## Level 4 — Impact evaluation

> **Do users with access to the product improve development outcomes?** · [Level 4 →](https://eval.playbook.org.ai/social-impact/level-4-impact-evaluation/overview)

**Decision problem.** Does an AI companion improve uptake of HIV testing and prevention, and retention in care — and how can that be shown rigorously when trial funding is scarce and ministries need tools in people's hands now?

**What they did.** Has relied on observational and quasi-experimental designs. In a nine-month study of Aimee — Audere's first generative AI program and the first built on the platform — with 10,000 adolescent girls and young women (AGYW), about 35 percent took up HIV testing and about 15 percent PrEP, partly verified against a partner's clinical records. One randomized trial has been approved.

**What changed.** The Aimee study shaped the design of Audere's later pilots: it changed how the team measures connection to care and outcomes, and what it learned about engagement and drop-off fed product changes that made the service more robust.

<details>

<summary>How they did it — design, counterfactual, and outcomes</summary>

**Method, and why it was chosen** _(playbook L4, methods primer)_

Of one completed, three live, and one upcoming program, two were studied under IRB approval but not as randomized trials. No alternative designs were considered, given pressure to show results sooner — and not only from funders. As US State Department funding has left South Africa and Zimbabwe, ministries' priority has been getting tools into people's hands as clinics close and providers disappear, which has meant embedding AI in live programs quickly.

**Design and counterfactual** _(playbook L4, key design considerations)_

The approved RCT has two arms: users with the AI companion, and users without it.

**Outcome measures**

Aimee ran with SHOUT-IT-NOW's community HIV prevention program in Gauteng from March to November 2025; when the study ended, its users moved to Self-Cav, the National Department of Health's youth companion. In the study, HIV testing uptake was about 35 percent and PrEP uptake about 15 percent, with successful connections to PEP and ART also reported. The study began as a feasibility and acceptability study, with care uptake added as a goal, so no uptake threshold was set.

**How uptake was recorded.** In Aimee, testing and PrEP uptake were composite measures, counted only after a user's first contact with the AI and drawn from three sources: SHOUT-IT-NOW's clinical management system, linked through privacy-preserving referral IDs; HIV self-test photos read by the computer-vision model and reviewed by a provider (testing only); and self-report in conversation. Care received at SHOUT-IT-NOW sites is verified by the partner's records; care received elsewhere, such as at public health facilities, could not be verified and rests on self-report. Audere's current programs measure uptake differently: mainly from what users say in conversation, through structured extraction and self-report. Some programs verify it against government clinic records or partner systems linked by a unique identifier, and Audere and its partners are working toward integration with national systems.

**Pitfalls addressed** _(playbook L4, common pitfalls)_

Audere's Chief Technology and AI Officer is taking an active role as co-investigator in the academic partnerships, so that study designs reflect the technical realities of AI deployment.

**Alternatives considered, and tools**

No alternative designs were considered, given the pressure to show results sooner.

</details>

***

#### Metrics, thresholds, and results

Decision-carrying metric per level, plus guardrails. Audere tracks about eight L1 metrics, continually augmented, and extracts 140+ data elements from conversations.

| Level          | Metric                                                                                                                                   | Threshold → Result                                                                                                                                                                                                                                                         | Why this metric                                                                            |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| L1             | Quarterly evaluation — clinical appropriateness, stigma, empathy, conciseness, cost, and others                                          | Pre-set per metric → reviewed with a weighted approach                                                                                                                                                                                                                     | Primary patient-safety check, before launch and every quarter                              |
| L1 · guardrail | Continuous field monitoring and harm-disclosure escalation — every live conversation scored; clinicians label a sample                   | <p>Pre-set per metric → failures filed and triaged; patient-safety issues escalated immediately; 16,554 self-harm conversations (12,830 clients), Sept 2025–Oct 2026, and 3,426 GBV</p><p>conversations (2,886 clients) since April 2026, flagged for clinician review</p> | Catches issues that quarterly evaluation alone can miss                                    |
| L2             | Engagement — share of users with conversations of more than two messages                                                                 | Pre-set: 50% → 60%                                                                                                                                                                                                                                                         | Conversation depth, read alongside connections to care                                     |
| L3             | None defined; Trust and leading indicators are in development                                                                            | Not applicable                                                                                                                                                                                                                                                             | <p>Audere is building</p><p>user-level indicators</p><p>that predict care</p><p>uptake</p> |
| L4             | HIV testing and PrEP uptake, Aimee cohort — partner clinical records, provider-reviewed self-test photos (testing only), and self-report | None pre-set; began as a feasibility study → \~35% HIV testing, \~15% PrEP                                                                                                                                                                                                 | Primary outcome signal ahead of a randomized trial                                         |

#### Time, effort, and cost

<table><thead><tr><th width="95.90911865234375">Level</th><th>Timeline</th><th>Effort</th><th>Direct cost</th></tr></thead><tbody><tr><td>L1</td><td>Framework R&#x26;D 2024-2026; quarterly cycles ongoing</td><td>Over 12 person-months (framework and metric work)</td><td><p>R&#x26;D: not disclosed; </p><p>~$500 per quarterly evaluation run</p></td></tr><tr><td>L2</td><td>Ongoing</td><td>About 2 person-months per year</td><td><p>Development: not disclosed; </p><p>field monitoring ~$0.05 per user per year, projected to fall to ~$0.025, within the delivery cost</p></td></tr><tr><td>L3</td><td>Not separable</td><td>Not separable</td><td>Not separable</td></tr><tr><td>L4</td><td>RCT pending</td><td>Not applicable</td><td>Not applicable</td></tr></tbody></table>

Costs in US dollars. Ongoing evaluation, safety, and monitoring are included in Audere's delivery cost of about $1.00 per user per year.

**Team composition.** Framework R\&D: two senior engineers, a senior product manager, and a local team including a clinician. Ongoing: a senior engineer, a senior product manager, a data scientist, and contracted labelling teams.

{% hint style="info" %}
**Hardest part.** That none of it stands still: the product, the clients, the models, and the metrics all keep changing — as the metrics should — so evaluation is "never a build once and deploy thing."
{% endhint %}

<details>

<summary>Tools used</summary>

**Product stack**

* **Base model** — primary and fallback pairs per task, re-selected after each evaluation: GPT-5.1 and Claude Haiku 4.5 for conversation; GPT-5 mini and Claude Haiku 4.5 for summarisation; GPT-5.2 and Claude Haiku 4.5 for structured data extraction; GPT-5 mini for selected tools called opportunistically. · L1
* **Fine-tuning or adaptation** — a fine-tuned GPT-4o for Northern Ndebele, paired with Google Translate as primary and fallback. · L1
* **Embeddings and retrieval** — text-embedding-3-small; RaptorPack. · L1
* **Vector store** — pgvector inside PostgreSQL. · L1
* **Orchestration** — Audere-built LLM orchestrator and router. · L1
* **Schema validation** — Audere-built. · L1
* **Speech to text** — Intron. · L1
* **Translation** — Gemini 2.5 Flash, GPT-4o, Google Translate, or Claude Sonnet 4.5, depending on language. · L1
* **Image or vision model** — an Audere-built computer-vision model to read and interpret rapid diagnostic tests. · L1
* **Delivery integration** — WhatsApp, via turn.io or 360dialog as business solution provider depending on the program. · L1, L2

**Evaluation tooling**

* **Annotation and labelling** — Audere text labeler, built in-house after MLflow. · L1
* **Golden dataset management** — DynamoDB. · L1
* **Evaluation harness** — Audere-built, after MLflow. · L1
* **Judge model** — candidates including Gemini 3 Flash Preview, GPT-OSS, Qwen 3, and Gemma 4; chosen per metric through regular judge evaluations against human-labelled data. · L1
* **Prompt and version tracking** — Audere-built, on GitHub. · L1
* **Telemetry and product analytics** — Plotly and psql. · L2
* **Error monitoring** — CloudWatch. · L1, L2
* **Experiment platform** — Audere-built, with Plotly dashboards. · L2
* **Survey instruments** — in-product six-question survey with free-form feedback; thumbs up or down; WhatsApp nudges; partner qualitative sessions and surveys; self-reported data extracted during conversations. · L3
* **Qualitative coding** — a structured-data-extraction schema of 140+ discrete data elements, built into the system, feeding impact measurement, product metrics, and safety. · L1, L3
* **Analysis** — Plotly, psql, and coding agents. · L1, L2, L4
* **Dashboards and reporting** — Plotly. · L2

</details>

<details>

<summary>Donor and funder engagement</summary>

**Was evaluation required by a funder, and at which level?** No. The Gates Foundation grant that funded Audere's initial Aimee program — an AI-powered sexual and reproductive health counselor and companion — about two years ago did not explicitly include safety or evaluation components. Building the framework was a self-driven decision, motivated by social responsibility and a background in traditional software engineering at companies such as Microsoft.

**Did evaluation evidence change the funding relationship?** Current and future funding is increasingly tied to evaluation capability. The Wellcome Trust is funding the open-sourcing of the framework's mental health component, with PATH as prime partner; a randomized trial has been approved; and Audere is exploring evaluation-focused grants from several funders, in what it describes as a competitive and limited funding environment. To contain development costs over the long term, Audere chose to self-invest in an extensible framework built to keep pace with regularly updated models.

</details>

<details>

<summary>Sources and reporting statement</summary>

**Sources.** Interviews with Rouella Mendonca, Audere Chief Technology and AI Officer, and Sarah Morris, Audere Chief Product Officer, a written pre-work sheet, and written communication.

**Relationship disclosure.** Audere has no funding or grantee relationship with the Agency Fund, IDinsight, and the Center for Global Development.

**Reporting statement.** Guarantor: Rouella Mendonca, Chief Technology and AI Officer, working with data scientist Sam Smedinghoff. Figures are as of October 2026. Figures are self-reported by the organization. Audere reviewed and verified this version for factual accuracy; editorial conclusions remain with the playbook authors.

**Limit.** This case study is not an audit. Figures have not been independently verified.

</details>
