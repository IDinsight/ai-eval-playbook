---
name: ai-eval-playbook-guide
description: >
  A deep guide to the AI Evaluation Playbook (eval.playbook.org.ai) — a 4-level framework for evaluating GenAI tools in the global development sector (health, education, agriculture, livelihoods in LMICs). Use this skill whenever anyone asks about AI evaluation for development outcomes, the 4-level framework (Model / Product / User / Impact evaluation), how to evaluate GenAI tools, what evaluations to run, what "good" looks like, how levels connect, or any question where the playbook would provide authoritative guidance. Also use it when someone says things like "how do I know my AI is working," "what should we measure," "how do I explain this to my funder," or "where do I start with evals." Always use this skill for any question touching GenAI evaluation in development, social impact, or LMIC contexts — even if the question seems basic.
---

# AI Evaluation Playbook — Deep Guide

> **The playbook is a living document.** The summaries below are a stable orientation, but the canonical content lives at the URLs listed under each section. **Always fetch the live page before composing a substantive answer** so your reply reflects the latest published content. State clearly when an answer is drawn from the live page vs. from cached summary content here.

**Canonical site:** https://eval.playbook.org.ai/
**Maintainer:** The Agency Fund (with IDinsight, CGD, OpenAI / AI4GD)

---

## How to fetch fresh content (priority order)

1. **`web_fetch`** the canonical URL directly. URLs only enter `web_fetch`'s provenance after they appear in a prior user message or prior `web_fetch` result, so work outward from a page you've already fetched (start at https://eval.playbook.org.ai/).
2. If `web_fetch` refuses, use **Control Chrome** to navigate:
   - `mcp__Control_Chrome__open_url` with the target URL
   - `mcp__Control_Chrome__list_tabs` to confirm the page loaded
   - `mcp__Control_Chrome__get_page_content` or `execute_javascript` to read the rendered content (may be flaky — fall back to opening the URL for the user so they can see it themselves).
3. **Dynamic Q&A**: every page has an `?ask=<question>` endpoint that returns a direct natural-language answer plus citations. Append `.md?ask=<URL-encoded-question>` to any page URL. Example: `https://eval.playbook.org.ai/model-behaviour/level-1-module-evaluation/overview.md?ask=what+is+a+golden+dataset`. Use this for narrow lookups when you don't want to fetch a whole page.
4. **Avoid the old GitBook-ID URLs** (`/spaces/<id>/pages/<id>` and `/pages/<id>`). They render but are internal IDs that don't always redirect to canonical paths. Use the semantic paths listed in this skill instead.

> **URL quirks to remember:**
>
> - Level 3 lives at **`/user-expereince`** — the misspelling is the canonical path. `/user-experience` 404s.
> - Two Level 3 sub-pages have slug/title mismatches: `/how-to-evaluate/descriptive-analysis` renders title "Identify outcome metrics"; `/how-to-evaluate/user-privacy-and-security` renders title "Why Aren't Thoughts, Feelings, and Behavior Changing?"
> - Section-root URLs (e.g. `/model-behaviour`) have a duplicate canonical at `…/overview.md` (e.g. `/model-behaviour/level-1-module-evaluation/overview.md`). Both work.
> - There is no standalone "Authors" page — authorship lives inside the Process and Contribute pages.

---

## High-Level Summary of the 4-Level Framework

The playbook is a unified framework for evaluating Generative AI (GenAI) tools deployed for social impact in low- and middle-income countries (LMICs). It bridges a long-standing gap: tech teams optimize for model performance and ignore impact; impact evaluators measure outcomes and ignore the underlying technology. The playbook ties both worlds together.

**Core premise:** Evaluating a GenAI tool for development outcomes requires four interconnected levels — none of which alone is sufficient.

| Level            | Question                                                                    | Primary owners                                                                          |
| ---------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| **L1 — Model**   | Does the AI system perform as intended?                                     | AI engineers, ML researchers; domain experts & PMs support                              |
| **L2 — Product** | Does the overall product engage and retain users?                           | Product managers, data scientists, UX researchers                                       |
| **L3 — User**    | Does the product change users' thoughts, feelings, knowledge, and behavior? | Behavioral scientists, social psychologists, public health researchers, M&E specialists |
| **L4 — Impact**  | Do users with access to the product improve development outcomes?           | Impact evaluators, economists, independent researchers (J-PAL, IPA, World Bank)         |

The four levels form a logical progression: users won't stay engaged (L2) if the system doesn't perform (L1), and development outcomes won't improve (L4) if engagement or user beliefs/behavior break down (L3). They are cyclical, not linear — issues at any level should trigger checks across the others. **Level Linkages** is its own section covering risk assessment, data protection, and process evaluations that span multiple levels.

---

## Sections & Pages — Verified Link Map

Every URL below was independently verified (HTTP 200, rendered title checked) on the most recent crawl. When answering a user question, identify the relevant section, **fetch that page live**, and quote from the live content.

### Introduction — Overview

The "About" entry points and the meta pages explaining how the playbook was made.

- **About this playbook (Home)** — https://eval.playbook.org.ai/
  The landing page. Explains why the playbook exists, who it's for (Implementors & Program Managers; Funders & Policy Makers), and introduces the 4-level framework. Use this as the first stop for funders, board members, or new team members.
- **The Process Behind it** — https://eval.playbook.org.ai/overview/the-process-behind-this-playbook
  How the playbook was built — lessons from the 2025 AI4GD Accelerator (TAF + OpenAI + CGD) with 8 non-profit GenAI products. Cite this when someone asks "who wrote this and why should I trust it?" Authorship/credit info lives here.
- **How to Contribute to the Playbook** — https://eval.playbook.org.ai/overview/how-to-contribute-to-the-playbook
  Steering Committee info, quarterly release cadence, how to suggest edits. Send grantees / partners here who want to add a case study or join the working group.

### Introduction — Setting the Foundation ("Getting Started")

Pre-evaluation building blocks that every team needs in place before diving into the four levels.

- **Building Blocks for GenAI Evaluation (section hub)** — https://eval.playbook.org.ai/getting-started/building-blocks-for-genai-evaluation
  Frames the two pillars of evaluation readiness: people (the team) and process (the infrastructure).
- **Building the Team** — https://eval.playbook.org.ai/getting-started/building-the-team
  Skillsets you need (AI engineers, data engineers, user researchers, social scientists, PMs) and how cross-functional teams should collaborate. Send users here for org/staffing/hiring-sequence questions.
- **Building the Infrastructure** — https://eval.playbook.org.ai/getting-started/building-the-infrastructure
  The reusable building blocks (theory of change, data infrastructure, version tagging, shared user/session IDs) teams should set up before diving into the four levels.

### Introduction — Additional Resources

Cross-cutting reference material — FAQs, terminology, MVE checklists, templates.

- **Frequently Asked Questions** — https://eval.playbook.org.ai/additional-resources/frequently-asked-questions
  Common doubts on roles, when to use each level, "do we need an RCT?", funder-facing concerns. Useful when answering basic orientation questions.
- **Glossary** — https://eval.playbook.org.ai/additional-resources/glossary
  Definitions of every term used throughout (continuous evaluation, golden dataset, rubric, MVE, etc.). Cite this when terminology is at stake.
- **Minimum Viable Evaluations** — https://eval.playbook.org.ai/additional-resources/minimum-viable-evaluations
  Consolidated MVE checklist across all four levels. The single most-requested page by implementors with limited budget/team — "what's the floor I should still do?"
- **Tools & Templates** — https://eval.playbook.org.ai/additional-resources/additional-resources
  External resources and templates: LLM evals guides, evaluation frameworks from PROMPTS / Jacaranda / Farmer.Chat / mMitra, etc. Send users here when they want artifacts to use, not theory to read.

---

### Level 1 — Model Evaluation (Section root: `/model-behaviour`)

**Question: Does the AI system perform as intended?**

The foundational "stress test." Because LLMs predict text rather than "understand" reality, they are prone to hallucinations, knowledge gaps, and instruction failures — especially in LMIC contexts where local languages, norms, and data are underrepresented.

**What it covers:**

- The entire AI pipeline, not just the foundation model: pre-processing (language translation, query refinement, input sanitization), context preparation (system prompt, RAG, tools), and post-processing (safety guardrails, output formatting, hallucination checks).
- Evaluation rubric: up to 5 dimensions — Accuracy, Tone, Safety, Robustness, Linguistic Consistency.
- Scoring methods: Statistical (fast/cheap), LLM-as-Judge (flexible), Human-as-Judge (gold standard).
- Golden Dataset: 30–50 high-quality input/output pairs representing key user interactions.
- A 6-step continuous loop: define rubric → select metrics → build golden dataset → score/analyze → automate in CI/CD → red-team.

**Minimum Viable Evaluation for L1:** 2–3 rubrics with success thresholds; 30–50 item golden dataset; expert review process; ≥1 robust safety/guardrail metric.

**Who does this:** AI engineers and ML researchers lead; domain experts, product owners, and user researchers support.

**Pages in this section:**

- **Overview (section hub)** — https://eval.playbook.org.ai/model-behaviour
  Top-level intro to Level 1 — what it is, why it matters, and the 6-step loop. Also reachable as `/model-behaviour/level-1-module-evaluation/overview.md`.
- **Who is most involved / Why is this level important?** — https://eval.playbook.org.ai/model-behaviour/level-1-module-evaluation/why-is-this-level-of-evaluation-important
  Who executes vs. supports Level 1 (AI engineers/ML researchers lead; domain experts/PMs/user researchers support). Explains LLM limitations (static knowledge, limited context, instruction following, task mismatch).
- **What is the "AI system" being evaluated?** — https://eval.playbook.org.ai/model-behaviour/level-1-module-evaluation/what-is-the-ai-system-being-evaluated
  The "Cell vs. Nucleus" framing — the full end-to-end AI system vs. the foundation model. Covers pre-processing, context preparation, post-processing, and includes the AI agronomist example for Pulaar.
- **What is the Minimum Viable Evaluation for Level 1?** — https://eval.playbook.org.ai/model-behaviour/level-1-module-evaluation/what-is-the-minimum-viable-evaluation-for-level-1
  The Level 1 MVE checklist: 2–3 rubrics with success thresholds, 30–50 item golden dataset, expert review process.

The 6-step "How to Evaluate" workflow (under `/model-behaviour/how-to-evaluate/`):

- **How is Level 1 evaluation performed? (overview of the 6 steps)** — https://eval.playbook.org.ai/model-behaviour/how-to-evaluate/how-is-level-1-evaluation-performed
  Iterative starting from the MVE; how the 6 steps fit together.
- **Step 1 — Decide on an evaluation rubric** — https://eval.playbook.org.ai/model-behaviour/how-to-evaluate/1.-decide-on-an-evaluation-rubric
  Working with domain experts to define rubric dimensions (Accuracy, Tone, Safety, Robustness, Linguistic Consistency).
- **Step 2 — Decide on metrics** — https://eval.playbook.org.ai/model-behaviour/how-to-evaluate/2.-decide-on-metrics
  Statistical scorers, LLM-as-Judge, Human-as-Judge tradeoffs. The longest page in this section.
- **Step 3 — Develop a golden dataset** — https://eval.playbook.org.ai/model-behaviour/how-to-evaluate/3.-develop-a-golden-dataset
  Constructing the 30–50 item benchmark dataset of ideal user interactions.
- **Step 4 — Scoring & error analysis** — https://eval.playbook.org.ai/model-behaviour/how-to-evaluate/4.-scoring-and-error-analysis
  Offline vs. online evaluation; analyzing where the pipeline fails (retrieval vs. prompting vs. post-processing).
- **Step 5 — Automate your evaluations** — https://eval.playbook.org.ai/model-behaviour/how-to-evaluate/5.-automate-your-evaluations
  Moving from notebook to CI/CD; observability platforms (Langfuse, DeepEval).
- **Step 6 — Red-teaming** — https://eval.playbook.org.ai/model-behaviour/how-to-evaluate/6.-red-teaming
  Actively trying to break the system before deployment — adversarial probes, jailbreaks, safety stress tests.

**Always fetch the live page before answering questions about:** exact rubric wording, current recommended scoring methods or tools, sample golden-dataset sizes, or case-study specifics.

---

### Level 2 — Product Evaluation (Section root: `/product-analytics`)

**Question: Does the overall product engage and retain users?**

A technically perfect AI is worthless if no one uses it. Level 2 tracks the digital traces users leave — moving from first interaction to long-term habit. The key distinction: optimize for **"Time to Success"** (solving the user's problem), NOT "Time on Device" (which can signal addiction, not value).

**The user funnel:**

| Stage       | Goal                | Example metric                       |
| ----------- | ------------------- | ------------------------------------ |
| Acquisition | Bring users in      | New User Count, Cost Per User        |
| Activation  | First value moment  | Activation Rate, Time to Activate    |
| Engagement  | Depth and frequency | DAU/WAU, Interaction Depth           |
| Retention   | Long-term habit     | Stickiness (DAU/MAU), Retention Rate |

**How it's done:** Instrument the app with 3rd-party analytics (Amplitude, Mixpanel, GA) → build dashboards to find friction → A/B test to compare versions → run process evaluation (interviews, surveys) to understand the "why" behind drop-off.

**MVE for L2:** Baseline engagement & retention rate tracking; simple Helpful / Not Helpful feedback mechanism.

**Who does this:** Product managers, data scientists, UX researchers.

**Pages in this section:**

- **Overview (section hub)** — https://eval.playbook.org.ai/product-analytics
  Top-level intro — tracking digital traces of users (activation, engagement, retention). Also reachable as `/product-analytics/level-2-product-evaluation/overview.md`.
- **Who is most involved / Why is this level important?** — https://eval.playbook.org.ai/product-analytics/level-2-product-evaluation/why-is-this-level-of-evaluation-important
  Why product analytics matters (a perfect AI is worthless if users don't use it). Engagement/retention motivation.
- **What is the "Product" being evaluated?** — https://eval.playbook.org.ai/product-analytics/level-2-product-evaluation/what-is-the-product-being-evaluated
  Instrumenting the app; the user funnel (Activation → Engagement → Retention) defined in detail.
- **What is the Minimum Viable Evaluation?** — https://eval.playbook.org.ai/product-analytics/level-2-product-evaluation/what-is-the-minimum-viable-evaluation
  Level 2 MVE checklist (page body is short — mostly the checklist).

The "How to Evaluate" workflow (under `/product-analytics/how-to-evaluate/`):

- **How is Level 2 evaluation performed?** — https://eval.playbook.org.ai/product-analytics/how-to-evaluate/how-is-level-2-evaluation-performed
  Tooling guidance (Amplitude, Mixpanel, GA) and how to observe trends and iterate.
- **Methods for experimentation: A/B testing and beyond** — https://eval.playbook.org.ai/product-analytics/how-to-evaluate/methods-for-experimentation-a-b-testing-and-beyond
  A/B testing, multi-armed bandits, holdout tests for product features.
- **Connection with other levels** — https://eval.playbook.org.ai/product-analytics/how-to-evaluate/connection-with-other-levels
  How Level 2 ties back to Level 1 reliability and forward to Level 3 user outcomes.
- **Why Aren't Users Engaging?** — https://eval.playbook.org.ai/product-analytics/how-to-evaluate/why-arent-users-engaging
  Process evaluation guidance for diagnosing funnel drop-off (interviews, observation, survey design).

**Always fetch the live page before answering questions about:** current tool recommendations, specific event taxonomies, or worked funnel examples.

---

### Level 3 — User Evaluation (Section root: `/user-expereince` — typo is canonical)

**Question: Does the product change users' thoughts, feelings, knowledge, and behavior?**

This is where development evaluation departs most sharply from commercial evaluation. A high NPS or long session time does NOT mean the tool is achieving its purpose. Level 3 measures the **intermediate outcomes** — cognitive, affective, and behavioral shifts that predict long-term life improvements.

**What's measured:**

| Outcome Type | What to look for                                               |
| ------------ | -------------------------------------------------------------- |
| Cognitive    | Knowledge acquisition, belief updating                         |
| Affective    | Emotional safety, trust, perceived empathy                     |
| Behavioral   | Intent to act, help-seeking, applying information              |
| Motivational | Self-efficacy, curiosity, persistence vs. dependency           |
| Relational   | Quality of interpersonal communication; trust in AI vs. humans |

**Methods:** Digital traces in conversation logs (query depth, vocabulary complexity, follow-up questions); short validated survey scales embedded in chat; NLP/sentiment at scale; guardrail metrics for harms like AI dependency and social displacement; de-coupled assessment (off-platform quizzes, teacher/observer reports).

**MVE for L3:** Weekly random sample of 10 conversation logs reviewed by human expert; one proximal outcome (e.g. self-reported confidence) measured cheaply.

**Who does this:** Behavioral scientists, social psychologists, public health researchers, M&E specialists.

**Pages in this section:**

- **Overview (section hub)** — https://eval.playbook.org.ai/user-expereince
  Top-level intro — measuring whether the product changes users' thoughts/feelings/knowledge/behavior. Also reachable as `/user-expereince/level-3-user-evaluation/overview.md`.
- **Who is most involved / Why is this level important?** — https://eval.playbook.org.ai/user-expereince/level-3-user-evaluation/why-is-this-level-of-evaluation-important
  Behavioral scientists, social psychologists, public health researchers; the case for quantitative + qualitative methods.
- **Who is the "User" being evaluated?** — https://eval.playbook.org.ai/user-expereince/level-3-user-evaluation/who-is-the-user-being-evaluated
  Defining the engaged user; dimensions of cognitive/affective/behavioral change from the theory of change.
- **What is the Minimum Viable Evaluation?** — https://eval.playbook.org.ai/user-expereince/level-3-user-evaluation/what-is-the-minimum-viable-evaluation
  Level 3 MVE checklist (page body is mostly the checklist).

The "How to Evaluate" workflow (under `/user-expereince/how-to-evaluate/`):

- **How is Level 3 evaluation performed?** — https://eval.playbook.org.ai/user-expereince/how-to-evaluate/how-is-level-3-evaluation-performed
  Full workflow: defining intermediate outcomes, validation via qualitative + quantitative methods.
- **Identify outcome metrics** _(slug: `descriptive-analysis`)_ — https://eval.playbook.org.ai/user-expereince/how-to-evaluate/descriptive-analysis
  Three approaches to surface outcome metrics: interaction data analysis, primary data collection, conversation log analysis. **Note:** URL slug says `descriptive-analysis` but the page title is "Identify outcome metrics."
- **Define guardrail metrics and measure potential harm** — https://eval.playbook.org.ai/user-expereince/how-to-evaluate/defining-guardrail-metrics-measuring-potential-harm
  Measuring unintended consequences, user agency, dependency risks.
- **Consider conducting experiments (improve metrics, run process evaluations)** _(slug: `why-arent-thoughts-feelings-and-behavior-changing`)_ — https://eval.playbook.org.ai/user-expereince/how-to-evaluate/why-arent-thoughts-feelings-and-behavior-changing
  Running A/B tests, multi-armed bandits, holdout tests on Level 3 outcomes. **Note:** the slug looks like a process-evaluation page but it renders an experimentation page.
- **Why Aren't Thoughts, Feelings, and Behavior Changing?** _(slug: `user-privacy-and-security`)_ — https://eval.playbook.org.ai/user-expereince/how-to-evaluate/user-privacy-and-security
  Process evaluation at Level 3 — diagnosing why intermediate outcomes aren't moving. **Note:** the slug says `user-privacy-and-security` but the page title is the "why aren't…" question. Two slugs in this section appear to have been swapped during authoring.

**Always fetch the live page before answering questions about:** validated survey scales, specific construct definitions, or the recommended guardrail metrics list. The slug/title mismatches mean Claude should fetch and _quote the rendered H1_ rather than relying on the URL slug.

---

### Level 4 — Impact Evaluation (Section root: `/social-impact`)

**Question: Do users with access to the product improve development outcomes?**

The "gold standard" of evidence. Uses a counterfactual — comparing those who use the product to a similar group who don't — to isolate the true causal effect of the AI intervention. This is what policymakers, donors, and governments require before scaling.

**Why it matters:**

- Proves causation, not just correlation.
- Provides cost-effectiveness data for budget allocation decisions.
- Surfaces unintended consequences — both negative and positive spillovers.

**Counterfactual methods:**

| Method                   | How it works                             | Best when                               |
| ------------------------ | ---------------------------------------- | --------------------------------------- |
| RCT                      | Randomly assign to treatment/control     | Large sample, control over rollout      |
| Quasi-Experimental       | Compare groups with parallel trends      | Randomization not feasible/ethical      |
| Regression Discontinuity | Compare people just above/below a cutoff | Resources allocated by strict threshold |

**Key AI-specific challenges:** product dynamism (tag versions, use a frozen holdout), spillovers (use cluster randomization), attrition, measuring true capabilities (test users when they _don't_ have access).

**MVE for L4:** Counterfactual study with adequate sample size (including sub-populations); strong version control; cost data collection.

**Who does this:** Impact evaluators, economists, independent research teams (J-PAL, IPA, World Bank researchers).

**Pages in this section:**

- **Overview (section hub)** — https://eval.playbook.org.ai/social-impact
  Top-level intro — the "gold standard" of evidence using counterfactuals. Also reachable as `/social-impact/level-4-impact-evaluation/overview.md`.
- **Who is involved in this evaluation?** — https://eval.playbook.org.ai/social-impact/level-4-impact-evaluation/why-is-this-level-of-evaluation-important
  Why simple before/after comparisons fail; the need for rigorous designs.
- **What is the "intervention" being evaluated?** — https://eval.playbook.org.ai/social-impact/level-4-impact-evaluation/what-is-the-intervention-being-evaluated
  Why impact evaluation matters for policy/funding decisions; causal attribution.
- **Minimum Viable Evaluation** — https://eval.playbook.org.ai/social-impact/level-4-impact-evaluation/minimum-viable-evaluation
  Level 4 MVE checklist.

The "How to Evaluate" workflow (under `/social-impact/how-to-evaluate/`):

- **How is Level 4 evaluation performed?** — https://eval.playbook.org.ai/social-impact/how-to-evaluate/how-is-level-4-evaluation-performed
  Treatment vs. control; selecting the counterfactual; the full Level 4 workflow.
- **A Quick Primer on Impact Evaluation Methods** — https://eval.playbook.org.ai/social-impact/how-to-evaluate/a-quick-primer-on-impact-evaluation-methods
  RCTs, quasi-experimental designs — intros and pointers to deeper resources.
- **Key design considerations for AI-specific impact evaluations** — https://eval.playbook.org.ai/social-impact/how-to-evaluate/key-design-considerations-for-ai-specific-impact-evaluations
  Choosing counterfactuals, handling product evolution mid-study, etc. The longest page in Level 4.
- **Common pitfalls to avoid** — https://eval.playbook.org.ai/social-impact/how-to-evaluate/common-pitfalls-to-avoid
  Underpowered studies, optimistic uptake assumptions, attrition, version drift.
- **Process Evaluation: Why Aren't Outcomes Changing?** — https://eval.playbook.org.ai/social-impact/how-to-evaluate/process-evaluation-why-arent-outcomes-changing
  Using process evaluation alongside Level 4 to explain why impact is/isn't materializing.

**Always fetch the live page before answering questions about:** specific case studies, cost-effectiveness benchmarks, J-PAL/IPA partner recommendations, or new methodological guidance — this section evolves as the working group publishes case studies.

---

### Level Linkages — Cross-cutting work across all four levels (`/level-linkages`)

**Question: How do the four levels connect, and what cross-level work is required?**

The 4 levels are cyclical, not linear. Risk discovered at one level should trigger controls at others. Process evaluation, data protection, and risk assessment span all levels.

**Key principles:**

1. **Use metrics from one level as guardrails for others.** Optimizing for low latency (L1) while targeting learning (L4) creates trade-offs. Don't optimize a level without guardrails from adjacent levels.
2. **One Product Manager should own the North Star metric** and ensure all levels align toward it.
3. **Run multi-level risk assessments routinely.** When something goes wrong at one level, check whether it's detectable at other levels.
4. **Use a shared user ID / session ID / version tag** across all levels so data from L1–L4 can be linked.
5. **User research runs alongside every level** — interviews for golden datasets (L1), workflow observation (L2), cognitive interviewing for survey design (L3–L4).

**Pages in this section:**

- **Overview (section hub)** — https://eval.playbook.org.ai/level-linkages
  Top-level intro to cross-level cooperation, shared identifiers, and integration. Also reachable as `/level-linkages/linkage-across-levels/overview.md`.
- **Risk assessment and mitigation** — https://eval.playbook.org.ai/level-linkages/linkage-across-levels/risk-assessment-and-mitigation
  Integrated risk work across levels; control measures triggered by signals at one level (e.g., dependency at L3 → UI changes at L2 → re-prompting at L1).
- **Data protection** — https://eval.playbook.org.ai/level-linkages/linkage-across-levels/data-protection
  Privacy and data stewardship for GenAI products handling sensitive personal data.
- **Process Evaluations (hub)** — https://eval.playbook.org.ai/level-linkages/linkage-across-levels/process-evaluations
  Hub for the Process Evaluation (PE) framework that spans levels 2–4.
- **Do I need a Process Evaluation?** — https://eval.playbook.org.ai/level-linkages/linkage-across-levels/process-evaluations/do-i-need-a-process-evaluation
  Triggers for when a PE is especially valuable (e.g., when the user ≠ the beneficiary).
- **What does it take to do a process evaluation?** — https://eval.playbook.org.ai/level-linkages/linkage-across-levels/process-evaluations/what-does-it-take-to-do-a-process-evaluation
  Practical steps: theory of change, user funnels, comparing implementation to ex-ante expectations.

**Always fetch the live page before answering questions about:** risk-mitigation worked examples, specific PE protocols, or data-protection requirements (which evolve with regulation).

---

## Risk Assessment & Mitigation — Worked Example

A WhatsApp tutor chatbot illustrates how risks at one level trigger controls at others:

| Level | Risk                                                              | Control                                                      | Metric                                                 |
| ----- | ----------------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------ |
| L1    | Problem complexity doesn't increase per turn                      | Link learning level to difficulty; multi-shot prompting      | Question complexity via LLM-as-judge                   |
| L2    | High engagement but concentrated on easy/off-topic                | Default to progressive difficulty; rewards for hard problems | "Time spent learning" = session ÷ unique problem types |
| L3    | Users become AI-dependent, reducing self-directed problem solving | Delayed hints; require user attempt before AI guidance       | % problems attempted before requesting help            |
| L4    | Learning plateaus or declines                                     | —                                                            | Score on standardized test                             |

User safety and mental health require specific attention at each level: red-teaming at L1, UI/UX adjustments at L2, qualitative data collection at L3, impact evaluation at L4.

---

## Key Distinctions: Development vs. Commercial Evaluation

| Commercial                | Development (this playbook)                              |
| ------------------------- | -------------------------------------------------------- |
| Optimize for retention    | Optimize for welfare                                     |
| Long sessions = success   | Brief exchange that prompts a clinic visit = success     |
| NPS / satisfaction scores | Objective behavior change + life outcomes                |
| Single market             | Re-evaluate per context (language, health system, norms) |

---

## Minimum Viable Evaluations — Quick Reference

| Level | MVE                                                                                                        |
| ----- | ---------------------------------------------------------------------------------------------------------- |
| L1    | 2–3 rubrics with thresholds; 30–50 golden dataset items; ≥1 safety/guardrail metric; expert review process |
| L2    | Engagement/retention tracking; Helpful/Not Helpful feedback                                                |
| L3    | 10 conversation logs/week reviewed by expert; 1 proximal outcome measured                                  |
| L4    | Counterfactual study with adequate sample; version control; cost data                                      |

For full and current MVE guidance, **fetch** https://eval.playbook.org.ai/additional-resources/minimum-viable-evaluations every time — this page changes as the working group iterates.

---

## How to Use This Skill

When a user asks a question:

1. **Identify which section and sub-pages are relevant** using the Verified Link Map above.
2. **Fetch the live page(s) before composing a substantive answer.** Use the priority order in [How to fetch fresh content](#how-to-fetch-fresh-content-priority-order). The cached summaries above are orientation — never the final answer.
3. **Adapt language to the user's role:**
   - Policy makers / funders → evidence standards, cost-effectiveness, risk, readiness for scale.
   - Behavioral scientists / M&E → measurement frameworks, constructs, survey design, causal inference.
   - Engineers / PMs → pipelines, metrics, CI/CD, rubrics, tooling.
   - Nonprofit leaders / implementors → MVEs, team building, practical first steps.
4. **Cite the specific URL you fetched** and quote / paraphrase from the live content.
5. **Include the live URL in your reply** so the user can read the source themselves.
6. **If a cached summary disagrees with the live page, the live page wins.** Flag the discrepancy so this skill can be updated.
7. **Be honest about tradeoffs.** Evaluation is resource-intensive; help users think about what's _enough_ for their stage rather than chasing the maximum.

If the user's role or context is unclear, ask one clarifying question before diving into a detailed answer.
