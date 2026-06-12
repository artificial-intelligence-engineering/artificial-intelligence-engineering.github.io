---
title: "Harness Engineering"
permalink: /harness/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

## What Is Harness Engineering?

Harness engineering is the discipline of designing the execution environment around an AI agent, not only the prompt sent to the model.

A harness includes the constraints, tools, feedback loops, and operational rules that keep autonomous behavior reliable over many steps.

In practice, this means engineering teams invest in:

- predictable tool access,
- clear project instructions,
- automated checks and retries,
- observability,
- and safety guardrails.

The main idea is simple: **agent quality depends as much on the environment as on the model itself**.

## Prompt vs Context vs Harness

Prompt engineering, context engineering, and harness engineering solve different layers of the same problem.

![Prompt, Context, and Harness layers](/assets/images/harness-engineering-layered.svg)

| Layer | Core question | Design target |
| --- | --- | --- |
| Prompt engineering | What should I ask? | The instruction text |
| Context engineering | What should the model see? | The tokens and retrieved information |
| Harness engineering | How should the whole system run? | Tools, constraints, feedback, and runtime controls |

Harness engineering is broader than prompt or context design because it also covers behavior outside the model call.

## Why It Matters for Long-Running Agents

Long-running agents usually fail for operational reasons before they fail for intelligence reasons.

Typical failure modes include:

- repeated mistakes after retries,
- drift from repository conventions,
- fragile tool usage,
- accumulation of technical debt,
- and limited traceability when something breaks.

A good harness reduces these failures by turning expectations into mechanisms.

## Core Components of a Practical Harness

![Harness components for production agents](/assets/images/harness-engineering-components.svg)

### 1) Context Files as System of Record

Project-level instructions (for example `AGENTS.md`, `CLAUDE.md`, or local docs) should capture architecture, coding rules, and build/test commands.

Treat these files as the single source of truth for agent behavior.

### 2) Selective Tooling and Integrations

Connect external tools only when needed for the task (issue trackers, docs, runtime telemetry, etc.).

More tools are not always better: each integration increases complexity and context overhead.

### 3) Mechanical Enforcement

Use CI checks, linters, and structural tests to block invalid outputs early.

A harness is stronger when policy is executable (tests/rules), not only documented.

### 4) Feedback Loops and Self-Repair

Agent runs should produce actionable feedback that can be fed back into the next decision step.

This includes:

- failing with clear reasons,
- returning structured diagnostics,
- and enabling automatic retry with correction.

### 5) Observability

Collect logs, traces, and key metrics so you can answer:

- What did the agent try?
- Which tool calls failed?
- Where did the plan diverge?

Without observability, harness tuning becomes guesswork.

## Minimal Adoption Plan

Teams can start small and grow the harness incrementally:

1. **Write one context file** with build, test, and architecture rules.
2. **Expose only essential tools** for the first workflows.
3. **Add enforcement in CI** for non-negotiable constraints.
4. **Instrument traces/logs** to learn from failures.
5. **Convert repeated incidents into rules** (documented and executable).

## Agent Feedback Loop (Reference Pattern)

![Harness feedback loop](/assets/images/harness-engineering-feedback-loop.svg)

A simple loop:

1. Agent plans.
2. Agent acts (tool call or code change).
3. Harness validates (tests/lints/policies).
4. Harness returns feedback.
5. Agent repairs or finalizes.

This loop is where reliability is built.

## Notes

- This page is inspired by the article "Beyond Prompts and Context: Harness Engineering for AI Agents" by MadPlay, adapted into original summary content for this glossary.
- Reference article: [madplay.github.io - Harness Engineering](https://madplay.github.io/en/post/harness-engineering)
- Related glossary terms: [AI Agent](/ai-agent/), [Agent Skills](/skills/), [Prompt Engineering](/prompt-patterns/)

