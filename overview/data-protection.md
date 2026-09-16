# Data protection

### Data protection

<details>

<summary><strong>Why data protection is important in GenAI</strong></summary>

Generative AI applications with potential for development impact typically deal with sensitive topics. Livelihoods, vulnerabilities, health-related questions, children's data in education and beyond: the list is long and substantial. Where users reveal details of their situation in these fields, registration data and chat logs record and process sensitive personal data. As responsible stewards, the providers of GenAI systems need to safeguard and protect that data carefully. But instead of being a burden, responsible data handling is an opportunity to build the trust necessary for open and honest user evaluation.

</details>

<details>

<summary><strong>Requirements depend on local context</strong></summary>

Compliance with local legal requirements is the foundation for processing personal information. These requirements differ substantially and it is thus impossible to list needs that are relevant in any setting. Instead, this section gives a brief overview of basic considerations for professional practice in handling sensitive data. It is neither legal advice nor a complete listing of advisable practices, but simply a starting point for assessing what responsible data protection means in a particular context. Since human subjects research is integral to evaluating generative AI applications, the need to involve institutional review boards and similar bodies should also be considered where appropriate.

</details>

<details>

<summary><strong>Minimum Data Protection Practices</strong></summary>

In addition to locally relevant data protection requirements – which often include standard principles such as data minimization, purpose and storage limitations – foundational steps towards responsible and trustworthy handling of sensitive personal information should include:

<table data-header-hidden="false" data-header-sticky><thead><tr><th width="223" valign="top">Practice</th><th>Description</th></tr></thead><tbody><tr><td valign="top"><strong>Data protection impact assessment (DPIA)</strong></td><td>A structured review of privacy risks should be conducted before deployment, and also whenever the system changes substantially. A DPIA includes documentation of data flows, the legal basis or other authorization for processing, potential harms such as re-identification or model memorisation, and the controls that mitigate them.</td></tr><tr><td valign="top"><strong>User rights</strong></td><td>Where required by regulations and perhaps also as a matter of transparent and fair practice, users should have access to the data held on them, the right to correct mistakes, and the option of ending their participation in consent-based activities (including data deletion). User-friendly processes that implement these rights need to be integrated into system design.</td></tr><tr><td valign="top"><strong>ICT security standards</strong></td><td>Although safe practices are discussed at various points of the Playbook, a general security posture that secures data and systems against internal and external threats is an essential part of data protection. Established frameworks such as the ISO 27k family or the NIST Cybersecurity Framework set out the core requirements.</td></tr><tr><td valign="top"><strong>Legal advice</strong></td><td>Jurisdiction-specific legal counsel should be sought before data collection even begins. The requirements vary strongly across regimes and cross-border transfers to upstream LLM providers introduce a second layer of complexity. The fast evolution of data protection and AI regulation suggests that compliance may need to be treated as ongoing rather than one-off.</td></tr></tbody></table>

</details>

<details>

<summary><strong>Consent is not a tick-box exercise</strong></summary>

A cautionary note is due for situations where consent to personal data processing – including items such as chat logs and registration information – is taken to be the legal basis. Development-focused AI applications often aim to support people in considerable need who may not have the ability to withhold or withdraw consent, or who may not be in a position to assess the processing fully. The economically vulnerable, illiterate, children, or older adults can be examples of such groups. In such situations, the AI provider should recognise that it is their duty to mitigate risks and take protective measures, foregoing performative consent in favour of user-centric intervention design.

</details>

<details>

<summary><strong>Cross-border transfer and third-party access</strong></summary>

The concentration of GenAI model providers and processing infrastructure in a few countries often implies the transfer of sensitive data across borders. Apart from verifying that this is permissible under local regulations, it also entails a duty to verify that the data will be processed in a compliant manner abroad. A similar need arises where third parties access, store and process personal data. Providers of GenAI systems must verify that they will uphold the same or higher custodial standards than the own organisation. Although verification may be burdensome, sensitive user data is as worthy of protection abroad and by others than by the direct system provider.

</details>

<details>

<summary><strong>Selected data protection considerations by evaluation level</strong></summary>

Data protection considerations reveal themselves in different ways across the Playbook's evaluation levels, including but not limited to:

<table data-header-hidden="false" data-header-sticky><thead><tr><th width="235" valign="top">Evaluation level</th><th>Key considerations</th></tr></thead><tbody><tr><td valign="top"><p><strong>Level 1 –</strong> </p><p><strong>Model (System) Evaluation</strong></p></td><td>Training data may itself be sensitive and require filtering or scrubbing to avoid leakage risks. Bias audits reliant on access to protected characteristics such as ethnic background pose additional governance challenges.</td></tr><tr><td valign="top"><p><strong>Level 2 –</strong> </p><p><strong>Product evaluation</strong></p></td><td>Usage tracking data can be sensitive, and the same is true for session-level analytics and potential metadata, such as location.</td></tr><tr><td valign="top"><p><strong>Level 3 –</strong> </p><p><strong>User evaluation</strong></p></td><td>Chat logs reveal thoughts, misconceptions, personal circumstances, representing the most sensitive interaction data. PII scrubbers for LLM inputs/outputs can partly mitigate resulting risks, but not eliminate them. Responsible data practices enable product optimisation as they can support the trust that is required to evaluate some L3 aspects adequately and accurately.</td></tr><tr><td valign="top"><p><strong>Level 4 –</strong> </p><p><strong>Impact evaluation</strong></p></td><td>Administrative data linkages, such as health records, exam scores, and social registries, represent data risks, including re-identification risk for de-identified or pseudonymized data. Primary data collection for evaluation may be held separately, but needs to be treated as carefully.</td></tr></tbody></table>

</details>

{% hint style="success" icon="star" %}
**Note:** **This playbook can be used directly with AI tools like Claude, ChatGPT, and NotebookLM.** \
[_**Explore how**_**&#x20;>**](https://app.gitbook.com/s/Ec5nQAw37GGYw1m7rYdO/additional-resources/using-the-playbook-with-ai-tools)
{% endhint %}

***

<details>

<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-1-model-evaluation%2Fhow-is-level-1-evaluation-performed" %}

</details>
