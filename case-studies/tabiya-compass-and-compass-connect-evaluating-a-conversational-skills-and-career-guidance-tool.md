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

# Tabiya - Compass and Compass Connect: evaluating a conversational skills and career-guidance tool

How Tabiya evaluated Compass and Compass Connect, a conversational skills and career-guidance tool for jobseekers, across the playbook's four levels — and the design choices behind each evaluation.

**Sector:** Employment & livelihoods | **Product maturity:** Pilot | **Impact evidence:** RCT underway | **Evaluation window:** 2024–2026, ongoing | **Last updated:** November 2026

#### How the product is expected to create value

**If** jobseekers get a profile of their skills in labour-market language, including experience that never appears on a CV, **then** they make better-informed decisions about which jobs, training, or self-employment to pursue, and employers can see and hire for skills they would otherwise miss, **because** poor information on both sides of the market keeps people, especially those with informal or unpaid work histories, out of opportunities that fit them.

#### At a glance

<table data-header-hidden data-search="false"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><strong>Organization</strong></td><td>Tabiya, a nonprofit: Tabiya US, a 501(c)(3) public charity in Washington, DC, and Tabiya Solutions for Economic Opportunity gGmbH, a nonprofit company in Cologne. Founded at the University of Oxford. All components are open source (MIT licence) at github.com/tabiya-tech.</td></tr><tr><td><strong>What the tool does</strong></td><td>Compass helps jobseekers describe their experience in conversation, including unpaid, informal, and care work, and turns it into a skills profile and CV in the language of the labour market. Compass Connect adds career guidance, career-readiness practice, and matches to specific vacancies.</td></tr><tr><td><strong>Primary user</strong></td><td>Jobseekers, most with little formal work history (where a counselor uses it alongside the jobseeker, as in Kenya, the jobseeker is the beneficiary)</td></tr><tr><td><strong>Reach</strong></td><td>About 6,000 onboarded jobseekers across five Tabiya-run pilot, evaluation, or research deployments, cumulative since each launched (earliest current deployment: September 2025), as of September 2026 <em>(platform analytics)</em>. An onboarded user is a distinct account that accepted the terms and started a first conversation. Partner-run components are not counted here.</td></tr><tr><td><strong>Delivery channel</strong></td><td>Mobile-optimized web chat; embedded in partner platforms; API or backend service; in-person facilitated</td></tr><tr><td><strong>Scope</strong></td><td>Compass and Compass Connect in Tabiya's own deployments, which Tabiya runs only for piloting, development, learning, and evaluation. Tabiya's other components (a taxonomy, a classifier, and a matching engine) and partner-run deployments are not covered. Because components run separately or together, Tabiya chooses the unit of evaluation per deployment; its preferred model is for governments and large platforms to run them in their own systems.</td></tr><tr><td><strong>Service context</strong></td><td>Varies by deployment, and enrollment follows each study's design. Most jobseekers use Compass on their own phones, with assisted onboarding at Zambian TEVET colleges; in Kenya it is used inside a counseling session, and the trial there tests whether AI and human counselors are complements or substitutes.</td></tr></tbody></table>

#### Evaluation coverage

|                   | L1 Model                                           | L2 Product                   | L3 User                                                                   | L4 Impact     |
| ----------------- | -------------------------------------------------- | ---------------------------- | ------------------------------------------------------------------------- | ------------- |
| **Depth**         | ● Substantive                                      | ● Substantive                | ◐ Partial                                                                 | ● Substantive |
| **Evidence base** | 1,596 synthetic queries; 1,000+ real conversations | \~6,000 users; 5 deployments | Trials of \~4,000 and \~3,950; surveys, focus groups, and in-app feedback | 4 RCTs        |

***

## Level 1 — Model evaluation

> **Does the AI system perform as intended?** · [Level 1 →](https://eval.playbook.org.ai/model-behaviour/level-1-module-evaluation/overview)

**Decision problem.** Before real users saw it, could Tabiya trust Compass to extract what people say accurately, link skills to the taxonomy with high recall, and trace every reported skill to something the user actually said?

**What they did.** Grew the evaluation bottom-up with the product, starting from end-to-end simulated conversations and adding targeted tests as tasks became clear — eight methods today, from 1,596 synthetic taxonomy queries and persona-based simulation to manual review of more than 1,000 real pilot conversations.

**What changed.** Prompt rewrites; a revised embedding strategy; state guardrails that replace ambiguous model decisions with rules — for example, "collect at least one complete experience before proceeding"; and repeated iterations of the matching algorithm.

<details>

<summary>How they did it — methods, datasets, and metric choices</summary>

**Rubric and metrics** _(playbook L1 steps 1–2)_

The current test bench scores four things. **Precision** is the share of skills in the skills report that are backed by something the user said. **Recall** is the share of a person's skills that the report captures; for taxonomy matching alone, it is recall at k on the synthetic query sets. **Ease** is how quickly, and with how little effort, a user gets to something useful, tracked through a small set of indicators. **Safety** covers whether the conversation stays within its guardrails.

Thresholds were defined but not quantified: the team wanted to maximize recall and would not accept fabricated skills, but did not write down numeric pass marks before looking at results.

The organization-wide dashboard keeps three level-1 indicators: classifier precision, recall, and F1 on labelled South African occupation and skill sets; automated evaluator scores by model configuration, including open-weight models; and the model and prompt version running in each deployment.

**Golden dataset** _(playbook L1 step 3)_

Mostly created by the team. The synthetic query sets and the scripted dialogues were written in-house; simulation personas come from Tabiya's own UX research; real conversations come from the pilots.

**The eight methods:** embedding evaluation (which taxonomy properties to embed and how many candidates to retrieve, on established datasets and synthetic queries); synthetic query testing; isolated component tests for each agent tool; summarization tests on hand-crafted conversations; scripted dialogue tests of agent-to-agent transitions; persona-based simulation, end to end and for partial flows; Wizard-of-Oz testing, in which a developer played Compass; and real-world pilots with manual review, tracing each reported skill back to the input.

**Scoring, error analysis, automation** _(playbook L1 steps 4–5)_

Both humans and models score: developers and reviewers doing trace analysis, and LLM judges for subjective dimensions such as relevance and conversation quality. Failures are categorized first by level — model (a wrong skill, a missed extraction) or product (drop-off, session loss) — then by component: which agent, which transition, which pipeline stage.

Every change goes through code review and an automated test suite in continuous integration (component tests, scripted dialogues, and simulation runs), and every new prompt, schema, or taxonomy update passes validation before deployment. There is no numeric gate; a change ships when the tests pass and a reviewer approves. LLM judges run on a stronger model than the agents they grade: Gemini Pro grades outputs from Gemini Flash and Flash-Lite.

**Red-teaming** _(playbook L1 step 6)_

Internally yes, externally no. The simulation driver includes personas and instructions written to stress the system — off-topic users, incomplete answers, users who ask questions back, users with no formal experience — and developers ran adversarial scripted dialogues and reviewed real conversations for misbehavior. The findings led to prompt improvements.

**Alternatives considered, and tools**

**Fine-tuning** was rejected in favour of prompting, task decomposition, and taxonomy grounding, which need no training data and keep the system portable across countries and models. **A single standardized scorecard** was rejected in favour of metrics matched to what each stage needed to learn. **A comprehensive test plan written up front** was rejected because the team did not yet know which tasks the system would need to perform. **Gemini on Vertex AI** was chosen over OpenAI models for task accuracy, latency, rate availability, cost, and the ability to keep inference in a specific Google Cloud region, and an **in-house multi-agent framework** over LangChain. Full inventory in the Tools section below.

</details>

***

## Level 2 — Product evaluation

> **Does the overall product engage and retain users?** · [Level 2 →](https://eval.playbook.org.ai/product-analytics/level-2-product-evaluation/overview)

**Decision problem.** Once real users had it: did they complete the conversation, and if not, where and why did they stop — and would the infrastructure hold when many arrived at once, on low-end phones and poor connections?

**What they did.** Tracks a funnel in every deployment, from accepting the terms through the core action — a skills report — to return visits at 1, 7, and 30 days, harmonized across deployments into five indicators with fixed definitions; the early pilot phases ran sequentially rather than randomized: fix, redeploy, measure again.

**What changed.** In the first product test, with Ajira Digital in Kenya from April 2025, drop-off fell from more than 90 percent in the first deployment phase to 44 percent in the last, after a series of fixes to authentication, onboarding, prompt length, and fallbacks. One change backfired. Compass asked about experience in a fixed order, with volunteering last, and many users whose most relevant experience was informal or voluntary dropped off before reaching it, so the team moved volunteering first. This had an unintended effect: the model treated volunteering as a fallback for users with nothing recorded, so placed first, it went into encouragement mode prematurely and misread users' situations. The fix removed fallback behavior tied to position and added state checks so tone matched what the user had said. A product decision had introduced bias into model behavior, against the users the tool was built for.

<details>

<summary>How they did it — instrumentation and changes made</summary>

**Metrics and instrumentation**

Each deployment's funnel covers: accepted terms and started the first conversation; progress through conversation phases; skills report generated (the core action); CV downloaded; return within 1, 7, and 30 days; monthly active users; and in-app feedback — plus conversation depth, skills identified per session, and the share of experiences from the unseen economy. Compass Connect adds matches viewed, applications, and referrals. The organization-wide dashboard harmonizes five indicators across deployments: onboarded users, monthly active users, N-day return rate, core-action completion, and three-month downstream outcomes. Monitoring runs live, through partner analytics and Sentry, with later batch review.

**Experimentation approach** _(playbook L2, methods for experimentation)_

No controlled comparison in production. Two things stopped it: user numbers per Tabiya-run deployment are in the hundreds to low thousands, too small for most A/B tests; and, more importantly, most users sit inside an impact-evaluation sample, where treatment cannot be changed for a subset without the principal investigators' agreement. The engineering side is ready — prompts and templates are versioned components — and the impact evaluations themselves compare versions in a controlled way.

**Why users weren't engaging** _(playbook L2, why aren't users engaging?)_

In the early Kenya pilot: authentication and session failures under load, no progress indicator, unclear onboarding, and cognitive load — the more experiences a user explored, the likelier they were to abandon — plus connectivity. Tabiya notes that drop-off can be a correct decision: a jobseeker who sees stale vacancies and leaves has not misunderstood the product.

**Changes made**

Simplified authentication with reconnect logic; entry without registration codes; progress bars and time estimates; short onboarding messages explaining what would be asked and why; shorter prompts broken into checkpoints; deterministic fallbacks in place of ambiguous model decisions.

**Alternatives considered, and tools**

The Agency Fund offered its **Evidential** platform for A/B tests; Tabiya would consider using it once user numbers allow, with the agreement of its partners. For organization-wide figures, Tabiya built an **analytics tool outside the product** rather than relying on in-product analytics, because funders need frozen, dated numbers and partner-reported figures have no database to read from.

</details>

***

## Level 3 — User evaluation

> **Does the product change users' thoughts, feelings, knowledge and behavior towards the development outcome?** · [Level 3 →](https://eval.playbook.org.ai/user-experience/level-3-user-evaluation/overview)

**Decision problem.** Does using Compass change what jobseekers believe and how they search — and could it leave someone worse off, if learning their skills are in low demand discourages rather than redirects them?

**What they did.** Measures belief updating, confidence, and search behavior as intermediate outcomes inside the randomized trials, alongside focus groups and open-ended in-app feedback.

**What changed.** Tabiya tried NLP analysis of conversation logs as an outcome signal; it did not produce a clear one, so the team decided against relying on it.

<details>

<summary>How they did it — measures and findings</summary>

**Outcome metrics** _(playbook L3, identify outcome metrics)_

Belief updating, confidence, and search behavior, measured as intermediate outcomes in the trial endlines. Not yet available in a causal sense for Compass.

**Guardrail metrics and harm** _(playbook L3, guardrail metrics)_

Two risks named: learning that one's skills are in low demand could discourage rather than redirect search, and a user can lose time on a product that holds nothing for them. Tabiya relies on the randomized trials to determine impact on users. The trials measure job-search self-efficacy and search effort, so a discouragement effect would show up there, and in production the team watches user feedback and sentiment in the logs.

**Methods and instruments**

Surveys, interviews, and behavior inside the product. Trial samples since September 2025: roughly 4,000 in South Africa, about 3,950 at baseline in Kenya, about 1,000 invited in Argentina, and a target of about 2,000 in Zambia. Qualitative work includes focus groups in Kenya and an analysis of open-ended in-app feedback.

**Findings** _(playbook L3, why aren't thoughts and behavior changing?)_

So far, these are descriptive signals only. South African pilot participants described the conversation as confidence-building and said they felt listened to. Users say that seeing where a skill came from makes them accept it.

**Alternatives considered, and tools**

**NLP analysis of conversation logs** as an outcome signal was tried and set aside, because it did not produce a clear signal. Qualitative coding is manual, with experimental LLM-assisted reading of conversation-log samples.

</details>

***

## Level 4 — Impact evaluation

> **Do users with access to the product improve development outcomes?** · [Level 4 →](https://eval.playbook.org.ai/social-impact/level-4-impact-evaluation/overview)

**Decision problem.** Does Compass cause better job search, employment, and earnings? Where in the chain does any effect sit, and when components ship together, which one is doing the work?

**What they did.** Four of Tabiya's Compass deployments include a randomized trial, in South Africa, Kenya, Argentina, and Zambia. In South Africa, the endline is being analyzed.

**What changed.** Nothing yet: the first endline is still being analyzed.

<details>

<summary>How they did it — design, counterfactual, and outcomes</summary>

**Method, and why it was chosen** _(playbook L4, methods primer)_

Tabiya grew out of research at the University of Oxford, and so rigorous evaluation has been at the core of all its work. Analysis plans were written down or registered before data collection in all cases; the South Africa plan is on the AEA registry.

**Design and counterfactual** _(playbook L4, key design considerations)_

* **South Africa** — on SAYouth.mobi with Harambee Youth Employment Accelerator; designed at Oxford and implemented with J-PAL Africa. About 4,000 participants (1,900 Compass, 1,900 control, 200 static skills form); pilot in September 2025; the main trial randomized 4,200, and about 3,800 completed treatment. Endline being analyzed.
* **Kenya** — with Swahilipot Hub Foundation and NCCK, funded by J-PAL and CSAE: AI-augmented counseling versus counseling alone versus control, testing whether AI and human counselors are complements or substitutes, and whether guidance works by informing or by persuading and activating. Target about 4,000; roughly 3,950 enrolled by mid-2026.
* **Argentina** — an individual-level trial with Fundación Empujar (Brújula) and the World Bank, led from Oxford with a University of Mannheim co-lead. Because the initial sample was low, Tabiya plans to run another round with the next cohort.
* **Zambia** — Njila.ai for TEVET students, evaluated independently by the World Bank's DIME unit; target about 2,000 students.
* **South Africa, employer side** — an evaluation of skills-based matching on SAYouth.mobi with Harambee, in design.

What the comparison group receives is context-specific.

The South Africa endline will finish in November 2026. In Kenya, the midline finishes in late October 2026 and the endline in March 2027; the Kenya study is currently under publication review.

**Outcome measures**

Intermediate: job-search behavior (application frequency, occupations targeted, search strategies), confidence in describing one's value, belief updating about prospects, and skills alignment. Final: employment status, earnings, job offers, and callbacks. Secondary: job quality, self-efficacy, time use, and well-being. A range of mechanisms, beliefs, and aspirations are also measured. Employment and earnings matter most in the end, but in labour markets where formal jobs are scarce, a shift in beliefs and search behavior is a meaningful result in itself — and the intermediate measures show where in the chain any effect sits. Data come from in-person surveys, phone surveys, WhatsApp and email surveys, Tabiya's own metadata, partner platform data, and qualitative feedback.

**Prior evidence**

A completed randomized evaluation in Addis Ababa, coauthored by Tabiya's CEO (Witte et al. 2025, IZA Discussion Paper 18005), found that better vacancy information in public employment offices raised the monthly earnings of lower-skill women by about 22 percent, at roughly USD 0.40 per targeted jobseeker. The study tested workflows and tools that motivated Tabiya's founding, but predates Tabiya's current tech stack. Tabiya does not present it as evidence for Compass.

**Alternatives considered, and tools**

Analysis in R, Stata, and Python.

</details>

***

#### Metrics, thresholds, and results

Tabiya tracks about fifteen organization-level indicators plus engineering metrics per release; in most cases no numeric target was set in advance. No safety metric is set at Levels 2 to 4.

| Level          | Metric                                               | Threshold → Result                                                                                      | Why this metric                                                                                          |
| -------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| L1             | Precision and recall                                 | Defined, not quantified (maximize recall; minimize fabricated skills) → not reported as a single figure | Decided the move from lab to first pilot; a missed skill is worse than an extra candidate filtered later |
| L1 · guardrail | Release gate — automated tests and simulations in CI | Pass or fail, no numeric gate → ships when tests pass and a reviewer approves                           | What would stop a release                                                                                |
| L2             | Conversation drop-off rate                           | None set → from more than 90% to 44% across pilot phases, Kenya, from April 2025                        | Decided the move from pilot to impact evaluation                                                         |
| L3             | Confidence and job-search behavior                   | Pre-registered → South Africa endline being analyzed                                                    | Shows where in the chain any effect sits                                                                 |
| L4             | Employment and income                                | Pre-specified → South Africa endline being analyzed                                                     | Employment and earnings matter most in the end                                                           |

#### Time, Effort, and Cost

| Level                  | Timeline           | Effort                                                                                                                        | Direct cost                                                                         |
| ---------------------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| L1                     | 2024 – ongoing     | Not separable; built into engineering                                                                                         | Not disclosed; described as very small (inference for simulations and judge models) |
| L2 and L3              | Apr 2025 – ongoing | Several people over about 5 calendar months of program and engineering time and UX research; not separated into person-months | Not disclosed (participant incentives, compute, infrastructure)                     |
| L4                     | Sep 2025 – ongoing | Largest item                                                                                                                  | Substantially partner-funded                                                        |
| Cross-level: analytics | 2026 – ongoing     | About 6 person-months (4 for organization-wide dashboards, 2 for partner analytics)                                           | Not disclosed; described as small (cloud hosting)                                   |

**Team composition.** CEO, Head of Programs, Research Lead, three software engineers, a fractional chief product officer, and a program associate, plus research-partner and partner staff.

{% hint style="info" %}
**Hardest part.** Observability: the model Tabiya prefers — a partner running its components — is the one it sees least of, and fixing that is as much contractual as technical. Also attribution within a bundle, year-long endlines, and reporting the same dated figures to every funder when partners hold part of the data.
{% endhint %}

<details>

<summary>Tools used</summary>

**Product stack**

* **Base model** — Gemini Flash and Flash-Lite; exploring open-weight models, which partners with data-residency requirements can run on their own infrastructure. · L1
* **Fine-tuning or adaptation** — none. · L1
* **Embeddings and retrieval** — text-embedding-005 on Vertex AI. · L1
* **Vector store** — MongoDB Atlas vector search. · L1
* **Orchestration** — in-house multi-agent framework in Python and FastAPI; an "agent director" coordinates task-specific agents with internal state; no LangChain. · L1
* **Schema validation** — Pydantic; JSON schema validation with retries. · L1
* **Speech to text / text to speech** — none in production; a voice prototype for Ethiopia uses Google Chirp and Twilio. · L1
* **Translation** — none. · L1
* **Image or vision model** — none. · L1
* **Delivery integration** — mobile-optimized web app (React, TypeScript, Material UI) served from Google Cloud Storage with Google Cloud CDN, a FastAPI backend on Google Cloud Run, infrastructure as code in Pulumi, and Docker Compose for self-hosted deployments. · L2

**Evaluation tooling**

* **Annotation and labelling** — manual, by the team. · L1
* **Golden dataset management** — synthetic query sets and scripted dialogues in the code repository. · L1
* **Evaluation harness** — in-house test suite (pytest) in continuous integration, with an LLM-driven simulated-user driver. · L1
* **Judge model** — Gemini Pro and Claude Opus, plus human reviewers. · L1
* **Prompt and version tracking** — Git, versioned prompt and template components, Langfuse. · L1, L2
* **Telemetry and product analytics** — Langfuse. · L2
* **Error monitoring** — Sentry, Google Cloud monitoring, Langfuse. · L1, L2
* **Experiment platform** — none yet. · L2
* **Survey instruments** — standard measures used in economics and psychology, plus piloted exploratory items, especially in the beliefs section; collected via different survey modalities (in-person, phone, WhatsApp, SMS, and online). · L3, L4
* **Qualitative coding** — manual coding of focus groups and open-ended feedback; experimental LLM-assisted reading of conversation-log samples. · L3
* **Analysis** — R, Stata, Python. · L4
* **Dashboards and reporting** — Tabiya's internal analytics dashboard; partner analytics in Compass Connect. · L2

</details>

<details>

<summary>Donor and funder engagement</summary>

**Was evaluation required by a funder, and at which level?** No. Tabiya grew out of research at the University of Oxford, and so rigorous evaluation has been at the core of all its work.

**Did evaluation evidence change the funding relationship?** Not in a way Tabiya can point to: its sense is that funders appreciate the strong focus on impact evaluation, but it cannot name a specific funding decision that depended on it.

</details>

<details>

<summary>Sources and reporting statement</summary>

**Sources.** A written pre-work sheet, Tabiya's review and edits of the draft, and written communication.

**Relationship disclosure.** No funding from the Agency Fund to date. The Agency Fund offered its Evidential platform for A/B tests, and Tabiya uses the Agency Fund's evaluation framework internally.

**Reporting statement.** Guarantor: Afsana Khan, Head of Programs. Figures as of September 2026. Figures are self-reported by the organization. Tabiya has verified this version for factual accuracy; editorial conclusions remain with the playbook authors.

**Limit.** This case study is not an audit. Figures have not been independently verified.

</details>
