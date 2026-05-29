---
permalink: /overview/
title: "Overview"
layout: single
author_profile: false
---

This section is dedicated to explaining the philosophy of this website focused on AI Engineering. The main approach is to structure AI Engineering around three primary areas: **Application Development**, which is the core focus of AI engineering; **Model Development**, focused on model development technologies, model selection, model adaptation, and related topics; and **AI Infrastructure**, centered on the infrastructure technologies required to build AI applications, including large LLM infrastructures, orchestration, and the different components that enable the creation of complex AI applications.

<div style="margin: 1.5rem 0; padding: 1rem; border: 1px solid #e5e5e5; border-radius: 10px; background: #fafafa;">
  <svg viewBox="0 0 960 520" role="img" aria-label="AI Engineering foundations diagram" style="width: 100%; height: auto; display: block;">
    <defs>
      <marker id="arrow" markerWidth="10" markerHeight="10" refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
        <path d="M0,0 L0,6 L9,3 z" fill="#6f5aa8" />
      </marker>
    </defs>

    <line x1="300" y1="150" x2="660" y2="150" stroke="#6f5aa8" stroke-width="3" marker-end="url(#arrow)" />
    <line x1="700" y1="190" x2="520" y2="350" stroke="#6f5aa8" stroke-width="3" marker-end="url(#arrow)" />
    <line x1="440" y1="350" x2="260" y2="190" stroke="#6f5aa8" stroke-width="3" marker-end="url(#arrow)" />

    <rect x="90" y="80" width="260" height="140" rx="14" fill="#ffffff" stroke="#d9d9d9" />
    <text x="220" y="118" text-anchor="middle" font-size="22" font-weight="700" fill="#222">Application</text>
    <text x="220" y="145" text-anchor="middle" font-size="22" font-weight="700" fill="#222">Development</text>
    <text x="220" y="176" text-anchor="middle" font-size="16" fill="#555">Products, UX, workflows</text>

    <rect x="610" y="80" width="260" height="140" rx="14" fill="#ffffff" stroke="#d9d9d9" />
    <text x="740" y="118" text-anchor="middle" font-size="22" font-weight="700" fill="#222">Model</text>
    <text x="740" y="145" text-anchor="middle" font-size="22" font-weight="700" fill="#222">Development</text>
    <text x="740" y="176" text-anchor="middle" font-size="16" fill="#555">Training, tuning, eval</text>

    <rect x="350" y="300" width="260" height="140" rx="14" fill="#ffffff" stroke="#d9d9d9" />
    <text x="480" y="338" text-anchor="middle" font-size="22" font-weight="700" fill="#222">AI Infrastructure</text>
    <text x="480" y="368" text-anchor="middle" font-size="16" fill="#555">Compute, storage, orchestration</text>

    <text x="480" y="490" text-anchor="middle" font-size="16" fill="#555">
      These foundations are interdependent: each one enables and constrains the others.
    </text>
  </svg>
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
