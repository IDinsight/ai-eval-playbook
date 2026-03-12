# How is Level 2 evaluation performed?

It is straightforward to instrument your product to track user actions and events in your product using 3rd party analytics tools (e.g. Amplitude, Mixpanel, Google Analytics). You can start delivering meaningful Level 2 results very quickly, simply by observing trends in user events over time. For example, users may get stuck during a specific chatbot interaction, or they might stop engaging after a specific prompt for action. With appropriate metrics, you can run rapid cycles of experimentation, testing variations in your product’s elements (or features) to find strategies that reduce user dropoff.

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

To test the effectiveness of promising new features or interventions, you can randomly assign users to receive either the existing product, or the “improved” variant. This is done through [A/B testing and other forms of experimentation](methods-for-experimentation-a-b-testing-and-beyond.md). The events associated with a new feature should be flagged in your 3rd party product analytics tool, so that you can easily assess their impact on priority metrics. Many engineering teams leverage automated experimentation platforms to manage feature testing; these platforms also help you track which versions of a product or feature are most effective, across experiments.
{% endstep %}
{% endstepper %}

Once the results of an experiment are available, product or program managers interpret the findings and work with engineering to roll out the most effective features or interventions to all users.

{% hint style="warning" %}
## <mark style="color:$warning;">Do not optimize your funnel metrics for the user engagement alone.</mark>&#x20;

While product use and retention may be necessary entry points for impact, you should avoid engaging users in ways that waste their time or worsen their well-being. Instead, optimize for a metric like “Time to Success”, where success is defined as solving the user’s problem or building their capabilities. Setting appropriate boundaries for a healthy level of engagement is also critical.
{% endhint %}
