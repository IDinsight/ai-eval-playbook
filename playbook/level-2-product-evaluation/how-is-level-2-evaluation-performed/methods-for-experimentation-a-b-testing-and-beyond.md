# Methods for experimentation: A/B testing and beyond

Once you routinely track product performance metrics, you can run rapid experiments to observe how new features or improvements affect your users’ behavior. For example, if you tweak the text on a call-to-action, you might expect to see an immediate rise in the corresponding user event. However, not every change yields a positive outcome, and often there are multiple ways to solve a single problem. To identify which product variant is best, you can run Level 2 evaluations.

A/B testing is the most common approach. It’s how tech companies build and refine products, and how digital marketers improve ad performance. The concept is simple: expose “version A” of a product to one set of users, and “version B” to another, then measure which version more effectively improves your funnel metrics.

For the A/B test to be valid, **randomization is critical**: it ensures that any observed final differences across groups can be attributed to the product changes being tested, rather than to pre-existing differences between user groups. The process begins with selecting a random sample of your user base for the experiment. Individuals within this sample are then randomly assigned to different treatment groups.

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

{% embed url="https://tally.so/r/A788l0?originPage=level-2-product-evaluation%2Fhow-is-level-2-evaluation-performed%2Fmethods-for-experimentation-a-b-testing-and-beyond" %}
{% endembed %}

---

{% details title="💬 Want to suggest edits or provide feedback?" %}
{% embed url="https://tally.so/r/A788l0?originPage=level-2-product-evaluation%2Fhow-is-level-2-evaluation-performed%2Fmethods-for-experimentation-a-b-testing-and-beyond" %}
{% endembed %}
{% enddetails %}
