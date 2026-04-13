# Identify outcome metrics

There are three potential ways to identify outcome metrics, through 1) analyzing interaction data, 2) primary data collection, and 3) analyzing conversation logs.

### Identify outcome metrics through analyzing interaction data

Review log data or conversation data, as well as Level 2 metrics, to better understand what constitutes psychologically and behaviorally meaningful user interaction. Can you construct measures that go beyond the standard Level 2 engagement and retention metrics? As a first step, look for on-platform behaviors (captured in your app’s telemetry or interaction logs) that can proxy for cognitive and affective outcomes. Examples are provided in the table below.

#### Example metrics

<details>

<summary><strong>Frequency and depth of queries</strong><br>How often and how deeply do users query your AI service?</summary>

An upward trend in the quantity of questions, and the specificity of those questions, may indicate that the user’s curiosity, confidence, and understanding are increasing over time.

* Increased frequency of interaction with an AI tutor can signal curiosity and learning gains. [A recent study](https://eric.ed.gov/?q=source:%22British+Journal+of+Educational+Technology%22\&ff1=pubReports+-+Research\&ff2=subLearner+Engagement\&id=EJ1427270) with an AI “study coach” found that the number of student-chatbot interactions predicts improvement in students’ self-regulated learning (SRL) behavior. As learners become more confident, they ask more questions and explore topics further.
* The technical depth of queries can be informative: if users progress from basic factual questions to more advanced specific inquiries, it indicates knowledge growth. [Learning analytics](https://moldstud.com/articles/p-essential-benchmarking-metrics-for-evaluating-e-learning-success) often track whether learners move on to advanced content as a proxy for learning progression.

</details>

<details>

<summary><strong>Changes in language</strong><br>How complex are user queries?</summary>

As users gain expertise, their vocabulary, syntax, and linguistic sophistication may advance.

* Empirical studies support the connection between language complexity and cognitive development. For instance, students tend to write lengthier, more complex sentences when [engaging in in-depth learning tasks](https://eprints.soton.ac.uk/390338/1/1761_Article_Text_8498_1_10_20160728.pdf).
* If a user’s questions or messages show increased application of advanced concepts, or more complex sentence structures, they may have achieved cognitive gains and/or subject matter mastery.

</details>

<details>

<summary><strong>Follow-up question rate</strong><br>Are users persisting in a line of questioning?</summary>

When a user asks a new question related to the previous answer (an indicator of engagement) they are likely engaging in deeper thinking.

* While direct experimental measures are still emerging, [educational theory](https://www.cambridge.org/elt/blog/2022/02/22/engine-achievement-role-curiosity-learner-engagement/) suggests that students who ask more questions are more actively engaged in their learning.
* Some conversational learning systems monitor average dialogue turns per query, with longer conversational exchanges indicating intellectual curiosity, active learning, and higher-order thinking.

{% hint style="warning" %}
It’s important to distinguish productive follow-up questions from those caused by confusion or misunderstanding.
{% endhint %}

</details>

<details>

<summary><strong>Feature utilization</strong><br>Do users follow recommendations or use suggested tools?</summary>

AI education platforms often include specific features or recommendations intended to drive learning actions. For example, a chatbot might offer to quiz you or provide links to further reading. Feature utilization rates – which track whether users adopt suggested tools or follow AI advice – can signal levels of trust and motivation.

* High follow-through rates imply that the user finds the suggestions valuable and trusts the guidance enough to act on it. In [a recent study](https://knowledge.wharton.upenn.edu/article/why-is-it-so-hard-for-ai-to-win-user-trust/), users built trust when they observed over time that AI recommendations were correct. Users with positive outcomes tended to rely on AI more.
* When learners consistently accept AI suggestions and complete optional exercises, this can signal trust in the AI and a high level of motivation to learn. Conversely, low uptake can indicate weak trust, poor relevance of the suggestions, or lack of motivation.

</details>

***

### Identify metrics through primary data collection

Often, the most direct way to gauge a user’s thoughts, feelings, knowledge, and behaviors is simply to ask them. Short surveys can capture self-reported changes and subjective experiences or perceptions.

#### Guidelines for developing the metrics

When developing such measures within an AI product, a few guidelines are important:

* **Use validated scales or questions:** Do not write questions from scratch if you don't have to. Adapt existing, well-tested psychological scales to measure things like self-efficacy, motivation, or emotional state. Instead of asking, "Do you like math now?" you can ask true/false questions about confidence (“I am more confident solving these problems on my own”), emotional state (“Using this app made me feel motivated to keep learning”), and behavioral intentions (“After using the app, I plan to try the recommended technique in real life”). Short, psychometrically sound surveys can capture short-term user outcomes with surprising depth if designed well.
* **Keep it Short**: To avoid fatiguing or annoying your users, limit surveys to a handful of items (e.g., a max of three questions). A mix of multiple-choice, rating scales, and an open-ended question can yield quantitative and qualitative insights. For example:
  * “How helpful was the advice you received?” (Likert scale)
  * “How did you feel during the conversation?” (use emojis or a frustration scale)
  * “What was the most useful part of this interaction?” (open response)
* **Integrate into the flow**: Carefully consider the timing and context of survey questions, so that feedback is tied to a concrete experience. Don't use a pop-up form that breaks the user experience. Have the AI ask for feedback naturally within the chat flow, ideally right after the user has completed a significant task or learned a new concept. Make the process feel like a natural dialogue or a reflection, not an intrusive add-on.
* **Account for interaction learning over time:** Improvements in engagement metrics may sometimes reflect users becoming more skilled at interacting with the system rather than genuine improvements in knowledge, emotions, or behavior. As users gain experience, they often develop more effective prompting strategies (_prompt maturity_) and interact with the interface more smoothly (_interaction habituation_). These changes can create the appearance of user improvement even if the underlying construct has not improved. Therefore, when designing on-platform measures, it is essential that the survey measures capture constructs beyond habituation to help distinguish user adaptation to the tool from meaningful gains (For example, survey items such as “I feel more confident solving similar problems without AI’s assistance” or “I understand why the recommended solution by AI works” assess self-efficacy and cognition that are not captured simply by smoother interactions with the produc).

{% hint style="info" %}
Recent research in AI psychometrics has used [GPTs to generate user-level survey items with strong construct validity](https://psychometrics.ai/); this technique can help you develop short survey assessments that unfold seamlessly within conversations.
{% endhint %}

Comprehensive evaluations will survey users off-platform, especially for behavior changes that manifest over longer periods or are difficult for users to perceive. These measures are designed to minimize direct references to the platform or intervention itself. Self-reports that explicitly ask users to evaluate the product (e.g., “How helpful was this AI tool?”) are susceptible to “halo effects,” in which users who like the product report more positive outcomes regardless of actual changes in knowledge, feelings, or behavior. To reduce this bias, evaluators should prioritize decoupled measurement approaches – for example, assessing knowledge, attitudes, or behaviors at multiple time points without framing questions in terms of the intervention.

In this context, you might conduct:

* **Longer Surveys or Interviews**: Outside the app, more extensive questionnaires or surveys can be administered to measure knowledge (quizzes or tests), psychological well-being, or frequency of behaviors (e.g., “How often did you practice math outside the app this week?”). Interviews and focus groups can delve into how users’ attitudes or habits have changed over time (e.g., a student might say, “I never liked math before, but now I find myself challenging myself with problems for fun”).
* **Observer Reports**: In an educational context, teachers or parents might report on the student’s changes (“I noticed my child now approaches homework more confidently”). These external perspectives can validate self-reported survey items and trace data.
* **Analysis of Objective Performance Data**: Whenever possible, tie AI usage to objective outcomes measured external to the AI solution. For example, if an AI writing assistant claims to improve writing skills, administer a writing assessment before and after prolonged use, with blind graders evaluating outputs (or conduct a randomized controlled trial, [as in this field experiment](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4895486)). You can correlate Level 2 metrics with exam scores, task completion rates, and even health indicators. This gets you closer to impact-level metrics, providing strong evidence of user-level change – but within a shorter time period.

***

### Identify metrics through analyzing conversation logs

An exciting addition to the toolkit is using Natural Language Processing (NLP) methods to analyze what users say or write during their interactions. The actual conversation logs or written outputs can be mined for signals of cognitive or emotional change. Several approaches are outlined in the table below:

<table data-full-width="true"><thead><tr><th width="246.18359375">Method</th><th>Examples</th></tr></thead><tbody><tr><td><strong>Sentiment Analysis</strong>: Automatically scoring the sentiment of user utterances over time.</td><td><ul><li>Are the words generated by the user more positive or less anxious with increased product use or dosage? A trend from negative to positive tone could indicate growing comfort or satisfaction.</li><li>Spikes of negative sentiment might flag frustration at certain points. Tools like fine-tuned transformer models can rate sentiment for each message or session.</li></ul></td></tr><tr><td><strong>Topic Modeling&#x26; Keyword Analysis</strong>: Analyze the content of conversations for emergent themes.</td><td><ul><li>Topic modeling can track a user’s progression over time. Topics discussed might shift from fundamental concepts to more advanced ones – indicating cognitive growth.</li><li>Keyword analysis can surface unexpected themes – e.g., users frequently citing “exam anxiety” might signal an affective need that your product should address.</li></ul></td></tr><tr><td><strong>Linguistic Inquiry and Word Count (LIWC)</strong></td><td><ul><li><a href="https://www.liwc.app/">LIWC</a> is a dictionary-based text analysis tool developed by psychologists that <a href="https://www.researchgate.net/publication/383061194_GPT_is_an_effective_tool_for_multilingual_psychological_text_analysis">maps words to psychological categories</a> (like emotion, social words, cognitive processes). You can analyze user text to quantify the percentage of words indicating analytical thinking or emotional dysregulation.</li><li><a href="https://journals.sagepub.com/doi/abs/10.1177/0261927x09351676">Decades of research</a> have shown that linguistic indicators correlate with psychological states. For instance, an increase in first-person plural pronouns (“we, us”) might indicate users feel more socially connected, whereas a drop in words like “never, not” might indicate reduced negativity.</li></ul></td></tr><tr><td><strong>LLM-Based Text Analysis</strong>:<br>Using LLMs to analyze text</td><td><p>Studies have shown that we can <a href="https://arxiv.org/abs/2309.10771">leverage large language models (like GPT)</a> to code or score text in nuanced, human-like ways: for instance, see <a href="https://openai.com/index/scaling-social-science-research/">OpenAI's Gabriel</a>  and <a href="https://developers.googleblog.com/introducing-langextract-a-gemini-powered-information-extraction-library/">Google's Langextract</a>. </p><ul><li>GPT-4 can accurately detect psychological constructs (i.e., sentiment, loneliness) in text with reliability often surpassing traditional dictionary methods. This appears to work across multiple languages. Example: prompt the model with “On a scale of 1–5, how much self-confidence does this message show?”</li><li>LLM text analysis can be used to profile user text generation over time. For example, we can prompt a model to score a chatbot conversation as {sentiment trend: positive; confidence expressed: moderate and rising; themes: independence 3/5, belongingness 4/5}. Quantified scores allow us to track subtle changes, at scale. Be careful when using an LLM to evaluate LLM-user interactions; you want to avoid bias and misinterpretation.</li></ul></td></tr></tbody></table>

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-3-user-evaluation%2Fhow-is-level-3-evaluation-performed%2Fdescriptive-analysis" %}

</details>
