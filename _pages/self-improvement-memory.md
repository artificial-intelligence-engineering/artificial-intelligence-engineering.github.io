---
title: "Self-Improvement Memory (SIM)"
permalink: /self-improvement-memory/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

## What Is Self-Improvement Memory (SIM)?

**Self-Improvement Memory (SIM)** is a persistent engineering memory architecture designed for **Continual Recursive Self-Improvement (CRSI)** of AI agent harnesses.

To understand SIM cleanly, it helps to separate two distinct roles:

- **Target Harness** (for example, [OpenCode](/opencode/)): the agent runtime, prompts, tools, and control logic you want to improve.
- **SIM + CRSI Optimizer**: the external process or meta-harness that observes failures, proposes changes to the target harness, evaluates variants, and records what worked and why.

In short, SIM is not a built-in feature of a coding agent like OpenCode; it is the structured memory of an external optimization loop that improves a harness through repeated cycles of **proposal, execution, evaluation, and selection**:

- **Optimization Agent** &rarr; proposes changes
- **Target Harness** &rarr; executes tasks (e.g., OpenCode)
- **SIM** &rarr; stores engineering rationale and outcomes
- **Evals** &rarr; decide whether a change genuinely improves the system

---

## Meta-Harness Architecture

Rather than simply giving a single agent more conversation memory or better tools, SIM/CRSI introduces a **meta-harness** (an optimizer harness) specialized in monitoring and improving the original harness `H`:

```text
User / Tasks
     │
     ▼
Original Harness H
  ├── runs the agent
  ├── manages context and tools
  ├── produces traces and outputs
  └── yields scores / test results / failures
     │
     ▼
Meta-Harness / Optimizer
  ├── analyzes failure traces
  ├── proposes changes to H
  ├── runs candidate variants
  ├── compares benchmark metrics
  ├── accepts or rejects changes
  └── records the experience in SIM
```

### Why Recursion Needs Guardrails

Conceptually, the structure is recursive:

```text
Meta-Harness
  └── observes and modifies Harness H1
        └── runs Agent A
              └── uses Model M and Tools
```

If the meta-harness is also allowed to modify its own optimization mechanism (`H2` optimizes `H1`, `H3` optimizes `H2`), uncontrolled recursion risks destabilizing the evaluator or drifting away from the real objective. In practice, teams keep the optimizer fixed and constrain it to modifying the target harness inside an isolated sandbox backed by external evaluations.

---

## Applied to a Coding Harness (e.g., OpenCode)

Applied to a coding harness such as [OpenCode](/opencode/), the conceptual optimization loop looks like this:

```text
OpenCode executes coding tasks
        ↓
traces, errors, tests, and outcomes are logged
        ↓
an optimizer analyzes recurring failures
        ↓
proposes changes to OpenCode
        ↓
each variant is tested on an independent benchmark
        ↓
the improvement is kept if it passes acceptance criteria
        ↓
SIM records what changed, why, and with what result
```

### What the Optimizer Can Modify

Depending on how the target harness is structured, proposed changes may target:

- system prompts and agent instructions,
- context selection and presentation,
- compaction timing and summarization policies,
- tool definitions and permissions,
- file-search strategies,
- maximum step limits and retry policies,
- completion criteria and test execution,
- error-recovery loops,
- model routing and handoff formats,
- plugins or [Agent Skills](/skills/).

### Concrete Example: Fixing Premature Completion

Suppose OpenCode repeatedly fails tasks because it declares a task complete right after editing code—without running tests.

The optimizer detects this failure pattern in the execution traces and proposes a **verification gate**:

> Before declaring completion:
> 1. Run type-checking
> 2. Run affected tests
> 3. Inspect `git diff`
> 4. Declare success only if every check passes

The variant is evaluated across a suite of benchmark tasks, and SIM logs the experiment:

```text
Problem:    Premature task completion without verification
Change:     Added pre-completion verification gate
Prediction: Reduce tasks falsely declared complete
Result:     +8% accepted tasks
Context:    Model X, Benchmark Y, Round 3
```

Later, when OpenCode is adapted to a **new underlying model** or a **different repository type**, the optimizer queries SIM. Instead of starting from scratch or blindly keeping old rules without context, it can reuse the verification gate and adapt it—for instance, adding integration tests if the new environment requires them.

---

## Three Degrees of Harness Self-Modification

Does the target harness rewrite itself autonomously? Not necessarily. There are three practical levels of autonomy:

### 1. External, Controlled Optimization
- **Setup:** The production harness remains stable; an external optimizer proposes changes on a fork or experimental branch and opens a Pull Request.
- **Gate:** Benchmarks and automated evals determine whether the PR is accepted.
- **Trade-off:** Safest and easiest to audit in production engineering workflows.

### 2. Evolutionary Configuration
- **Setup:** Core harness source code is left untouched. The optimizer tunes externalized configuration: prompts, `AGENTS.md`, skills, MCP tools, policies, parameters, model routing, and context templates.
- **Trade-off:** Highly practical for real-world teams because behavior improves without modifying or recompiling the core product.

### 3. Self-Modification of the Harness Code
- **Setup:** The optimizer directly edits the harness source code, rebuilds it, and tests the new artifact automatically.
- **Requirements:** This is the strongest form studied in research and requires strict safeguards:
  - sandboxed execution,
  - isolated tests and independent held-out benchmarks,
  - regression checks and diff review,
  - protection against reward hacking (optimizing the evaluator instead of solving the task),
  - automated rollback.

---

## What Research Shows—and What It Does Not

- **What SIM research demonstrates:** Preserving structured evolution memory allows a harness optimizer to continue improving performance across dataset shifts and underlying model changes, avoiding the "model-switching trap" where an evolved harness loses its experimental rationale.
- **What it does not claim:** There is no built-in, out-of-the-box SIM integration in OpenCode. OpenCode is simply a representative target harness whose configuration, source code, and evaluation signals can be connected to an external optimization loop.

### Safe Engineering Loop

In practice, "self-improvement" here means an automated engineering pipeline rather than an agent rewriting itself mid-conversation:

```text
Observe → Diagnose → Propose → Execute → Evaluate → Select
```

| Stage | Responsibility |
| --- | --- |
| **LLM Optimizer** | Diagnoses failure traces and proposes candidate edits |
| **Experimental Runtime** | Executes the modified harness in an isolated sandbox |
| **External Evaluator** | Measures task success, regressions, cost, and latency |
| **Selector / Gate** | Accepts or rejects the candidate based on objective criteria |
| **SIM Memory** | Persists the rationale, context, and outcome history |

---

## References

- [Self-Improvement Memory Enables Continual Recursive Self-Improvement – arXiv (2611.18856)](https://arxiv.org/abs/2611.18856)
- [memsim – GitHub (nuster1128/memsim)](https://github.com/nuster1128/memsim)
- [Forget Agent Harness: Recursive Harness Memory Is 10x Better – Medium](https://medium.com/data-science-collective/forget-agent-harness-recursive-harness-memory-10x-better-b0d4c419277d?sk=805a8ce54130d1e45ea5449d09f74891)
- [Related Research Paper – arXiv (2409.20163v1)](https://arxiv.org/html/2409.20163v1)
