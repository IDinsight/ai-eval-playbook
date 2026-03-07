---
description: Does the overall product engage and retain users?
icon: box-isometric
---

# Level 2 – Product evaluation

## Why is this level of evaluation important?

​​An AI system that produces perfect responses is worthless if users do not use it. Once you deploy your AI system as a product (e.g., a chatbot or app), you must track a few critical user signals, like:

* Engagement: How many users are using the product?
* Retention: How likely are they to continue using it?

If users never engage—or stop interacting because they see no value—they are unlikely to change their behavior in ways that improve their life outcomes.

Like AI system evals, Level 2 evaluation is a continuous, iterative cycle, not a one-time exercise. We track user interaction metrics over time, and look for unexpected drop-off (or improvements, for example when a new feature is released as part of an A/B test). Product evaluations are critical for iterative improvement, but they can also be a matter of safety. Suppose you have an experimental new feature in your chatbot – but you’re not sure how people will react. It might be risky to roll out this new feature to all users, all at once. As you will see, Level 2 evaluation can be used to detect changes in user behavior that might signal risk.

## What is the “Product” being evaluated?

To understand if users are actually finding value in your product, you must "instrument" your application, setting it up to automatically log specific user actions. The resulting log data allow you to track users as they move through the User Funnel: from their first interaction (Activation), to regular usage (Engagement) to long-term commitment or habit formation (Retention).

In the tech sector, companies might track "clicks" and "purchases" as users move through a website. By analyzing logs, you can then identify which content or products are likely to bring users back to the website over time, or how different web experiences affect browsing time. In the development sector, we need to track actions that signal user intent, and estimate the value returned to users in response. For example:

* For an AI Agronomist, instead of tracking page views you might track whether a farmer uploads a photo of a diseased crop, listens to audio advice to completion, or shares content with another person.
* For an AI Tutor, you might track if a student completes a quiz, how many follow-up questions they ask in a single session, or if they return to the app the night before an exam.

By analyzing these "digital traces," we can identify exactly where users lose interest. Does the farmer drop off because the photo upload takes too long? Does the student quit because the AI’s first response was too complex?

The good news: Fortunately, Level 2 evaluation methods are well-scoped; you don't need to reinvent the wheel. The technology sector has spent decades standardizing digital product metrics. Most off-the-shelf analytics tools for web/mobile applications (like Amplitude or Google Analytics) come ready-made to measure the standard metrics you need, such as Daily Active Users (DAU), Time to Activate, and Retention Rates.

The following table defines common Level 2 product metrics for each stage:

<table data-full-width="true"><thead><tr><th width="186.6953125">Stage</th><th>Metric</th><th>Examples</th><th>Notes</th></tr></thead><tbody><tr><td><strong>Acquisition</strong></td><td>New Users (#):<br>Total count of users entering the top of the funnel</td><td># farmers consenting to receive WhatsApp messages; # students downloading an app; # health workers attending a training session.</td><td>There are costs associated with recruitment, so you may wish to target your ideal users effectively and efficiently. Track the source of each new user (e.g., "Referral" vs. "Field Visit") to identify which channels yield the most relevant users, then scale the channel with the highest yield.</td></tr><tr><td><strong>Cost Per User (CAC)</strong>:<br>Cost of running a recruitment activity, divided by new users acquired. Also called User Recruitment Cost.</td><td>Cost of printing flyers / # of QR code scans.<br>Cost of field agent stipend / # of farmer sign-ups.</td><td>High CAC may be unsustainable for low-margin services (i.e. general advice) but acceptable for high-impact interventions like urgent telemedicine consults.</td><td></td></tr><tr><td><strong>Activation</strong></td><td>Activation rate:<br>% of users who complete the "First Value" action after signing up or being recruited.</td><td>% of mothers who complete their health profile<br>% of teachers who create their first lesson plan</td><td>Activation measures if users actually start using the tool or service, not just if they installed it. It is a user's early experience with the product, so important to “get right” to prevent drop-off. Onboarding can also be a critical point for collecting user demographic data used for personalization and subgroup analysis.</td></tr><tr><td><strong>Time to activate</strong>:<br>Average time elapsed between sign-up and the first core action.</td><td>Minutes from first WhatsApp message to asking the first medical question<br>Days from initial training to logging the first case data</td><td>New user interest tends to taper off exponentially after sign-up, so it’s important to encourage users to complete onboarding within the first few hours/days.<br>Long activation times usually signal a confusing interface or a lack of trust or value.</td><td></td></tr><tr><td><strong>Engagement</strong></td><td>Monthly, weekly, and/or daily active users (MAU, WAU, DAU):<br>Number of users using the app/feature in a time window.</td><td># Community Health Workers using a reporting tool daily<br># Students using a study bot weekly before exams</td><td>Do not optimize for addiction. In welfare-focused apps, "Time to Success" (i.e., getting to an urgent answer quickly) is better than "Time on Device."</td></tr><tr><td><strong>Interaction depth</strong>:<br>Volume of interaction per session (e.g., turns per conversation).</td><td>Average # of follow-up questions a student asks (signals curiosity) per session<br>Rate at which a user accepts a suggestion (signals trust)</td><td>For a chatbot, the # of conversation turns can be good (deep inquiry) or bad (confusion). Pair engagement metrics with qualitative inquiry (Level 3).<br>Remember that frequent interaction (e.g. page loads, button clicks, form submits, session length) may not translate to meaningful interaction.</td><td></td></tr><tr><td><strong>Retention</strong></td><td>Stickiness (DAU/MAU):<br>Ratio of daily users to monthly users.</td><td>A ratio of 0.25 means the average user uses the tool 7-8 days per month.<br>A ratio close to 1 indicates sustained value or habit formation.</td><td>High stickiness indicates the tool is part of a daily workflow. A low ratio suggests the tool is only useful for sporadic problems (e.g., seasonal crop disease) rather than daily habits. Is habit formation critical to your welfare goals?</td></tr></tbody></table>

In addition to these, you may want to specify negative metrics (or safety guardrails) that track problematic user behavior. For example, if a mother uses a health chatbot for an emergency, a long session may indicate confusion and inefficiency. We must aggressively distinguish between intense or extensive engagement, and effective engagement.

## How is Level 2 evaluation performed?

It is straightforward to instrument your product to track user actions and events using 3rd party analytics tools (e.g. Amplitude, Mixpanel, Google Analytics). You can start delivering meaningful Level 2 results very quickly, simply by observing trends in user events over time. For example, users may get stuck during a specific chatbot interaction, or they might stop engaging after a specific prompt for action. With appropriate metrics, you can run rapid cycles of experimentation, testing variations in your product’s elements (or features) to find strategies that reduce user dropoff.

These are the critical steps in a Level 2 evaluation:

{% stepper %}
{% step %}
### Define the user funnel and metrics

First, qualitatively define the stages of your user journey. How do you describe the user who is: acquired (recruited), activated (onboarded), engaged (using regularly), and retained (coming back). An acquired user could be someone who has attended a recruitment event, and given their consent to participate in a program. An activated user might be one who has completed the training needed to start benefiting from an app or service. Once stages of the funnel are defined, select industry-standard metrics that match the expected behavior at each stage. If your app is designed for weekly use, track Weekly Active Users (WAU) over time, rather than Daily Active Users (DAU).
{% endstep %}

{% step %}
### Instrument the product

Next, you must identify the specific events, or user actions, that signal progress through the user funnel. These might include "app opened," "question asked," or "training completed." Select the events that are most consequential to the user's success. The events you select will be used to calculate your metrics. Some events may not be used to calculate a metric, but can still be useful to track, for example if they help you understand the user’s path and identify potential bottlenecks (like clicking the help icon). Your engineering team can implement a third-party analytics tool (e.g., Amplitude, Mixpanel) to capture and log these events automatically.

{% hint style="warning" %}
Always log a unique User ID with these events; this connects your product data to evaluations at Levels 3 & 4.
{% endhint %}
{% endstep %}

{% step %}
### Automate metrics and analyze trends

From the event data being logged, your data scientist or engineer will construct the metrics you have selected. For instance, “Time to Activate” can be calculated by counting the number of days between the first and last user actions required for completion of the "activation" stage. Your engineering team can display key metrics in a dashboard that can be shared across the entire organization. Out of the box, most commercial analytics platforms can display time-series charts and funnel charts (to visualize drop-offs at each stage). Ideally, each metric has a directly responsible individual who is accountable for monitoring and improving the value over time.
{% endstep %}

{% step %}
### Identify frictions and design improvements

Once you configure your analytics tool to visualize your metrics, use the data to identify friction points—specific steps in the product flow where users consistently drop off. For example, you might notice expectant mothers stop engaging specifically when a maternal health chatbot asks for their location. Or you might see farmers abandon an advisory app if a prompt requires too much typing. Where you identify failure points or bottlenecks, brief user interviews or surveys can be conducted to investigate. Program or product leads can then propose new features, interventions, or nudges to help users progress through the funnel.
{% endstep %}

{% step %}
### Test product upgrades

To test the effectiveness of promising new features or interventions, you can randomly assign users to receive either the existing product, or the “improved” variant. This is done through A/B testing and other forms of experimentation (described below). The events associated with a new feature should be flagged in your 3rd party product analytics tool, so that you can easily assess their impact on priority metrics. Many engineering teams leverage automated experimentation platforms to manage feature testing; these platforms also help you track which versions of a product or feature are most effective, across experiments.
{% endstep %}
{% endstepper %}

Once the results of an experiment are available, product or program managers interpret the findings and work with engineering to roll out the most effective features or interventions to all users.

{% hint style="danger" %}
<mark style="color:red;">**Do not optimize your funnel metrics for user engagement alone.**</mark>&#x20;

While product use and retention may be necessary entry points for impact, you should avoid engaging users in ways that waste their time or worsen their well-being. Instead, optimize for a metric like “Time to Success”, where success is defined as solving the user’s problem or building their capabilities. Setting appropriate boundaries for a healthy level of engagement is also critical. - User evaluations. This is why
{% endhint %}

## Methods for experimentation: A/B testing and beyond

Once you routinely track product performance metrics, you can run rapid experiments to observe how new features or improvements affect your users’ behavior. For example, if you tweak the text on a call-to-action, you might expect to see an immediate rise in the corresponding user event. However, not every change yields a positive outcome, and often there are multiple ways to solve a single problem. To identify which product variant is best, you can run Level 2 evaluations.

A/B testing is the most common approach. It’s how tech companies build and refine products, and how digital marketers improve ad performance. The concept is simple: expose “version A” of a product to one set of users, and “version B” to another, then measure which version more effectively improves your funnel metrics.

For the A/B test to be valid, randomization is critical: it ensures that any observed final differences across groups can be attributed to the product changes being tested, rather than to pre-existing differences between user groups. The process begins with selecting a random sample of your user base for the experiment. Individuals within this sample are then randomly assigned to different treatment groups.

It is important to select a user sample large enough to ensure your test is representative of the entire user base. The treatment groups must also be large enough to generate statistically significant estimates of test effects.

While we recommend randomized evaluations, there are multiple methods for testing your product changes:

### Pre/post comparison

This is the simplest method: you simply compare the value of a metric before the change with the value of the metric after. For high-impact, obvious updates, this time-series analysis is often enough. If the product change does not have the intended effect, you simply roll it back.

### Multivariate testing

If you need to test multiple feature variations at once—such as changing text, visuals, and timing of content simultaneously—you can use Multivariate Testing. This reveals the combined effect of these changes, helping you find the optimal combination of elements. For this test, you will randomize the roll-out of different combinations of changes across users, and then compare metrics across user groups.

### A/B testing (recommended)

For the most reliable evaluation of a change in your product, we recommend A/B Testing. Rather than rolling out a change to everyone at once, you expose different versions of the product to different randomized groups of users. This allows you to compare the effects of a change directly, or rapidly test multiple ideas at once. Because this approach balances statistical rigor with feasibility, A/B testing is considered a part of any "Minimum Viable Evaluation" (MVE). There are two flavors of A/B testing:

* **A/B Tests with Planned Assignment (recommended)**: Individual product features or content variants are deployed to randomized user groups. This design works well for testing discrete changes with clear hypotheses. The approach can be extended by testing several competing ideas at the same time, although this requires larger sample sizes to maintain statistical power across all comparison groups.
* **A/B Tests with Self-Assignment**: Users can dynamically self-assign themselves to different variants based on conditional, logic-based paths. For example, some users may choose to attend an in-person training for an app, while others attend an online training. This approach is designed to analyze how different segments of users interact with and respond to the specific variant they chose. Be cautious when analyzing these results: because users self-select, the comparison groups are not random. Differences in performance may stem from the users' inherent traits (e.g., users choosing in-person training may naturally be more motivated) rather than the effectiveness of the variant itself.

### Dynamic assignment

Instead of randomizing users into fixed A/B groups, you can dynamically route users over time to different product variants, using a method known as multi-armed bandit (MAB) testing. If a product variant results in large improvements in user metrics, the MAB algorithm will progressively allocate more users to that variant over the course of the experiment. Contextual bandits is a further refinement that allocates versions of a product based on a combination of the variant’s performance and the user's characteristics. These algorithms allow you to maximize success for your users overall, while still running a rigorous experiment. However, they require more sophisticated real-time analysis and assignment infrastructure, and if you also need unbiased estimates of effect, they also require substantially larger sample sizes.

### Holdout testing

To track performance of your product over the long term, you can use Holdout Testing. In this design, a small group of users is kept on a "status quo" version of the product, frozen in time, while the majority receives the accumulation of new, tested features. Comparing metrics across these groups allows you to measure the total value of your improvements over months or years. This approach can be used in combination with any of the evaluation methods above.

The technical implementation of A/B testing has been greatly simplified by modern tooling. Randomized assignment can be automated using both open-source frameworks and commercial platforms. Open source tools like Evidential and GrowthBook offer flexibility and control for teams with engineering capabilities. Commercial analytics tools like Amplitude and Mixpanel offer ready-to-use experimentation interfaces that automatically track and analyze results using events data. Solutions like Optimizely provide visual editors, statistical analysis, and more sophisticated targeting capabilities.

A/B testing has become indispensable because it replaces opinion-driven decision-making with empirical evidence. When implemented rigorously, it enables organizations to continuously improve their products and experiences based on how real users actually behave rather than how we think they might behave.

## How do Level 2 evaluations connect with other levels?

Ideally, as your Level 1 metrics improve and the AI system becomes more reliable, your Level 2 engagement metrics should also improve. However, technical performance does not always guarantee user adoption, so it is critical to monitor AI system metrics and product analytics in tandem, to ensure that engineering “improvements” actually translate into a better user experience.

In this playbook, Level 2 evaluation focuses exclusively on the digital traces users leave within the product. It does not include qualitative interviews or surveys that probe user beliefs and moods; these activities will fall under the domain of Level 3 evaluation. Level 3 is also where we track many of the metrics used to monitor harm (e.g., anxiety, addiction). This is why we must evaluate Levels 2 and 3 in tandem.

Note that Level 2 also ignores the external, “real world” inputs to a social program or service (like in-person trainings or customer support) that complement a digital product. Metrics to track these in-person events are typically captured in process evaluations, conducted by Monitoring and Evaluation (M\&E) teams. We recommend reviewing process evaluation data alongside Level 2 product analytics, to better understand whether user frictions result from failures in the product, or in the associated offline services.

As your product evolves, remember to refine and revalidate your Level 2 metrics, to better capture the nuance of the user experience. Metrics that record meaningful interactions are more valuable than raw event counts.

## What is the Minimum Viable Evaluation?

We recommend using commercial platforms, when feasible, to track user metrics and automate experiments.

{% include "../.gitbook/includes/level-2-mve.md" %}

## Who is most involved in this level of evaluation?

{% include "../.gitbook/includes/level-2-roles.md" %}

## Additional Resources

The tech industry has published numerous guidebooks and tools to help you define, collect, and analyze user funnel metrics. For details on how to construct common metrics, consider reviewing [The Agency Fund’s User Funnel Playbook](https://www.google.com/url?q=https://theagencyfund.substack.com/p/user-funnel-playbook-for-the-social\&sa=D\&source=editors\&ust=1770879887074264\&usg=AOvVaw0U7ZiNYW1t6uSMGvwCrn7k).

In addition, you can leverage these reference materials:

* [The Amplitude Guide to Product Metrics](https://www.google.com/url?q=https://info.amplitude.com/rs/138-CDN-550/images/The%2520Amplitude%2520Guide%2520to%2520Product%2520Metrics.pdf\&sa=D\&source=editors\&ust=1770879887074800\&usg=AOvVaw3Gw4GO84ftsbU7kTARW0sV)
* [User Analytics for ChatGPT Enterprise and Edu](https://www.google.com/url?q=https://help.openai.com/en/articles/10875114-user-analytics-for-chatgpt-enterprise-and-edu-public-beta\&sa=D\&source=editors\&ust=1770879887075105\&usg=AOvVaw005sJUqXHiBchsro_K4jTY)
* [What We Know About Using Non-Engagement Signals in Content Ranking](https://www.google.com/url?q=https://arxiv.org/abs/2402.06831%23:~:text%3DWhat%2520We%2520Know%2520About%2520Using%2520Non%252DEngagement%2520Signals%2520in%2520Content%2520Ranking,-Tom%2520Cunningham%252C%2520Sana%26text%3DMany%2520online%2520platforms%2520predominantly%2520rank,for%2520society%2520as%2520a%2520whole.\&sa=D\&source=editors\&ust=1770879887075470\&usg=AOvVaw3CU_FAxt448jSHky8V0XFx)

For more details on A/B testing, please review these resources:

* [https://www.youth-impact.org/insights/a-b-testing-toolkit](https://www.google.com/url?q=https://www.youth-impact.org/insights/a-b-testing-toolkit\&sa=D\&source=editors\&ust=1770879887075927\&usg=AOvVaw3x21gqolmL_0E9_fDy6dRX)
* [Optimizely: What is A/B testing?](https://www.google.com/url?q=https://www.optimizely.com/optimization-glossary/ab-testing/\&sa=D\&source=editors\&ust=1770879887076174\&usg=AOvVaw3PKvBKt3EJLt8sZn70Vxx3)
* [Amplitude: What is A/B testing? How it works and when to use it](https://www.google.com/url?q=https://amplitude.com/blog/ab-testing\&sa=D\&source=editors\&ust=1770879887076429\&usg=AOvVaw3sG72ntnL5ErkzmLbKVjJ-)
