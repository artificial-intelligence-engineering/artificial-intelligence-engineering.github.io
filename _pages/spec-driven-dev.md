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

## The Core Methodology

In standard LLM usage, a developer usually prompts conversationally and iterates on the code.
In SDD, the development lifecycle is strictly separated into formal phases:

1. Specification (The Contract): Developers write explicit, structured definitions (often in formats like YAML or TOML) outlining intent,
behaviors, edge cases, and architectural constraints.

2. Planning & Task Decomposition: The LLM or an agent parses the spec to generate a detailed implementation plan and an atomic task list,
rather than attacking a monolithic prompt.

3. Generation: AI coding agents (or developers) execute the task list strictly referencing the original spec to generate code or tests.

4. Validation: CI/CD pipelines and linters automatically test the generated codebase against the specification. If the code deviates from the spec, the build fails.

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

## A real example

In the context of Large Language Models (LLMs) and Artificial Intelligence, **SDD** stands for **Specification-Driven Development**. Software legend "Uncle Bob" (Robert C. Martin) advocates for this approach as a necessary, disciplined guardrail to prevent AI agents from writing uncontrolled or hallucinated code

Core concepts of Uncle Bob's approach to SDD include:

1. Living Specifications (Gherkin): Specifications should be written in structured, natural-language formats like Gherkin (Feature/Scenario). This serves as the single "source of truth" that the human and the AI agree upon.

2. Iterative Slicing (Avoid BUFD): To avoid "Big Up Front Design" (BUFD), Uncle Bob emphasizes writing "just enough specs" iteratively for the specific stories in your current sprint. The AI should never be left to assume what to build without a localized, actionable spec.

3. Human Veto Power: Specs should be co-authored or refined by both humans and the AI, but final approval and enforcement remain strictly in the hands of the humans.

4. Testing is Mandatory: AI-generated code should never be blindly trusted. Uncle Bob emphasizes that disciplined Test-Driven Development (TDD) and acceptance testing are critical to catch inaccuracies.

The following Gherkin DSL code snapshots show how to express SDD work items in a structured, testable format.

### Gherkin code snapshot 1: Feature + Rule + Background + Scenario

```gherkin
Feature: Account transfer risk controls
	To reduce transfer fraud
	As a banking platform
	We enforce transfer limits and dual approval rules

	Rule: Transfers above threshold require dual approval

		Background:
			Given an account "A-102" with a balance of 12000 EUR
			And a transfer threshold of 5000 EUR

		Scenario: A high-value transfer remains pending until second approval
			When an operator submits a transfer of 7000 EUR from "A-102" to "B-220"
			Then the transfer status should be "PendingApproval"
			And an approval request should be visible to a second approver
```

### Gherkin code snapshot 2: Scenario Outline with Examples

```gherkin
Feature: Credit scoring decisions

	Scenario Outline: Decision is based on score and debt ratio
		Given an applicant with credit score <score>
		And a debt ratio of <debt_ratio>
		When the underwriting engine evaluates the application
		Then the decision should be <decision>

		Examples:
			| score | debt_ratio | decision   |
			| 810   | 0.22       | Approved   |
			| 690   | 0.31       | ManualReview |
			| 580   | 0.45       | Rejected   |
```

### Gherkin code snapshot 3: Data Table and observable outcomes

```gherkin
Feature: Product search ranking

	Scenario: Ranked results prioritize in-stock products
		Given the catalog contains:
			| sku   | title                  | in_stock | score |
			| P-101 | Noise Cancelling Headset | true     | 0.86  |
			| P-202 | USB-C Dock             | false    | 0.91  |
			| P-303 | 4K Webcam              | true     | 0.84  |
		When a shopper searches for "office setup"
		Then the first visible product should be "Noise Cancelling Headset"
		And "USB-C Dock" should appear after all in-stock products
```

### AI-oriented Gherkin writing notes

Following the Cucumber reference and AI-oriented guidelines:

- Keep scenarios short (typically 3-5 steps) and behavior-focused.
- Use domain language, not UI implementation details.
- Prefer observable outcomes in `Then` steps instead of internal database checks.
- Use `Rule` to separate business constraints clearly.
- Use `Scenario Outline` and `Examples` for variable combinations instead of duplicating scenarios.
- Maintain consistent formatting (for example, 2-space indentation) for tool and agent reliability.

## Reference

This page is based on the analysis in:

- [Understanding Spec-Driven-Development: Kiro, spec-kit, and Tessl](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html)
- [DSLs Enable Reliable Use of LLMs](https://martinfowler.com/articles/llm-and-dsls.html#DomainAbstractionsAndDsls)
