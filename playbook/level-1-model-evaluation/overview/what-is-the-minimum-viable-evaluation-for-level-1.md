# What is the Minimum Viable Evaluation for Level 1?

The earliest stage of AI development involves prototyping with offline evaluations. Here, we strongly recommend using notebooks (e.g. Jupyter notebooks, or Google Colab) to establish reproducible workflows instead of aiming to set up an automated pipeline from the start.

The goal of this step is to quickly analyze errors in the current configuration, make suitable changes, and test for resolution of issues. Working inside a notebook helps you access every component in one place—data, configs, models, metrics and any other intermediate steps like retrieval, tool calling—giving you full visibility into your existing system and a test bed for validating your experiments end-to-end.

Once you are ready to deploy a product to actual users, consider using an observability platform (like Langfuse or DeepEval) to automatically record traces as you iterate. This is important for understanding where your AI system is failing and why. But don’t let this delay your launch.

{% include "../../.gitbook/includes/level-2-mve.md" %}
