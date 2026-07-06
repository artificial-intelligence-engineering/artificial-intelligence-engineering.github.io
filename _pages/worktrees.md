---
title: "Worktrees"
permalink: /worktrees/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

## Why worktrees matter for AI Agents

In modern AI coding environments, such as Claude Code or GitHub Copilot, worktrees provide the ultimate desk for your agents.

1. **Parallel Processing**: You can launch multiple AI agents simultaneously. Each agent gets its own worktree on its own branch, which means one agent's file edits never bleed into another agent's session.
2. **No Context Pollution**: Switching branches while an AI agent is analyzing your codebase can cause memory and context loss. Worktrees eliminate this issue by keeping each agent's environment completely separated at the filesystem level.
3. **Clean Task Division**: You can have one agent research a refactor in one worktree while another agent actively fixes a production bug in a separate folder.

## The problem with switching branches

In our day-to-day work as developers, it is common to handle more than one task at a time. This can happen because a bug is discovered and must be fixed as soon as possible, because the client decides that something else has higher priority within the sprint, or because we need to test work completed by another team member.

When this happens, we have to leave what we are doing on one Git branch and switch to another branch, which creates the risk of losing our work if we do not save it first. To avoid this, we usually commit with a note that the work is still in progress, create a patch, or store changes with `git stash`. None of these options is completely safe or convenient.

**git stash** temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on. Stashing is handy if you need to quickly switch context and work on something else, but you're mid-way through a code change and aren't quite ready to commit. The git stash command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy.

```
$ git status
On branch main
Changes to be committed:

    new file:   style.css

Changes not staged for commit:

    modified:   index.html

$ git stash
Saved working directory and index state WIP on main: 5002d47 our new homepage
HEAD is now at 5002d47 our new homepage

$ git status
On branch main
nothing to commit, working tree clean
```
At this point you're free to make changes, create new commits, switch branches, and perform any other Git operations; then come back and re-apply your stash when you're ready.

Note that the stash is local to your Git repository; stashes are not transferred to the server when you push.

You can reapply previously stashed changes with **git stash pop**:

```
$ git status
On branch main
nothing to commit, working tree clean

$ git stash pop
On branch main
Changes to be committed:

    new file:   style.css

Changes not staged for commit:

    modified:   index.html

Dropped refs/stash@{0} (32b3aa1d185dfe6d57b3c3cc3b32cbf3e380cc6a)
```
Popping your stash removes the changes from your stash and reapplies them to your working copy.

Alternatively, you can reapply the changes to your working copy and keep them in your stash with **git stash apply**:

```
$ git stash apply
On branch main
Changes to be committed:

    new file:   style.css

Changes not staged for commit:

    modified:   index.html
```
This is useful if you want to apply the same stashed changes to multiple branches.
