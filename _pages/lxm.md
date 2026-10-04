---
title: "LxM Ecosystem Table"
permalink: /lxm/
layout: splash
---

<nav class="lxm-toc" aria-label="Ecosystem navigation">
  <strong>Ecosystems</strong>
  <ul>
    <li><a href="#ecosystem-openai">OpenAI</a></li>
    <li><a href="#ecosystem-google">Google</a></li>
    <li><a href="#ecosystem-meta">Meta</a></li>
    <li><a href="#ecosystem-microsoft">Microsoft</a></li>
    <li><a href="#ecosystem-anthropic">Anthropic</a></li>
    <li><a href="#ecosystem-mistral">Mistral AI</a></li>
    <li><a href="#ecosystem-xai">xAI</a></li>
    <li><a href="#ecosystem-cohere">Cohere</a></li>
    <li><a href="#ecosystem-alibaba">Alibaba (Qwen)</a></li>
    <li><a href="#ecosystem-deepseek">DeepSeek</a></li>
    <li><a href="#ecosystem-aws">AWS</a></li>
    <li><a href="#ecosystem-ai21">AI21 Labs</a></li>
    <li><a href="#ecosystem-minimax">MiniMax</a></li>
    <li><a href="#ecosystem-moonshot">Moonshot AI</a></li>
    <li><a href="#ecosystem-nvidia">NVIDIA</a></li>
    <li><a href="#ecosystem-writer">Writer</a></li>
    <li><a href="#ecosystem-zai">Z.AI</a></li>
    <li><a href="#ecosystem-opencode">Opencode</a></li>
  </ul>
</nav>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    var toc = document.querySelector(".lxm-toc");
    if (!toc) {
      return;
    }

    var links = toc.querySelectorAll("a[href^='#ecosystem-']");

    Array.prototype.forEach.call(links, function (link) {
      link.addEventListener("click", function (event) {
        var hash = link.getAttribute("href");
        var target = document.querySelector(hash);
        if (!target) {
          return;
        }

        event.preventDefault();

        // Offset keeps the target row fully visible below the sticky TOC.
        var stickyOffset = toc.offsetHeight + 12;
        var targetTop = target.getBoundingClientRect().top + window.pageYOffset;

        window.scrollTo(0, Math.max(0, targetTop - stickyOffset));

        if (history.pushState) {
          history.pushState(null, "", hash);
        } else {
          window.location.hash = hash;
        }
      });
    });
  });
</script>

<table class="lxm-table lxm-ecosystem-table">
  <colgroup>
    <col style="width: 12%;">
    <col style="width: 24%;">
    <col style="width: 16%;">
    <col style="width: 12%;">
    <col style="width: 36%;">
  </colgroup>
  <thead>
    <tr>
      <th scope="col">Ecosystem</th>
      <th scope="col">Model</th>
      <th scope="col" style="white-space: nowrap;">Release Date</th>
      <th scope="col">Status</th>
      <th scope="col">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row" id="ecosystem-openai"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=chatgpt.com&sz=128" alt="OpenAI / ChatGPT logo" loading="lazy">OpenAI</span></th>
        <td>
            GPT-1
        </td>
        <td>
            June, 2018
        </td>
        <td>
            Active
        </td>
        <td>
            Trained with BookCorpus 4.5 GB of text, from 7,000 unpublished books of various genres.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-2
        </td>
        <td>
            February, 2019
        </td>
        <td>
            Active
        </td>
        <td>
            Trained with WebText: 40 GB of text, 8 million documents, from 45 million webpages upvoted on Reddit.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-3
        </td>
        <td>
            May, 2020
        </td>
        <td>
            Active
        </td>
        <td>
            Trained with 499 billion tokens consisting of CommonCrawl (570 GB), WebText, English Wikipedia, and two books corpora 
            (Books1 and Books2)
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-3.5
        </td>
        <td>
            March, 2022
        </td>
        <td>
            Active
        </td>
        <td>
            Undisclosed
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-4
        </td>
        <td>
            March, 2023
        </td>
        <td>
            Active
        </td>
        <td>
            Undisclosed
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-4o
        </td>
        <td>
            May, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Undisclosed
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-4.5
        </td>
        <td>
            February, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Undisclosed
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
           GPT-4.1 
        </td>
        <td>
            April, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Undisclosed
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
           GPT-5
        </td>
        <td>
           August, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Undisclosed
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.1
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental GPT-5 update listed in the ChatGPT model timeline on Wikipedia.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.2
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Follow-up GPT-5 release listed in the ChatGPT model timeline; discontinued in ChatGPT as of June 12, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.3
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Discontinued
        </td>
        <td>
            GPT-5.3 generation (comprising GPT-5.3-Codex and GPT-5.3 Instant) listed in the ChatGPT model timeline.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.3-Codex
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Coding-specialized GPT-5.3 variant listed on the ChatGPT page.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.3 Instant
        </td>
        <td>
            March, 2026
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Fast-response variant in the GPT-5.3 branch released in March 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.4
        </td>
        <td>
            March, 2026
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Enterprise-focused GPT-5 update with improved autonomous computer and external tool use.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.5
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Designed for complex, multi-step professional work including agentic coding and computer use.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.5-Cyber
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Cyber-defense specialized variant of GPT-5.5 listed in the ChatGPT model versions table.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.6 Series
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Three-tier GPT-5.6 family (Luna, Terra, and Sol) previewed on June 26, 2026 and publicly released on July 9, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.6 Sol
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Flagship GPT-5.6 tier publicly released on July 9, 2026 for complex reasoning, coding, and agentic workflows.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.6 Terra
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Balanced GPT-5.6 intermediate tier publicly released on July 9, 2026 with GPT-5.5-class quality at lower cost.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.6 Luna
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Fast, budget-oriented GPT-5.6 tier publicly released on July 9, 2026 for high-volume and latency-sensitive workloads.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.6-Cyber
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Cybersecurity-focused GPT-5.6 variant launched on August 10, 2026 for defensive security tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-6 Astra
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Flagship GPT-6 tier released on September 4, 2026 (previewed September 3) using a looped-transformer reasoning architecture.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-6 Sol
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            High-capability GPT-6 tier released on September 22, 2026 alongside GPT-6 Luna.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-6 Luna
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Efficiency-focused tier of the GPT-6 family released on September 22, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-6.1 Sol
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Released on September 29, 2026 with near-Astra intelligence at lower per-task cost.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-6.1 Astra
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Announced
        </td>
        <td>
            Announced GPT-6.1 frontier tier whose public release was delayed in late September 2026 for safety alignment review.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-4 Turbo
        </td>
        <td>
            November, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Earlier lower-cost GPT-4 generation that preceded GPT-4.1 and GPT-4o families.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-4o mini
        </td>
        <td>
            July, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Cost-efficient GPT-4o variant for high-throughput and latency-sensitive use cases.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            o1-preview
        </td>
        <td>
            September, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Early reasoning-model preview that introduced explicit long-thought style inference.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            o1-mini
        </td>
        <td>
            September, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Smaller reasoning-focused model optimized for lower cost.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            o1
        </td>
        <td>
            December, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Production reasoning model for complex coding, math and multi-step planning.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            o3-mini
        </td>
        <td>
            January, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Fast and efficient reasoning model for routine analytical workloads.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            o3
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Higher-capability reasoning model tier for difficult multi-step tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            o4-mini
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Latest mini reasoning family focused on strong capability at low cost and latency.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            gpt-oss-20b
        </td>
        <td>
            August, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            21B-parameter Apache 2.0 open-weight reasoning model released by OpenAI and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            gpt-oss-120b
        </td>
        <td>
            August, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            117B-parameter Apache 2.0 open-weight reasoning model released by OpenAI and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-google"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://cdn.simpleicons.org/googlegemini" alt="Gemini logo" loading="lazy">Google</span></th>
        <td>
            LaMDA
        </td>
        <td>
           May, 2022
        </td>
        <td>
           Active
        </td>
        <td>
           Currently, LaMDA is not available to the public but is accessible to select developers for testing and refinement.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
             Bard
        </td>
        <td>
           March, 2023
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Google's first experimental chatbot service based on LaMDA
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
             PaLM
        </td>
        <td>
           April, 2022
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Pathways Language Model family that preceded PaLM 2 and Gemini.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
             PaLM 2
        </td>
        <td>
           May, 2023
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Successor to PaLM with stronger multilingual, reasoning and coding capabilities.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
             Gemini 1.0 Nano
        </td>
        <td>
           December, 2023
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Designed for on-device tasks and first available in Google's Pixel 8 Pro
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
             Gemini 1.0 Pro
        </td>
        <td>
           December, 2023
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Designed for a diverse range of tasks
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
             Gemini 1.0 Ultra
        </td>
        <td>
           	February, 2024
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Google's most powerful offering in the Gemini 1.0 family
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 1.5 Pro
        </td>
        <td>
           	February, 2024
        </td>
        <td>
           Discontinued
        </td>
        <td>
           As a successor to the 1.0 series of models, 1.5 Pro offers significantly increased context size 
           (up to 1 million tokens). It is designed to be the most capable model in the Gemini 1.5 family.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 1.5 Flash
        </td>
        <td>
           	May, 2024
        </td>
        <td>
           Discontinued
        </td>
        <td>
            Faster 1.5 variant announced at Google I/O 2024 for lower latency and cost.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 2.0 Flash
        </td>
        <td>
           January, 2025
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Developed by Google with a focus on multimodality, agentic capabilities, and speed; succeeded by Gemini 2.5 Flash.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 2.0 Flash Thinking
        </td>
        <td>
           December, 2024
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Reasoning-oriented Gemini 2.0 variant designed for longer multi-step problem solving.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 2.0 Pro (Experimental)
        </td>
        <td>
           February, 2025
        </td>
        <td>
           Discontinued
        </td>
        <td>
           Experimental higher-capability Gemini 2.0 tier succeeded by Gemini 2.5 Pro.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 2.0 Flash-Lite
        </td>
        <td>
           February, 2025
        </td>
        <td>
           Discontinued
        </td>
        <td>
           First Gemini Flash-Lite model designed for cost-efficiency and speed; succeeded by Gemini 2.5 Flash-Lite.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 2.5 Pro
        </td>
        <td>
           March, 2025
        </td>
        <td>
           Active
        </td>
        <td>
            Introduced first as 2.5 Pro Experimental and later made generally available in June 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 2.5 Flash
        </td>
        <td>
          April, 2025
        </td>
        <td>
           Active
        </td>
        <td>
            Default Gemini model announced at I/O 2025, optimized for speed with strong multimodal capability.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 2.5 Flash-Lite
        </td>
        <td>
          June, 2025
        </td>
        <td>
           Active
        </td>
        <td>
            Cost-efficient Flash variant introduced in the June 2025 Gemini 2.5 family expansion.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 2.5 Flash Image (Nano Banana)
        </td>
        <td>
          August, 2025
        </td>
        <td>
           Active
        </td>
        <td>
            Image generation/editing model publicly released as "Nano Banana" and later identified as Gemini 2.5 Flash Image.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemma
        </td>
        <td>
           February, 2024
        </td>
        <td>
           Active
        </td>
        <td>
           Lightweight open model family released by Google for local and research usage.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemma 2
        </td>
        <td>
           June, 2024
        </td>
        <td>
           Active
        </td>
        <td>
           Improved open model generation with stronger quality and efficiency.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemma 3
        </td>
        <td>
           March, 2025
        </td>
        <td>
           Active
        </td>
        <td>
           Multimodal open-weight Gemma generation (1B, 4B, 12B, 27B) with 128k context window, later expanded with Gemma 3n.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3 Pro
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            First Gemini 3 flagship model released on November 18, 2025 and shut down on March 9, 2026 in favor of Gemini 3.1 Pro.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3 Pro Image (Nano Banana Pro)
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Image generation and editing model released in preview on November 20, 2025 and made generally available on May 28, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3 Deep Think
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Preview
        </td>
        <td>
            Reasoning-focused Gemini 3 mode released on December 4, 2025 for Google AI Ultra subscribers and updated on February 12, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3 Flash
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Frontier-speed Gemini 3 model optimized for low latency and high throughput.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.1 Pro
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental Pro update for more complex reasoning and enterprise workloads.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.1 Flash Image (Nano Banana 2)
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Multimodal image and text generation model based on Gemini 3 Flash, released on February 26, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.1 Flash-Lite
        </td>
        <td>
            March, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Flash-Lite 3.1 release targeted at intelligence at scale with low-cost serving.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.5 Flash
        </td>
        <td>
            May, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            First Gemini 3.5 family release; frontier-speed model for agentic workflows and coding.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.1 Flash-Lite Image (Nano Banana 2 Lite)
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Cost-effective image generation model based on Gemini 3.1 Flash-Lite, released on June 30, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.5 Flash-Lite
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Released on July 21, 2026 based on Gemini 3.1 Flash-Lite for high-volume, latency-sensitive, and agentic workflows.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.6 Flash
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Released on July 21, 2026 with improvements in coding, multimodal processing, and token efficiency over Gemini 3.5 Flash.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.7 Flash
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Released on August 13, 2026 featuring core reasoning foundation improvements over Gemini 3.6 Flash.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3.8 Flash
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Released on September 2, 2026 as the latest Flash iteration, alongside the 3.8 Flash Cyber variant for Google's Fairwind Program.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 4 Argon
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Limited preview released on September 30, 2026 expanding output token capacity to 1M tokens with stronger coding and safety guardrails.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini Robotics
        </td>
        <td>
            March, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Vision-language-action model built on Gemini 2.0 for robotics control tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemma 4
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Apache 2.0 open-weight family (E2B, E4B, 26B MoE, 31B Dense) with native vision/audio support and up to 256k context window.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-meta"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://cdn.simpleicons.org/meta" alt="Meta logo" loading="lazy">Meta</span></th>
        <td>
            OPT 
        </td>
        <td>
            May, 2022
        </td>
        <td>
            Non-commercial
        </td>
        <td>
            GPT-3 architecture with some adaptations from Megatron. Uniquely, the training logbook written by the team was published.
            Corpus size 180 billion tokens.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Galactica
        </td>
        <td>
            November, 2022
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Research model family focused on scientific text generation; withdrawn shortly after release.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 1
        </td>
        <td>
            February, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Corpus size 1.4 trillion tokens
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Chameleon
        </td>
        <td>
            June, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Early-fusion multimodal model architecture from Meta Research for text+image generation.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 2
        </td>
        <td>
            July, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Corpus size 2 trillion tokens
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Code Llama
        </td>
        <td>
            August, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Code-specialized Llama 2 derivative tuned for code completion and infilling.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 3
        </td>
        <td>
            April, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Corpus size 15 trillion tokens
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 3.1
        </td>
        <td>
            July, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Corpus size 15.6 trillion tokens
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 3.2
        </td>
        <td>
            September, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Corpus size 9 trillion tokens
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 3.3
        </td>
        <td>
            December, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Corpus size 15 trillion tokens
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 4
        </td>
        <td>
            April, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Corpus size 40 trillion tokens
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 4 Maverick
        </td>
        <td>
            April, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Llama 4 released variant (17B active parameters, 128-expert MoE) listed as stable on Wikipedia.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 4 Scout
        </td>
        <td>
            April, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Llama 4 released variant (17B active parameters, 16-expert MoE) with very long context support.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Llama 4 Behemoth
        </td>
        <td>
            2025
        </td>
        <td>
            Announced
        </td>
        <td>
            Announced by Meta as a ~2T-parameter teacher model (288B active parameters) but not publicly released.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Muse Spark
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Proprietary multimodal reasoning model introduced on April 8, 2026 by Meta Superintelligence Labs to power Meta AI.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Muse Spark 1.1
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            First production release in Meta's Muse family (July 9, 2026) with a 1M context window for multimodal reasoning and coding.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Muse Spark 1.2
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Released on August 5, 2026 alongside the Muse Code terminal coding agent and made available via the Meta Model API.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Muse Glimmer
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weight 30B multimodal model released under Apache 2.0 on August 10, 2026 for local agentic and coding workloads.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Muse Spark 1.3
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Latest release in the Muse Spark model family, launched on September 2, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-microsoft"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=microsoft.com&sz=128" alt="Microsoft logo" loading="lazy">Microsoft</span></th>
        <td>
            Copilot
        </td>
        <td>
            September, 2023
        </td>
        <td>
           Active
        </td>
        <td>
            Based on Microsoft's Prometheus model, which is based on OpenAI's GPT-4 series
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-1
        </td>
        <td>
            June, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Small language model (1.3B) trained with textbook-quality data.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-1.5
        </td>
        <td>
            September, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Improved 1.3B small model with stronger reasoning and coding than Phi-1.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-2
        </td>
        <td>
            December, 2023
        </td>
        <td>
            Active
        </td>
        <td>
            1.4T tokens, 2.7B parameters, strong benchmark performance for its size.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-3
        </td>
        <td>
            April, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Phi-3-mini, Phi-3-small, Phi-3-medium and Phi-3-vision.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-3.5
        </td>
        <td>
            August, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Mid-cycle Phi update with stronger long-context and multilingual performance.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-4
        </td>
        <td>
            December, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Next-generation Phi family tuned for reasoning and agent workloads.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-4-mini
        </td>
        <td>
            February, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Lower-latency, lower-cost 3.8B Phi-4 variant for edge and high-throughput scenarios.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-4-multimodal
        </td>
        <td>
            February, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            5.6B multimodal Phi-4 variant supporting text, image, and audio understanding.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-4-reasoning
        </td>
        <td>
            April, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-focused 14B Phi-4 variant (alongside Phi-4-reasoning-plus and Phi-4-mini-reasoning) optimized for multi-step analytical tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-4-reasoning-vision-15B
        </td>
        <td>
            March, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            15B-parameter open-weights vision-language model released under MIT license capable of dynamically deciding when to invoke reasoning.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MAI-Thinking-1
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Microsoft AI flagship reasoning model. Medium-sized model that ranks among the strongest in its weight class, matching leading models on key software engineering benchmarks, showing advanced mathematical reasoning, and preferred over Claude Sonnet 4.6 in blind side-by-side human evaluations. Trained from the ground up on clean data without distillation from third-party models.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MAI-Code-1-Flash
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Inference-efficient agentic coding model tailored for and deeply integrated into GitHub Copilot, VS Code and the Microsoft stack. With 5 billion active parameters, it is positioned as comparable to Claude Haiku-class models at lower cost.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MAI-Image-2.5
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Image generation and editing model supporting world-class text-to-image and image editing tasks. Microsoft states it surpasses the Arena score of Nano Banana Pro.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MAI-Image-2.5-Flash
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Ultra-efficient Flash variant of MAI-Image-2.5 for lower-cost text-to-image and image editing workloads.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MAI-Transcribe-1.5
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Speech-to-text model described by Microsoft as state-of-the-art in transcription accuracy, five times faster than competing models, with built-in support for domain-specific terminology across 43 languages.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MAI-Voice-2
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            High-quality multilingual speech generation model across 15 languages, capable of adapting to a voice from a short sample and including safeguards against misuse.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MAI-Voice-2-Flash
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Announced
        </td>
        <td>
            Lower-cost, ultra-efficient upcoming variant of MAI-Voice-2 announced as coming soon.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-anthropic"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://cdn.simpleicons.org/anthropic" alt="Anthropic logo" loading="lazy">Anthropic</span></th>
        <td>
            Claude 1
        </td>
        <td>
            March, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            First public Claude generation focused on helpful and safer assistant behavior.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude 2
        </td>
        <td>
            July, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Major capability and context window increase over Claude 1.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Instant 1.2
        </td>
        <td>
            2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Lower-latency Claude 2-era variant used for fast and lower-cost responses.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude 2.1
        </td>
        <td>
            November, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Improved reliability and reduced hallucinations.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude 3 (Haiku, Sonnet, Opus)
        </td>
        <td>
            March, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Multimodal family balancing speed, cost and reasoning quality; retired following the Claude 4 and 4.5 releases.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude 3.5 Sonnet
        </td>
        <td>
            June, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Strong coding and agentic performance with computer use capability introduced in the October 2024 refresh; retired in October 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude 3.5 Haiku
        </td>
        <td>
            October, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Fast and cost-efficient model for high-throughput use cases; retired in February 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude 3.7 Sonnet
        </td>
        <td>
            February, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Hybrid reasoning model with extended thinking mode; retired in February 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Sonnet 4
        </td>
        <td>
            May, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Claude 4 generation tuned for coding, tool use and production workflows; retired in June 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4
        </td>
        <td>
            May, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Highest-capability Claude 4 tier for complex reasoning and agent tasks; retired in June 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.1
        </td>
        <td>
            August, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Incremental Opus 4 update released in August 2025 for agentic coding and reasoning; retired in June 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Sonnet 4.5
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Sonnet 4.5 release launched on September 29, 2025 for coding, agent building, and computer use.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Haiku 4.5
        </td>
        <td>
            October, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Haiku 4.5 release launched on October 15, 2025 focused on speed and cost efficiency.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.5
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Opus 4.5 release launched on November 24, 2025 with improved token efficiency and coding capabilities.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.6
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Opus 4.6 release launched on February 5, 2026 featuring agent teams and a 1M token context window in beta.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Sonnet 4.6
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Sonnet 4.6 release launched on February 17, 2026 with improved coding, computer use, and 1M context window in beta.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Mythos Preview
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Limited-availability cybersecurity preview launched on April 7, 2026 via Project Glasswing and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.7
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Opus 4.7 release launched on April 16, 2026 with stronger self-verification and high-resolution vision support.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.8
        </td>
        <td>
            May, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Opus 4.8 release launched on May 28, 2026 and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Fable 5
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Publicly released Mythos-class model launched on June 9, 2026 with additional safety guardrails for general use.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Mythos 5 (preview)
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Limited-availability version of the Fable 5 underlying model released on June 9, 2026 for cyberdefenders and infrastructure providers.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Sonnet 5
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Sonnet 5 release launched on June 24, 2026 with major improvements in planning, tool use, and coding at lower cost than Opus 4.8.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Fable 5 (redeployed)
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Access was restored globally on July 3, 2026 after redeployment with updated safeguards blocking reported classifier bypasses.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Mythos 5 (redeployed)
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Access was restored for approved organizations in July 2026, with expansion coordinated through Project Glasswing partners.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 5
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Opus-tier model in the Claude 5 generation, released on July 24, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Fable 5.1
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Updated Fable 5.1 release launched on September 1, 2026 with improved token efficiency and lower workload costs.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Mythos 5.1
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Limited-availability Mythos 5.1 update released on September 1, 2026 alongside Claude Fable 5.1.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 5.5
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            First model in the Claude 5.5 series, released on September 22, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Sonnet 5.5
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Sonnet-tier model in the Claude 5.5 generation, released on September 28, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-mistral"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://cdn.simpleicons.org/mistralai" alt="Mistral AI logo" loading="lazy">Mistral AI</span></th>
        <td>
            Mistral 7B
        </td>
        <td>
            September, 2023
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weights base model that accelerated the open model ecosystem.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mixtral 8x7B
        </td>
        <td>
            December, 2023
        </td>
        <td>
            Active
        </td>
        <td>
            Sparse MoE model with strong quality/latency tradeoff.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mixtral 8x22B
        </td>
        <td>
            April, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Larger MoE model for higher reasoning and generation quality.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Large 2
        </td>
        <td>
            July, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Flagship frontier model offered through API and cloud partners.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Pixtral 12B
        </td>
        <td>
            September, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Multimodal model line for image + text tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Large (24.02)
        </td>
        <td>
            February, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            First Mistral Large release for enterprise and multilingual/coding tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Small
        </td>
        <td>
            February, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Smaller companion model launched alongside Mistral Large (24.02).
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Codestral 22B
        </td>
        <td>
            May, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            First Mistral code-focused open-weight model family.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mathstral 7B
        </td>
        <td>
            July, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            STEM and mathematical reasoning-focused model.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Codestral Mamba 7B
        </td>
        <td>
            July, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Code model variant built on Mamba architecture for longer-context generation.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Ministral 3B
        </td>
        <td>
            October, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Small dense model in the Ministral line.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Ministral 8B
        </td>
        <td>
            October, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Larger dense Ministral variant for stronger capability at moderate cost.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Pixtral Large (24.11)
        </td>
        <td>
            November, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Large multimodal model combining a visual encoder with Mistral Large 2.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Large 2 (24.11)
        </td>
        <td>
            November, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Refreshed Mistral Large 2 release in the model timeline.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Small 3
        </td>
        <td>
            January, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            24B-parameter small model generation preceding 3.1 and 3.2 refreshes.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Codestral 25.01
        </td>
        <td>
            January, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Codestral model refresh for coding workloads.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Small 3.1
        </td>
        <td>
            March, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Smaller and more efficient successor to Mistral Small 3.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Medium 3
        </td>
        <td>
            May, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Medium-tier model release announced in May 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Devstral Small (25.05)
        </td>
        <td>
            May, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Early Devstral branch for agentic coding tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Small 3.2
        </td>
        <td>
            June, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Refresh release of Mistral Small 3.1.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Devstral Medium 1.0
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Agentic coding model in the Devstral lineup.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Devstral Small 1.1 (25.07)
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Updated small Devstral variant for coding and tool use.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Voxtral Small
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            24B-parameter open-weights speech understanding model released under Apache 2.0 alongside Voxtral Mini.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Codestral 25.08
        </td>
        <td>
            August, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Updated Codestral release in the enterprise coding stack.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Medium 3.1 (25.08)
        </td>
        <td>
            August, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Proprietary refresh of Mistral Medium 3 with improved tone and performance.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Magistral Medium
        </td>
        <td>
            June, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-focused medium model released alongside Magistral Small.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Magistral Small 2509
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            24B Apache 2.0 reasoning-focused Mistral release (Magistral Small 1.2) listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Large 3
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Sparse MoE flagship generation (675B total, 41B active parameters) succeeding Mistral Large 2 under Apache 2.0.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Ministral 3
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Dense small-model family (3B/8B/14B) released with Mistral Large 3.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Devstral 2
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            123B-parameter Devstral generation focused on stronger coding performance.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Devstral Small 2
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            24B Apache 2.0 compact coding model released alongside Devstral 2.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Voxtral Mini Transcribe V2
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Proprietary speech understanding and transcription model released in February 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Voxtral Realtime
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            4B-parameter Apache 2.0 model designed for real-time speech transcription.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Small 4
        </td>
        <td>
            March, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            119B-parameter open-weights MoE model (6B active parameters) released under Apache 2.0 in March 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Voxtral TTS
        </td>
        <td>
            March, 2026
        </td>
        <td>
            Non-commercial
        </td>
        <td>
            4B-parameter open-weights text-to-speech model (CC BY-NC 4.0) supporting multilingual voice generation and real-time streaming.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Medium 3.5
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Medium-tier model released in April 2026 in the Mistral product lineup.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral OCR 4
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Optical character recognition and document-understanding model released in June 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Robostral Navigate
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Embodied navigation model introduced in July 2026 for physical environment interaction.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Shieldstral
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Model focused on AI safety and security applications, introduced in August 2026.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-xai"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=x.ai&sz=64" alt="xAI logo" loading="lazy">xAI</span></th>
        <td>
            Grok-1
        </td>
        <td>
            November, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            First Grok generation integrated into X ecosystem products.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok-1.5
        </td>
        <td>
            May, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Improved reasoning and long-context capabilities (128k context window).
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok-2
        </td>
        <td>
            August, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Stronger general model with improved coding and tool use; predecessor to Grok 3.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok-2 mini
        </td>
        <td>
            August, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Smaller Grok-2 variant focused on speed and efficiency.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok-2.5
        </td>
        <td>
            August, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Source-available Grok update released after Grok-2 and before Grok 4 family.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok-3
        </td>
        <td>
            February, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Major flagship release with reasoning modes and DeepSearch, open-sourced in February 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok-3 mini
        </td>
        <td>
            February, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Faster and smaller Grok-3 variant released alongside Grok-3.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Successor to Grok 3; flagship generation introduced with native tool use and real-time search.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4 Heavy
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Higher-compute multi-agent reasoning tier introduced alongside Grok 4 for SuperGrok Heavy subscribers.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok Code Fast 1
        </td>
        <td>
            August, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Coding-focused reasoning model introduced for agentic development workflows.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4 Fast
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Unified reasoning/non-reasoning model with a 2M context window tuned for lower latency and reduced token cost.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.1
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental Grok 4 update aimed at better reasoning, creative interaction, and lower hallucination rates.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.1 Thinking
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-enabled variant released alongside Grok 4.1 in November 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.1 Fast
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Fast variant of Grok 4.1 optimized for tool-calling and agentic workflows with a 2M context window.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.20
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Flagship Grok 4.x release emphasizing speed, agentic tool calling, low hallucination rate, and prompt adherence.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.3
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Originally released as Grok 4.3 Beta in April 2026 with three-mode effort controls for reasoning intensity.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok Build
        </td>
        <td>
            May, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Terminal-based coding agent released in beta in May 2026 and open-sourced under Apache 2.0 in July 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.5
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Publicly released on July 8, 2026 on a 1.5T-parameter V9 foundation model with Cursor coding dataset integration.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.6
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Released on August 12, 2026 on the 1.5T-parameter V9 foundation and distributed via xAI API, GitHub Copilot, and Amazon Bedrock.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.7
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Latest stable Grok release launched on September 21, 2026, trained with Cursor dataset integration.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-cohere"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=cohere.com&sz=128" alt="Cohere logo" loading="lazy">Cohere</span></th>
        <td>
            Command R
        </td>
        <td>
            March, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Enterprise-focused model optimized for retrieval and tool use.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Command R+
        </td>
        <td>
            April, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Higher-capability tier in the Command R family.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Aya 23
        </td>
        <td>
            May, 2024
        </td>
        <td>
            Non-commercial
        </td>
        <td>
            Open-weights multilingual model family (8B and 35B) from Cohere Labs covering 23 languages.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Aya Vision
        </td>
        <td>
            March, 2025
        </td>
        <td>
            Non-commercial
        </td>
        <td>
            Multimodal vision-language model from Cohere Labs for image description, translation, and summarization across 23 languages.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Command A
        </td>
        <td>
            March, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            111B-parameter enterprise generative model succeeding Command R+, later expanded with Command A Reasoning, Translate, and Vision variants.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Command A+
        </td>
        <td>
            May, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Flagship enterprise Command A+ model released on May 20, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-alibaba"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://cdn.simpleicons.org/alibabacloud" alt="Alibaba logo" loading="lazy">Alibaba (Qwen)</span></th>
        <td>
            Qwen 1.5
        </td>
        <td>
            February, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Major open model line update with broad size variants.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen 2
        </td>
        <td>
            June, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Improved multilingual and coding performance.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen 2.5
        </td>
        <td>
            September, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Strong open model family with broad ecosystem adoption.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen2.5-Max
        </td>
        <td>
            January, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Higher-capability Qwen2.5 release announced at the end of January 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen 3
        </td>
        <td>
            April, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Next generation Qwen family with stronger reasoning variants.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            QwQ-32B-Preview
        </td>
        <td>
            November, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Initial reasoning preview that preceded the full QwQ-32B release.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            QwQ-32B
        </td>
        <td>
            March, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Full QwQ reasoning model release under Apache 2.0 license.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen2.5-Coder
        </td>
        <td>
            November, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Code generation family for software engineering workloads.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen2.5-VL
        </td>
        <td>
            January, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Vision-language family with multimodal understanding across image and text.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen2.5-Omni
        </td>
        <td>
            March, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Multimodal model supporting text, image, video and audio interactions.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3-Coder
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Advanced coding-focused Qwen3 branch for agentic software development.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3-Coder-Flash
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Fast coding-focused Qwen3 variant released alongside Qwen3-Coder under Apache 2.0.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3-Max
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Proprietary flagship model in the Qwen3 series released in September 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3-Next
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weights Apache 2.0 model line in the Qwen3 family released in September 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3-Omni
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Omni branch of Qwen3 targeting unified multimodal I/O.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3-VL
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Vision-language continuation in the Qwen3 generation.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3-Coder-Next
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Hybrid coding model positioned as a next-step update in the coder branch.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.5
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weights Qwen3.5 release focused on complex task completion.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.5-Plus
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Higher-capability proprietary tier in the Qwen3.5 generation.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.5-Omni
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Proprietary multimodal model in the Qwen3.5 series released in April 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.6
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weights Apache 2.0 release of the Qwen3.6 model family in April 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.6-Plus
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Proprietary higher-capability tier in the Qwen3.6 generation released in April 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.6-35B-A3B
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Open model release in the Qwen3.6 line (MoE-style activated parameters).
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.6-27B
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Qwen3.6 line release listed in the stable release timeline.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.7 Plus
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Proprietary Qwen3.7 Plus release launched on June 30, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.7 Max
        </td>
        <td>
            May, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Proprietary flagship Qwen3.7 Max release launched in May 2026 (previewed on May 22, 2026).
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.8-Max
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Flagship 2.4T-parameter sparse MoE model (95B active, 1M context window) previewed in July and released on August 3, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.8-2.4T-A95B
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weights release of Qwen3.8-Max (2.4T total, 95B active parameters) published on August 12, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.8-27B
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            27B-parameter open-weights model released under Apache 2.0 on August 14, 2026 with image input and non-thinking mode.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Qwen3.8-Flash
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Fast Qwen3.8 tier released in August 2026 alongside Qwen3.8-Flash-Next.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-deepseek"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=deepseek.com&sz=64" alt="DeepSeek logo" loading="lazy">DeepSeek</span></th>
        <td>
            DeepSeek Coder
        </td>
        <td>
            November, 2023
        </td>
        <td>
            Discontinued
        </td>
        <td>
            First DeepSeek model family focused on code generation tasks, succeeded by DeepSeek-Coder-V2.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V2
        </td>
        <td>
            May, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            236B MoE model (21B active) introducing Multi-head Latent Attention (MLA); succeeded by V2.5 and V3.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V2.5
        </td>
        <td>
            September, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Unified update combining general and coding capabilities from DeepSeek-V2-Chat and DeepSeek-Coder-V2.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-VL2
        </td>
        <td>
            December, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            MoE vision-language model family (Tiny, Small, and VL2) extending DeepSeek multimodal capabilities.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V3
        </td>
        <td>
            December, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            671B-parameter MoE base model (37B active parameters) with strong benchmark results.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-R1-Lite-Preview
        </td>
        <td>
            November, 2024
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Early preview release of the R1 reasoning line via DeepSeek chat.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-R1
        </td>
        <td>
            January, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            MIT-licensed reasoning-focused model family (including R1-Zero and distilled variants) emphasizing chain-of-thought quality.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V3-0324
        </td>
        <td>
            March, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            MIT-licensed refresh of the V3 line released in March 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-Prover-V2
        </td>
        <td>
            May, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weights formal theorem-proving model family released in 7B and 671B variants on May 1, 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-R1-0528
        </td>
        <td>
            May, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Updated R1 release under MIT license with improved reasoning behavior.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V3.1
        </td>
        <td>
            August, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Hybrid thinking/non-thinking architecture with improved coding benchmarks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V3.1-Terminus
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental V3.1 update released as the Terminus variant.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V3.2-Exp
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Discontinued
        </td>
        <td>
            Experimental V3.2 preview introducing DeepSeek Sparse Attention before the final V3.2 release.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-Math-V2
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            685B-parameter Apache 2.0 mathematical reasoning model released on November 27, 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V3.2
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            MIT-licensed V3.2 production release in the DeepSeek V3 family.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V3.2-Speciale
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-specialized variant released alongside DeepSeek-V3.2 under MIT license on December 1, 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V4-Pro (Preview)
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Preview of the V4-Pro series with 1M context window in the April 2026 announcement.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V4-Flash (Preview)
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Faster V4 preview variant released alongside V4-Pro in April 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V4-Flash
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Official release of the 284B-parameter V4-Flash model on July 31, 2026 with a 1M context window under MIT license.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V4-Pro
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Official release of the 1.6T-parameter V4-Pro model on August 13, 2026 with a 1M context window under MIT license.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-V4.1-Flash
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Released on September 10, 2026 under MIT license, introducing a causal encoder-decoder architecture with reduced memory usage.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-aws"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=aws.amazon.com&sz=128" alt="AWS logo" loading="lazy">AWS</span></th>
        <td>
            Titan
        </td>
        <td>
            April, 2023
        </td>
        <td>
            Active
        </td>
        <td>
            Earlier Amazon Bedrock model family. Titan includes first-generation AWS foundation
            model lines such as Titan Text, Titan Embeddings, and Titan Image.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Nova
        </td>
        <td>
            December, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Newer Amazon Bedrock model family (for example Nova Micro, Lite, Pro, and Premier),
            positioned as the latest AWS generation relative to Titan.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Nova Pro
        </td>
        <td>
            2024
        </td>
        <td>
            Active
        </td>
        <td>
            Nova text/multimodal model variant explicitly listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-ai21"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=ai21.com&sz=64" alt="AI21 Labs logo" loading="lazy">AI21 Labs</span></th>
        <td>
            Jamba 1.5 Mini
        </td>
        <td>
            2024
        </td>
        <td>
            Active
        </td>
        <td>
            AI21 hybrid model available in Amazon Bedrock.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Jamba 1.5 Large
        </td>
        <td>
            2024
        </td>
        <td>
            Active
        </td>
        <td>
            Larger AI21 Jamba variant listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-minimax"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=minimax.io&sz=64" alt="MiniMax logo" loading="lazy">MiniMax</span></th>
        <td>
            MiniMax M1
        </td>
        <td>
            June, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weights hybrid-attention reasoning model with a 1M token context window.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MiniMax M2
        </td>
        <td>
            October, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            MiniMax model family listed in Amazon Bedrock model cards and released in October 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MiniMax M2.1
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental MiniMax M2 line release in Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MiniMax M2.5
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            230B-parameter MoE model (10B active parameters) released in February 2026 and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MiniMax M2.7
        </td>
        <td>
            March, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental M2-series release launched on March 18, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MiniMax M3
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            MiniMax M3 generation released on June 17, 2026 and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-moonshot"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=moonshot.ai&sz=64" alt="Moonshot AI logo" loading="lazy">Moonshot AI</span></th>
        <td>
            Kimi K1.5
        </td>
        <td>
            January, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Multimodal reinforcement-learning reasoning model released on January 20, 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi K2
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            1T-parameter open-weights MoE model (32B active parameters) released under Modified MIT license in July 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi Linear
        </td>
        <td>
            October, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            48B-parameter MoE model (3B active parameters) using hybrid linear attention (Kimi Delta Attention), released under MIT license.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi K2 Thinking
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-focused 1T-parameter MoE Kimi model released on November 6, 2025 and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi K2.5
        </td>
        <td>
            January, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Multimodal agentic update to Kimi K2 (1T total, 32B active parameters) released on January 26, 2026 and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi K2.6
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weights Kimi K2.6 update released on April 20, 2026 under Modified MIT license.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi K2.7 Code
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Coding-specialized Kimi release listed in the Moonshot model timeline (June 2026).
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi K3
        </td>
        <td>
            July, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Next-generation Kimi K3 model family announced in July 2026 with a 2T-parameter architecture.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-nvidia"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://cdn.simpleicons.org/nvidia" alt="NVIDIA logo" loading="lazy">NVIDIA</span></th>
        <td>
            NVIDIA Nemotron Nano 9B v2
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Compact Nemotron model listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            NVIDIA Nemotron 3 Super 120B
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Large NVIDIA Nemotron model listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-writer"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=writer.com&sz=64" alt="Writer logo" loading="lazy">Writer</span></th>
        <td>
            Palmyra X4
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Writer enterprise model listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Palmyra X5
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Newer Writer Palmyra release listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-zai"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=z.ai&sz=64" alt="Z.AI logo" loading="lazy">Z.AI</span></th>
        <td>
            GLM 4.5
        </td>
        <td>
            July, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            355B-parameter open-weights MoE model (32B active parameters) released under MIT license on July 28, 2025, alongside GLM-4.5-Air and GLM-4.5V.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 4.6
        </td>
        <td>
            September, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Updated 355B MoE model released on September 30, 2025 with improved coding and agentic performance, followed by GLM-4.6V in December 2025.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 4.7
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            355B MoE release (December 22, 2025) with stronger coding and reasoning capabilities, listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 4.7 Flash
        </td>
        <td>
            January, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            30B-parameter MoE (3B active) fast GLM 4.7 variant released on January 19, 2026 and listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 5
        </td>
        <td>
            February, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            744B-parameter open-weights MoE model (40B active parameters) with DeepSeek Sparse Attention, released under MIT license on February 11, 2026 and expanded with GLM-5-Turbo and GLM-5V-Turbo.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 5.1
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            744B-parameter MoE update released under MIT license on April 7, 2026 for long-horizon agentic coding tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 5.2
        </td>
        <td>
            June, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental GLM 5 update released in June 2026, trained on clean data without distillation.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 5.3
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            1.15T-parameter open-weights MoE model (48B active parameters) released under MIT license on August 10, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 5.3-Flash
        </td>
        <td>
            August, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            215B-parameter open-weights MoE model (12B active parameters) released under MIT license on August 31, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 5.3-FlashX
        </td>
        <td>
            September, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Proprietary high-speed variant of GLM 5.3-Flash released on September 2, 2026.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-opencode"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=opencode.ai&sz=64" alt="Opencode logo" loading="lazy">Opencode</span></th>
        <td>
            Go
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
           AI Gateway that provides a curated list of models from the OpenCode team. It acts as a provider hub for tested coding agents. Entry
           level subscription. 
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Zen
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
           AI Gateway that provides a curated list of models from the OpenCode team. It acts as a provider hub for tested coding agents. Expert
           level subscription. 
        </td>
    </tr>
  </tbody>
</table>
