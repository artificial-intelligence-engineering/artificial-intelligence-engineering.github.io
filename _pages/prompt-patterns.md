---
title: "Prompt Patterns Guide"
permalink: /prompt-patterns/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

<style>
  .page__content .highlight pre,
  .page__content pre {
    background: #fdf6e3;
    color: #657b83;
    border: 1px solid #eee8d5;
    border-radius: 8px;
    padding: 0.9rem 1rem;
  }

  .page__content pre code,
  .page__content .highlight pre code {
    background: transparent;
    color: #657b83;
  }

  .page__content strong {
    color: #586e75;
  }

  .page__content table {
    width: 100%;
    border-collapse: collapse;
    background: #fdf6e3;
    border: 1px solid #eee8d5;
    border-radius: 8px;
    overflow: hidden;
  }

  .page__content table th,
  .page__content table td {
    border: 1px solid #eee8d5;
    padding: 0.65rem 0.75rem;
  }

  .page__content table thead th,
  .page__content table tr:first-child th {
    background: #e8f4fb;
    color: #355f7c;
  }

  .page__content table tbody tr:nth-child(even),
  .page__content table tr:nth-child(even):has(td) {
    background: #f8f1dd;
  }

  .page__content table tbody tr:hover,
  .page__content table tr:hover:has(td) {
    background: #eef8f0;
  }
</style>

<div style="padding: 0.9rem 1rem; border-left: 4px solid #5b58d6; background: #f6f7ff; margin-bottom: 1rem;">
This page expands each prompting pattern used in <strong>Application Development</strong> with practical examples.
</div>

<div style="padding: 0.8rem 1rem; border-left: 4px solid #268bd2; background: #f2f9ff; margin-bottom: 1rem;">
Reference basis: <a href="https://www.promptingguide.ai/techniques">Prompting Guide - Techniques</a>. The notes below translate those techniques into implementation-oriented guidance for product teams.
</div>

## Zero-Shot Prompting

Give one direct instruction without examples. This is the fastest baseline for tasks where instructions are unambiguous and output structure is simple.

- **Use it when**: You need low-latency responses and can describe the task clearly in one shot.
- **Implementation tip**: Add explicit output constraints (format, length, style, language).
- **Common pitfall**: Vague instructions lead to broad or inconsistent answers.

**Illustrative example**

```text
You are a product analyst. Summarize this user feedback in 3 bullet points:
"The new dashboard is fast, but filters are confusing and export fails on mobile."
```

## Few-Shot Prompting

Provide a few examples so the model learns the expected format, style, and decision boundary.

- **Use it when**: Output consistency matters more than minimal prompt size.
- **Implementation tip**: Keep examples diverse but representative; include edge cases.
- **Common pitfall**: Overfitting to examples that are too narrow or biased.

**Illustrative example**

```text
Classify sentiment as Positive, Neutral, or Negative.

Text: "The onboarding was clear and quick."
Answer: Positive

Text: "It works as expected."
Answer: Neutral

Text: "The app crashes every day."
Answer: Negative

Text: "Support solved my issue in minutes."
Answer:
```

## Chain-of-Thought (CoT)

Ask for intermediate reasoning steps on multi-step tasks, especially where decomposition improves correctness.

- **Use it when**: The task requires arithmetic, logic, planning, or explicit decomposition.
- **Implementation tip**: Request concise reasoning and a final answer in a fixed schema.
- **Common pitfall**: Long verbose chains can increase latency and noise.

**Illustrative example**

```text
Solve step by step: A team has 24 GPUs. 25% are reserved for experiments and the rest for training.
How many GPUs are used for training?
```

## Meta Prompting

Use one prompt to generate, critique, or optimize another prompt.

- **Use it when**: You are iterating prompt quality across many tasks or domains.
- **Implementation tip**: Ask for versioned prompt outputs and rationale for each change.
- **Common pitfall**: Optimizing style without validating task-level metrics.

**Illustrative example**

```text
You are a prompt reviewer. Improve the following prompt for clarity, constraints, and output format.
Prompt: "Explain cloud costs."
Return: Improved prompt + why each change helps.
```

## Self-Consistency

Generate multiple reasoning paths and select the most consistent final answer.

- **Use it when**: Single-pass reasoning is unstable on hard problems.
- **Implementation tip**: Sample at moderate diversity and vote only on final answers.
- **Common pitfall**: Higher cost and latency if sample count is not controlled.

**Illustrative example**

```text
Solve this logic puzzle 5 different ways, then output only the answer that appears most often.
Puzzle: ...
```

## Generate Knowledge Prompting

Ask the model to produce relevant facts first, then solve the target task using those facts.

- **Use it when**: Background knowledge is needed before synthesis or recommendation.
- **Implementation tip**: Separate "fact generation" and "answer generation" steps.
- **Common pitfall**: Treating generated facts as ground truth without verification.

**Illustrative example**

```text
Step 1: List key facts about vector databases for RAG.
Step 2: Using those facts, recommend one architecture for a customer support bot.
```

## Prompt Chaining

Split a complex workflow into multiple prompts where each output feeds the next stage.

- **Use it when**: The task naturally breaks into extraction, transformation, and decision phases.
- **Implementation tip**: Define strict I/O contracts between steps (JSON schemas help).
- **Common pitfall**: Error propagation when intermediate outputs are not validated.

**Illustrative example**

```text
Prompt A: Extract user requirements from this meeting transcript.
Prompt B: Convert requirements into a technical specification.
Prompt C: Create a release checklist from the specification.
```

## Tree of Thoughts (ToT)

Explore multiple reasoning branches before committing to a final answer.

- **Use it when**: There are multiple plausible solution paths and planning is required.
- **Implementation tip**: Add branch scoring criteria before selecting a branch.
- **Common pitfall**: Branch explosion without pruning heuristics.

**Illustrative example**

```text
Generate 3 solution paths for reducing LLM latency.
Evaluate pros/cons of each path.
Pick the best path and provide a rollout plan.
```

## Retrieval-Augmented Generation (RAG)

Retrieve external context first, then answer grounded in that context.

- **Use it when**: You need factual grounding over internal or frequently updated data.
- **Implementation tip**: Constrain answers to retrieved chunks and require citations.
- **Common pitfall**: Poor retrieval quality causing confident but incomplete answers.

**Illustrative example**

```text
Context:
- Doc 1: API rate limits
- Doc 2: Authentication policy

Question: What is the max request rate for a service account?
Answer only from the provided context and cite the doc used.
```

## Automatic Reasoning and Tool-use (ART)

Combine reasoning with tools (search, calculator, code executor, APIs) to solve tasks beyond pure text prediction.

- **Use it when**: Correctness depends on external computation or up-to-date data.
- **Implementation tip**: Define tool contracts and explicit fallback behavior.
- **Common pitfall**: Unbounded tool calls that hurt reliability and cost.

**Illustrative example**

```text
Task: Estimate monthly infrastructure cost.
Use tool calls for pricing lookup and arithmetic.
Show assumptions, then return total cost.
```

## Automatic Prompt Engineer (APE)

Automatically generate and test multiple prompt candidates.

- **Use it when**: You want data-driven prompt optimization at scale.
- **Implementation tip**: Evaluate prompts on a fixed validation set with clear metrics.
- **Common pitfall**: Selecting prompts that optimize one metric while degrading others.

**Illustrative example**

```text
Create 10 prompt variants for intent classification.
Evaluate each variant on this validation set.
Return the top 2 prompts by accuracy.
```

## Active-Prompt

Select uncertain or high-value examples to improve performance iteratively.

- **Use it when**: Labeling budget is limited and you need efficient improvement.
- **Implementation tip**: Prioritize high-uncertainty or high-impact samples.
- **Common pitfall**: Ignoring class balance while selecting uncertain examples.

**Illustrative example**

```text
From 200 support tickets, identify the 20 most uncertain classifications.
Use them as new examples and rerun classification.
```

## Directional Stimulus Prompting (DSP)

Inject hints that nudge the model toward desired output direction.

- **Use it when**: You need stronger control over framing, emphasis, or tone.
- **Implementation tip**: Keep stimuli short and explicit; avoid conflicting cues.
- **Common pitfall**: Over-constraining the model and reducing useful creativity.

**Illustrative example**

```text
Write a release note. Emphasize reliability improvements and measurable outcomes.
Use a professional and concise tone.
```

## Program-Aided Language Models (PAL)

Let the model write code to solve tasks more reliably, then execute and verify outputs.

- **Use it when**: Symbolic, numeric, or algorithmic correctness is critical.
- **Implementation tip**: Run code in a sandbox and validate outputs automatically.
- **Common pitfall**: Trusting generated code without execution safeguards.

**Illustrative example**

```text
Write Python code to compute the weighted average latency from this dataset.
Then execute the code and return only the final metric.
```

## ReAct

Interleave reasoning and actions in loops: think, act, observe, repeat.

- **Use it when**: Agents must query tools or documents iteratively.
- **Implementation tip**: Enforce a maximum step budget and stop criteria.
- **Common pitfall**: Tool loops with no convergence policy.

**Illustrative example**

```text
Goal: Answer a product question from internal docs.
Format:
Thought: ...
Action: search_docs("...")
Observation: ...
Final Answer: ...
```

## Reflexion

Add self-critique loops so the model reviews and improves its own output.

- **Use it when**: First-pass drafts are useful but need stronger quality control.
- **Implementation tip**: Separate roles (draft -> critic -> reviser) in structured steps.
- **Common pitfall**: Infinite refinement loops without acceptance checks.

**Illustrative example**

```text
Draft an architecture proposal.
Then critique it against scalability, security, and cost.
Revise the proposal based on the critique.
```

## Multimodal CoT

Apply stepwise reasoning when inputs include text plus images/documents.

- **Use it when**: Diagnosis or decisions depend on both visual and textual evidence.
- **Implementation tip**: Ask for evidence mapping (which visual clue supports which claim).
- **Common pitfall**: Ignoring modality conflicts between image and text sources.

**Illustrative example**

```text
Given this screenshot and error log, reason step by step:
1) Identify the failing component
2) Infer likely root cause
3) Propose next debugging action
```

## Graph Prompting

Use graph structure (entities and relations) as explicit reasoning context.

- **Use it when**: Problems depend on relationship traversal (dependency, impact, lineage).
- **Implementation tip**: Force explicit traversal steps before the final answer.
- **Common pitfall**: Missing edge direction or relation type in complex graphs.

**Illustrative example**

```text
Knowledge graph edges:
(Customer)-[uses]->(Product A)
(Product A)-[depends_on]->(Service B)
(Service B)-[hosted_in]->(Region EU)

Question: Which customers are impacted by an outage in Region EU?
Explain the traversal used.
```

<div style="padding: 0.85rem 1rem; border-left: 4px solid #00b48c; background: #f2fff9; margin-top: 1.2rem;">
Tip: Start with the simplest pattern that solves your task, then move to more advanced ones (RAG, ReAct, ToT, Reflexion) only when needed.
</div>

## Prompt Patterns Quick Reference

| Technique | What it is | Best use case |
| --- | --- | --- |
| Zero-Shot Prompting | Direct instruction with no examples. | Clear tasks with strict constraints and low latency needs. |
| Few-Shot Prompting | Adds example input/output pairs to guide behavior. | Structured outputs, style control, and consistency. |
| Chain-of-Thought (CoT) | Asks for intermediate reasoning steps. | Multi-step logic, math, and planning tasks. |
| Meta Prompting | Uses prompts to improve or generate prompts. | Prompt quality iteration and reusable templates. |
| Self-Consistency | Samples multiple reasoning paths and votes. | Hard reasoning where single-pass output is unstable. |
| Generate Knowledge Prompting | Produces relevant facts before final answering. | Knowledge-heavy recommendations and synthesis. |
| Prompt Chaining | Splits a workflow into sequential prompt steps. | Complex pipelines with extraction -> transform -> decision. |
| Tree of Thoughts (ToT) | Explores and evaluates multiple reasoning branches. | Search/planning tasks with several plausible paths. |
| Retrieval-Augmented Generation (RAG) | Grounds responses with retrieved external context. | Enterprise QA over private docs and fresh information. |
| Automatic Reasoning and Tool-use (ART) | Combines reasoning with tools/APIs. | Tasks requiring calculations, lookups, or execution. |
| Automatic Prompt Engineer (APE) | Auto-generates and evaluates prompt variants. | Data-driven prompt optimization at scale. |
| Active-Prompt | Selects uncertain/high-value samples iteratively. | Efficient quality improvements with limited labeling budget. |
| Directional Stimulus Prompting (DSP) | Adds guidance signals to steer generation. | Output framing, tone, and emphasis control. |
| Program-Aided Language Models (PAL) | Solves tasks via generated executable code. | Numeric/symbolic tasks where correctness is critical. |
| ReAct | Interleaves thought, action, and observation loops. | Agentic workflows with iterative tool use. |
| Reflexion | Uses self-critique and revision loops. | Improving draft quality and reducing first-pass errors. |
| Multimodal CoT | Extends stepwise reasoning across modalities. | Vision-language diagnosis and evidence-based analysis. |
| Graph Prompting | Reasons over entities and explicit relations. | Dependency, impact, lineage, and graph-centric tasks. |
