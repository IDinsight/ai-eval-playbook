# Collect Survey Data

Often, the most direct way to gauge a user’s thoughts, feelings, knowledge, and behaviors is simply to ask them. Short surveys can capture self-reported changes and subjective experiences or perceptions.

#### Guidelines for developing the metrics

When developing such measures within an AI product, a few guidelines are important:

* **Use validated scales or questions:** Do not write questions from scratch if you don't have to. Adapt existing, well-tested psychological scales to measure things like self-efficacy, motivation, or emotional state. Instead of asking, "Do you like math now?" you can ask true/false questions about confidence (“I am more confident solving these problems on my own”), emotional state (“Using this app made me feel motivated to keep learning”), and behavioral intentions (“After using the app, I plan to try the recommended technique in real life”). Short, psychometrically sound surveys can capture short-term user outcomes with surprising depth if designed well.
* **Keep it Short**: To avoid fatiguing or annoying your users, limit surveys to a handful of items (e.g., a max of three questions). A mix of multiple-choice, rating scales, and an open-ended question can yield quantitative and qualitative insights. For example:&#x20;
  * “How helpful was the advice you received?” (Likert scale)
  * “How did you feel during the conversation?” (use emojis or a frustration scale)
  * “What was the most useful part of this interaction?” (open response)
* **Integrate into the flow**: Carefully consider the timing and context of survey questions, so that feedback is tied to a concrete experience. Don't use a pop-up form that breaks the user experience. Have the AI ask for feedback naturally within the chat flow, ideally right after the user has completed a significant task or learned a new concept. Make the process feel like a natural dialogue or a reflection, not an intrusive add-on.
* **Account for interaction learning over time:** Improvements in engagement metrics may sometimes reflect users becoming more skilled at interacting with the system rather than genuine improvements in knowledge, emotions, or behavior. As users gain experience, they often develop more effective prompting strategies (_prompt maturity_) and interact with the interface more smoothly (_interaction habituation_). These changes can create the appearance of user improvement even if the underlying construct has not improved. Therefore, when designing on-platform measures, it is essential that the survey measures capture constructs beyond habituation to help distinguish user adaptation to the tool from meaningful gains (For example, survey items such as “I feel more confident solving similar problems without AI’s assistance” or “I understand why the recommended solution by AI works” assess self-efficacy and cognition that are not captured simply by smoother interactions with the produc).

{% hint style="info" %}
Recent research in AI psychometrics has used [GPTs to generate user-level survey items with strong construct validity](https://psychometrics.ai/); this technique can help you develop short survey assessments that unfold seamlessly within conversations.
{% endhint %}



Comprehensive evaluations will survey users off-platform, especially for behavior changes that manifest over longer periods or are difficult for users to perceive. These measures are designed to minimize direct references to the platform or intervention itself. Self-reports that explicitly ask users to evaluate the product (e.g., “How helpful was this AI tool?”) are susceptible to “halo effects,” in which users who like the product report more positive outcomes regardless of actual changes in knowledge, feelings, or behavior. To reduce this bias, evaluators should prioritize decoupled measurement approaches – for example, assessing knowledge, attitudes, or behaviors at multiple time points without framing questions in terms of the intervention.&#x20;

In this context, you might conduct:

* **Longer Surveys or Interviews**: Outside the app, more extensive questionnaires or surveys can be administered to measure knowledge (quizzes or tests), psychological well-being, or frequency of behaviors (e.g., “How often did you practice math outside the app this week?”). Interviews and focus groups can delve into how users’ attitudes or habits have changed over time (e.g., a student might say, “I never liked math before, but now I find myself challenging myself with problems for fun”).
* **Observer Reports**: In an educational context, teachers or parents might report on the student’s changes (“I noticed my child now approaches homework more confidently”). These external perspectives can validate self-reported survey items and trace data.
* **Analysis of Objective Performance Data**: Whenever possible, tie AI usage to objective outcomes measured external to the AI solution. For example, if an AI writing assistant claims to improve writing skills, administer a writing assessment before and after prolonged use, with blind graders evaluating outputs (or conduct a randomized controlled trial, [as in this field experiment](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4895486)). You can correlate Level 2 metrics with exam scores, task completion rates, and even health indicators. This gets you closer to impact-level metrics, providing strong evidence of user-level change – but within a shorter time period.

