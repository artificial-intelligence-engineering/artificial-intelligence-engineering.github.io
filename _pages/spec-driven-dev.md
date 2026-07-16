---
title: "Spec Driven Development"
permalink: /spec-driven-dev/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

## Overview

Spec-Driven Development (SDD) in LLM-enabled software delivery is an engineering approach in which structured specifications are treated as the main source of truth, instead of relying on ad-hoc prompt conversations. By defining requirements, constraints, interfaces, and acceptance criteria before generation, teams improve predictability, traceability, and governance of AI-assisted changes.

## Working Definition

SDD can be understood as documentation-first development for AI agents: a specification describes intent and expected behavior in a structured way, and implementation is generated or guided from that specification.

In practice, a high-quality spec usually includes:

- functional requirements and user outcomes
- acceptance criteria in testable form
- API and data contracts
- non-functional constraints such as security, performance, and compliance
- boundaries between existing behavior and new behavior

## Levels of Adoption

Current industry practice commonly shows three maturity levels:

1. **Spec-first**: the spec is created before coding for a single change request.
2. **Spec-anchored**: the spec remains active after delivery and evolves with the feature.
3. **Spec-as-source**: the spec becomes the primary maintained artifact, and code is generated as a downstream output.

These levels are cumulative and represent progressively stronger coupling between product intent and generated implementation.

## Tooling Patterns (Kiro, Spec-kit, Tessl)

Based on the referenced analysis of current tooling ecosystems, three representative patterns are visible:

- **Kiro**: a lightweight requirements -> design -> tasks flow, typically aligned with spec-first usage.
- **Spec-kit**: a CLI-oriented workflow with constitution, specification, planning, and task artifacts; highly customizable in repository workflows.
- **Tessl Framework**: a stronger emphasis on spec-anchored and spec-as-source models, including code generation linked directly to spec files.

Although all three are framed as SDD, they differ significantly in artifact model, workflow strictness, and long-term maintenance strategy.

## Expected Benefits

- higher consistency in AI outputs due to explicit constraints
- clearer auditability for reviews and regulated environments
- better alignment between product intent and implementation
- improved onboarding through explicit decision records
- stronger change impact visibility via requirements-to-task traceability

## Risks and Practical Limits

Early usage patterns also reveal recurring risks:

- documentation overhead can exceed implementation value for small tasks
- excessive markdown artifacts can shift review burden from code to repetitive documents
- larger context windows do not guarantee full instruction adherence
- weak separation between functional intent and technical design can introduce ambiguity
- non-determinism remains present even under strict specification workflows

For these reasons, SDD should be calibrated to problem size, domain criticality, and team maturity.

## Recommended Adoption Strategy

1. Start with **spec-first** for medium/high-impact changes.
2. Use concise, testable specs rather than verbose narratives.
3. Maintain a stable project memory layer (architecture, conventions, constraints) separate from per-feature specs.
4. Apply iterative delivery: short cycles, continuous verification, and incremental spec refinement.
5. Promote to **spec-anchored** only when repeated evolution of the same feature justifies it.

## Relationship with TDD, BDD, and MDD

SDD is adjacent to established methods but not equivalent:

- **TDD** focuses on executable tests as the driver.
- **BDD** emphasizes shared behavior language across stakeholders.
- **MDD** treats formal models as generation sources, often with rigid DSL/tool chains.

SDD introduces natural-language specifications for AI agents, reducing some tooling rigidity while accepting greater probabilistic behavior from model-based generation.

## Domain Abstractions and DSLs in SDD

For SDD execution, natural-language specs can be strengthened by introducing domain abstractions and focused DSLs for work definition. The key principle is to move from broad prompt interpretation to constrained, domain-shaped instructions.

In this model, a DSL does not replace product requirements; it operationalizes them. The specification remains the intent layer, while the DSL defines executable work items with reduced ambiguity.

Typical examples include:

- Mermaid or PlantUML for architecture and sequence constraints
- SQL and policy DSLs for data and compliance rules
- YAML/JSON schemas for deployment, workflow, and task orchestration
- internal test/scenario DSLs for deterministic behavioral validation

## Defining SDD Jobs with a DSL

When SDD jobs are defined in DSL form, each job can be represented as a constrained contract instead of a free-form instruction block.

A practical job schema can include:

- `job_id`: immutable identifier for traceability
- `intent`: business purpose and expected user outcome
- `inputs`: required artifacts, contracts, and dependencies
- `constraints`: security, performance, architecture, and compliance boundaries
- `actions`: allowed domain operations in DSL vocabulary
- `validation`: deterministic checks (schema, compiler, linter, tests)
- `done_criteria`: explicit completion conditions

This pattern improves reproducibility because the agent works inside a smaller state space and receives domain-level validation errors instead of opaque runtime failures.

## Two-Phase Operating Model

The DSL-oriented SDD workflow is most effective when split into two phases:

1. **Abstraction design phase**: the team iteratively shapes the domain model and DSL vocabulary.
2. **Execution phase**: the LLM acts as a natural-language interface that maps requests into valid DSL artifacts.

This distinction is critical. The first phase is design-intensive and human-led. The second phase is automation-intensive and validation-led.

## Why DSLs Improve Reliability in SDD

- constrained syntax reduces generation variance
- in-context examples become more effective on narrow vocabularies
- validators provide deterministic feedback loops for autonomous correction
- reviewers can assess intent-level artifacts instead of low-level incidental code

However, DSL adoption has an upfront cost and should be justified by repetition, domain complexity, or strong governance requirements.

## Summary of the DSL Article

The referenced article highlights five practical conclusions:

1. Upfront specification alone is insufficient; iterative design discovery remains necessary.
2. Domain abstractions are foundational; DSLs are a strong extension of those abstractions.
3. LLM reliability increases when generation targets constrained languages with validators.
4. The same LLM plays two roles: co-designer of abstractions first, generator within those abstractions later.
5. In mature setups, the DSL artifact can become a durable source of truth, reducing dependence on original prompts.

## SDD + DSL Adoption Guidance

1. Start by stabilizing domain abstractions in code before creating a custom DSL.
2. Introduce DSLs only for high-value repetitive work (for example: scenarios, policies, workflow jobs).
3. Attach every DSL job to deterministic validation gates.
4. Keep specs concise and map each requirement to one or more DSL jobs.
5. Track evolution by versioning both specs and DSL artifacts together.

## Reference

This page is based on the analysis in:

- [Understanding Spec-Driven-Development: Kiro, spec-kit, and Tessl](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html)
- [DSLs Enable Reliable Use of LLMs](https://martinfowler.com/articles/llm-and-dsls.html#DomainAbstractionsAndDsls)
