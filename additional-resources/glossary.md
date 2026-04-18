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
metaLinks:
  alternates:
    - https://app.gitbook.com/s/pbloAUUbQhacfW14WRJm/references/glossary
---

# Glossary



## Core Concepts

**Continuous Evaluation:** An ongoing process where deployment, adaptation, evaluation, and improvement happen in rapid cycles. It ensures that GenAI applications remain safe, effective, and aligned with intended goals even as models or data evolve.

**Repeatable Motions:** Concrete, actionable processes that embed evaluation into ongoing development cycles, such as user funnel mapping, ETL pipelines, targeted hypothesis testing, and experimentation.

**Cross-Functional Team:** A multidisciplinary group (AI engineers, data scientists, product managers, behavioral scientists, economists) that collaborates across all four evaluation levels to connect model performance with social outcomes.

**User Funnel:** A structured map showing how users move through a product journey, from recruitment and onboarding to engagement, retention, and long-term outcomes, defining metrics, thresholds, and responsible leads for each stage.

**ETL Pipeline (Extract, Transform, Load):** A data pipeline that extracts data from multiple sources, cleans and standardizes it, and loads it into centralized storage for consistent and reliable measurement.

**Observability and Tracing:** Systematic logging of inputs, outputs, and metadata (like model parameters and costs) for every AI interaction, enabling transparency, debugging, and continuous improvement.

**Experimentation:** A disciplined process of testing hypotheses through controlled methods such as A/B tests, holdout studies, or randomized trials to generate causal evidence about what works.

**Randomized Controlled Trial (RCT):** A study design that randomly assigns participants to a treatment group (receiving the AI product) or a control group (without it) to establish causal impact.

**Holdout Testing:** An evaluation method that withholds a subset of users from receiving a feature or product update to serve as a comparison group.

**A/B Test:** A method of comparing two versions of a product or feature (A and B) to see which one performs better, typically by randomly assigning users to one version or the other.

### Level 1 – Model Evaluation

**Rubric:** A list of qualitative characteristics and their domain-specific definitions (e.g., accuracy, empathy, clarity) that define what “good” performance looks like for a specific AI product or domain.

**Metric:** A quantitative measure used to evaluate how well the model meets each rubric criterion (for example, accuracy of classifying a user’s message as relevant or irrelevant).

**Scorer:** A tool or method that produces a numeric score for a given metric. Scorers can be statistical (like precision or recall), or model-based (like using a stronger LLM to judge the quality of responses from a weaker LLM ), or human evaluators.

**Golden Dataset:** A curated collection of representative inputs used to evaluate a model’s performance across iterations, paired with either ideal reference outputs or structured evaluation rubrics that define the characteristics of high-quality responses (e.g., as in [HealthBench](https://www.google.com/url?q=https://openai.com/index/healthbench/\&sa=D\&source=editors\&ust=1770879887200975\&usg=AOvVaw0u-TKPSSZu5Bu--gVy5Hsw)), and including real, edge-case, out-of-scope, and adversarial examples.

**Red-Teaming:** A structured, adversarial testing process in which evaluators intentionally try to break or exploit the system to uncover vulnerabilities, biases, or unsafe behaviors before deployment.

**Human Evaluation:** Manual assessment by domain experts or human raters, used when subtlety or context sensitivity is needed, or when automated scorers may miss key nuances.

**Statistical Scorers:** Automated metrics that quantitatively compare model outputs to reference targets using predefined mathematical criteria (e.g., word overlap for text, precision/recall for classification, or error functions like MSE for regression). They are fast and scalable but limited in capturing higher-order semantic or contextual quality.

**Model-Based Scorers:** 1) Smaller, trained models that assess semantic similarity or text quality (e.g., BLEURT, COMET, BARTScore), or 2) LLM-as-Judge: an evaluation method that uses a Large Language Model (LLM) to assess and score the outputs of another model, typically calibrated against human judgments.

**WER (Word Error Rate):** A measure of speech recognition accuracy, calculated by counting substitutions, insertions, and deletions between predicted and reference transcripts.

**CER (Character Error Rate):** Similar to WER but computed at the character level, used for fine-grained evaluation of transcription models.

**MER (Match Error Rate):** A variation of error metrics that focuses on matching semantic meaning rather than exact words or characters.

**Context Precision:** The extent to which the retrieved context consists of information that is actually relevant to answering the user’s query, minimizing irrelevant or noisy content.

**Context Recall:** The extent to which the retrieved context includes all the necessary information required to answer the user’s query, minimizing missing or omitted relevant content.

**Answer Relevancy:** The extent to which an AI-generated response directly addresses the user’s question or task, staying on-topic and aligned with the user’s intent.

**Faithfulness:** The extent to which an AI-generated response accurately reflects information from retrieved or reference sources, avoiding hallucinations.

**Observability Tools:** Software such as Helicone, Langfuse, or Traceloop that logs the inputs, outputs and other metadata (like, cost, latency, and version history) of your AI system for debugging and evaluation.

**Benchmarking:** Comparing model performance against standardized public metrics or datasets to understand relative performance, though often insufficient for context-specific evaluation.

### Level 2 – Product Evaluation

**Engagement Metrics:** Measures of user participation and interaction with the product, such as session length, number of turns, or frequency of logins.

**Non-Engagement Metrics:** Quality and experience metrics that go beyond raw usage data, including user satisfaction ratings, toxicity scores, or perceived helpfulness.

**Retention Metrics:** Indicators of how many users continue to actively use the product over time, such as Daily Active Users (DAU) or Monthly Active Users (MAU).

**Action-Based Engagement:** Measures of how users respond to AI-generated outputs (e.g., clicks, prompt rewrites, or emoji reactions) that show behavioral engagement.

**Feature Uptake:** The rate at which users adopt optional product features, indicating trust in and perceived usefulness of the AI’s suggestions or capabilities.

**A/B Test:** A method of comparing two versions of a product or feature (A and B) to see which one performs better, typically by randomly assigning users to one version or the other.

**Multi-Armed Bandit:** An adaptive experimental approach that allocates more users to the better-performing variant as evidence accumulates.

**Holdout Testing:** An evaluation method that withholds a subset of users from receiving a feature or product update to serve as a comparison group.

**Quality Scores:** Automated or human-assigned ratings that evaluate AI outputs for attributes like clarity, correctness, empathy, or tone.

**User-Level Surveys:** Post-interaction questionnaires that measure satisfaction, usability, and perceived value of the product experience.

**Experimentation Platform:** Tools such as Evidential that automate randomization, monitor outcomes, and streamline experimental workflows.

### Level 3 – User Evaluation

**Cognitive Outcomes:** Changes in users’ knowledge, reasoning, comprehension, or decision-making abilities as a result of using the AI tool.

**Affective Outcomes:** Changes in users’ emotions, motivation, or sense of trust, belonging, and empathy while interacting with the AI.

**Behavioral Outcomes:** Observable actions such as following AI recommendations, asking more questions, or applying learned information in real-world contexts.

**On-Platform Behavioral Measures:** Telemetry or interaction data collected within the app, such as the number of sessions, conversation depth, or rate of follow-up questions.

**Self-Report Surveys:** Short questionnaires embedded in the product experience that directly ask users about their feelings, confidence, or learning outcomes.

**Psychometrically Sound Measures:** Survey instruments or scales that have been validated for reliability and construct validity, ensuring they accurately measure psychological constructs.

**Sentiment Analysis:** Automated scoring of the emotional tone in users’ messages, detecting trends such as increased positivity or reduced anxiety over time.

**Topic Modeling:** An NLP method that clusters user text into recurring themes or topics to track what users are discussing and how it evolves.

**Linguistic Inquiry and Word Count (LIWC):** A dictionary-based text analysis tool that categorizes words into psychological and linguistic domains, revealing shifts in emotion, thinking, or social connection.

**LLM-Based Text Analysis:** Using large language models to infer psychological or behavioral constructs (e.g., confidence, agency) from user text in a scalable and nuanced way.

**Off-Platform Assessments**: Methods such as structured interviews, standardized tests, or observer reports (from teachers, caregivers, etc.) that evaluate real-world behavioral or attitudinal changes.

**Proximal Outcomes:** Near-term indicators (cognitive or behavioral) that signal whether a product is on track to achieve longer-term development outcomes.

### Level 4 – Impact Evaluation

**Impact Evaluation:** The rigorous assessment of whether an intervention leads to measurable improvements in long-term outcomes such as health, learning, or income.

**Randomized Controlled Trial (RCT):** A study design that randomly assigns participants to a treatment group (receiving the AI product) or a control group (without it) to establish causal impact.

**Counterfactual:** The hypothetical scenario representing what would have happened without the intervention; used to isolate true program effects.

**Treatment Group:** The participants or units who receive access to the AI product or intervention being evaluated.

**Control Group:** Participants or units deliberately withheld from receiving the AI product to serve as a comparison.

**Evaluability:** The degree to which a product or program is ready for rigorous impact evaluation, including whether randomization or measurement structures can be feasibly implemented.

**Product Dynamism:** The tendency of AI products to evolve during evaluation (through retraining or updates), which must be managed through version tagging and careful analysis.

**Spillovers and Contamination**: When participants in the control group are unintentionally exposed to the AI product, potentially biasing results, mitigated through clustered or encouragement designs.

**Cost-Effectiveness:** A measure comparing the magnitude of impact achieved relative to the cost of implementation, often used by funders to guide scaling decisions.

**External Validity:** The degree to which the results of an RCT can be generalized to other settings, populations, or time periods.

**Attrition:** Loss of participants during an evaluation, which can threaten the validity and interpretability of results if not managed and reported transparently.

**Theory of Change:** A logical model describing how an intervention is expected to lead to its intended outcomes, outlining causal pathways and assumptions.

### Tools

**Prompt Engineering:** The process of designing and refining prompts to elicit desired model behavior or output quality.

**Promptfoo:** An open-source tool for testing, red-teaming, and securing prompt pipelines.

**DeepEval:** An open-source evaluation framework for automated model testing and guardrails.

**RAG (Retrieval-Augmented Generation):** An AI architecture that retrieves relevant knowledge before generating responses, improving factual accuracy and grounding.

**RAGAS Metrics:** A set of evaluation metrics for RAG systems, including Answer Relevancy, Faithfulness, Contextual Recall, Precision, and Relevancy.

**Helicone / Langfuse / Traceloop:** Observability and telemetry platforms that capture prompts, model calls, costs, and latency for continuous evaluation.

**OpenTelemetry:** An open-source standard for collecting and exporting metrics, logs, and traces across systems.

**Evidential:** A lightweight experimentation tool that automates randomization, tracking, and analysis for A/B or holdout tests.

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=references%2Fglossary" %}

</details>
