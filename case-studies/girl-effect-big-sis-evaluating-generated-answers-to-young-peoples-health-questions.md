# Girl Effect — Big Sis: evaluating generated answers to young people's health questions

How Girl Effect evaluated generated answers in Big Sis, a chatbot for young people's sexual, reproductive, and mental health questions in South Africa, across the playbook's four levels — and the design choices behind each evaluation.

**Sector:** Health | **Product maturity:** Deployed at scale | **Impact evidence:** Observational | **Evaluation window:** 2024 to 2026, ongoing | **Last updated:** November 2026

#### How the product is expected to create value

**If** young people get a direct, non-judgemental answer to their own question, instantly and in their own language, with a clear next step, **then** they keep asking, come back, and move towards preventive action or care, **because** a trusted answer at the moment they would otherwise stall replaces rumour with facts and gives them the confidence to act.

#### At a glance

<table data-header-hidden data-search="false"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><strong>Organization</strong></td><td>Girl Effect, a nonprofit. The generative AI service is proprietary while under active development; the chatbot runs on RapidPro, an open-source platform. Girl Effect's April 2025 white paper publishes its architecture, guardrail and judge prompts, evaluation datasets, and A/B test results.</td></tr><tr><td><strong>What the tool does</strong></td><td>Big Sis gives young people in South Africa a private, judgement-free place to ask about sex, relationships, and mental health, with escalation to trained healthcare agents. The generative AI feature answers questions directly, drawing only on content vetted by Girl Effect and its partners, with safety checks on every question and response.</td></tr><tr><td><strong>Primary user</strong></td><td>Young people in South Africa aged 18 to 24, about half female and half male, most writing in mix-coded English — English mixed with isiZulu, isiXhosa, and slang. The user is the beneficiary.</td></tr><tr><td><strong>Reach</strong></td><td>About 180,000 unique users of the generative AI feature — people whose text the feature processed — and 767,000 messages processed, from launch in December 2024 to October 2026 <em>(platform analytics)</em>. Big Sis as a whole has had about 2.8 million unique users since 2018.</td></tr><tr><td><strong>Delivery channel</strong></td><td>Moya Messenger (about 90 percent of users, data-free) and WhatsApp</td></tr><tr><td><strong>Scope</strong></td><td>Big Sis's generative AI answer feature, not the wider chatbot, which has run since 2018. Sister chatbots in India and Kenya do not yet generate answers.</td></tr><tr><td><strong>Service context</strong></td><td>Part of Girl Effect's Jiki'Zinto program in South Africa, alongside a TV drama, radio and podcasts, social media, and community mobilization; used free of data charges on Moya Messenger. The AI gives one-to-one answers no team of counsellors could provide at this scale, while trained healthcare agents handle high-risk disclosures and the cases that most need a person.</td></tr></tbody></table>

#### Evaluation coverage

|                   | L1 Model                                                                                         | L2 Product                 | L3 User                                               | L4 Impact                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------ | -------------------------- | ----------------------------------------------------- | ----------------------------------------------------------------------- |
| **Depth**         | ● Substantive                                                                                    | ● Substantive              | ● Substantive                                         | ◐ Partial                                                               |
| **Evidence base** | \~200 synthetic items per metric dataset; \~100-item retrieval dataset; every live answer judged | \~4,000 users; 3 A/B tests | 1,677 survey respondents; 12 think-aloud participants | Repeated cross-sectional survey, about 4000 participants; 1 RCT planned |

***

## Level 1 — Model evaluation

> **Does the AI system perform as intended?** · [Level 1 →](https://eval.playbook.org.ai/model-behaviour/level-1-module-evaluation/overview)

**Decision problem.** Before unsupervised young people saw generated answers: were they safe, did they match Girl Effect's editorial and behavior-change approach, and which metrics could judge that in mix-coded South African English?

**What they did.** Built its own LLM-as-judge metrics for safety, accuracy, relevance, and resonance — off-the-shelf metrics failed on this audience — tested at scale on synthetic datasets built from years of real user questions, alongside specialist review and supervised testing with young people in Cape Town.

**What changed.** Supervised testing in September 2024 showed the guardrails were too strict: the prompt writing answers was also deciding whether a question was in scope, so toxicity and hallucination checks fired on messages that should never have reached them. Girl Effect moved the in-topic check to the start of the pipeline, learned to test guardrails as a chain, and turned toxicity and hallucination into monitored metrics rather than blocks. Choosing the in-topic check was a deliberate trade-off: the most accurate option (91.7 percent) turned away the most real questions, so the team chose a combined check with lower accuracy (88.8 percent) that recognizes 98.4 percent of genuine questions. Answering a stray question costs little; turning away a young person who needed help costs them a lot.

<details>

<summary>How they did it — methods, datasets, and metric choices</summary>

### Rubric and metrics

_(playbook L1 steps 1–2)_

Four evaluation metrics: **safety**, **accuracy**, **relevance**, and **resonance**. The safety judge checks every generated answer for stigma, discrimination, dismissive language, and one-sided views. Because it misses subtler bias, checks for gender bias, LGBTQ+ bias, and Western-centric framing are in development. For retrieval settings, the deciding measures were context relevance and faithfulness — whether answers came from the right vetted content. Thresholds depended on the metric. Targets were defined but not quantified in advance, except safety, which needed to be close to 100 percent on test data before unsupervised users saw any answer. The safety judge scored 100 percent on test datasets, and 99 percent of live answers passed during the A/B test.

Off-the-shelf metrics did not work: they were not built for mix-coded South African English, for sexual and mental health topics, or for Big Sis's tone, and on balanced test data several either passed almost everything or flagged almost everything.

### Golden dataset

_(playbook L1 step 3)_

Users have sent questions since 2018, first answered by hand weekly, then through content suggestions based on intent classification. Data curators used this history as inspiration to build synthetic datasets weighted for testing each tool, including deliberately toxic and hallucinated responses to check that the guards catch them, and revised them as feedback arrived. The datasets are managed in LangSmith and git.

The metric datasets contain about 200 items each, and the retrieval dataset about 100, each a question paired with the passage of vetted content where the answer appears.

### Scoring, error analysis, automation

_(playbook L1 steps 4–5)_

LLM judges test at scale against every message received, while experts evaluate sample datasets to check that responses match Girl Effect's programmatic approach. Agreeing what "sensitive" means was hard: on sensitive disclosures, each expert reviewer agreed with the model about 89 percent of the time, but rarely on the same messages. Failures are categorized by where in the pipeline they occur — the API connection to the chatbot, the connection to the model, or a bug introduced into a guardrail — with Slack alerts on API failures. Before a prompt change goes live, expert evaluators review the new responses to the question set and approve them, or the team iterates until they do.

Since a recent model upgrade, GPT-5.4 mini both writes and judges answers; during the A/B test, GPT-4o wrote the answers and the smaller GPT-4o-mini judged them. Girl Effect has spotted the overlap and is separating the two again, so the judge does not score its own model's output. A person reviews every answer the judge fails.

### Red-teaming

_(playbook L1 step 6)_

Internally yes. The QA team and specialists in safeguarding, sexual and reproductive health, and social and behaviour change design scenarios to break the bot: abusive messages, attempts to extract harmful information, and attempts to pull it off-topic. Because any failure could become a safeguarding issue, this is treated as a release gate rather than a one-off exercise. The main defence is narrow scope: the bot answers only in-topic questions, only from vetted content, and sends anything that looks like a sensitive disclosure to a trained person. Content recommendations were kept as a further pathway. Recognizing that its own team knows the system too well to attack it as an outsider would, Girl Effect plans to commission independent external red-teaming.

### Alternatives considered, and tools

Girl Effect considered and rejected several approaches. It tested six off-the-shelf guardrail frameworks (Guardrails AI, LLM Guard, Llama Guard, NeMo Guardrails, DeepEval, and MLflow) and built its own LLM-as-judge prompts instead, because most required adopting their whole system and several failed on balanced test data. For the first live test, it replaced only question answering rather than building a fully conversational chatbot, keeping the test fast and the cause of any difference clear. It also held back a new sensitive-disclosure classifier after users in supervised testing found its service nudges alarming. Within testing, it compared candidate in-topic checks and chose the one that turned away the fewest genuine questions, as described above. Prompts were tested against several models using LangChain.

</details>

***

## Level 2 — Product evaluation

> **Does the overall product engage and retain users?** · [Level 2 →](https://eval.playbook.org.ai/product-analytics/level-2-product-evaluation/overview)

**Decision problem.** Did generated answers beat the existing content recommendations clearly enough to roll out — and would the system hold up at scale?

**What they did.** Ran a randomized A/B test from 9 December 2024 to 13 January 2025: new users who asked a question received either a generated answer or the existing recommendations, with about 4,000 users in each group, against a pre-written analysis plan.

**What changed.** Generated answers won on every pre-specified measure, so Girl Effect rolled them out across the chatbot, and monthly users whose questions it processed rose from 3,000 to almost 20,000. Two later A/B tests — specialist co-designed prompts, and a feature for off-topic messages — produced no significant changes.

<details>

<summary>How they did it — instrumentation and changes made</summary>

### Metrics and instrumentation

Tracked through RapidPro and a PowerBI dashboard covering the AI architecture, satisfaction results, and de-identified user submissions: users entering the experiment, entering the feature, and submitting a question; the share of in-topic questions; the share of users sending multiple messages and returning; satisfaction in each arm; and response latency. An observability framework feeds a data warehouse, with dashboards for the feature showing disclosures, in-topic and off-topic shares, and the message log. Since launch in December 2024, about 10 percent of users who start a Big Sis conversation have gone on to ask a question that the generative AI feature processes; that share has up to 30 percent in the past three months. Monitoring was daily during the test, with analysis once enough users had engaged.

Cost per generated answer: about $0.00683 — a product running cost, not an evaluation cost.

### Experimentation approach

_(playbook L2, methods for experimentation)_

The A/B test ran in RapidPro with new Big Sis users. The analysis plan was written down before launch but not registered, because the test was a product improvement informing a rollout decision rather than a research study. It set out four hypotheses — a better experience, more recommended content reached, more engagement, return use and access to service information, and ultimately support for behavior change — each mapped to metrics on the outcome ladder in Girl Effect's theory of change. The target was a statistically significant result on the pre-specified measures, not a minimum effect size. Of 4,000 users, 1,677 answered the satisfaction survey, more than the design required.

### Why users weren't engaging

_(playbook L2, why aren't users engaging?)_

The chatbot platform shows exactly where users drop off, so logic errors can be debugged; API failures trigger Slack alerts; the satisfaction survey surfaces users having problems; and the dashboards show how many questions are stopped by the sensitive-disclosure and in-topic stages before an answer is generated. Many messages flagged as off-topic were not: users said hello, asked who Big Sis was, or tested the bot before asking what they really wanted to know.

### Changes made

After the A/B test:

* Generated answers made available to all users of the question feature.
* Extended to questions asked elsewhere in the chatbot, such as in a menu.
* The chatbot's information architecture changed to offer a question earlier.
* A conversational-skills classifier added to respond warmly to off-topic messages.

### Alternatives considered, and tools

None reported. The A/B test and the satisfaction survey both run in RapidPro; dashboards in PowerBI.

</details>

***

## Level 3 — User evaluation

> **Does the product change users' thoughts, feelings, knowledge and behavior towards the development outcome?** · [Level 3 →](https://eval.playbook.org.ai/user-experience/level-3-user-evaluation/overview)

**Decision problem.** Does a generated answer change what young people know and do — and could it leave someone worse off by being unsafe, missing someone at risk, or alarming or turning them away?

**What they did.** Tracks behavior inside the product — behavior-change content reached, service lookups, requests for a trained healthcare agent — alongside knowledge quizzes, surveys, answer ratings, and think-aloud sessions with 12 young people.

**What changed.** When disclosure detection suggested seeking support, some young people felt their problem was treated as more serious than it was — Girl Effect's definition of a sensitive disclosure was stricter than theirs — so the team held back a new classifier while aligning the two definitions with users.

<details>

<summary>How they did it — measures and findings</summary>

### Outcome metrics

_(playbook L3, identify outcome metrics)_

Within the chatbot, an outcome ladder: satisfaction, engagement, meaningful engagement, return use, knowledge uptake, and access to services. Message sets carrying key behavior-change content are tagged "significant," and Girl Effect tracks how many each user reaches, then service-finder use and requests for a trained healthcare agent. Those agents are community health workers trained in mental health support, trauma response, and sexual and reproductive health, so connecting to one is itself a form of care. Over the last 18 months, more than 350,000 Big Sis users looked up health service information or asked to speak to an agent.

In the A/B test, users who received a generated answer reached 17 percent more key behavior-change content on average and were more likely to look up health service information (38.8 percent versus 34.5 percent). Girl Effect tried to measure knowledge through in-chat quizzes, but too few users completed them to draw a conclusion.

### Guardrail metrics and harm

_(playbook L3, guardrail metrics)_

The system-level protections — narrow scope, vetted content, the safeguarding layer, and the safety judge — are described under Level 1. At the user level, Girl Effect watches for signs that an answer left a young person worse off, through ratings and free-text feedback and through help desk agents flagging concerns. Supervised testing surfaced one such harm: a suggestion to seek support made some young people feel their problem was being treated as more serious than it was.

### Methods and instruments

Behavior inside the product is the main measure. Knowledge quizzes compare users who have and have not seen particular content: users exposed to Big Sis's mental health content scored about 30 percent higher on knowledge of coping strategies. Every user who asks a question receives a short survey six hours later on satisfaction, supportiveness, and whether they would recommend Big Sis, and users who get a generated answer can rate it immediately. Helpdesk agents report on each case they handle.

### Findings

_(playbook L3, why aren't thoughts and behavior changing?)_

Three surprises:

* Users wanted a conversation, not just an answer: asked to rate a generated answer, most replied with a follow-up question, and the one-question-at-a-time design is now shaping what comes next.
* What users asked barely changed from the earlier system — young people always had these questions.
* Many off-topic messages were greetings or tests, which led to a feature that responds warmly.

One effect was unexpected in a good way: the team doubted a single answer would change what young people did next, but service lookups rose — an early, soft signal of intent to act, not proof of care.

### Alternatives considered, and tools

None reported. Surveys run in RapidPro; no dedicated qualitative coding tool.

</details>

***

## Level 4 — Impact evaluation

> **Do users with access to the product improve development outcomes?** · [Level 4 →](https://eval.playbook.org.ai/social-impact/level-4-impact-evaluation/overview)

**Decision problem.** Does the feature help young people get care and make healthier choices outside the chatbot, when Girl Effect loses sight of them the moment they leave?

**What they did.** No feature-specific outcome study yet, by deliberate choice: real-world change is measured across the whole program. An independent 2026 evaluation of Girl Effect's wider South Africa program found Big Sis users nearly twice as likely as non-users to have used mental health services — an association, for Big Sis as a whole. A feasibility trial comparing AI and non-AI versions of an intervention is planned.

**What changed.** To close the gap the evaluations expose — referrals that vanish into the health system — Girl Effect has new investment to link with government and supply-side services, so referrals can be confirmed when a young person reaches care.

<details>

<summary>How they did it — design, counterfactual, and outcomes</summary>

### Method, and why it was chosen

_(playbook L4, methods primer)_

For the feature itself, Girl Effect measures what it can attribute — in-product behaviour, through randomised A/B tests. For real-world behaviour, it relies on independent evaluation of the wider programme. Girl Effect is explicit that the programme survey compares users with non-users at a point in time, so it shows a strong association, not proof that Big Sis caused the difference.

### Design and counterfactual

_(playbook L4, key design considerations)_

* **Jiki'Zinto evaluation (2026)** — a repeated cross-sectional survey of young women aged 18 to 25 across Gauteng, KwaZulu-Natal, Western Cape, and North West Province: 4,011 at baseline in 2024 and 4,079 at endline in 2026. Jiki'Zinto combines a TV drama, radio and podcasts, social media, digital platforms, Big Sis, and community mobilisation. The survey asked which channels each young person had used and what they had done about their health, letting evaluators compare channels and measure dose.
* **Planned feasibility RCT** — with the University of Cape Town, Stellenbosch University, 3ie (the International Initiative for Impact Evaluation), and Oxford University Innovation: a generative AI mental health intervention for young people, delivered through mobile chat and co-designed with South African youth. One arm delivers the same intervention through a rules-based, menu-driven chatbot with no generative AI, comparing feasibility, safety, and acceptability, with anxiety measured by the GAD-7. Ethics approval, trial registration, and protocol publication are planned.

### Outcome measures

The outcomes Girl Effect ultimately cares about are using contraception, testing for HIV and STIs, seeking help for mental health, and getting care from health services; Jiki'Zinto measured all four, plus access to economic opportunities. Receiving care, especially mental health support, matters most. In Jiki'Zinto, each additional channel a young person used raised the odds of using contraception and seeking mental health support by about 13 percent, and where Big Sis was combined with community outreach, use of formal mental health services rose by 21 percentage points. The evaluators called Big Sis the programme's "trusted psychosocial pathway."

### Pitfalls addressed

_(playbook L4, common pitfalls)_

Girl Effect keeps three claims apart: the A/B test measures in-chatbot engagement and intent to act, not health behaviour outside it; Jiki'Zinto measures Big Sis as a whole, not the feature; and the programme survey shows association, not causation. Referrals go to trusted services through memoranda of understanding with partners such as Lifeline and the South African Depression and Anxiety Group, but what users did next still relies on self-report.

### Alternatives considered, and tools

The planned trial's non-AI arm is the key design choice: it compares generative AI against a simpler version of the same intervention rather than against nothing. Analysis is in Python.

</details>

***

#### Metrics, thresholds, and results

About fifteen metrics tracked; the rollout bar was statistical significance, not a minimum effect size.

| Level          | Metric                                          | Threshold → Result                                       | Why this metric                                             |
| -------------- | ----------------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------- |
| L1 · guardrail | Safety (LLM judge)                              | Close to 100% on test data → 100% on test data; 99% live | Deciding measure before unsupervised use                    |
| L1             | Genuine questions let through by in-topic check | Prioritized over accuracy → 98.4%, at 88.8% accuracy     | Turning away someone in need costs more than a stray answer |
| L2             | Satisfaction with the answer                    | Statistical significance → 86.2% vs 80.3%                | Core experience measure for rollout                         |
| L2             | Returned to Big Sis                             | Statistical significance → 59.5% vs 53.2%                | Change rarely happens in one conversation                   |
| L3             | Looked up health service information            | Statistical significance → 38.8% vs 34.5%                | Intent to act; mattered most for rollout                    |
| L4             | Mental health service use, users vs non-users   | Not applicable → nearly twice as likely                  | Strongest program link to any outcome; an association       |

#### Time, Effort, and Cost

| Level                   | Timeline                               | Effort                                              | Direct cost                                                  |
| ----------------------- | -------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------ |
| L1–L3 (main evaluation) | Mid-2024 – early 2025 (about 8 months) | \~28 person-months (staff time \~$105,000–$165,000) | \~$2,000–$6,000, incl. \~$80 of model usage for the A/B test |
| Ongoing monitoring      | Dec 2024 – ongoing                     | ⅓–½ of one person (\~$15,000–$25,000/yr)            | $3,000–$8,000/yr                                             |
| L4                      | 2024 – 2026                            | Not separable                                       | Not separable — program-wide evaluation                      |

Direct costs covered evaluation tooling, model usage, and participant incentives and travel for user testing. US dollars, 2024–2025; staff costs at average market rates in Kenya, South Africa, and the UK. Partner Solid Lines supported the data science.

**Team composition.** A full-time data scientist, QA, two content writers and data curators, product, ML ops, engineering, UX, project and programme managers, and safeguarding and behavior-change specialists. The biggest single need is the full-time data scientist.

{% hint style="info" %}
**Hardest part.** Building metrics it could trust, since once young people used the tool unsupervised the metrics were the only way to know it was safe — and, harder still, agreeing what "safe" and "sensitive" mean when experts disagreed and young people drew the line elsewhere.
{% endhint %}

<details>

<summary>Tools used</summary>

### Product stack

* **Base model** — GPT-5.4 mini on Azure OpenAI (GPT-4o during the A/B test). · L1
* **Fine-tuning or adaptation** — none. · L1
* **Embeddings and retrieval** — Azure OpenAI text-embedding-3-large. · L1
* **Vector store** — Chroma, PostgreSQL, and Alembic. · L1
* **Orchestration** — none. · L1
* **Schema validation** — Pydantic. · L1
* **Speech to text / text to speech** — none. · L1
* **Translation** — none. · L1
* **Image or vision model** — none. · L1
* **Delivery integration** — RapidPro, with the generative AI feature as a separate service on Azure; reached through Moya Messenger and WhatsApp. · L2

### Evaluation tooling

* **Annotation and labelling** — no dedicated tool. · L1
* **Golden dataset management** — LangSmith datasets and git. · L1
* **Evaluation harness** — pytest and LangSmith; prompts tested across models with LangChain. · L1
* **Judge model** — GPT-5.4 mini on Azure OpenAI, now being separated from the answer model (GPT-4o-mini during the A/B test). · L1
* **Prompt and version tracking** — git. · L1
* **Telemetry and product analytics** — PowerBI, LangSmith, PostgreSQL. · L2
* **Error monitoring** — LangSmith, PowerBI, API logs, with Slack alerts. · L1, L2
* **Experiment platform** — RapidPro. · L2
* **Survey instruments** — RapidPro. · L3
* **Qualitative coding** — none. · L3
* **Analysis** — Python. · L2, L4
* **Dashboards and reporting** — PowerBI. · L2

</details>

<details>

<summary>Donor and funder engagement</summary>

**Was evaluation required by a funder, and at which level?** Not as a requirement, but a funder backed it from the start. The Enlight Foundation, an early investor in Girl Effect's generative AI work, trusted it to build the evaluation approach alongside the product, with a shared understanding that Girl Effect would publish what it learned openly — including what did not work.

**Did evaluation evidence change the funding relationship?** Yes, it unlocked funding. After Girl Effect shared the results, the Enlight Foundation provided follow-up funding. The safety evidence has mattered most to new funders — showing how answers are checked, how sensitive disclosures reach a trained person, and how live conversations are monitored — and has been central to securing new grants, including from the Gates Foundation.

</details>

<details>

<summary>Sources and reporting statement</summary>

**Sources.** A written pre-work sheet and written communication.

**Relationship disclosure.** Girl Effect has no funding or partnership relationship with the Center for Global Development, the Agency Fund, or IDinsight.

**Reporting statement.** Guarantor: Karina Rios Michel, Chief Creative & Technology Officer, Girl Effect. Figures as of October 2026. Girl Effect has verified this version for factual accuracy; editorial conclusions remain with the playbook authors.

**Limit.** This case study is not an audit. Figures have not been independently verified.

</details>
