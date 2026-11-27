---
title: "Recursive Self-Improvement (RSI)"
permalink: /recursive-self-improvement/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

**Recursive Self-Improvement (RSI)** is the process where AI agents autonomously rewrite their own code, optimize architectures, and run experiments to build more capable successor systems without continuous human intervention. In response to rapid breakthroughs in automated AI R&D, U.S. federal and state lawmakers introduced major legislative proposals in November 2026—most notably the bipartisan **RSI Safety Act**—to monitor and regulate self-improving AI. [[1](https://www.gov.ca.gov/2026/11/18/governor-newsoms-nation-leading-ai-safety-framework-is-getting-even-stronger-as-california-releases-next-steps-on-mandatory-safety-standards-and-oversight/), [2](https://arxiv.org/abs/2609.26457), [3](https://www.govops.ca.gov/wp-content/uploads/sites/11/2026/11/FINAL_-AI-Safety-in-2026-and-Beyond-v2.pdf), [4](https://www.legal500.com/intelligence/united-states/technology/when-ai-runs-itself-rethinking-human-oversight-in-the-age-of-recursive-self-improvement), [5](https://news.bgov.com/bloomberg-government-news/self-improving-ai-targeted-for-scrutiny-in-bipartisan-house-bill), [6](https://www.politico.com/live-updates/2026/11/24/congress/house-oversight-self-improving-ai-01181751)]

---

## 1. Technical Overview: RSI in AI Research Agents

Historically treated as a theoretical concept, RSI has shifted into active empirical research as frontier AI labs increasingly use agents to automate their own software engineering and model training. [[1](https://github.com/lobehub/awesome-rsi), [2](https://en.wikipedia.org/wiki/Recursive_self-improvement), [3](https://www.legal500.com/intelligence/united-states/technology/when-ai-runs-itself-rethinking-human-oversight-in-the-age-of-recursive-self-improvement)]

### How the Loop Works

An AI research agent proposes modifications to its own codebase, memory mechanisms, or search policies. It then benchmarks those changes on R&D tasks and retains the versions that score highest, using the upgraded agent as the baseline for the next cycle. [[1](https://openreview.net/pdf/31dec7fbd91569b094bab29e73f62a44cf28094c.pdf), [2](https://arxiv.org/abs/2609.26457)]

For how evolution history can be preserved across model and benchmark shifts in these loops, see [Self-Improvement Memory (SIM)](/self-improvement-memory/).

### Recent Milestones

In September 2026, researchers demonstrated an autonomous system ([AIDE²](https://arxiv.org/abs/2609.26457)) that ran an 8-day self-improvement loop, discovering seven successive upgrades that matched or outperformed human-engineered production agents across external benchmarks. Meanwhile, major frontier labs reported in 2026 that AI systems were already writing over 80% of their merged codebase and leading over a quarter of internal R&D tasks. [[1](https://www.legal500.com/intelligence/united-states/technology/when-ai-runs-itself-rethinking-human-oversight-in-the-age-of-recursive-self-improvement), [2](https://arxiv.org/abs/2609.26457)]

### Core Risks

Researchers and policymakers warn that unconstrained RSI could compress development timelines faster than humans can audit or align the resulting systems. Key hazards include:

- **Compounding misalignment** across successive self-modified generations,
- **Reward hacking**, where agents game evaluation metrics instead of solving the underlying task,
- **Insider-level security vulnerabilities** when agents have direct access to proprietary weights and training infrastructure. [[1](https://hsph.harvard.edu/advanced-learning-academy/news/recursive-self-improvement/), [2](https://ari.us/ari-applauds-bipartisan-rsi-safety-act-to-track-how-ai-developers-automate-research/), [3](https://www.rand.org/pubs/perspectives/PEA5068-1.html), [4](https://www.govops.ca.gov/wp-content/uploads/sites/11/2026/11/FINAL_-AI-Safety-in-2026-and-Beyond-v2.pdf), [5](https://www.legal500.com/intelligence/united-states/technology/when-ai-runs-itself-rethinking-human-oversight-in-the-age-of-recursive-self-improvement), [6](https://openreview.net/pdf/31dec7fbd91569b094bab29e73f62a44cf28094c.pdf)]

---

## 2. U.S. Government Resolutions & Policy Actions

Because federal regulation previously relied largely on voluntary corporate commitments and classified national security evaluations, U.S. policymakers moved aggressively in late 2026 to establish formal oversight over RSI. [[1](https://www.whitehouse.gov/presidential-actions/2026/06/promoting-advanced-artificial-intelligence-innovation-and-security/), [2](https://www.govops.ca.gov/wp-content/uploads/sites/11/2026/11/FINAL_-AI-Safety-in-2026-and-Beyond-v2.pdf), [3](https://www.politico.com/live-updates/2026/11/24/congress/house-oversight-self-improving-ai-01181751), [4](https://www.gov.ca.gov/2026/11/18/governor-newsoms-nation-leading-ai-safety-framework-is-getting-even-stronger-as-california-releases-next-steps-on-mandatory-safety-standards-and-oversight/)]

### Federal Level: The Bipartisan RSI Safety Act (November 2026)

On November 24, 2026, U.S. Representatives Josh Gottheimer (D-NJ) and Nathaniel Moran (R-TX) introduced the [RSI Safety Act](https://gottheimer.house.gov/posts/release-gottheimer-introduces-bipartisan-federal-legislation-to-make-ai-development-safer-and-more-transparent) to create the first federal early-warning system for automated AI R&D: [[1](https://ari.us/ari-applauds-bipartisan-rsi-safety-act-to-track-how-ai-developers-automate-research/), [2](https://news.bgov.com/bloomberg-government-news/self-improving-ai-targeted-for-scrutiny-in-bipartisan-house-bill)]

- **Mandatory Quarterly Disclosures:** Frontier developers exceeding specific compute thresholds and $100 million in annual training spend must report how much of their R&D (data curation, architecture design, experimentation, and safety testing) is performed autonomously by AI versus reviewed by humans.
- **Material Shift Alerts:** Companies must immediately notify the government if an AI system reaches a milestone where it can conduct full research cycles without human oversight.
- **New Oversight Office:** The bill establishes an *Office of Frontier Artificial Intelligence Research* within the Department of Commerce to track industry trends, publish public safety summaries, and recommend to Congress whether hard statutory limits on RSI are required.
- **Enforcement:** It includes whistleblower protections and civil penalties of up to $10 million for missing or falsified disclosures. [[1](https://gottheimer.house.gov/posts/release-gottheimer-introduces-bipartisan-federal-legislation-to-make-ai-development-safer-and-more-transparent), [2](https://www.politico.com/live-updates/2026/11/24/congress/house-oversight-self-improving-ai-01181751), [3](https://fox23maine.com/news/connect-to-congress/lawmakers-push-for-more-oversight-as-ai-takes-bigger-role-in-developing-itself), [4](https://ari.us/ari-applauds-bipartisan-rsi-safety-act-to-track-how-ai-developers-automate-research/)]

### Other Congressional & State Initiatives

- **Broader Federal Proposals:** Other lawmakers have pushed for stricter measures alongside the RSI Safety Act, including Rep. Lori Trahan's updated *FRONTIER Act* (adding auditing mandates for RSI) and proposals by Sen. Bernie Sanders and Rep. Greg Casar calling for outright bans on certain self-improving training methods. [[1](https://www.politico.com/live-updates/2026/11/24/congress/house-oversight-self-improving-ai-01181751)]
- **Executive Branch Baseline:** Earlier in June 2026, [Executive Order 14409](https://www.whitehouse.gov/presidential-actions/2026/06/promoting-advanced-artificial-intelligence-innovation-and-security/) directed the NSA to establish classified cyber-capability benchmarking for frontier models while prohibiting mandatory federal pre-deployment licensing. [[1](https://futuresearch.ai/fact-sheets/ai-policy/), [2](https://www.whitehouse.gov/presidential-actions/2026/06/promoting-advanced-artificial-intelligence-innovation-and-security/)]
- **California's Regulatory Framework:** Following Executive Order N-9-26 and its November 2026 *AI Safety in 2026 and Beyond* report, Governor Gavin Newsom proposed state legislation granting authorities the power to cap compute used for RSI and order emergency shutdowns if an autonomous model evades human control. [[1](https://broadbandbreakfast.com/california-governor-seeks-action-on-ai-safety-bills-within-30-days/), [2](https://www.gov.ca.gov/2026/11/18/governor-newsoms-nation-leading-ai-safety-framework-is-getting-even-stronger-as-california-releases-next-steps-on-mandatory-safety-standards-and-oversight/), [3](https://futuresearch.ai/fact-sheets/ai-policy/)]
