---
permalink: /overview/
title: "Overview"
layout: single
author_profile: false
---

This section is dedicated to explaining the philosophy of this website focused on AI Engineering. The main approach is to structure AI Engineering around three primary areas: **Application Development**, which is the core focus of AI engineering; **Model Development**, focused on model development technologies, model selection, model adaptation, and related topics; and **AI Infrastructure**, centered on the infrastructure technologies required to build AI applications, including large LLM infrastructures, orchestration, and the different components that enable the creation of complex AI applications.

## Application Development (The Product Layer)

This layer focuses on building real AI-powered products and user-facing systems on top of models. It is the most visible part of AI Engineering because it turns model capabilities into useful applications, workflows, and business value.

- **Application Design**: Defining user journeys, interaction patterns, and product experiences that make AI features useful and reliable.
- **Context Engineering**: Supplying the right instructions, retrieved knowledge, conversation state, and external tools so the model can respond effectively.
- **Evaluation and Guardrails**: Measuring output quality, robustness, and safety while reducing hallucinations and ensuring production readiness.

## Model Development (The Intelligence)

This layer focuses on the creation, training, and fine-tuning of the core algorithms and Large Language Models (LLMs).

- **Data Pipelines**: Aggregating, cleaning, and vectorizing data for model ingestion.
- **Training/Fine-Tuning**: Using frameworks such as PyTorch and TensorFlow to train models from scratch or adapt pre-existing models to specific domains.
- **Evaluation**: Benchmarking models for accuracy, latency, and hallucination rates before production.

## AI Infrastructure (The Foundation)

AI infrastructure provides the hardware, networking, and orchestration required to support massive AI workloads. Traditional IT systems are often insufficient.

- **Compute**: Heavy utilization of GPUs (Graphics Processing Units) and TPUs for parallel processing.
- **Networking & Storage**: High-bandwidth fabrics such as InfiniBand and specialized, high-throughput storage systems to feed data to processors.
- **Management**: Platforms such as Kubernetes to orchestrate distributed workloads and manage container scaling.

