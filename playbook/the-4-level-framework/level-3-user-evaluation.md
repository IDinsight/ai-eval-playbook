---
description: >-
  Does the product impact users’ thoughts, feelings, knowledge, and behavior in
  a way that moves towards the development outcome?
icon: user
---

# Level 3 – User evaluation

## Why is this level of evaluation important?

Once an AI system is functioning as expected (Level 1), and the product is engaging users as intended (Level 2), we can ask a deeper question: Is the product influencing how users think, feel, or act—and in ways that advance a development outcome of interest?

The success of commercial AI products is often measured via user satisfaction ratings or Net Promoter Score (NPS)—essentially asking, 'Do you like this product enough to recommend it?' But in the development sector, satisfaction is not a proxy for impact. A student might enjoy a tutoring app (high NPS) without actually mastering the curriculum. A patient may favorably review a health provider, even when harmed by sub-standard care.

In Level 3 evaluation, we identify and measure specific behaviors, beliefs, or feelings that predict long-term improvements in health, education, or livelihoods. We will use a program’s Theory of Change (TOC) to specify the “stepping stones” that users traverse on their path toward impact. Instead of waiting years to see if health or education outcomes improve, we will identify intermediate changes in how users think, feel, or act to serve as early signals of success.

To do this, organizations should address 5 key issues:

1. **Measures**: Which specific user-level changes actually matter to our Theory of Change? Can we measure these short-term changes relatively cheaply and frequently?
2. **Attribution**: Can we plausibly claim these changes are caused by our AI product?
3. **Trajectory**: Are metrics trending in the right direction? Do sub-groups behave differently?
4. **Malleability**: Can we shift metrics by altering the product experience? Do users show increased drive to act (e.g., asking proactive questions or expressing intent to change) when we intervene with product improvements?
5. **Perception**: Do users feel more empowered to act (e.g., do they have a clearer understanding of their next steps), even if they do not immediately take action? User perceptions can be predictive of outcomes, for example when a student recognizes the learning gains they have achieved while using an app.

By defining and tracking intermediate outcomes, Level 3 helps you conduct fast product iterations during pilots and ongoing feature development, setting the stage for a successful Level 4 evaluation down the road.

## Who is the “User” being evaluated?

At Level 3, we will examine whether the engaged user (i.e., a user receiving an “adequate” dosage) is thinking, feeling, or acting differently as a result of the product – hopefully in ways that predict improved life outcomes. This level of evaluation typically occurs in advance of an impact assessment. Before committing to a rigorous and time-intensive impact study, we want to observe users changing along three dimensions:

* **Cognitive outcomes**: Are users learning? Are they gaining new knowledge or updating beliefs? Do they demonstrate improved skills or decision-making ability as a result of engaging with the product?
* **Constructs to measure**: comprehension, reflection, reasoning, perceived clarity, understanding during interaction.
* **Affective outcomes**: How does the product make users feel? Do users report feeling supported, motivated, and capable after interactions, or are there indications of confusion, anger, or emotional distress?
* **Constructs to measure**: mood, sense of belonging, perceived empathy, trust, or comfort interacting with AI.
* **Behavioral outcomes**: Is the user doing something different? Are users taking small but meaningful actions that predict longer-term development?
* **Constructs to measure**: application of new information, intent to try recommended behaviors, observable behaviors (e.g., asking more complex questions) that proxy for longer-term development outcomes.

### Level 3 vs. Traditional User Research

User research plays a critical role across the product lifecycle (e.g., [Discover, Explore, Test, and Listen](https://www.google.com/url?q=https://www.nngroup.com/articles/ux-research-cheat-sheet/\&sa=D\&source=editors\&ust=1770879887087555\&usg=AOvVaw3WdLHlHcJMdYF1YoJB-99E)). However, in Level 3 we will focus on quantitative user research that captures intermediate outcomes at scale. These outcomes are sometimes observed in the product logs described in Level 2, but more often captured in surveys or automated analysis of user text and voice recordings. At Level 3, our goal is to cheaply track cognitive, affective, and behavioral “states” across a large sample of users, for use in product monitoring and rapid-cycle experiments. We want to understand user shifts in psychology or behavior, but without needing to conduct bespoke qualitative research every time a new feature is being tested.

Of course quantitative methods (e.g. logs, surveys, sentiment analysis) should be complemented with qualitative methods (interviews, ethnography) to validate why users behave the way they do. Ideally, qualitative user research contributes to the theory of change and informs every stage of the evaluation framework:

* <i class="fa-gear-code">:gear-code:</i> Level 1 (AI system): Interviews help define the "Golden Dataset" by gathering realistic user questions, identifying edge cases, and defining "ideal" answers based on needs expressed by real users.
* <i class="fa-box-isometric">:box-isometric:</i> Level 2 (Product): Interviews and direct observation can contextualize engagement data. If an A/B test reveals a drop in retention, qualitative research helps diagnose the underlying friction or confusion.
* <i class="fa-user">:user:</i> Level 3 (User): Interviews or focus groups can validate that intermediate outcome metrics (e.g., user-reported confidence) actually correlate with real-world behavior changes.

### Individual vs. System Outcomes

You may have noticed that in Level 3, we focus on individual outcomes, rather than the broader community or system. This is a practical choice, not a philosophical one. While changing social norms (e.g., how a village views vaccination) is often the ultimate goal of development, measuring those shifts requires slower, more extensive fieldwork (as discussed in Level 4).

In contrast, individual changes can be immediate. You can observe if a user is learning or motivated right now, even if the full impact of an AI product requires changes in social dynamics. This makes individual metrics the fastest, most sensitive signals for rapid product iteration.

Our recommendation: Do not ignore social dynamics, but do not let them slow down your experimentation. Measure what you can see today (i.e., the user’s behavior) and until you are ready for a full impact evaluation, use lightweight proxies to track social effects (e.g., asking "Did you share this advice with a neighbor?").

## How is Level 3 evaluation performed?

The first stage of a Level 3 evaluation is identifying the intermediate outcomes that serve as early indicators of the development outcome of interest. The second stage is designing experiments to track how product changes can shift Level 3 outcomes. The evaluation methods are the same as Level 2, but tracking a different set of outcomes:

* A/B testing: Feature A vs. Feature B
* Multi-armed bandits: Performance-based adaptive allocations
* Holdout testing: e.g., AI vs. non-AI

The full workflow includes:

1. [Hypothesis generation](level-3-user-evaluation.md#step-1.-hypothesis-generation)
2. [Descriptive analyses](level-3-user-evaluation.md#step-2.-descriptive-analyses)
3. [Collect survey data](level-3-user-evaluation.md#step-3.-collect-survey-data)
4. [Analyze user generated content](level-3-user-evaluation.md#step-4.-analyze-user-generated-content)

### 1. Hypothesis generation

Based on the theory of change, define intermediate cognitive and affective outcomes that are plausibly linked to your targeted social impact. Validate these via qualitative methods (e.g., user interviews) as well as quantitative research or reviews of the academic literature.

### 2. Descriptive analyses

Review log data or conversation data, as well as Level 2 metrics, to better understand what constitutes psychologically and behaviorally meaningful user interaction. Can you construct measures that go beyond the standard Level 2 engagement and retention metrics? As a first step, look for on-platform behaviors (captured in your app’s telemetry or interaction logs) that can proxy for cognitive and affective outcomes. Examples are provided in the table below.

#### Example metrics

<details>

<summary><strong>Frequency and depth of queries</strong><br>How often and how deeply do users query your AI service?</summary>

An upward trend in the quantity of questions, and the specificity of those questions, may indicate that the user’s curiosity, confidence, and understanding are increasing over time.

* Increased frequency of interaction with an AI tutor can signal curiosity and learning gains. [A recent study](https://www.google.com/url?q=https://eric.ed.gov/?q%3Dsource%253A%2522British%2BJournal%2Bof%2BEducational%2BTechnology%2522%26ff1%3DpubReports%2B-%2BResearch%26ff2%3DsubLearner%2BEngagement%26id%3DEJ1427270%23:~:text%3Dthe%2520control%2520group%2520utilized%2520rule,regulation%2520behaviours\&sa=D\&source=editors\&ust=1770879887105725\&usg=AOvVaw1-5Gq7uRphy7y8iBbsNUyC) with an AI “study coach” found that the number of student-chatbot interactions predicts improvement in students’ self-regulated learning (SRL) behavior. As learners become more confident, they ask more questions and explore topics further.
* The technical depth of queries can be informative: if users progress from basic factual questions to more advanced specific inquiries, it indicates knowledge growth. [Learning analytics](https://www.google.com/url?q=https://moldstud.com/articles/p-essential-benchmarking-metrics-for-evaluating-e-learning-success%23:~:text%3DAnalyze%2520user%2520behavior%2520data%2520to,learners%2520progressing%2520to%2520subsequent%2520sections\&sa=D\&source=editors\&ust=1770879887107745\&usg=AOvVaw1TjYXTvjqiMxRiTIOKNQ8C) often track whether learners move on to advanced content as a proxy for learning progression.

</details>

<details>

<summary><strong>Changes in language</strong><br>How complex are user queries?</summary>

As users gain expertise, their vocabulary, syntax, and linguistic sophistication may advance.

* Empirical studies support the connection between language complexity and cognitive development. For instance, students tend to write lengthier, more complex sentences when [engaging in in-depth learning tasks](https://www.google.com/url?q=https://eprints.soton.ac.uk/390338/1/1761_Article_Text_8498_1_10_20160728.pdf%23:~:text%3Dscores,The%2520negative%2520association%2520of%2520positive\&sa=D\&source=editors\&ust=1770879887110643\&usg=AOvVaw1B3bbVScl6-fW6Txi-CAfr).
* If a user’s questions or messages show increased application of advanced concepts, or more complex sentence structures, they may have achieved cognitive gains and/or subject matter mastery.

</details>

<details>

<summary><strong>Follow-up question rate</strong><br>Are users persisting in a line of questioning?</summary>

When a user asks a new question related to the previous answer (an indicator of engagement) they are likely engaging in deeper thinking.

* While direct experimental measures are still emerging, [educational theory](https://www.google.com/url?q=https://www.cambridge.org/elt/blog/2022/02/22/engine-achievement-role-curiosity-learner-engagement/%23:~:text%3DCuriosity%2520is%2520an%2520important%2520condition,classrooms%2520to%2520increase%2520learner%2520engagement\&sa=D\&source=editors\&ust=1770879887112281\&usg=AOvVaw2n57QKj-YSO7xyr0wLb-po) suggests that students who ask more questions are more actively engaged in their learning.
* Some conversational learning systems monitor average dialogue turns per query, with longer conversational exchanges indicating intellectual curiosity, active learning, and higher-order thinking.

{% hint style="warning" %}
It’s important to distinguish productive follow-up questions from those caused by confusion or misunderstanding.
{% endhint %}

</details>

<details>

<summary><strong>Feature utilization</strong><br>Do users follow recommendations or use suggested tools?</summary>

AI education platforms often include specific features or recommendations intended to drive learning actions. For example, a chatbot might offer to quiz you or provide links to further reading. Feature utilization rates – which track whether users adopt suggested tools or follow AI advice – can signal levels of trust and motivation.

* High follow-through rates imply that the user finds the suggestions valuable and trusts the guidance enough to act on it. In [a recent study](https://www.google.com/url?q=https://knowledge.wharton.upenn.edu/article/why-is-it-so-hard-for-ai-to-win-user-trust/%23:~:text%3DThe%2520study%25E2%2580%2599s%2520findings%2520rejected%2520the,and%252C%2520consequently%252C%2520on%2520user%2520performance\&sa=D\&source=editors\&ust=1770879887114908\&usg=AOvVaw38QlFg0NJvvairwrnuzFV9), users built trust when they observed over time that AI recommendations were correct. Users with positive outcomes tended to rely on AI more.
* When learners consistently accept AI suggestions and complete optional exercises, this can signal trust in the AI and a high level of motivation to learn. Conversely, low uptake can indicate weak trust, poor relevance of the suggestions, or lack of motivation.

</details>

#### Guidelines for developing the metrics

When developing such measures within an AI product, a few guidelines are important:

*   **Use validated scales or questions (Don't Reinvent the Wheel)**: Do not write questions from scratch if you don't have to. Adapt existing, well-tested psychological scales to measure things like self-efficacy, motivation, or emotional state. Instead of asking, "Do you like math now?" you can ask&#x20;

    * true/false questions about confidence (“I am more confident solving these problems on my own”)
    * emotional state (“Using this app made me feel motivated to keep learning”)
    * behavioral intentions (“After using the app, I plan to try the recommended technique in real life”)

    Short, psychometrically sound surveys can capture short-term user outcomes with surprising depth if designed well.
* **Keep it Short (Max 3 Questions)**: To avoid fatiguing or annoying your users, limit surveys to a handful of items. A mix of multiple-choice, rating scales, and an open-ended question can yield quantitative and qualitative insights. For example:&#x20;
  * “How helpful was the advice you received?” (Likert scale)
  * “How did you feel during the conversation?” (use emojis or a frustration scale)
  * “What was the most useful part of this interaction?” (open response)
* **Integrate into the flow**: Carefully consider the timing and context of survey questions, so that feedback is tied to a concrete experience. Don't use a pop-up form that breaks the user experience. Have the AI ask for feedback naturally within the chat flow, ideally right after the user has completed a significant task or learned a new concept. Make the process feel like a natural dialogue or a reflection, not an intrusive add-on.

{% hint style="info" %}
Recent research in AI psychometrics has used [GPTs to generate user-level survey items with strong construct validity](https://www.google.com/url?q=https://psychometrics.ai/\&sa=D\&source=editors\&ust=1770879887119775\&usg=AOvVaw1LvGUJpHTAhfTVndYLDhZ9); this technique can help you develop short survey assessments that unfold seamlessly within conversations.
{% endhint %}

### 3. Collect Survey Data

Often, the most direct way to gauge a user’s thoughts, feelings, knowledge, and behaviors is simply to ask them. Short surveys can capture self-reported changes and subjective experiences or perceptions.

In some cases, you will need to survey users off-platform, especially for behavior changes that manifest over longer periods or are difficult for users to perceive. In this context, you might conduct:

* **Longer Surveys or Interviews**: Outside the app, more extensive questionnaires or surveys can be administered to measure knowledge (quizzes or tests), psychological well-being, or frequency of behaviors (e.g., “How often did you practice math outside the app this week?”). Interviews and focus groups can delve into how users’ attitudes or habits have changed over time (e.g., a student might say, “I never liked math before, but now I find myself challenging myself with problems for fun”).
* **Observer Reports**: In an educational context, teachers or parents might report on the student’s changes (“I noticed my child now approaches homework more confidently”). These external perspectives can validate self-reported survey items and trace data.
* **Analysis of Objective Performance Data**: Whenever possible, tie AI usage to objective outcomes measured external to the AI solution. For example, if an AI writing assistant claims to improve writing skills, administer a writing assessment before and after prolonged use, with blind graders evaluating outputs (or conduct a randomized controlled trial, [as in this field experiment](https://www.google.com/url?q=https://papers.ssrn.com/sol3/papers.cfm?abstract_id%3D4895486%23:~:text%3DThese%2520tutors%2520comprise%2520about%252015,successful%252C%2520perform%2520worse%2520on%2520their\&sa=D\&source=editors\&ust=1770879887122242\&usg=AOvVaw1TG0pd4tokWsfyxHmq9ygx)). You can correlate Level 2 metrics with exam scores, task completion rates, and even health indicators. This gets you closer to impact-level metrics, providing strong evidence of user-level change – but within a shorter time period.

### 4. Analyze user-generated content

An exciting addition to the toolkit is using Natural Language Processing (NLP) methods to analyze what users say or write during their interactions. The actual conversation logs or written outputs can be mined for signals of cognitive or emotional change. Several approaches are outlined in the table below:

<table data-full-width="true"><thead><tr><th width="246.18359375">Method</th><th>Examples</th></tr></thead><tbody><tr><td><strong>Sentiment Analysis</strong>: Automatically scoring the sentiment of user utterances over time.</td><td><ul><li>Are the words generated by the user more positive or less anxious with increased product use or dosage? A trend from negative to positive tone could indicate growing comfort or satisfaction.</li><li>Spikes of negative sentiment might flag frustration at certain points. Tools like fine-tuned transformer models can rate sentiment for each message or session.</li></ul></td></tr><tr><td><strong>Topic Modeling&#x26; Keyword Analysis</strong>: Analyze the content of conversations for emergent themes.</td><td><ul><li>Topic modeling can track a user’s progression over time. Topics discussed might shift from fundamental concepts to more advanced ones – indicating cognitive growth.</li><li>Keyword analysis can surface unexpected themes – e.g., users frequently citing “exam anxiety” might signal an affective need that your product should address.</li></ul></td></tr><tr><td><strong>Linguistic Inquiry and Word Count (LIWC)</strong></td><td><ul><li><a href="https://www.google.com/url?q=https://www.liwc.app/&#x26;sa=D&#x26;source=editors&#x26;ust=1770879887126051&#x26;usg=AOvVaw0hWI7y2Pk_FTXnsDObhuKA">LIWC</a> is a dictionary-based text analysis tool developed by psychologists that <a href="https://www.google.com/url?q=https://www.researchgate.net/publication/383061194_GPT_is_an_effective_tool_for_multilingual_psychological_text_analysis%23:~:text%3Dimproved%2520across%2520successive%2520versions%2520of,may%2520help%2520facilitate%2520more%2520cross&#x26;sa=D&#x26;source=editors&#x26;ust=1770879887126522&#x26;usg=AOvVaw0vpBZpGvUwZJgA9KlLl82F">maps words to psychological categories</a> (like emotion, social words, cognitive processes). You can analyze user text to quantify the percentage of words indicating analytical thinking or emotional dysregulation.<br></li><li><a href="https://www.google.com/url?q=https://journals.sagepub.com/doi/abs/10.1177/0261927x09351676&#x26;sa=D&#x26;source=editors&#x26;ust=1770879887127078&#x26;usg=AOvVaw2kzxF9rOTuHTVoDFuiNrk3">Decades of research</a> have shown that linguistic indicators correlate with psychological states. For instance, an increase in first-person plural pronouns (“we, us”) might indicate users feel more socially connected, whereas a drop in words like “never, not” might indicate reduced negativity.</li></ul></td></tr><tr><td><strong>LLM-Based Text Analysis</strong>:<br>Using LLMs to analyze text</td><td><p>Studies have shown that we can <a href="https://www.google.com/url?q=https://arxiv.org/abs/2309.10771&#x26;sa=D&#x26;source=editors&#x26;ust=1770879887128236&#x26;usg=AOvVaw30j6uV1pX7DzxeER6W77Bt">leverage large language models (like GPT)</a> to code or score text in nuanced, human-like ways.</p><ul><li>GPT-4 can accurately detect psychological constructs (i.e., sentiment, loneliness) in text with reliability often surpassing traditional dictionary methods. This appears to work across multiple languages. Example: prompt the model with “On a scale of 1–5, how much self-confidence does this message show?”</li><li>LLM text analysis can be used to profile user text generation over time. For example, we can prompt a model to score a chatbot conversation as {sentiment trend: positive; confidence expressed: moderate and rising; themes: independence 3/5, belongingness 4/5}. Quantified scores allow us to track subtle changes, at scale. Be careful when using an LLM to evaluate LLM-user interactions; you want to avoid bias and misinterpretation.</li></ul></td></tr></tbody></table>

### Defining guardrail metrics: measuring potential harm

As you reach Level 3 evaluations, you are not just measuring if your product is working; you want to measure if it is causing harm. While Level 2 metrics track usage, Level 3 is your opportunity to use direct interviews and surveys to track unintended consequences.

AI models and agents can empower or disempower users. In evaluating social impact, user agency can be a critical guardrail for AI products. There is a risk that "helpful" AI agents might actually undermine development, creating dependency for users or communities rather than building capabilities. You will want to track whether your tool is improving or reducing participant well-being.

We recommend measuring agency in two ways:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><strong>Subjective Agency (Internal-Facing)</strong></td><td>This captures users’ beliefs and perceptions of their own capabilities (e.g. <a href="https://www.google.com/url?q=https://albertbandura.com/albert-bandura-agency.html&#x26;sa=D&#x26;source=editors&#x26;ust=1770879887131259&#x26;usg=AOvVaw16YhjaGx912hq09iENz-53">Albert Bandura’s Social Cognitive Theory</a>), measured through qualitative or survey methods. Ask users about their sense of self-efficacy: do they believe they can solve the problem on their own now?</td></tr><tr><td><strong>Objective Agency (External-Facing)</strong></td><td>These are the capabilities required to plan, navigate, execute, and reflect on personal goals (e.g. <a href="https://www.google.com/url?q=https://www.cambridge.org/core/books/abs/amartya-sen/capability-and-agency/65BD3415B565147A740E03F42E41D047&#x26;sa=D&#x26;source=editors&#x26;ust=1770879887132080&#x26;usg=AOvVaw32UWwt_5zCTBKeWIFq3dgj">Amartya Sen’s Capability Approach</a>). Does the user have the skills to act? Test their ability to plan and execute goals without the AI's help. Are they learning the underlying logic, or just copy-pasting answers?</td></tr></tbody></table>

### User privacy and security

Collecting data on user thoughts and feelings (Level 3) carries significant legal and ethical responsibilities. Because using GenAI models may involve sending data to third-party model providers (e.g., OpenAI, Google, Anthropic), it is important to pay attention to data governance:

1. **Know the Legal Landscape**: Data privacy laws vary by jurisdiction (e.g., Data Protection Act in Kenya, GDPR in Europe). Organizations should consult with legal counsel to define clear Terms of Use and Privacy Policies for the AI products they deploy.
   * Be especially cautious if your user base includes minors or if you are handling sensitive health information or Personally Identifiable Information (PII).
   * Vulnerable Populations: Users with low literacy or digital literacy may not understand standard legal disclaimers. You have an ethical obligation to ensure they genuinely understand how their data will be used.
2. **Industry vs. Academic Standards**: The rules governing data collection and analysis depend on your goals and your partners:
   * Internal Product Improvement (Industry Standard): If you are analyzing data solely to improve the product, this is typically governed by your internal data policies and the user’s consent via Terms of Service. Most organizations ask individuals to consent to data collection when using their products and establish internal procedures for reviewing the safety and ethics of user studies.
   * Generalizable Knowledge (Academic Standard): If you partner with academic researchers or intend to publish your findings as "research," you will likely require Institutional Review Board (IRB) approval. IRBs oversee the ethical treatment of human subjects and ensure informed consent.
3. **Value of Responsible Data**: While user privacy constraints require effort, they enable the safe leveraging of product data to generate concrete intermediate metrics for A/B testing. Sometimes analyzing chat logs and feedback is the only way to optimize your product for users (Level 3) and ensure it is ready to drive development outcomes (Level 4). Responsible data practices build the user trust necessary for this impact.

## What is the Minimum Viable Evaluation?

{% include "../.gitbook/includes/level-3-mve.md" %}

## Who is most involved in this level of evaluation?

In Level 3, researchers evaluate users’ attitudes and behaviors using [quantitative and/or qualitative methods](https://www.google.com/url?q=https://www.nngroup.com/articles/which-ux-research-methods/\&sa=D\&source=editors\&ust=1770879887137574\&usg=AOvVaw0J6hnWoQ93Soc_yax75utB). Contributors are often trained in behavioral science, social psychology, public health, or behavioral economics. They should have a mix of quantitative and qualitative skills, or be knowledgeable enough to support a multi-methods team using:

* Quantitative approaches (analyzing logs, surveys, and conversation data) to infer users’ state or traits. These approaches measure constructs such as knowledge, beliefs, intention, norms, feelings, behaviors, etc.
* Qualitative approaches (interviews, focus groups, usability tests, and ethnographic methods) to understand how users interact with a product. These approaches help researchers validate assumptions, understand mechanisms, surface unintended effects, and expose contextual or environmental drivers of user pain points.

{% include "../.gitbook/includes/level-3-roles.md" %}

## Additional Resources

Case Study: [ChatSEL](https://www.google.com/url?q=https://agency-fund.github.io/chatsel-docs/docs/t1-intro\&sa=D\&source=editors\&ust=1770879887140960\&usg=AOvVaw2LUrXy5jbqiz0qvFf0O1J3) is a GenAI coach developed at the Agency Fund that provides teachers with evidence-based and context-sensitive guidance on understanding and implementing SEL programs in a low-resource classroom. Please see the following document for how we might measure Level 3 outcomes in the context of ChatSEL.

[User Evaluation Workshop - ChatSEL](https://www.google.com/url?q=https://docs.google.com/document/d/18AXtIeDx6HsidhMKTJ2kIDb7hUwHEkEnwGPZuC9JJo0/edit?tab%3Dt.0\&sa=D\&source=editors\&ust=1770879887141682\&usg=AOvVaw1gh5ryGKTXgLHYERa1LGPc)
