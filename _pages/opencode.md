---
permalink: /opencode/
title: "OpenCode Architecture"
author_profile: false
---

This page summarizes how OpenCode routes model traffic depending on the provider path you choose.

![OpenCode architecture diagram](/assets/images/opencode-architecture.svg)

## Reading the Diagram

- OpenCode is the entry point (CLI, TUI, and Web).
- You choose a provider/model route at the OpenCode layer.
- OpenCode Zen and OpenCode Go route through their corresponding gateways.
- The direct provider path is BYOK and connects straight to provider APIs.
- Both Zen and Go rely on shared OpenCode infrastructure and the link.com wallet layer.
- Credits and balances are managed per plan (Zen balance and Go credits).

## Ways to Use OpenCode

Based on the official OpenCode documentation and repository, the supported usage modes are:

1. Terminal-based interface (CLI / TUI)
2. Desktop App (Beta)
3. IDE Extension (official VS Code extension)

Note: the CLI/TUI image is an official screenshot from the OpenCode repository. The Desktop, IDE, and Web images below are generated illustrative captures.

### 1) CLI / TUI

Official terminal screenshot from the OpenCode repository.

![OpenCode CLI/TUI screenshot](/assets/images/opencode-capture-cli.png)

### 2) Desktop Application (Beta)

OpenCode is officially distributed as a desktop app for macOS, Windows, and Linux.

![OpenCode Desktop illustrative capture](/assets/images/opencode-capture-desktop.svg)

### 3) IDE Extension (VS Code)

OpenCode is also available as an official VS Code extension (`sst-dev.opencode`).

![OpenCode IDE extension illustrative capture](/assets/images/opencode-capture-ide.svg)

### 4) Web

OpenCode has an official web presence (`opencode.ai`) for docs, install, downloads, and project information.
Current official docs describe the coding interfaces as terminal, desktop app, and IDE extension.

![OpenCode web illustrative capture](/assets/images/opencode-capture-web.svg)

## How OpenCode Works with AGENTS.md and SKILL.md

OpenCode supports both rule-style instruction files (`AGENTS.md`) and reusable skill files (`SKILL.md`), but it handles them differently.

### AGENTS.md behavior (rules/instructions)

- OpenCode includes `AGENTS.md` instructions in model context as project rules.
- On startup, it resolves rule files with precedence:
	1. Local files while traversing up from the current directory (`AGENTS.md`, `CLAUDE.md`)
	2. Global rules at `~/.config/opencode/AGENTS.md`
	3. Claude fallback at `~/.claude/CLAUDE.md` (if compatibility is enabled)
- Within each category, first match wins, and `AGENTS.md` takes precedence over `CLAUDE.md`.
- Additional instruction files can be configured through `instructions` in `opencode.json`, and those are combined with `AGENTS.md` context.

### SKILL.md behavior (agent skills)

- Skills are discovered automatically from supported folders, but they are loaded on demand when the agent invokes the native `skill` tool.
- This means OpenCode does not inject full contents of every `SKILL.md` at session start. Instead, the agent first sees the available skill names and descriptions, then requests full content only when relevant.
- Discovery paths include:
	- Project: `.opencode/skills/<name>/SKILL.md` (and `.opencode/skill/...`)
	- Global: `~/.config/opencode/skills/<name>/SKILL.md`
	- Compatibility paths: `.claude/skills/...`, `~/.claude/skills/...`, `.agents/skills/...`, `~/.agents/skills/...`
- OpenCode walks up from the current working directory to the git worktree root for project-local discovery.

### What this means for OpenCode agents

- AGENTS-style rules shape baseline behavior for the whole session.
- Skills provide targeted, reusable capability packs that agents pull only when needed.
- This hybrid model keeps context lean while still allowing deep domain guidance at the moment of use.

### Practical recommendation

- Put stable project rules in `AGENTS.md`.
- Put reusable task playbooks in `.opencode/skills/<name>/SKILL.md`.
- Keep high-signal `description` fields in skills, because selection is driven by name and description before loading full content.

### Complete practical example (AGENTS.md + multiple SKILL.md)

This example shows a realistic project layout with one global instruction file and multiple specialized skills.

	ai-engineering-project/
	|- AGENTS.md
	|- opencode.json
	|- src/
	|  |- api/
	|  |- web/
	|- docs/
	|- .opencode/
	   |- skills/
		  |- code-review/
		  |  |- SKILL.md
		  |- docs-authoring/
		  |  |- SKILL.md
		  |- incident-triage/
			 |- SKILL.md

Suggested AGENTS.md:

	# AGENTS.md
    
	## Mission
	- Keep the repository stable, readable, and easy to review.
	- Prefer minimal changes with explicit rationale.
    
	## Engineering rules
	- Do not modify generated output directories.
	- Preserve front matter on documentation pages.
	- Keep edits in English.
	- When adding a new page, also update navigation and cross-links.
    
	## Quality gates
	- Validate links and headings after docs edits.
	- For code changes, prefer narrow scope and avoid unrelated refactors.

Suggested opencode.json:

	{
	  "instructions": [
		"./AGENTS.md"
	  ]
	}

Skill 1: .opencode/skills/code-review/SKILL.md

	---
	name: code-review
	description: Review changed files, list risks by severity, and propose concrete fixes.
	---
    
	# Code Review Skill
    
	## Scope
	- Analyze only changed files unless requested otherwise.
	- Prioritize correctness, regressions, security, and maintainability.
    
	## Output format
	- Findings first, sorted by severity.
	- Each finding includes file, line, impact, and fix suggestion.
	- If no findings exist, state that explicitly and mention residual risks.

Skill 2: .opencode/skills/docs-authoring/SKILL.md

	---
	name: docs-authoring
	description: Create or update technical documentation with consistent structure and actionable examples.
	---
    
	# Docs Authoring Skill
    
	## Scope
	- Write concise, task-oriented documentation.
	- Prefer examples that can be executed directly.
    
	## Rules
	- Keep title hierarchy clean (H2 then H3).
	- Add a practical example section when introducing a concept.
	- Add references for external claims.

Skill 3: .opencode/skills/incident-triage/SKILL.md

	---
	name: incident-triage
	description: Diagnose production issues using logs, hypotheses, and fast containment steps.
	---
    
	# Incident Triage Skill
    
	## Workflow
	1. Summarize symptoms and blast radius.
	2. Build top three hypotheses.
	3. Identify fastest safe containment action.
	4. Propose verification checks and rollback criteria.
    
	## Guardrails
	- Avoid destructive actions without explicit confirmation.
	- Document assumptions when evidence is incomplete.

How OpenCode uses this setup in practice:

1. Session starts and AGENTS.md is loaded as baseline behavior.
2. OpenCode discovers available skills from .opencode/skills.
3. The agent sees skill names and descriptions first.
4. When a task matches (for example, a review request), OpenCode loads only the matching SKILL.md content.
5. The final response combines AGENTS.md rules plus the selected skill guidance.

Example prompts that trigger each skill naturally:

- "Review this patch and list critical risks first." -> code-review
- "Draft a new docs section with steps and references." -> docs-authoring
- "We have a spike in 500 errors, propose triage and containment." -> incident-triage

### References

- OpenCode Rules docs: https://github.com/anomalyco/opencode/tree/dev/packages/web/src/content/docs/rules.mdx
- OpenCode Skills docs: https://github.com/anomalyco/opencode/tree/dev/packages/web/src/content/docs/skills.mdx
- OpenCode tools (`skill`): https://github.com/anomalyco/opencode/tree/dev/packages/web/src/content/docs/tools.mdx
- OpenCode skill loader implementation: https://github.com/anomalyco/opencode/tree/dev/packages/opencode/src/skill/index.ts
- OpenCode skill tool implementation: https://github.com/anomalyco/opencode/tree/dev/packages/opencode/src/tool/skill.ts

## Sources

- OpenCode repository: https://github.com/anomalyco/opencode
- OpenCode README (modes + install): https://raw.githubusercontent.com/anomalyco/opencode/dev/README.md
- VS Code extension listing (`sst-dev.opencode`): https://marketplace.visualstudio.com/items?itemName=sst-dev.opencode
