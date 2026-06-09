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

To go deeper into each technique with practical examples:

<a href="{% link _pages/prompt-patterns.md %}" class="btn btn--primary btn--large">Open the Prompt Patterns Guide</a>

### Prompting evolution: Skills

The AI prompting landscape has shifted away from writing ephemeral instructions for single interactions to building persistent, reusable Skills. Instead of typing a quick prompt, a skill acts as a version-controlled document that compounds expertise (often saved as a `SKILL.md` file).

This evolution splits the prompting process into four core disciplines:

- **Prompt Craft:** Writing clear, structured instructions and constraints.
- **Context Engineering:** Curing and maintaining the optimal tokens, message history, and documents.
- **Intent Engineering:** Encoding goals, values, and decision boundaries into the AI.
- **Specification Engineering:** Writing comprehensive documents that autonomous agents can execute against.

Building skills instead of writing isolated prompts is transforming development workflows and organizational AI. The following best practices can help approach and refine this skill:

- **Treat Prompts as Assets:** Shift from typing driving directions (a prompt) to providing a map (a skill).
- **Define Acceptance Criteria:** Clearly outline exactly what "done" looks like so the model understands when a task is completed successfully.
- **Establish Context:** Provide background information, constraints, and relevant documents so the AI does not have to guess.
- **Assign Explicit Roles:** Assign a specific expert persona (e.g., strategist, editor, or developer) to narrow the AI's focus.

To go deeper into skills with practical examples and references:

<a href="{% link _pages/skills.md %}" class="btn btn--primary btn--large">Open Skills development Guide</a>

## Basic Tooling

The current minimum setup for AI application development is converging around three core tools. This is the direction most major vendors are pushing (Google, Anthropic, Microsoft, and others):

1. An IDE plugin/extension for in-context coding assistance.
2. A CLI to drive the agent from terminal workflows and automation.
3. A standalone chat UI to collaborate with the agent outside the editor.

This three-surface model is quickly becoming the most practical baseline used by AI application developers.

For example, Anthropic's Claude strategy maps clearly to this model: Claude-powered coding flows in the IDE, `claude-code` as CLI-first agent control, and `claude.ai` for general chat and planning. In the Google ecosystem, teams combine Gemini Code Assist in the IDE, Gemini CLI-style terminal workflows, and the Gemini chat UI. Some third-party bundles (including Antigravity-style setups) package these same three interfaces together: editor plugin + Electron chat + CLI.

| Vendor                  | IDE plugin / extension | CLI agent interface | Standalone chat UI | Notes |
|-------------------------| --- | --- | --- | --- |
| Anthropic (Claude Code) | [Claude Code IDE integrations](https://docs.anthropic.com/en/docs/claude-code/ide-integrations) | [Claude Code (GitHub)](https://github.com/anthropics/claude-code) | [Claude](https://claude.ai/) | Strong CLI-first agent workflow with coding focus |
| Google  (Antigravity)   | [Gemini Code Assist](https://developers.google.com/gemini-code-assist) | [Gemini CLI (GitHub)](https://github.com/google-gemini/gemini-cli) | [Gemini](https://gemini.google.com/) | Unified Gemini experience across editor, terminal, and chat |
| Microsoft / GitHub      | [GitHub Copilot](https://github.com/features/copilot) | [GitHub Copilot in the CLI](https://docs.github.com/en/copilot/github-copilot-in-the-cli) | [Microsoft Copilot](https://copilot.microsoft.com/) | Enterprise-friendly compliance and Microsoft ecosystem integration |
| OpenAI (Codex)          | [OpenAI Codex](https://openai.com/codex/) | [OpenAI API platform](https://platform.openai.com/docs) | [ChatGPT](https://chatgpt.com/) | OpenAI coding assistant stack across API and chat workflows |
| Cursor                  | [Cursor](https://www.cursor.com/) | [Cursor CLI docs](https://docs.cursor.com/) | [Cursor](https://www.cursor.com/) | AI-native IDE with agentic coding workflows |
| Cognition (Devin)       | [Devin](https://devin.ai/) | [Devin API](https://devin.ai/) | [Devin](https://devin.ai/) | Autonomous software engineer with collaborative web workspace |
| OpenCode                | [OpenCode](https://opencode.ai/) | [OpenCode CLI (GitHub)](https://github.com/sst/opencode) | [OpenCode](https://opencode.ai/) | Open tooling stack for terminal-first AI coding workflows |

**Practical recommendation:** start with these three surfaces from day one. Even for small teams, this setup reduces context switching, improves reproducibility, and supports both interactive development and automated agent runs.

