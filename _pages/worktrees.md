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

You are not limited to a single stash. You can run `git stash` several times to create multiple stashes, and then use `git stash list` to view them. By default, stashes are identified simply as a WIP (work in progress) on top of the branch and commit where you created the stash. After a while, it can be difficult to remember what each stash contains:

```bash
$ git stash list
stash@{0}: WIP on main: 5002d47 our new homepage
stash@{1}: WIP on main: 5002d47 our new homepage
stash@{2}: WIP on main: 5002d47 our new homepage
```

To provide more context, it is good practice to annotate your stashes with a description, using `git stash save "message"`:

```bash
$ git stash save "add style to our site"
Saved working directory and index state On main: add style to our site
HEAD is now at 5002d47 our new homepage

$ git stash list
stash@{0}: On main: add style to our site
stash@{1}: WIP on main: 5002d47 our new homepage
stash@{2}: WIP on main: 5002d47 our new homepage
```

By default, `git stash pop` reapplies the most recently created stash: `stash@{0}`.

You can choose which stash to re-apply by passing its identifier as the last argument, for example:

```bash
$ git stash pop stash@{2}
```
Git stash seems like a convenient solution at first glance. Quick, easy, and built right into Git. However, those who use it regularly often encounter frustrating limitations:

- **The Stash Stack of Confusion**

As stashes accumulate, they become increasingly difficult to manage. Which stash contains those UI changes from last Tuesday? What happens when you have multiple stashes with similar messages? The `git stash list` command might show something like:

```bash
$ git stash list
stash@{0}: On feature-x: Second stash
stash@{1}: On feature-x: First stash
```

But determining which stash contains specific changes becomes a guessing game.

- **Lost in Translation (and Restoration)**

Applying stashes can be error-prone, especially when dealing with specific stashes:

```bash
$ git stash apply stash@{1}
# Wait, did it work? Which changes were applied?
```

Moreover, using advanced stash options like `--all` can lead to unexpected behavior. Consider this real-world scenario:

```bash
$ git stash push --all  # Stashes untracked AND ignored files
$ git stash pop         # Error: could not restore untracked files from stash
```

Now you are stuck with some changes back and others still in the stash, a debugging nightmare.

- **The Context Switch Tax**

Each time you stash changes, switch branches, and then return, you force your brain to reload the mental context of what you were working on. This cognitive overhead adds up and reduces your overall productivity.

## Enter Git Worktree: The Better Alternative

The concept is beautifully simple. Instead of stashing changes to switch contexts, you create a separate working directory for each task:

```bash
# From your main repository folder
$ git worktree add ../project-hotfix hotfix-branch
```

This creates a new directory called "project-hotfix" with the "hotfix-branch" checked out, allowing you to work on both branches simultaneously without any stashing required.

With this approach, you get quick advantages:

- **True Parallel Development**
With worktrees, you can literally have **multiple branches open at the same time**, even in different editor windows. Need to compare how your feature looks against the main branch? No problem. You can run both versions side by side.

- **Shared Git Infrastructure**
Unlike having multiple clones of the same repository (another common workaround), worktrees share the same `.git` directory. This means:

- Less disk space used
- Shared object database and history
- Shared configuration
- No need to push and pull between local clones

- **Clean Mental Separation**
Each worktree represents a dedicated workspace for a specific task. This separation helps maintain focus and reduces the mental overhead of context switching.

## Getting Started with Git Worktree: A Step-by-Step Guide

### Prerequisites

- Git version 2.5 or newer
- Basic familiarity with Git branching

### Basic Workflow

#### Step 1: Create a new worktree for a specific branch

```bash
# Syntax: git worktree add
$ git worktree add ../project-feature feature-branch
```

This creates a new directory with the specified branch checked out.

#### Step 2: Work in either directory as needed

You can now freely switch between directories, working on different branches without stashing.

```bash
# Work on your main branch
$ cd original-project
# Make some changes, commit

# Work on your feature branch
$ cd ../project-feature
# Make some changes, commit
```

#### Step 3: List your active worktrees

```bash
$ git worktree list
/home/dev/original-project    abcd123 [main]
/home/dev/project-feature     efgh456 [feature-branch]
```

#### Step 4: Clean up when finished

When you are done with a particular worktree, you can remove it:

```bash
$ git worktree remove ../project-feature
# OR clean up any worktrees with deleted directories
$ git worktree prune
```

## Real-World Scenario: The Bug Fix Interruption

Let's see how this works in practice. You are developing a new feature when an urgent bug fix is needed:

```bash
# You're working on a feature in your main directory
# Urgent bug fix needed on production!

# Create a worktree for the hotfix
$ git worktree add ../hotfix-workspace hotfix-branch

# Navigate to the hotfix directory
$ cd ../hotfix-workspace

# Fix the bug, commit and push
$ git commit -am "Fix critical production issue"
$ git push

# Return to your feature work without missing a beat
$ cd ../original-project
# Continue where you left off, no stashing required!
```

## Best Practices for Git Worktree

- Use a consistent naming convention for your worktree directories
- Keep worktrees organized in a parent directory
- Regularly prune unused worktrees to avoid clutter
- Consider IDE integration for seamless switching between worktrees
- Use worktrees for long-running parallel tasks rather than quick context switches

## When to Stick with Stash

While worktrees are powerful, stashing still has its place for:

- Very quick, temporary changes
- Situations where disk space is extremely limited
- Simple checkpoints that do not require a full context switch

## Conclusions

Worktrees are one of the most practical foundations for parallel AI-assisted development. Instead of forcing one branch and one context per repository folder, they let teams run multiple streams of work at once with clear isolation. This is exactly the operating model modern AI agents need: separate task contexts, predictable file state, and minimal interference between parallel edits.

In real workflows, many AI coding agents can be used effectively with worktrees because they run against the current directory context. A common pattern is one agent session per worktree (for example, feature work in one directory and urgent fixes in another), while keeping a shared Git object database underneath.

Examples of tools and integrations that support or align well with worktree-based workflows:

- GitHub Copilot (VS Code and cloud/local agent workflows): <a href="https://docs.github.com/en/copilot" target="_blank">GitHub Copilot documentation</a>
- Claude Code (agentic coding from the terminal/editor context): <a href="https://code.claude.com/docs/en/overview" target="_blank">Claude Code overview</a>
- VS Code plugin: <a href="https://marketplace.visualstudio.com/items?itemName=gitworktrees.git-worktrees" target="_blank">Git Worktrees (gitworktrees.git-worktrees)</a>
- VS Code plugin: <a href="https://marketplace.visualstudio.com/items?itemName=philstainer.git-worktree" target="_blank">Git Worktree (philstainer.git-worktree)</a>
- VS Code plugin: <a href="https://marketplace.visualstudio.com/items?itemName=codeinklingon.git-worktree-menu" target="_blank">Git Worktree Menu (codeinklingon.git-worktree-menu)</a>

Key reference for the underlying Git model:

- <a href="https://git-scm.com/docs/git-worktree" target="_blank">git-worktree official documentation</a>

