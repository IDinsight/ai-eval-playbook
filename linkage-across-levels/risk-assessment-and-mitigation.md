---
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/pbloAUUbQhacfW14WRJm/linkages-across-levels/risk-assessment-and-mitigation
---

# Risk assessment and mitigation

The discovery of risks or potential failure modes - and developing and testing control measures - requires integrated work across evaluation levels. Use outcomes at one level to guide control levers or solution updates that influence others. Risk mitigation should support comprehensive, iterative detection and response, with the associated cost and intensity varying by level.

### Example scenario: WhatsApp tutor chatbot

As an example, suppose we identify edtech failure modes after observing aberrant behavior at one level. The solution is a WhatsApp tutoring bot for secondary students, providing math and logic problems to solve independently at home, linked to their school curriculum. How might risks show up at each level, what mitigations would we use, and which control metrics would measure mitigation effectiveness?

### Cross-level risk mitigation

<table data-header-hidden="false" data-header-sticky data-first-column-sticky><thead><tr><th width="119.88671875" valign="top">Level</th><th valign="top">Risk Discovered</th><th valign="top">Control Strategies</th><th valign="top">Control Metric</th></tr></thead><tbody><tr><td valign="top"><i class="fa-gear-code">:gear-code:</i> <strong>Level 1</strong></td><td valign="top">The problem complexity does not increase with each turn of the WhatsApp dialogue</td><td valign="top">Link weekly assessed learning level to problem difficulty; increase the model context window;<br>use multi-shot prompting</td><td valign="top">Question complexity (LLM-as-a-judge using a rubric aligned to curriculum standards)</td></tr><tr><td valign="top"><i class="fa-box-isometric">:box-isometric:</i> <strong>Level 2</strong></td><td valign="top">High engagement, but concentrated on easy problems or off-topic conversations</td><td valign="top">Default to progressive difficulty;<br>add rewards for completing challenging problems</td><td valign="top">“Time spent learning” = session length ÷ # unique problem types solved</td></tr><tr><td valign="top"><i class="fa-user">:user:</i> <strong>Level 3</strong></td><td valign="top">Users become overly dependent on the AI, reducing self-directed problem solving and help-seeking agency</td><td valign="top">Introduce delayed hints and scaffolded responses; require users to attempt a solution before seeing AI guidance; prompts that encourage reflection (“What would you try next?”)</td><td valign="top">% of problems attempted before requesting help; average number of user-initiated solution steps per problem; self-efficacy score from survey</td></tr><tr><td valign="top"><i class="fa-chart-column">:chart-column:</i> <strong>Level 4</strong></td><td valign="top">Learning plateaus or declines</td><td valign="top">—</td><td valign="top"># correct on standardized test; % of students exceeding threshold score</td></tr></tbody></table>

As in red teaming, you can define different risk classes to investigate (e.g., safety, privacy, security). User safety and mental health are critical concerns, and can be mitigated through activities at each level:

<table data-header-hidden="false" data-header-sticky><thead><tr><th width="120.4453125" valign="top">Level</th><th width="268.84765625" valign="top">Approach</th><th valign="top">Mitigation</th></tr></thead><tbody><tr><td valign="top"><i class="fa-gear-code">:gear-code:</i> <strong>Level 1</strong></td><td valign="top">Red-team GenAI models</td><td valign="top">Detect/classify harmful outputs;<br>align models via pre-/post-processing</td></tr><tr><td valign="top"><i class="fa-gear-code">:gear-code:</i> <strong>Level 1</strong></td><td valign="top">Inspect model logs</td><td valign="top">Update knowledge base;<br>apply pre-/post-processing (e.g., content filters)</td></tr><tr><td valign="top"><i class="fa-box-isometric">:box-isometric:</i> <strong>Level 2</strong></td><td valign="top">Observe product use</td><td valign="top">Adjust UI/UX to reduce friction or harm</td></tr><tr><td valign="top"><i class="fa-box-isometric">:box-isometric:</i> <strong>Level 2</strong></td><td valign="top">Analyze trace data</td><td valign="top">Add nudges/notifications;<br>build affordances for different user segments</td></tr><tr><td valign="top"><i class="fa-user">:user:</i> <strong>Level 3</strong></td><td valign="top">Collect qualitative data (interviews, focus groups)</td><td valign="top">Surface risks, cultural fit, and harms;<br>invite community input on mitigations</td></tr><tr><td valign="top"><i class="fa-user">:user:</i> <strong>Level 3</strong></td><td valign="top">Identify and analyze metrics that embed in conversation text</td><td valign="top">Trigger risk-reduction interventions and referrals</td></tr><tr><td valign="top"><i class="fa-chart-column">:chart-column:</i> <strong>Level 4</strong></td><td valign="top">Run impact evaluations</td><td valign="top">Qualitative research to explore unintended consequences</td></tr></tbody></table>

As you mitigate risk, weigh the financial and moral costs of failures across evaluation levels. A Level 1 error may be minor (extra developer time), while a Level 3 failure (e.g., loss of user trust) may require intensive in-person outreach and far higher cost. Use a routine workflow: start with risk discovery (aberrant metrics, one-off surveys, user interviews), then translate findings into new routine metrics. Three questions guide the investigation:

> Why is the behavior occurring?

> How could it have been discovered earlier?

> What can be changed to align with the theory of change?

{% hint style="warning" icon="circle-info" %}
If product development reveals an incompatible insight, then you may need to **modify the theory of change** for it to maintain its guiding function.
{% endhint %}

{% hint style="success" icon="star" %}
**Note:** **This playbook can be used directly with AI tools like Claude, ChatGPT, and NotebookLM.** \
[_**Explore how**_**&#x20;>**](https://app.gitbook.com/s/Ec5nQAw37GGYw1m7rYdO/additional-resources/using-the-playbook-with-ai-tools)
{% endhint %}

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=linkages-across-levels%2Frisk-assessment-and-mitigation" %}

</details>
