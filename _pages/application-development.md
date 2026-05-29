---
title: "Application Development"
permalink: /application-development/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

## Overview

Application Development in AI Engineering focuses on building user-facing applications that leverage foundation 
models and other AI technologies. This section covers the key concepts, tools, and best practices for developing 
AI-powered applications.

The main task of the software engineer working with LLMs is not to train an LLM, or even to fine-tune one (usually), 
but rather to take an existing LLM and work out how to get it to accomplish the task you need for your application.

## Key Concepts

### Prompt Engineering

> Adapting an existing LLM for your task is called prompt engineering. It involves crafting the input to the model in a way that guides it to produce the desired output.

A prompt is the text instruction or question given to an AI system, such as a large language model, to produce an answer. 
It is the main way to direct how the model behaves, clarify the task, and establish the context of the exchange. 
Because prompt wording strongly influences output quality and relevance, selecting the appropriate prompt style for 
each use case is critical. 

To get the most reliable results from AI models, it is important to understand the different prompt structures and when 
to apply each one based on the goal. We name prompting techniques or prompting patterns this structures. 

### Prompt Patterns

| Technique | What it is | Best use case |
| --- | --- | --- |
| Zero-Shot Prompting | Direct instruction with no examples. | Simple, clearly defined tasks with stable output format. |
| Few-Shot Prompting | Includes a few input/output examples to guide behavior. | Tasks that need specific tone, format, or style. |
| Chain-of-Thought (CoT) | Encourages intermediate reasoning steps. | Multi-step reasoning, math, and logic tasks. |
| Meta Prompting | Prompts the model to design or refine prompts. | Improving prompt quality or creating reusable prompt templates. |
| Self-Consistency | Samples multiple reasoning paths and picks the most consistent answer. | Hard reasoning tasks where one pass is brittle. |
| Generate Knowledge Prompting | Generates relevant facts first, then solves the task. | Knowledge-heavy questions needing extra context. |
| Prompt Chaining | Splits one complex task into sequential prompts. | Workflows with distinct stages (analyze, draft, verify). |
| Tree of Thoughts (ToT) | Explores multiple reasoning branches and selects promising ones. | Search-like problems and complex planning. |
| Retrieval-Augmented Generation (RAG) | Injects retrieved external context before generation. | Grounded QA over private docs and up-to-date information. |
| Automatic Reasoning and Tool-use (ART) | Combines reasoning with tool invocations. | Tasks requiring calculators, APIs, or external systems. |
| Automatic Prompt Engineer (APE) | Automatically generates and optimizes prompt variants. | Systematic prompt tuning for better task performance. |
| Active-Prompt | Prioritizes uncertain/informative examples for iterative improvement. | Improving reasoning reliability with targeted examples. |
| Directional Stimulus Prompting (DSP) | Uses guiding hints to steer the model toward target outputs. | Controlled generation when output direction matters. |
| Program-Aided Language Models (PAL) | Solves tasks by generating code and executing it. | Math, symbolic reasoning, and algorithmic tasks. |
| ReAct | Interleaves reasoning traces with actions and observations. | Agent workflows involving tools, search, or environments. |
| Reflexion | Adds self-critique and iterative correction loops. | Reducing mistakes in non-trivial multi-step tasks. |
| Multimodal CoT | Extends CoT to mixed modalities (text + image, etc.). | Vision-language tasks that need structured reasoning. |
| Graph Prompting | Uses graph-structured context and relations during prompting. | Knowledge graph tasks and relationship-centric reasoning. |
