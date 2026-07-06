---
title: "Agent Loop"
permalink: /agent-loop/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

The concept of the "agent loop" evolved alongside autonomous AI. Developers such as **Simon Willison**, co-creator of Django, helped popularize the early definition that an LLM agent runs tools in a loop to achieve a goal.

Note: see Simon Willison's article, <a href="https://simonwillison.net/2025/May/22/tools-in-a-loop/">Tools in a Loop</a>.

Around the same time, three people independently arrived at the same idea and gave it the same name. **Peter Steinberger** of the OpenClaw Project, **Boris Cherny**, who leads Claude Code at Anthropic, and **Addy Osmani**, an engineer on Google Chrome, described the same shift: the professional steps out of the loop and builds the loop. In particular, the term Osmani used in his blog was **loop engineering**. His working definition is to replace yourself as the person writing prompts for the agent and instead design the system that does it on your behalf. The professional is no longer inside the loop giving instructions turn by turn. They are outside it, having built the mechanism that gives those instructions.

## The five pieces, and then notes

According to Addy Osmani, a loop needs five things and then one place to remember stuff:

1. Automations that go off on a schedule and do discovery and triage by themselves.
2. Worktrees so two agents working in parallel don't step on each other.
3. Skills to write down the project knowledge the agent would otherwise just guess.
4. Plugins and connectors to plug the agent into the tools you already use.
5. Sub-agents so one of them has the idea and a different one checks it.

Then the sixth thing, **the memory**. A markdown file, or a Linear board, anything that lives outside the single conversation and holds what's done and what is next. Sounds too dumb to matter. But it's the same trick every long-running agent depends on and I went into it in long-running agents: the model forgets everything between runs, so the memory has to be on disk and not in the context. The agent forgets, the repo doesn't.

As an example of this proposal, two of the major AI vendors are already implementing these six points; let’s see how OpenAI Codex and Antrophic Claude Code are approaching them:

| Primitive | Job in the loop | Codex app | Claude Code |
| --- | --- | --- | --- |
| Automations | Discovery + triage on a schedule | Automations tab: pick project, prompt, cadence, and environment; results land in a triage inbox; `/goal` for run-until-done | Scheduled tasks and cron, `/loop`, `/goal`, hooks, and GitHub Actions |
| Worktrees | Isolate parallel features | Built-in worktree per thread | `git worktree`, `--worktree`, isolation: worktree on a sub-agent |
| Skills | Codify project knowledge | Agent Skills (`SKILL.md`), invoked with `$name` or implicitly | Agent Skills (`SKILL.md`) |
| Plugins / connectors | Connect your tools | Connectors (MCP) plus plugins for distribution | MCP servers plus plugins |
| Sub-agents | Ideate and verify | Sub-agents defined as TOML in `.codex/agents/` | Task sub-agents in `.claude/agents/`, agent teams |
| State | Track what's done | Markdown or Linear via a connector | Markdown (`AGENTS.md`, progress files) or Linear via MCP |


## References

- [Peter Steinberger](https://steipete.me/)
- [Simon Willison](https://simonwillison.net/)
- [Boris Cherny](https://borischerny.com/)
- [Addy Osmani](https://addyosmani.com/blog/)

