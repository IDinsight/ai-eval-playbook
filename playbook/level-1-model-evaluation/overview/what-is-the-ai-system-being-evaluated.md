# What is the “AI system” being evaluated?

In this playbook, we will distinguish between two different concepts:

**Foundation Model (The "Nucleus")**: This is a large-scale model, trained on vast datasets, used as part of an overall system. Examples: GPT-5, Claude Opus 4.5, Gemini 3

**End-to-End AI System (The "Cell")**: This is the entire AI workflow or system that you build. It incorporates one or more foundation models, plus all the other components that make the pipeline work for a user. Just as a cell contains a nucleus, mitochondria (for energy) and a cell wall, your full pipeline will include multiple components, like:

* Knowledge bases containing specific information for retrieval
* Instructions for the AI model (“system prompt”) and safety guardrails, like content filters
* Language translation, speech-to-text/text-to-speech transformations, and other processing steps
* Tools that let the model take actions like sending an email or performing web search

When we say “AI system”, we generally are referring to the End-to-End AI System described above. To avoid confusion, we will always use the term foundation model when referring to the “nucleus” and use “AI system” or “AI pipeline” when referring to the “cell”.

![Figure 6: Defining the AI System](<../../.gitbook/assets/unknown (2).png>)

To simplify the evaluation of an AI system, we define three distinct components:

1. **Pre-processing**: Before a user input hits the foundation model, it is transformed into a suitable format. Common steps include:
   * Sanitization: Rejecting unsafe or irrelevant inputs
   * Conversion: Turning speech into text (e.g. using an automatic speech recognition model)
   * Refinement: Paraphrasing the request (e.g. converting a vague message to more specific based on the conversation history) or translating it from a low-resource language to a high-resource one (since LLMs perform better in high-resource languages)
2. **LLM Context Preparation**: Beyond the user’s pre-processed request, a foundation model requires the following additional components to function:
   * The “system prompt”: These instructions guide the foundation model’s behavior.
   * External Tools: These augment the foundation model by letting it take actions (e.g. web search)
   * Context: Relevant background, such as conversation history, data retrieved from a knowledge base, or responses received from calling tools (e.g. web search results).
3. **Post-processing**: Before the output reaches the user, it undergoes final checks and transformations. Common steps include:
   * Quality Control: Checking for hallucinations (e.g. by ensuring the response is always grounded in the knowledge base) and verifying safety guardrails as defined by you
   * Formatting: Converting text to speech or translating the answer back into the user’s preferred language.

Level 1 evaluations should cover this entire pipeline. They assess your complete AI system, from the user's input to the final output, verifying that each piece of the pipeline exhibits desirable behaviors. You can (and should) test individual components of this workflow using unit tests. Note that others have written at length on the topic of [unit testing](#user-content-fn-1)[^1], and it is not covered here in detail.

Remember that AI solutions can take many forms. They can be chatbots, voice bots for real-time conversation, or agents that take actions, like filling out our forms or calling external services. Level 1 evaluations cover all these modalities.

### Example: an AI agronomist deployed in Senegal

Consider a product answering questions from farmers in Pulaar. The AI system includes the three components as follows:

<table><thead><tr><th width="203.69140625">Component</th><th>Workflow Steps</th></tr></thead><tbody><tr><td>Pre-processing</td><td><ul><li>Check input for malicious or off-topic content (filtering model)</li><li>Translate query from Pulaar to English (translation model)</li></ul></td></tr><tr><td>Context Preparation</td><td><ul><li>Retrieve relevant agricultural content from the database</li><li>Retrieve specific information about the farmer from the context window</li><li>Generate response to processed user input (large language model)</li></ul></td></tr><tr><td>Post-processing</td><td><ul><li>Verify the answer is grounded in the content provided in your knowledge base</li><li>Translate the response back to Pulaa (translation model)</li></ul></td></tr></tbody></table>

### Low vs high-resource languages

Most LLMs are trained on digitized text in just a handful of languages, predominantly English. Yet they are used in contexts where users speak ”low-resource” languages, such as Kannada or Hikuyu. These languages may be spoken by tens of millions of people, but there is relatively less digitized text (and even fewer labeled datasets) available to train foundation models. As a result, LLM queries in these languages may result in higher rates of hallucination or other failure modes. In contrast, “high-resource” languages like English or Hindi have far more internet and digital data available, leading to stronger performance. To improve the performance of an AI system operating in “low-resource” languages, you may want to design your systems to first translate the user’s input from their language to a high-resource one, generate the AI response in a high-resource foundation model, then translate the answer back, so the user receives guidance in the language they prefer.

[^1]: e.g. [Unit tests for AI models](https://hamel.dev/blog/posts/evals/#level-1-unit-tests) by Hamel Husain.



    Numerous books exist on unit testing. We found chapters 11-14 of Software Engineering at Google especially useful when building right sized, right scope, and repeatable tests.

---

<details>
<summary>💬 Want to suggest edits or provide feedback?</summary>

{% embed url="https://tally.so/r/A788l0?originPage=level-1-model-evaluation%2Foverview%2Fwhat-is-the-ai-system-being-evaluated" %}
{% endembed %}

</details>
