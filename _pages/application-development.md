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

Application development involves providing a model with good prompts and necessary context. This layer requires rigorous evaluation. Good applications also demand good interfaces.

## Key Concepts

### Prompt Engineering

> Adapting an existing LLM for your task is called prompt engineering. It involves crafting the input to the model in a way that guides it to produce the desired output.

A prompt is the text instruction or question given to an AI system, such as a large language model, to produce an answer. 
It is the main way to direct how the model behaves, clarify the task, and establish the context of the exchange. 
Because prompt wording strongly influences output quality and relevance, selecting the appropriate prompt style for 
each use case is critical. 

Prompt engineering is the easiest and most common model adaptation technique. Unlike finetuning, prompt engineering guides a model's behavior. You can think of prompt engineering as human-to-AI communication: you communicate with AI models to get them to do what you want. Anyone can communicate, but not everyone can communicate effectively. Similarly, it's easy to write prompts but not easy to construct effective prompts. Some people argue that "prompt engineering" lacks the rigor to qualify as an engineering discipline. However, this doesn't have to be the case. Prompt experiments should be conducted with the same rigor as any ML experiment, with systematic experimentation and evaluation.

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

### System Prompt and User Prompt

Many model APIs give you the option to split a prompt into a system prompt and a user prompt. You can think of the system prompt as the task description and the user prompt as the task.

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

### Prompting evolution: Spec Driven

Prompt evolution in a spec-driven workflow is the maturation of AI-assisted engineering from unstructured prompting ("vibe coding") to structured, specification-first development. Instead of relying on a single, massive prompt to generate an entire feature, developers first define a rigorous engineering spec, and then allow AI agents to execute parallel tasks governed by that spec.

<a href="{% link _pages/spec-driven-dev.md %}" class="btn btn--primary btn--large">Open Spec Driven Development</a>

### Prompting evolution: Loop

The key sentence for understanding a agent loop is: "design loops that prompt your agents". A loop is a small program that prompts the agent, evaluates the response, decides whether the goal is met, and, if not, prompts again with what it has learned. It runs on a schedule rather than on human attention. Loops dispatch other loops.

To go deeper into loop engineering:

<a href="{% link _pages/agent-loop.md %}" class="btn btn--primary btn--large">Open Loop Engineering Guide</a>

### AGENTS.md & SKILL.md

Summary: AI agents use certain markdown files for discovery and behavior instructions, but there is no universal standard. AGENTS.md usually acts as the general guide for a repository or project, while SKILL.md usually defines reusable capabilities for specific platforms such as GitHub Copilot. If you want something portable across agents, the most common approach today is to combine a root-level AGENTS.md with regular human documentation (README.md, docs/, runbooks) and treat agent-specific files as an optional layer.

**1. Role of these markdown files**

**AGENTS.md**

It is usually used for:

- instructions for agents working in a repository
- editing conventions
- test, lint, and build commands
- quick architecture notes
- safety rules and operational limits
- expectations for pull requests, formatting, migrations, and related changes

In practice, it is similar to:

- an agent-oriented CONTRIBUTING.md
- a short operational manual to automate repository changes

Not every agent supports it officially, but several ecosystems adopt it or emulate it.

**SKILL.md**

It is usually used for:

- defining a specialized skill or capability
- reusable instructions for specific task types
- context, workflows, checklists, tools, and limits

It is more specific than AGENTS.md. It is usually not the repository guide, but rather a guide for executing one task type well.

Examples:

- a skill for SQL migrations
- a skill for releases
- a skill for payment debugging
- a skill for updating test snapshots

**2. Typical locations**

**AGENTS.md**

The most common approach is placing it at the repository root:

- /AGENTS.md

Some teams also use per-subdirectory variants, but that depends heavily on the tool.

**SKILL.md**

In GitHub Copilot skills, it usually lives inside a skill folder:

- .github/skills/<skill-name>/SKILL.md

Alternative locations exist depending on ecosystem or tooling, for example:

- .claude/skills/<skill-name>/SKILL.md
- .agents/skills/<skill-name>/SKILL.md
- ~/.copilot/skills/<skill-name>/SKILL.md

General pattern:

- one folder per skill
- SKILL.md inside that folder
- optional supporting resources in the same folder

**3. Differences between agents**

Yes, there are many.

- **Discovery:** not all agents look for the same files or paths. Some load AGENTS.md, others ignore it. Some support formal skills with SKILL.md, others rely only on system prompts or proprietary configuration.
- **When files are used:** some agents read instructions at startup, some reread files when changing folders, some load skills only when they detect relevance, and none can guarantee 100% compliance with those files.
- **Priority hierarchy:** these files do not usually have absolute priority. They are typically below the system prompt, product policies, explicit user instructions, and available permissions or tools.
- **Granularity:** AGENTS.md is usually repository or project level, SKILL.md is usually task or capability level, and other agents prefer YAML, JSON, or proprietary config instead of markdown.

**4. Most common approach today**

The most practical approach is layered:

- **Layer 1: Standard human documentation**
Keep these up to date: README.md, CONTRIBUTING.md, docs/architecture.md, docs/runbooks/, and reproducible scripts such as make test or npm run lint.
- **Layer 2: Root AGENTS.md**
Add a short operational AGENTS.md covering how to start, how to validate changes, restrictions, expected change style, sensitive code areas, and what must not be changed without review.
- **Layer 3: Platform-specific skills**
If your platform supports skills, add task-specific files such as .github/skills/<skill>/SKILL.md for repetitive specialized work.

**5. Least agent-dependent approach**

If you want maximum portability:

- put your primary source of truth in standard documentation: README.md, CONTRIBUTING.md, and docs/
- use AGENTS.md as a short operational summary
- use SKILL.md only as an extension, not as the only place for critical information

Why:

- README.md and docs/ are human-readable
- any file-access-capable agent can read them
- they are not vendor-specific
- they survive tooling changes better over time

SKILL.md can be very useful, but it is generally more ecosystem-dependent.

**6. Practical design rule**

Think about these files this way:

- README.md = what this is and how to use it
- CONTRIBUTING.md = how to contribute correctly
- AGENTS.md = how an agent should operate here
- SKILL.md = how to execute one specialized task very well

**7. What to include in each file**

Good content for AGENTS.md:

- setup commands
- test, lint, and build commands
- branch and pull request conventions
- minimal-change policy
- rules for migrations, secrets, and generated files
- sensitive modules
- verification checklist before finishing

Good content for SKILL.md:

- when to use the skill
- expected inputs
- procedure
- validations
- common errors
- completion criteria

**8. Important practical differences**

- **AGENTS.md is often more portable:** even when not officially supported, agents with repository access can still read it as useful documentation.
- **SKILL.md is often more structured but less portable:** it depends more on whether a platform provides a formal skill discovery system.
- **Markdown wins on simplicity:** most tools prefer markdown because it is easy to edit, versions well, is human-readable, and works both as prompt material and documentation.

## Basic Development Environment

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

## Development Process Approaches

In this section, we study different approaches for building AI products, including development models, tooling integration patterns, and quality-control workflows for human plus agent collaboration.

### The Karpathy method

The "Karpathy method," popularized by AI pioneer Andrej Karpathy, is a workflow for building a self-evolving, AI-powered "Second Brain." It uses an LLM (such as Claude Code, Gemini, and so forth) as an automated researcher that reads, synthesizes, and continuously structures raw information into a personal, interlinked markdown wiki. Traditional AI chats operate ephemerally—once a conversation ends, the context and accumulated knowledge disappear. The Karpathy method bypasses traditional Retrieval-Augmented Generation (RAG) constraints, resulting in a permanent, customized knowledge base that actually remembers everything you feed it. Because the wiki lives in plain text (.md files) on your local drive, it remains completely portable, secure, and future-proof.

![The Karpathy method workflow loop](/assets/images/karpathy-loop-generated.svg)

Karpathy's approach treats raw information as "source code" and the LLM as the "compiler" that turns it into a structured knowledge base, allowing your information to compound over time instead of getting lost in chat histories.

1. **Collect:** You gather raw sources—such as YouTube transcripts, articles, research papers, and notes—and drop them into a local directory. Many users rely on the Obsidian Web Clipper to easily save content.
2. **Compile:** You prompt a terminal-based LLM agent (like Claude Code) pointing it at your raw data. The agent reads the text, extracts key concepts, synthesizes them, and builds or updates an interconnected web of markdown pages.
3. **Query & Refine:** Rather than browsing manually, you query the AI directly about your wiki. You can ask it to identify contradictions, highlight knowledge gaps, or perform "linting" (health checks) to ensure your data stays organized and up to date.

### Robert C. Martin (Uncle Bob) AI Development Approach

Robert C. Martin (Uncle Bob) approaches AI development by treating language models like Claude Code or GitHub Copilot as junior developers. His process emphasizes strict, language-independent specification through ATDD (Acceptance Test-Driven Development) to keep the AI focused and prevent implementation details from leaking into the design.

His methodology for safer AI-assisted development revolves around several specific practices:

- **Strict ATDD (Acceptance Test-Driven Development):** He writes rigorous Given/When/Then specifications before allowing the AI to generate any code. These act as a portable, language-independent contract for the agent.
- **Constraining the AI:** Leaving an AI completely open-ended often degrades architecture quality and introduces hallucinated details. He limits scope with precise constraints and simple, explicit rules so the model computes logically instead of generating generic boilerplate.
- **Agent Filtering:** To reduce the model tendency to mix business logic with implementation details, he advocates using additional review layers (including AI-based review) to audit specifications before implementation.
- **Human-in-the-Loop Discipline:** Because AI-generated code can include subtle defects, human developers still need strong software engineering fundamentals to review, correct, and own the final system.

Useful references for this working style:

- [The Clean Coder Blog - Robert C. Martin](https://blog.cleancoder.com/)
- [Clean Coder resources and training](https://cleancoder.com/)
- [Given-When-Then and BDD/ATDD structure (Cucumber docs)](https://cucumber.io/docs/gherkin/reference/)

### Applying SOLID principles to AI

In the AI era, where code generation is cheap and understanding is expensive, SOLID is less about ceremony and more about preserving clarity, composability, and maintainability.

The Foundation We Built On

Let's run through the familiar set, but not as definitions you could pull from Wikipedia. Let's talk about what they actually meant in practice.

**Single Responsibility Principle**

This was the sanity rule. Keep your classes (or other similar code elements) from doing too much. If it has more than one reason to change, it will eventually collapse under its own weight. I learned this one early, often the hard way, cleaning up classes that had taken on the personality of their developer, a little of everything, in one chaotic pile.

**Open/Closed Principle**

The guiding star of extensibility: extend without modifying. In theory, that meant safety from regression and in many cases if done well it would help with regression and ongoing feature development. In reality, it meant endless debates about whether you were violating OCP every time you opened a file to fix something.

**Liskov Substitution Principle**

The quiet workhorse. Inheritance should make sense. If your subclass breaks expectations, you are not using polymorphism, you are just lying to your codebase.

**Interface Segregation Principle**

This was the rebellion against god interfaces. The countless times I've seen an `IThingManager` with thirty methods, half of which every implementation ignores. ISP was the call to split those monsters into sane, digestible contracts.

**Dependency Inversion Principle**

The rise of abstractions over implementations. This principle was both a blessing and a curse, the birthplace of dependency injection frameworks and inversion-of-control containers that we alternately loved and cursed. It gave structure but also a new layer of complexity.

**When SOLID Worked**

Over the years, I have seen SOLID absolutely save teams, including mine, from coding disasters. For example, when a project scaled from three developers to thirty, SOLID acted as the stabilizing force. It created a shared language around what good code meant.

It kept monoliths from turning to spaghetti. It made refactoring survivable. It let teams ship features faster without worrying that a small change in the billing module would trigger a cascade failure in authentication.

In essence, SOLID made code cooperative. It taught us to think in modules, contracts, and boundaries. Those were lessons worth keeping.

**When SOLID Became a Problem**

But for every clean, modular, testable success story, there is an over-engineered mess hiding behind the same banner. I have walked into codebases where every noun in the business domain had an interface, an abstract class, and two decorators, none of which did anything meaningful. All in the name of being SOLID.

Here is where it tends to go wrong:

- **Too many abstractions:** open for extension became never touch anything again. Layers of indirection were added to prevent change, not to enable it.
- **Framework fetishism:** dependency injection containers got treated like religion. If you were not injecting it, mocking it, or wrapping it in a factory, were you even a developer?
- **Premature architecture:** entire hierarchies were built for features that never came. Extensibility for the sake of hypotheticals.
- **Cognitive overhead:** code so modular that new developers spent a week tracing interfaces before finding the line that actually did something.

SOLID was meant to reduce complexity, but taken too far, it became its own source of it.

**The Shift: SOLID in the Age of AI-Generated Code**

The SOLID principles aren't just relevant in AI agent development. They might be essential.

S — Single Responsibility Principle
The best agentic systems I've built or worked with follow this principle strictly. Each agent in the system should have a single, well-defined responsibility. A ResearchAgent should gather information. A SummaryAgent should condense findings into a concise output. A CodeReviewAgent should analyse code for issues. When you build one God agent that researches, summarises, writes code, reviews it, sends emails, AND updates a project tracker, the quality of every single one of those tasks degrades. The agent tries to be everything and ends up being mediocre at all of it. Single responsibility for agents isn't just good architecture; it directly affects the quality of the AI's output. Smaller, focused agents produce better results because the system prompt, the context window, and the reasoning are all concentrated on one job.

O — Open/Closed Principle
A well-designed multi-agent system is one where you can add new agents without modifying the existing orchestration logic. The orchestrator that coordinates your agents should be closed for modification. You shouldn't have to rewrite the routing or coordination logic every time you need a new capability. Instead, you register a new specialised agent with its description and responsibilities, and the orchestrator can start delegating to it. The existing agents remain untouched. This is exactly the philosophy behind frameworks like LangGraph, CrewAI, and the Model Context Protocol (MCP) — they let you extend the system by plugging in new agents or servers rather than modifying the ones that already work.

L — Liskov Substitution Principle
In a multi-agent system, you should be able to swap one agent for another as long as it fulfils the same contract. If your orchestrator delegates summarisation to a SummaryAgent, you should be able to replace that agent with an improved version — perhaps one powered by a different model, or one that uses a different prompting strategy — without the orchestrator knowing or caring. The contract is: "give me text, I'll give you a summary." How the agent internally achieves that is its own business. This is also why it matters to have clean interfaces between agents. If your SummaryAgent can be backed by GPT-4, Claude, or a fine-tuned local model, and the rest of the system works regardless, you've achieved Liskov substitution at the agent level.

I — Interface Segregation Principle
When designing agentic systems, it's far better to have many focused agents than one Swiss Army knife agent. You should have a DataExtractionAgent, a ValidationAgent, and a FormattingAgent rather than one monolithic DataProcessingAgent that tries to handle everything based on a mode parameter. Why? Because each agent can have a tightly scoped system prompt, a focused set of examples, and a narrow context window. The LLM performs better when it has a clear, specific job. A general-purpose agent with a system prompt that reads like a novel ends up confused about which hat it's supposed to be wearing at any given moment. This is interface segregation applied to AI: many specialised agents with narrow responsibilities are better than one general-purpose agent that does everything poorly.

D — Dependency Inversion Principle
This is critical in agent architecture. Your orchestrator should depend on abstractions of agents, not on concrete implementations. If your orchestration logic is tightly coupled to a specific agent that uses a specific model with a specific prompt template, you've made the whole system rigid. Instead, define what an agent looks like in abstract terms — it takes an input, it returns an output, it has a description of what it does — and let the orchestrator depend on that abstraction. The concrete agent (which model it uses, how it prompts, what tools it has access to) is an implementation detail that gets injected. Tomorrow you might want to replace your Claude-powered ResearchAgent with one that calls a specialised fine-tuned model, or even a non-LLM heuristic agent. If your orchestrator depends on the abstraction, that swap is trivial. This is the same principle I was advocating for with InversifyJS years ago, and it's exactly the approach taken by agent frameworks that separate the agent interface from the agent implementation.

**What Remains Solid?**

In the end, SOLID was not just about code. It was about discipline. About having a mental model for systems that grow beyond a single developer's head.

But as AI tooling takes over more of the mechanical parts of design, the real question becomes:

Are we still designing for humans to understand the system, or for systems to understand themselves?

Further reading:

- [Reflection on SOLID Decades](https://compositecode.blog/2025/10/30/reflection-on-solid-decades/)
- [SOLID principles (Wikipedia)](https://en.wikipedia.org/wiki/SOLID)
- [Clean Architecture resources - Robert C. Martin](https://blog.cleancoder.com/)
