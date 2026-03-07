# Linkages Across Levels

We have identified several ways to link the four levels as you develop and evaluate an AI solution. These cross-level linkages are essential for tracing how changes in your model system, product, solution, and/or program affect outcomes—whether intentional or not. Key practices include:

* Developing Level 1-4 metrics at each stage of the user funnel;
* Defining a single set of identifiers that links data collected at each level (e.g. the user ID, session, and model/product version)
* Product managers, data scientists, and user researchers cooperating across levels to ensure continuity and context while iterating the product.

Here are a few other actions you can take to link your evaluations across levels:

1. **Use critical metrics from one evaluation level as guardrails for others** (or other funnel stages) so engagement optimizations don’t undermine “North Star” outcomes. For example, optimizing a bot for low latency (L1) while targeting student learning (L4) creates trade-offs: added latency may improve chain-of-thought correctness but reduce engagement and learning. Do not track L1 without L4 guardrails; North Star metrics propagate trade-offs across L1–L4, requiring deliberate weighting and interpretation.

{% hint style="info" %}
A more sophisticated—but less mature—option is multi-objective optimization, which optimizes an AI solution across multiple goals at once (e.g., cost, latency, safety). These [techniques](https://www.google.com/url?q=https://arxiv.org/pdf/2502.18635\&sa=D\&source=editors\&ust=1770879887178919\&usg=AOvVaw0flt_RuIhAWI7Tl4aogVuN) are still new and under development.
{% endhint %}

2. **Identify a product manager to “own” the North Star metric.** They are responsible for shaping the roadmap by balancing engineering and design trade-offs across all levels. This person ensures design choices—such as adding UI friction for specialized users—stay aligned with the overall goal, even if they look sub-optimal in one level’s metrics in isolation.
3. **Conduct routine multi-level risk assessments and failure-mode analyses.** Risk is discussed further down. When conducting error analysis, flag aberrant behavior at any level—for example, benchmark drift (Level 1) or user gaming (Level 3)—then assess whether it is detectable in the data produced at that level or other levels. Combine these insights with user research to predict fixes: issues appearing in Level 1 metrics near the top of the funnel often require IA system changes (e.g., knowledge base updates, prompt engineering), while downstream failures may require new product features or broader solution/intervention changes.

User research should sit alongside each evaluation level to interpret log data. Its depth varies by level: interviews to design golden datasets (L1), workflow observation to develop hypotheses (L2), and cognitive interviewing to inform survey design (L3–L4).

## Risk assessment and mitigation

The discovery of risks or potential failure modes - and developing and testing control measures - requires integrated work across evaluation levels. Use outcomes at one level to guide control levers or solution updates that influence others. Risk mitigation should support comprehensive, iterative detection and response, with the associated cost and intensity varying by level.

### Example scenario: WhatsApp tutor chatbot

As an example, suppose we identify edtech failure modes after observing aberrant behavior at one level. The solution is a WhatsApp tutoring bot for secondary students, providing math and logic problems to solve independently at home, linked to their school curriculum. How might risks show up at each level, what mitigations would we use, and which control metrics would measure mitigation effectiveness?

### Cross-level risk mitigation

<table data-full-width="true"><thead><tr><th width="119.88671875">Level</th><th>Risk Discovered</th><th>Control Strategies</th><th>Control Metric</th></tr></thead><tbody><tr><td><i class="fa-gear-code">:gear-code:</i> <strong>Level 1</strong></td><td>The problem complexity does not increase with each turn of the WhatsApp dialogue</td><td>Link weekly assessed learning level to problem difficulty; increase the model context window;<br>use multi-shot prompting</td><td>Question complexity (LLM-as-a-judge using a rubric aligned to curriculum standards)</td></tr><tr><td><i class="fa-box-isometric">:box-isometric:</i> <strong>Level 2</strong></td><td>High engagement, but concentrated on easy problems or off-topic conversations</td><td>Default to progressive difficulty;<br>add rewards for completing challenging problems</td><td>“Time spent learning” = session length ÷ # unique problem types solved</td></tr><tr><td><i class="fa-user">:user:</i> <strong>Level 3</strong></td><td>Users become overly dependent on the AI, reducing self-directed problem solving and help-seeking agency</td><td>Introduce delayed hints and scaffolded responses; require users to attempt a solution before seeing AI guidance; prompts that encourage reflection (“What would you try next?”)</td><td>% of problems attempted before requesting help; average number of user-initiated solution steps per problem; self-efficacy score from survey</td></tr><tr><td><i class="fa-chart-column">:chart-column:</i> <strong>Level 4</strong></td><td>Learning plateaus or declines</td><td>—</td><td># correct on standardized test; % of students exceeding threshold score</td></tr></tbody></table>

You can define different risk classes to investigate (e.g., safety, privacy, security). User safety and mental health are critical concerns, and can be mitigated through activities at each level:

<table data-full-width="true"><thead><tr><th width="120.4453125">Level</th><th>Approach</th><th>Mitigation</th></tr></thead><tbody><tr><td><i class="fa-gear-code">:gear-code:</i> <strong>Level 1</strong></td><td>Red-team GenAI models</td><td>Detect/classify harmful outputs;<br>align models via pre-/post-processing</td></tr><tr><td><i class="fa-gear-code">:gear-code:</i> <strong>Level 1</strong></td><td>Inspect model logs</td><td>Update knowledge base;<br>apply pre-/post-processing (e.g., content filters)</td></tr><tr><td><i class="fa-box-isometric">:box-isometric:</i> <strong>Level 2</strong></td><td>Observe product use</td><td>Adjust UI/UX to reduce friction or harm</td></tr><tr><td><i class="fa-box-isometric">:box-isometric:</i> <strong>Level 2</strong></td><td>Analyze trace data</td><td>Add nudges/notifications;<br>build affordances for different user segments</td></tr><tr><td><i class="fa-user">:user:</i> <strong>Level 3</strong></td><td>Collect qualitative data (interviews, focus groups)</td><td>Surface risks, cultural fit, and harms;<br>invite community input on mitigations</td></tr><tr><td><i class="fa-user">:user:</i> <strong>Level 3</strong></td><td>Identify and analyze metrics that embed in conversation text</td><td>Trigger risk-reduction interventions;<br>provide referrals reduction interventions, referrals</td></tr><tr><td><i class="fa-chart-column">:chart-column:</i> <strong>Level 4</strong></td><td>Run impact evaluations</td><td>Qualitative research to explore unintended consequences</td></tr></tbody></table>

As you mitigate risk, weigh the financial and moral costs of failures across evaluation levels. A Level 1 error may be minor (extra developer time), while a Level 3 failure (e.g., loss of user trust) may require intensive in-person outreach and far higher cost. Use a routine workflow: start with risk discovery (aberrant metrics, one-off surveys, user interviews), then translate findings into new routine metrics. Three questions guide the investigation:

> Why is the behavior occurring?

> How could it have been discovered earlier?

> What can be changed to align with the theory of change?

If product development reveals an incompatible insight, then you may need to modify the theory of change for it to maintain its guiding function.
