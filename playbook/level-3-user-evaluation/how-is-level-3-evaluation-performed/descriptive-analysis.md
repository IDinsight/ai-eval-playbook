# Descriptive Analysis

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
