---
permalink: /overview/
title: "Overview"
layout: single
author_profile: false
---

This section is dedicated to explaining the philosophy of this website focused on AI Engineering. The main approach is to structure AI Engineering around three primary areas: **Application Development**, which is the core focus of AI engineering; **Model Development**, focused on model development technologies, model selection, model adaptation, and related topics; and **AI Infrastructure**, centered on the infrastructure technologies required to build AI applications, including large LLM infrastructures, orchestration, and the different components that enable the creation of complex AI applications.

<div style="margin: 1.5rem 0; padding: 1rem; border: 1px solid #e5e5e5; border-radius: 10px; background: #fafafa;">
  <div style="display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: 0.75rem; text-align: center;">
	<div style="flex: 1 1 220px; min-width: 220px; padding: 1rem; border: 1px solid #d9d9d9; border-radius: 10px; background: #ffffff;">
	  <strong>Application Development</strong><br>
	  <span style="font-size: 0.92em;">Build products, experiences, and workflows on top of AI.</span>
	</div>
	<div style="font-size: 1.6rem; color: #6f5aa8; font-weight: 700;">→</div>
	<div style="flex: 1 1 220px; min-width: 220px; padding: 1rem; border: 1px solid #d9d9d9; border-radius: 10px; background: #ffffff;">
	  <strong>Model Development</strong><br>
	  <span style="font-size: 0.92em;">Create, train, adapt, and evaluate the models that power the system.</span>
	</div>
	<div style="font-size: 1.6rem; color: #6f5aa8; font-weight: 700;">→</div>
	<div style="flex: 1 1 220px; min-width: 220px; padding: 1rem; border: 1px solid #d9d9d9; border-radius: 10px; background: #ffffff;">
	  <strong>AI Infrastructure</strong><br>
	  <span style="font-size: 0.92em;">Provide compute, storage, orchestration, and scaling foundations.</span>
	</div>
  </div>
  <div style="margin-top: 0.85rem; text-align: center; font-size: 0.95em; color: #555;">
	These three layers are interdependent: applications define requirements, models provide intelligence, and infrastructure makes both scalable and reliable.
  </div>
</div>

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

