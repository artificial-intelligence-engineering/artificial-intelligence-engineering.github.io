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

## Sources

- OpenCode repository: https://github.com/anomalyco/opencode
- OpenCode README (modes + install): https://raw.githubusercontent.com/anomalyco/opencode/dev/README.md
- VS Code extension listing (`sst-dev.opencode`): https://marketplace.visualstudio.com/items?itemName=sst-dev.opencode
