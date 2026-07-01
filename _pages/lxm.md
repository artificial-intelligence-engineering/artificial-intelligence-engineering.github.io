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
            Active
        </td>
        <td>
            Follow-up GPT-5 release listed in the ChatGPT model timeline on Wikipedia.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.3
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            GPT-5 branch update listed in the ChatGPT model list on Wikipedia.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.3-Codex
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Coding-specialized GPT-5.3 variant listed on the ChatGPT page.
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
            Active
        </td>
        <td>
            Enterprise-focused GPT-5 update listed in the ChatGPT timeline on Wikipedia.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GPT-5.5
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Most capable GPT-5 branch release listed as the current engine on Wikipedia.
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
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Open-weight OpenAI model listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            gpt-oss-120b
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Larger open-weight OpenAI model listed in Amazon Bedrock model cards.
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
           Active
        </td>
        <td>
           	Developed by Google with a focus on multimodality, agentic capabilities, and speed
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
           Active
        </td>
        <td>
           Reasoning-oriented Gemini variant designed for longer multi-step problem solving.
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
           Active
        </td>
        <td>
           Experimental higher-capability Gemini 2.0 tier for advanced tasks.
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
           Active
        </td>
        <td>
           	First-ever Gemini Flash-Lite model designed for cost-efficiency and speed	
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
           2025
        </td>
        <td>
           Active
        </td>
        <td>
           Latest Gemma family iteration focused on stronger reasoning and multimodal support.
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
            Active
        </td>
        <td>
            New Gemini 3 flagship generation that replaced 2.5 Pro in Google announcements.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Gemini 3 Deep Think
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-focused Gemini 3 variant based on the 2.5 Pro Deep Think mode.
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
            Gemma generation designed for stronger reasoning and agentic workflows.
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
            Announced by Meta but not publicly released at the time Scout and Maverick shipped.
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
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Lower-latency, lower-cost Phi-4 variant for edge and high-throughput scenarios.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-4-multimodal
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Multimodal Phi-4 variant supporting image+text understanding and generation.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Phi-4-reasoning
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-focused Phi-4 variant optimized for multi-step analytical tasks.
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
            Active
        </td>
        <td>
            Multimodal family balancing speed, cost and reasoning quality.
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
            Active
        </td>
        <td>
            Strong coding and agentic performance with better latency/cost profile.
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
            Active
        </td>
        <td>
            Fast and cost-efficient model for high-throughput use cases.
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
            Active
        </td>
        <td>
            Hybrid reasoning model with improved long-horizon task execution.
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
            Active
        </td>
        <td>
            New generation tuned for coding, tool use and production workflows.
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
            Active
        </td>
        <td>
            Highest-capability Claude tier for complex reasoning and agent tasks.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.1
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental Opus 4 update listed in the Claude model timeline on Wikipedia.
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
            Haiku branch update focused on speed and cost efficiency.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Sonnet 4.5
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Sonnet branch update listed in the model versions table on Wikipedia.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.5
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Opus branch update listed in the model versions table on Wikipedia.
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
            Sonnet branch update listed as a stable release in the Wikipedia infobox.
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
            Most agentic Sonnet generation, with major improvements in planning, tool use, and coding at lower cost than Opus 4.8.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.6
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Opus branch update listed in the model versions table on Wikipedia.
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
            Latest Opus stable release listed in the Wikipedia infobox timeline.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Opus 4.8
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Newer Opus release listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Mythos Preview
        </td>
        <td>
            2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Preview Claude model listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Fable 5
        </td>
        <td>
            9 June 2026
        </td>
        <td>
            Active
        </td>
        <td>
            A Mythos-class model that we've made safe for general use.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Claude Mythos 5 (preview)
        </td>
        <td>
            9 June 2026
        </td>
        <td>
            Limited availability
        </td>
        <td>
            Ready for a small group of cyberdefenders and infrastructure providers. It's the same underlying model as Fable 5, but with the safeguards lifted in some areas.
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
            Mistral Large 3
        </td>
        <td>
            December, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Sparse MoE flagship generation succeeding Mistral Large 2.
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
            New Devstral generation focused on stronger coding performance.
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
            Compact coding model released alongside Devstral 2.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Medium 3.5
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Medium-tier model listed in the current product lineup.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Mistral Small 4
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Latest small model generation in the Mistral product line.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Magistral Small 2509
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-focused Mistral release listed in Amazon Bedrock model cards.
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
            Discontinued
        </td>
        <td>
            Major flagship release with reasoning modes and DeepSearch.
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
            Successor to Grok 3; flagship generation introduced with Grok 4 Heavy.
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
            Enterprise-focused variant tuned for lower latency and reduced token usage.
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
            Incremental Grok 4 update aimed at better reasoning and lower hallucination rates.
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
            Fast variant of Grok 4.1 optimized for tool-calling and agentic workflows.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Grok 4.3 Beta
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Latest stable track listed in Wikipedia infobox timeline.
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
            2024
        </td>
        <td>
            Active
        </td>
        <td>
            Open multilingual model family from Cohere For AI.
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
            QwQ-32B
        </td>
        <td>
            November, 2024
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-focused model line released with open weights.
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
            May, 2026
        </td>
        <td>
            Active
        </td>
        <td>
            Latest stable-track Qwen3.7 Plus release listed in the infobox timeline.
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
            Latest flagship stable-track Qwen3.7 Max release.
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
            Active
        </td>
        <td>
            First DeepSeek model family focused on code generation tasks.
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
            Active
        </td>
        <td>
            Efficient MoE model focused on cost/performance.
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
            Active
        </td>
        <td>
            Unified update combining general and coding capabilities from the V2 line.
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
            Upgraded base model with strong benchmark results.
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
            Experimental V3.2 preview before final V3.2 release.
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
            V3.2 production release in the DeepSeek V3 family.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            DeepSeek-VL2
        </td>
        <td>
            November, 2025
        </td>
        <td>
            Active
        </td>
        <td>
            Vision-language model line extending DeepSeek multimodal capabilities.
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
            Early preview release of the R1 reasoning line via chat.
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
            Reasoning-focused model family emphasizing chain-of-thought quality.
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
            DeepSeek-V4-Pro (Preview)
        </td>
        <td>
            April, 2026
        </td>
        <td>
            Preview
        </td>
        <td>
            Preview of the V4 series with 1M context window in the April 2026 announcement.
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
            Faster V4 preview variant released alongside V4-Pro.
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
            MiniMax M2
        </td>
        <td>
            2025
        </td>
        <td>
            Active
        </td>
        <td>
            MiniMax model family listed in Amazon Bedrock model cards.
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
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Latest MiniMax model listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            MiniMax M3
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            New MiniMax M3 generation listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row" id="ecosystem-moonshot"><span class="ecosystem-label"><img class="ecosystem-logo" src="https://www.google.com/s2/favicons?domain=moonshot.ai&sz=64" alt="Moonshot AI logo" loading="lazy">Moonshot AI</span></th>
        <td>
            Kimi K2 Thinking
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Reasoning-focused Kimi model listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi K2.5
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Updated Kimi family release listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            Kimi K2.7 Code
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Coding-specialized Kimi release listed in the Moonshot model timeline.
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
            GLM 4.7
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Z.AI GLM series release listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 4.7 Flash
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Faster GLM variant listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 5
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Latest GLM generation listed in Amazon Bedrock model cards.
        </td>
    </tr>
    <tr>
      <th scope="row"></th>
        <td>
            GLM 5.2
        </td>
        <td>
            2026
        </td>
        <td>
            Active
        </td>
        <td>
            Incremental GLM 5 update listed in the Z.AI model timeline.
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
