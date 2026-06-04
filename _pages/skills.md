---
title: "Agent Skills"
permalink: /skills/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

## What Are Agent Skills?

The problem with many AI assistants is that each conversation starts from scratch. This forces developers to spend the first minutes of every task providing context: project conventions, folder structure, or code boundaries.

Agent Skills eliminate that repetition. They allow AI agents to discover and reuse repository information on their own. As a result, AI stops starting from zero and becomes integrated into the workflow with the context already defined by the project itself.

But what exactly are they?
The official definition describes them as folders with instructions and resources that agents consult to be more accurate. In practice, an Agent Skill is a container of specialized knowledge that AI uses only when necessary.

This "load on demand" approach is key: it prevents saturating the AI context window with irrelevant rules, saving time and improving response accuracy.

This container can include:

- Specific instructions for your workflow.
- Scripts and real code examples.
- Reference documentation.

Its structure is simple:

```text
my-skill/
├── SKILL.md (The "brain" of the skill)
├── scripts/
├── references/
└── assets/
```

The most important file is `SKILL.md`. That is where you define what to do and under which conditions the agent should activate it. Because it is a simple format, it is easy for teams to read, can be versioned in Git, and can be shared across projects without friction.

## A Real Example

Imagine you want AI to stop using generic HTML and start using your own components. The `SKILL.md` file would include activation conditions (or guiding questions) so the AI knows when to act:

```text
---
name: design-system-compliance
description: Ensures the use of components from the internal UI library.
---

# Design System Compliance

## Purpose
Ensure that all interface code respects the corporate design system, maintaining visual consistency, component reuse, and quality standards across the application.

## Behavior
- Automatically replace basic HTML tags (<button>, <input>) with corporate components (<CustomButton>, <CustomInput>).
- Apply only design-system variables for colors, typography, and spacing.
- Use only the organization's official icon package.

## Restrictions
- Do not use inline styles.
- Do not use manually defined hexadecimal colors.
- Avoid any implementation that is not aligned with the corporate component library.

## Activation Conditions
This skill should be applied automatically when at least one of the following conditions is met:
- The request asks for creation or modification of interface components.
- Work is being done on `.jsx` or `.tsx` files.
- Basic HTML tags are detected that can be replaced by design-system components.
```

Result: instead of correcting the AI every time it generates a button that does not follow your rules, AI already knows what to do from the start. Knowledge stops living in the prompt and becomes part of the project itself in a transparent and auditable way.

## How Does an Agent Use Skills?

An agent does not load all rules at once, because that would be inefficient and would mix unnecessary information. Instead, it uses a progressive disclosure system split into three steps:

1. **Discovery:** The agent scans titles and descriptions of available skills. It knows what tools it has, but has not read detailed instructions yet.
2. **Activation:** Only when your request matches one of those descriptions does the agent decide to "open" that folder and read the `SKILL.md` file with all detailed instructions.
3. **Execution:** If the task requires specific files (for example, a cleanup script), the agent loads them only at that moment.

## Why Does This Change the Game?

The most relevant part of this system is that it is not a closed solution. The `SKILL.md` format (maintained at `agentskills.io`) was created to establish a common standard for packaged knowledge.

Today, this format is being adopted across the ecosystem: from coding assistants to cloud platforms. This creates a clear strategic advantage: technological independence.

By adopting an open standard:

- You avoid lock-in: your team's knowledge is not trapped in one specific tool; it belongs to the project.
- You optimize effort: define a skill once and run it across multiple assistants or IDEs.
- You future-proof your workflow: any new tool that adopts the standard will understand your way of working from day one.

## Industry Backing: The Microsoft Case

This approach already has support from major companies. A strong example is Microsoft's official repository, where they publish hundreds of Agent Skills for Azure.

The objective is to solve a critical problem: AI agents do not always have up-to-date or precise information about complex cloud services. Instead of letting AI improvise or interpret extensive documentation, these skills provide:

- Exact commands and valid parameters.
- Secure configuration instructions.
- Optimized usage examples.

This way, AI does not "guess" how to work with Azure; it consults expert knowledge packaged directly by Microsoft.

## References

- Agent Skills format and ecosystem: [agentskills.io](https://agentskills.io/)
- Microsoft Agent Skills for Azure: [azure-ai-agents-skills](https://github.com/Azure/azure-ai-agents-skills)
- Anthropic engineering perspective on long-running agents: [Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)

