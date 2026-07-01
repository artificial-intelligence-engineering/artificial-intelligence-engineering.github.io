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
