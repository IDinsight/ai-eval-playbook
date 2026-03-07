---
description: Do users with access to the product improve development outcomes?
icon: chart-column
---

# Level 4 – Impact evaluation

## Why is this level of evaluation important?

Interventions in the development sector aim to improve the quality of people’s lives. Impact evaluations (IEs) measure the effects of the intervention on outcomes such as mortality, learning outcomes, and earnings. The main issue these evaluations face is that the world is a messy place: as an intervention is being implemented, many other things are happening that would make a simple before-and-after comparison a bad way to judge program effectiveness.

To address this, we use a counterfactual: a sample as similar as possible to the group that received the intervention. It represents what would have happened without the program. Comparing the two allows us to isolate the intervention’s impact.

There are a number of ways to construct the counterfactual. The most straightforward approach is usually a randomized controlled trial (RCT). In an RCT, participants are randomly assigned to one or more treatment groups that receive an intervention (or variants of it) and a comparison group that does not. Researchers then measure outcomes across groups. Randomized evaluations enable credible, unbiased estimates of causal impact—that is, which changes in participants’ lives can be attributed to the program. Other techniques for the counterfactual construction include propensity score matching, difference in differences, and regression discontinuity designs. These are discussed further below.

## What is the “intervention” being evaluated?

The central reason to do an impact evaluation is to inform policymakers, donors and implementers on whether and how to incorporate an intervention in their plans.

By isolating the intervention from other influences, impact evaluation enables causal attribution of outcome changes. Once effectiveness is established for a specific setting and population, additional evaluations can test whether it works elsewhere or for other groups. Moreover, since impact evaluations isolate causal effects, they are ideal for measuring unintended (as well as intended) impacts of an intervention.[\[4\]](https://docs.google.com/document/d/18du_LUMPGGu4pZQ1nZ-pKoEwu2zlzmQhFLYwX-A-ix0/export?format=html#ftnt4)

For many funders and public sector partners, IEs are central to decision-making. They seek credible evidence that a product improves lives—beyond engagement metrics or self-reports—before scaling. A well-designed IE signals real-world effectiveness and the likelihood of meaningful social returns (see e.g. [Hauser et al., 2025](https://www.google.com/url?q=https://www.nature.com/articles/d41586-025-02266-7.epdf?sharing_token%3DjCKO3Tx8dFeQfucqP5VCcNRgN0jAjWel9jnR3ZoTv0PS1htX8Sko7IudKf1MVjrKQ-g3NeuYAsnuJ-Io9wHN3uMBrjSLLnu_wjpJLF2G-unWgOw27UqLqC_yalnt2AFTYmMZAO31agMcWvNwKRpfYsfrMt3fmIKm0iVbftxqAsY%253D\&sa=D\&source=editors\&ust=1770879887145842\&usg=AOvVaw1Rj4U3SfnruUmN8P6ynHcC); [UK GOV, 2025](https://www.google.com/url?q=https://www.gov.uk/government/publications/the-magenta-book/guidance-on-the-impact-evaluation-of-ai-interventions-html\&sa=D\&source=editors\&ust=1770879887146044\&usg=AOvVaw1ZZzYKbX_TLn4ShgD2f3Xu)).

IEs also help funders compare options. Combined with cost data, they enable cost-effectiveness and cost-benefit analysis—critical when governments, donors, and multilaterals allocate scarce resources. In many cases, IE results directly inform decisions to scale, replicate, or exit.

### When is it appropriate to do an IE?

IEs are high-investment undertakings, both financially and operationally, although strategies exist to address both financial and operational constraints. They are most useful when your product is mature enough to test and when the decision stakes are high enough to justify the effort. In general, consider an IE when:

* [x] **Levels 1–3 are strong**: The model performs well, users engage meaningfully, and early evidence suggests improvements in knowledge, attitudes, or behavior.
* [x] **You are preparing to scale**: Funders or policymakers are considering wider adoption, but want evidence, including cost-effectiveness or cost-benefit estimates, to support the decision.
* [x] **You have bandwidth**: Implementing an IE is a lot of work for both the research team and implementer; doing it well takes time and effort.
* [x] **You are confident your product works**: You should run an IE once earlier-stage evaluations give you confident priors that you will likely observe effects on development outcomes.

You do not need to run an IE if your product is still in early design or usage is too inconsistent to expect impacts. In such cases, Level 3 evaluations—focused on user cognition and behavior—are more appropriate. Once you have confidence that the theory of change is working, you can revisit an impact evaluation.

### Plan for evaluability early

Although IEs are usually run later, a credible and cost-effective evaluation requires early design choices. Building in features like holdout groups, staged rollouts, or embedded randomization from the start (also useful for A/B testing) preserves the ability to estimate causal effects without disruptive redesigns. Even if a full IE is premature, these choices create opportunities for credible inference later and reduce evaluation burden. Funders assessing scale readiness should look for signs of early evaluability.

### How to do an IE responsibly

Rigorous IEs require expertise. We recommend working with an independent evaluator—such as an academic partner, a research or research-and-policy organization (e.g., J-PAL, IPA), or a third-party M\&E firm—to strengthen technical quality and perceived independence. Being clear on your evaluation goals (as discussed above) will help you choose among evaluator options.

At a minimum, we suggest:

* [x] **Clarifying roles**: who builds the product, who runs the study, who communicates findings
* [x] **Pre-registering the design**: on platforms such as the AEA RCT Registry, EGAP, or RIDIE
* [x] **Sharing results transparently**: Disclose all findings, including null or negative results, and make methods and materials publicly available where feasible to support reproducibility and sector-wide learning.

## How is Level 4 evaluation performed?

### A quick primer on impact evaluation methods

Once it is the right time and resources are in place, you must choose a method. At its core, an impact evaluation compares outcomes between groups that differ only in exposure to the intervention—that is, treatment versus control. There are several ways to achieve or approximate this:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><strong>Randomized Control Trials (RCTs)</strong></td><td>RCTs assign a sufficiently large number of units (e.g., individuals, schools, clinics) at random to receive the intervention, while others are excluded (often via a waitlist). Randomization ensures groups are comparable on average, except for the intervention. Sometimes, politics, ethics, or other constraints will make it less feasible to randomize, so we can turn to other methods.</td></tr><tr><td><strong>Propensity score matching</strong></td><td>This approach requires a large dataset covering both participants and non-participants, with a clear indicator of treatment. It uses statistical techniques to match treated units with similar untreated ones based on observable characteristics. Because it relies only on what is observed, robustness declines when unobservable differences are likely to matter.</td></tr><tr><td><strong>Difference-in-differences</strong></td><td>This method relies on the assumption that treated and untreated groups would have followed parallel trends in outcomes. By comparing differences before and after the intervention, impact can be estimated. It is often combined with other approaches.</td></tr><tr><td><strong>Regression discontinuity design</strong></td><td>This approach uses a cutoff, comparing people (or other treatment units) just below it to those just above. For example, if students below a threshold receive remedial education, impact is estimated by comparing students near the cutoff on either side. Valid implementation requires that the cutoff itself does not directly affect outcomes (e.g., it reflects budget constraints, not pedagogy) and that there are many observations close to the threshold, since differences grow farther from it.</td></tr></tbody></table>

These are very basic introductions. For more on methods as well as a step-by-step guide to impact evaluation planning – including sampling, power calculations, and analysis – we strongly recommend:

* [Impact Evaluation in Practice](https://www.google.com/url?q=https://openknowledge.worldbank.org/server/api/core/bitstreams/4659ef23-61ff-5df7-9b4e-89fda12b074d/content\&sa=D\&source=editors\&ust=1770879887154899\&usg=AOvVaw15KrFzlG5c0hSTPnR6P_BB) (Gertler et al., World Bank)
* [Running Randomized Evaluations](https://www.google.com/url?q=https://www.amazon.co.uk/Running-Randomized-Evaluations-Practical-Guide/dp/0691159270\&sa=D\&source=editors\&ust=1770879887155250\&usg=AOvVaw1Guc4APOHO6NPhp2c7QjYs) (Glennerster & Takavarasha)

In the following section, we do not replicate that guidance. Instead, we focus on what is distinctive when evaluating AI-based products in the development sector.

### Key design considerations for AI-specific impact evaluations

With the increased evaluations of AI products, distinct challenges for impact evaluation are emerging. Below are some considerations that merit special attention.

#### 1. Selecting the right counterfactual

Choosing the counterfactual—what participants would receive without the AI-enabled intervention—is foundational to impact evaluation design. In GenAI evaluations, the range of plausible comparators is often larger, making clear justification essential.[\[5\]](https://docs.google.com/document/d/18du_LUMPGGu4pZQ1nZ-pKoEwu2zlzmQhFLYwX-A-ix0/export?format=html#ftnt5) The counterfactual should represent a meaningful alternative to your product and credibly reflect what the world would look like without it at scale.

There is no single “correct” counterfactual. In some cases, a pure control (no intervention at all) may be appropriate (more on this in the next point). In others, a more active comparator offers greater policy relevance. Common options include:

* Business-as-usual (e.g., no digital support or sporadic human guidance), especially when evaluating incremental improvement in an existing service delivery model.
* Non-AI digital tools (e.g., static chatbots or curated content), when considering whether generative AI adds value over existing tech products.
* Human-delivered services, when the AI tool substitutes for scarce professional labor (e.g., teachers, health workers). In such cases, it will be valuable to measure not only outcomes but also the cost of implementation (for resources on how to measure costs well see [here](https://www.google.com/url?q=https://www.worldbank.org/en/programs/sief-trust-fund/brief/cost-measurement\&sa=D\&source=editors\&ust=1770879887158330\&usg=AOvVaw2G9VDIBWqLt6EJqeUwIjO6)).

Thoughtful counterfactual choice affects not only estimated effect size, but also the interpretability and generalizability of results. A strong evaluation will explain both why a given comparator was selected and what alternative scenarios it helps illuminate.

#### 2. Measuring latent access and contextual factors

The marginal impact of an AI product depends on users’ baseline access to support, including existing AI tools, related technologies, informal use of the product, and competitors. Measuring this baseline is essential for interpreting effects. Where such tools are already widespread, gains may be modest; in low-capacity settings, the same product may yield much larger (or smaller) benefits. Because access can change quickly, it should be tracked throughout the evaluation.

Evaluators should:

1. Measure existing technology use, including frequency, type, and purpose of AI or other digital tool usage, whether directly or indirectly.
2. Measure what users rely on today, such as informal networks, human advisors, basic technology, or no support at all.
3. Keep a sharp eye out for leakage – since the AI-enabled intervention is likely to be easily portable or shareable, it is important to measure how much of the control group has access to the intervention in some form (more on this below).

Substitutes that users turn to when they don’t use, or have access to your AI product can shape

These fallback options and access patterns shape the AI product’s incremental value. This makes understanding your target population—and which segments face different access, resources, or barriers—essential. Anticipate these dynamics and measure impacts across key dimensions of heterogeneity (e.g., age, gender, poverty, or their interactions), ensuring sufficient sample size to do so.

#### 3. Managing product dynamism

RCTs enable powerful causal inference, but only under specific assumptions. One of the most important is the Stable Unit Treatment Value Assumption (SUTVA). [A key component of SUTVA is the no-multiple-versions condition: all treated units must receive the same version of the intervention.](#user-content-fn-1)[^1]

In practice, this condition is often only imperfectly met (e.g., motivated providers continuously adapt their services). For AI and other digital products, it is almost systematically violated: these tools are designed to improve iteratively through retraining, interface changes, or content updates, often alongside ongoing experimentation. As a result, participants within the same trial may face different product versions. This can bias estimates if version exposure correlates with unobserved potential outcomes and, even when identification holds, complicate the interpretation of the causal estimand.

Freezing the product version during a trial would restore the single-version condition but undermine ecological validity by eliminating the adaptation that defines product interventions. A better approach is to design evaluations that permit evolution while still delivering credible, interpretable causal estimates.

We recommend four practices:

1. **Tag your versions** – Define in advance what counts as a substantively distinct change, including updates to underlying models outside implementers’ control. Tag each release with a unique version label. Calibrate granularity: definitions that are too fine reduce power, while definitions that are too coarse can hide meaningful heterogeneity.
2. **If A/B testing, randomise test participation** – Do not only randomize between versions A and B; also randomize which users enter the A/B test. Pre-specify the procedure so participation is not correlated with unobserved outcomes. Both this and version tagging require close coordination between the evaluation and tech teams.
3. **Maintain a hold-out group on the baseline version** – If sample size allows, keep a subset of treated participants on a frozen baseline version throughout the trial. Comparing them to users on updated versions allows estimation of the incremental effect of product changes. In a more dynamic variation on this, [adaptive experiments](#user-content-fn-2)[^2] could be a useful approach.
4. **Pre-specify at a high level** – In the pre-analysis plan, specify how versions are defined, how rollouts occur, and how exposure is measured. Avoid overly detailed commitments that limit flexibility in responding to unforeseen product changes.

#### 4. Measuring true development outcomes

AI tools often simulate expertise. But does the user learn, or just copy?

* Invest in using industry-standard validated assessments and administrative data to credibly measure improvements in capabilities and welfare.
* Avoid measurement tools that can be gamed by simply repeating AI output (e.g., regurgitating chatbot answers). In educational contexts, for example, use measures where performance tests students’ ability when they don’t have access to AI.

#### 5. Managing spillovers and contamination

AI tools are often built to scale—easy to access and share—which makes contamination a real risk in impact evaluations. Your randomization (or other identification strategy) should reflect how the product is delivered.

* If access is controlled (e.g., via onboarding or closed rollout), individual or cluster assignment to treatment may be appropriate.
* If the product is public or spreads organically, consider a randomized encouragement design that invites or incentivizes only some users. Because these are often underpowered, pilot the encouragement to ensure it works.

When contamination risk is high, it may be best to run trials in settings with low existing exposure (e.g., regions or populations where the product is not yet known) and to closely monitor control groups for access to the product or close substitutes.

Cluster randomisation (e.g., by school or clinic) can further reduce spillovers. In all cases, monitor usage and be prepared to adjust power calculations or analytic strategies if cross-group exposure occurs.

### Common pitfalls to avoid

Impact evaluations are high-leverage, high-effort undertakings. Avoiding a few predictable errors can significantly improve the value – and credibility – of your results. While these issues face many non-AI impact evaluations, here we have tried to capture the ways these risks are manifesting differently in early impact evaluations of AI products.

#### Being underpowered

Even real impacts can go undetected in underpowered studies. For AI products, low uptake—especially early on—is a key risk. Overly optimistic uptake assumptions can leave treatment groups too small to detect effects. Set realistic expectations by piloting uptake with groups similar to the intended treatment population, involve skeptics in planning, and use recent Level 2 evaluations to inform assumptions.

As discussed earlier, you track your target population and key sub-groups across all four evaluation stages. At Level 4, it is critical to have sufficient sample size to detect statistically significant, programmatically meaningful effects, including differences across groups. This challenge is not AI-specific but applies to any sub-group analysis; however, AI interventions may see groups participate in different ways and at different rates. Insights from Levels 1–3 should inform Level 4 sample design and outcome measurement. If budget allows, keep samples and outcomes broad enough to detect unintended positive or negative effects not flagged earlier.

#### Mismanaging transparency

Impact evaluations should build confidence by involving credible, independent investigators, sharing data where appropriate, and pre-specifying key measures and analyses. But transparency should not come at the expense of adaptability. Allow for reasonable adjustments as implementation evolves, and work with evaluators to balance rigor and responsiveness. Given how quickly AI interventions change, establish mechanisms for early and ongoing coordination during implementation.

#### Letting product evolution obscure the analysis

If the product may change during the study, pre-specify how changes will be handled analytically. One option is to freeze a version for the trial; if that is not feasible, define and log substantive changes, tag version exposure, and use this metadata to test for improvements or degradations over time. While this creates risk, it is also an opportunity for GenAI evaluations. Unlike analog interventions—where changes often went unobserved—version tracking, and even repeating Levels 1–3 evaluations after major updates, can enable much richer analysis during the impact evaluation period.

#### Underestimating the risks of attrition

Attrition—through disengagement or loss to follow-up—can seriously weaken power and interpretability. In digital interventions, only a small share of sign-ups may engage, and drop-off is easy. Plan for this: track engagement early, power studies accordingly, and use passive data where possible. If attrition is unavoidable, pre-specify how it will be handled and report it transparently. Use Level 2 and 3 data to monitor attrition early, adjust design, and link it to version tracking to understand who drops out and when.

## What is the Minimum Viable Evaluation?

{% include "../.gitbook/includes/level-4-mve.md" %}

## Who is most involved in this level of evaluation?

{% include "../.gitbook/includes/level-4-roles.md" %}

[^1]: For a rigorous treatment of this, see [VanderWeele and Hernán (2013)](https://pmc.ncbi.nlm.nih.gov/articles/PMC4219328/)

[^2]: See [https://www.gsb.stanford.edu/sites/default/files/publication/pdfs/academic-publication-desiging-adaptive-experiments-2021-mar.pdf](https://www.gsb.stanford.edu/sites/default/files/publication/pdfs/academic-publication-desiging-adaptive-experiments-2021-mar.pdf) for a good introduction to adaptive experiments
