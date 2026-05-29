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
</style>

<div style="padding: 0.9rem 1rem; border-left: 4px solid #5b58d6; background: #f6f7ff; margin-bottom: 1rem;">
This page expands each prompting pattern used in <strong>Application Development</strong> with practical examples.
</div>

## Zero-Shot Prompting

Give one direct instruction without examples.

**Illustrative example**

```text
You are a product analyst. Summarize this user feedback in 3 bullet points:
"The new dashboard is fast, but filters are confusing and export fails on mobile."
```

## Few-Shot Prompting

Provide a few examples so the model learns the expected format or style.

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

Ask for intermediate reasoning steps on multi-step tasks.

**Illustrative example**

```text
Solve step by step: A team has 24 GPUs. 25% are reserved for experiments and the rest for training.
How many GPUs are used for training?
```

## Meta Prompting

Use one prompt to generate or improve another prompt.

**Illustrative example**

```text
You are a prompt reviewer. Improve the following prompt for clarity, constraints, and output format.
Prompt: "Explain cloud costs."
Return: Improved prompt + why each change helps.
```

## Self-Consistency

Generate multiple reasoning paths and select the most consistent final answer.

**Illustrative example**

```text
Solve this logic puzzle 5 different ways, then output only the answer that appears most often.
Puzzle: ...
```

## Generate Knowledge Prompting

Ask the model to produce relevant facts first, then solve the target task.

**Illustrative example**

```text
Step 1: List key facts about vector databases for RAG.
Step 2: Using those facts, recommend one architecture for a customer support bot.
```

## Prompt Chaining

Split a complex workflow into multiple prompts where each output feeds the next stage.

**Illustrative example**

```text
Prompt A: Extract user requirements from this meeting transcript.
Prompt B: Convert requirements into a technical specification.
Prompt C: Create a release checklist from the specification.
```

## Tree of Thoughts (ToT)

Explore multiple reasoning branches before committing to a final answer.

**Illustrative example**

```text
Generate 3 solution paths for reducing LLM latency.
Evaluate pros/cons of each path.
Pick the best path and provide a rollout plan.
```

## Retrieval-Augmented Generation (RAG)

Retrieve external context first, then answer grounded in that context.

**Illustrative example**

```text
Context:
- Doc 1: API rate limits
- Doc 2: Authentication policy

Question: What is the max request rate for a service account?
Answer only from the provided context and cite the doc used.
```

## Automatic Reasoning and Tool-use (ART)

Combine reasoning with tools (search, calculator, code executor, APIs).

**Illustrative example**

```text
Task: Estimate monthly infrastructure cost.
Use tool calls for pricing lookup and arithmetic.
Show assumptions, then return total cost.
```

## Automatic Prompt Engineer (APE)

Automatically generate and test multiple prompt candidates.

**Illustrative example**

```text
Create 10 prompt variants for intent classification.
Evaluate each variant on this validation set.
Return the top 2 prompts by accuracy.
```

## Active-Prompt

Select uncertain or high-value examples to improve performance iteratively.

**Illustrative example**

```text
From 200 support tickets, identify the 20 most uncertain classifications.
Use them as new examples and rerun classification.
```

## Directional Stimulus Prompting (DSP)

Inject hints that nudge the model toward desired output direction.

**Illustrative example**

```text
Write a release note. Emphasize reliability improvements and measurable outcomes.
Use a professional and concise tone.
```

## Program-Aided Language Models (PAL)

Let the model write code to solve tasks more reliably.

**Illustrative example**

```text
Write Python code to compute the weighted average latency from this dataset.
Then execute the code and return only the final metric.
```

## ReAct

Interleave reasoning and actions in loops: think, act, observe, repeat.

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

**Illustrative example**

```text
Draft an architecture proposal.
Then critique it against scalability, security, and cost.
Revise the proposal based on the critique.
```

## Multimodal CoT

Apply stepwise reasoning when inputs include text plus images/documents.

**Illustrative example**

```text
Given this screenshot and error log, reason step by step:
1) Identify the failing component
2) Infer likely root cause
3) Propose next debugging action
```

## Graph Prompting

Use graph structure (entities and relations) as explicit reasoning context.

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
