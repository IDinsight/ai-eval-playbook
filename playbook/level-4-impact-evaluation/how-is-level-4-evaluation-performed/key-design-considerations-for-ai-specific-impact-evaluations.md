# Key design considerations for AI-specific impact evaluations

With the increased evaluations of AI products, distinct challenges for impact evaluation are emerging. Below are some considerations that merit special attention.

{% stepper %}
{% step %}
### Selecting the right counterfactual

Choosing the counterfactual—what participants would receive without the AI-enabled intervention—is foundational to impact evaluation design. In GenAI evaluations, the range of plausible comparators is often larger, making clear justification essential.[\[5\]](https://docs.google.com/document/d/18du_LUMPGGu4pZQ1nZ-pKoEwu2zlzmQhFLYwX-A-ix0/export?format=html#ftnt5) The counterfactual should represent a meaningful alternative to your product and credibly reflect what the world would look like without it at scale.

There is no single “correct” counterfactual. In some cases, a pure control (no intervention at all) may be appropriate (more on this in the next point). In others, a more active comparator offers greater policy relevance. Common options include:

* _Business-as-usual_ (e.g., no digital support or sporadic human guidance), an established intervention without GenAI interaction is especially relevant when evaluating a potential improvement on an existing service delivery model.
* _Non-AI digital tools_ (e.g., static chatbots or curated content), when considering whether generative AI adds value over existing tech products.
* _Human-delivered services_, when the AI tool substitutes for scarce professional labor (e.g., teachers, health workers). In such cases, it will be valuable to measure not only outcomes but also the cost of implementation (for resources on how to measure costs well see [here](https://www.worldbank.org/en/programs/sief-trust-fund/brief/cost-measurement)).

Thoughtful counterfactual choice affects not only estimated effect size, but also the interpretability and generalizability of results. A strong evaluation will explain both why a given comparator was selected and what alternative scenarios it helps illuminate.
{% endstep %}

{% step %}
### Measuring latent access and contextual factors

The marginal impact of an AI product depends on users’ baseline access to support, including existing AI tools, related technologies, informal use of the product, and competitors. Measuring this baseline is essential for interpreting effects. Where such tools are already widespread, gains may be modest; in low-capacity settings, the same product may yield much larger (or smaller) benefits. Because access can change quickly, it should be tracked throughout the evaluation.

Evaluators should:

1. _Measure existing technology use_, including frequency, type, and purpose of AI or other digital tool usage, whether directly or indirectly.
2. _Measure what users rely on today_, such as informal networks, human advisors, basic technology, or no support at all.
3. _Keep a sharp eye out for leakage_ – since the AI-enabled intervention is likely to be easily portable or shareable, it is important to measure how much of the control group has access to the intervention in some form (more on this below).

Substitutes that users turn to when they don’t use, or have access to your AI product can shape the outcomes you are trying to measure. These fallback options and access patterns shape the AI product’s incremental value. This makes understanding your target population—and which segments face different access, resources, or barriers—essential. Anticipate these dynamics and measure impacts across key dimensions of heterogeneity (e.g., age, gender, poverty, or their interactions), ensuring sufficient sample size to do so.
{% endstep %}

{% step %}
### Managing product dynamism

RCTs enable powerful causal inference, but only under specific assumptions. One of the most important is the Stable Unit Treatment Value Assumption (SUTVA). [A key component of SUTVA is the _no-multiple-versions_ condition: all treated units must receive the same version of the intervention.](#user-content-fn-1)[^1]

In practice, this condition is often only imperfectly met (e.g., motivated providers continuously adapt their services). For GenAI and many other digital platforms, it is almost systematically violated: these tools improve iteratively through retraining, interface changes, or content updates, often alongside ongoing experimentation. As a result, participants within the same trial may face different product versions. This can bias estimates if version exposure correlates with unobserved potential outcomes and, even when identification holds, complicate interpretation of the causal estimand, making it difficult to draw policy recommendations.

Freezing the product version during a trial would restore the single-version condition but undermine ecological validity by eliminating the adaptation that defines product interventions. A better approach is to design evaluations that permit evolution while still delivering credible, interpretable causal estimates.

We recommend four practices:

1. **Tag your versions** – Define in advance what counts as a substantively distinct change, including updates to underlying models outside implementers’ control. Tag each release with a unique version label. Calibrate granularity: definitions that are too fine reduce power, while definitions that are too coarse can hide meaningful heterogeneity.
2. **If A/B testing, randomise test participation** – Do not only randomize between versions A and B; also randomize which users enter the A/B test. Pre-specify the procedure so participation is not correlated with unobserved outcomes. Both this and version tagging require close coordination between the evaluation and tech teams.
3. **Maintain a hold-out group on the baseline version** – If sample size allows, keep a subset of treated participants on a frozen baseline version throughout the trial. Comparing them to users on updated versions allows estimation of the incremental effect of product changes. In a more dynamic variation on this, adaptive experiments could be a [useful approach](#user-content-fn-2)[^2].
4. **Pre-specify at a high level** – In the pre-analysis plan, specify how versions are defined, how rollouts occur, and how exposure is measured. Avoid overly detailed commitments that limit flexibility in responding to unforeseen product changes.

These can seem daunting.  The first step is to focus on the primary purpose of the evaluation: whether it's to prove out an individual product/intervention or whether you are trying to generate generalizable insights about human behavior and how this technology is affecting them.  Referring back to the primary objective (and maybe giving the secondary some weight) will help you decide, for example, at what level of granularity you want to tag your versions (or at least at what level the tags are important).

In addition, the good news is that there is data to help inform decisions about when to exercise these practices.  If L1 and L2 are running frequently (or even continuously), these will provide insights into the magnitude of changes in the models and user use. And L3 evaluations can help you understand whether these changes are associated with changes in behaviors and practices (some quick qualitative work can help you gauge how causal you think these changes are).  These data, together with the purpose of the evaluation, will help you judge what merits a significant enough change, for example, that merits a tag or consideration of an A/B test.&#x20;


{% endstep %}

{% step %}
### Measuring true development outcomes

AI tools often simulate expertise. But does the user _learn_, or just _copy_?

* Invest in using industry-standard **validated assessments** and **administrative data** to credibly measure improvements in capabilities and welfare.
* Avoid measurement tools that can be gamed by simply repeating AI output (e.g., regurgitating chatbot answers). In educational contexts, for example, use measures where performance tests students’ ability when they don’t have access to AI.
{% endstep %}

{% step %}
### Embracing Spillovers to Improve Estimates

GenAI tools are often built to scale—easy to access and share—which makes contamination a real risk in impact evaluations. Information spillovers, where users obtain information about the GenAI solution and perhaps also from it, is one aspect. Another is actual use of GenAI solution despite being in the non-treatment group. &#x20;

Your randomization (or other identification strategy) should reflect how the product is delivered.

* If access is controlled (e.g., via onboarding or closed rollout), individual or cluster assignment to treatment may be appropriate.
* If the product is public or spreads organically, consider a randomized encouragement design that invites or incentivizes only some users. Because these are often underpowered to detect final outcomes, pilot the encouragement to ensure it works.

When contamination risk is high, it may be best to run trials in settings with low existing exposure (e.g., regions or populations where the product is not yet known) and to closely monitor control groups for access to the product or close substitutes. But GenAI access is increasingly widespread, and embracing this situation rather than avoiding it may be the most constructive approach. First, consider the likely magnitude of spillovers. If it may be substantial enough to lead to a bias, then it is best to build into the design some measurement of the spillover. Analysing the impact of the spillover on the treatment can then enhance the learning, and even often point to paths to scale and maximize impact.

Cluster randomization (e.g., by school or clinic) can further reduce spillovers. In all cases, monitor usage and be prepared to adjust power calculations or analytic strategies if cross-group exposure occurs.

<br>
{% endstep %}
{% endstepper %}





[^1]: For a rigorous treatment of this, see [VanderWeele and Hernán (2013)](https://pmc.ncbi.nlm.nih.gov/articles/PMC4219328/)

[^2]: See [https://www.gsb.stanford.edu/sites/default/files/publication/pdfs/academic-publication-desiging-adaptive-experiments-2021-mar.pdf](https://www.gsb.stanford.edu/sites/default/files/publication/pdfs/academic-publication-desiging-adaptive-experiments-2021-mar.pdf) for a good introduction to adaptive experiments.

{% embed url="https://tally.so/r/A788l0?originPage=level-4-impact-evaluation%2Fhow-is-level-4-evaluation-performed%2Fkey-design-considerations-for-ai-specific-impact-evaluations" %}
{% endembed %}
