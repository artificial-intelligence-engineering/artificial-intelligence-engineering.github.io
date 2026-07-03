---
title: "Glossary Table"
permalink: /glossary/
layout: splash
---

<table style="width:100%; table-layout:fixed;">
  <colgroup>
    <col style="width:18%;">
    <col style="width:52%;">
    <col style="width:30%;">
  </colgroup>
  <thead>
    <tr>
      <th scope="col" style="white-space:nowrap;">Term</th>
      <th scope="col">Definition</th>
      <th scope="col">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Foundation Model</th>
        <td>
            Foundation models, sometimes known as base models, are powerful artificial intelligence (AI) models that are 
            trained on a massive amount of data and can be adapted to a wide range of tasks. They serve as the base or 
            building blocks for crafting more specialized applications. These more specialized applications are the
            main task for the AI Engineering teams.
        </td>
        <td>
            The term "foundation model" was coined by the Stanford Institute for Human-Centered Artificial Intelligence 
            (HAI) in 2021.
            <ul>
              <li><a href="https://arxiv.org/abs/2108.07258" target="_blank">On the Opportunities and Risks of Foundation Models – Stanford HAI (2021)</a></li>
              <li><a href="https://hai.stanford.edu/news/introducing-foundation-models" target="_blank">Introducing Foundation Models – Stanford HAI</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">Frontier Model</th>
        <td>
            A frontier model is an artificial intelligence system that represents the absolute cutting edge of capability at any given time.
            These highly advanced, general-purpose models push the boundaries of technology in areas like reasoning,
            multimodal understanding, and autonomous task execution.
        </td>
        <td>
            External references explaining the concept.
            <ul>
              <li><a href="https://www.youtube.com/watch?v=BPQnd5n5Ya4" target="_blank">Frontier Models: The New Frontier of AI – Gen AI Summit EU - Valencia</a></li>
              <li><a href="https://www.youtube.com/watch?v=AVQzG2MY858" target="_blank">LLM vs. SLM vs. FM: Choosing the Right AI Model – IBM Technology</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">LLM</th>
        <td>
            Large Language Model (LLM) is the technical term and conceptually the beginning of the named Foundation Models.
            A Large Language Model (LLM) is a specific, advanced type of machine learning model used within the broader 
            field of Natural Language Processing (NLP). NLP is the overall field that enables computers to understand 
            and process human language, while an LLM is huge trained model for achieving many NLP tasks, such as generating 
            text, translation, and summarization, by using deep learning on massive datasets. 
        </td>
        <td>
            NLP based on Transformers is the foundation of LLMs.
            <ul>
              <li><a href="https://arxiv.org/abs/1706.03762" target="_blank">Attention Is All You Need – Vaswani et al. (2017), the Transformer paper</a></li>
              <li><a href="https://www.elastic.co/what-is/large-language-models" target="_blank">What is a Large Language Model (LLM)? – Elastic</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">LMM</th>
        <td>
            Large Multimodal Models (aka, MLLMs - Multimodal LLMs) expand the capabilities of traditional large language 
            models (LLMs), which are primarily focused on processing and generating text. By integrating multiple types 
            of data, LMMs enable more complex and versatile applications that require the synthesis and interpretation 
            of both textual and nontextual information, such as text, images, video, audio, and more.
        </td>
        <td>
            This term is related to the concept of Multimodal AI which refers to machine learning models capable of 
            processing and integrating information from multiple modalities or types of data. These modalities can 
            include text, images, audio, video and other forms of sensory input.
            <ul>
              <li><a href="https://arxiv.org/abs/2309.10020" target="_blank">A Survey on Multimodal Large Language Models – arXiv (2023)</a></li>
              <li><a href="https://openai.com/research/gpt-4v-system-card" target="_blank">GPT-4V System Card – OpenAI (vision multimodal)</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">LxM</th>
        <td>
            Large "x" Models family. An LxM is just an umbrella term for representing the LLM, LMM and further terminologies.
            It's another way of naming the Foundation Models (FM).
        </td>
        <td>
            <ul>
              <li><a href="https://huyenchip.com/2024/03/14/ai-engineering.html" target="_blank">The Rise of LxMs – Chip Huyen</a></li>
              <li><a href="https://www.youtube.com/watch?v=zjkBMFhNj_g" target="_blank">Intro to Large Language Models – Andrej Karpathy</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">SLM</th>
        <td>
            Small language models (SLMs) in this context are AI models that are trained on smaller, more focused 
            amounts of data compared to large language models. Despite their smaller size, SLMs can perform a variety 
            of tasks, such as text generation, summarization, translation, and classification. While they may not match 
            the extensive capabilities of LLMs, SLMs are often more resource efficient and can be highly effective for specific, targeted applications. 
        </td>
        <td>
            <ul>
              <li><a href="https://www.microsoft.com/en-us/research/blog/phi-2-the-surprising-power-of-small-language-models/" target="_blank">Phi-2: The Surprising Power of Small Language Models – Microsoft Research</a></li>
              <li><a href="https://huggingface.co/blog/smollm" target="_blank">SmolLM: Blazingly Fast and Remarkably Powerful – Hugging Face</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row"><a href="/open-weight/">Open-Weight<br>vs Open-Source Models</a></th>
        <td>
            Most models commonly referred to as "open source" are actually open-weight. While you can download their
            parameters to use them locally without paying per API call, their developers restrict full openness to
            protect intellectual property.
        </td>
        <td>
            The distinction matters because open weights do not necessarily include the training code, dataset details,
            or the legal freedoms needed to study, modify, and fully reproduce the model.
            <ul>
              <li><a href="https://opensource.org/ai/open-source-ai-definition" target="_blank">Open Source AI Definition 1.0 – Open Source Initiative</a></li>
              <li><a href="https://opensource.org/ai/open-weights" target="_blank">What are Open Weights? – Open Source Initiative</a></li>
              <li><a href="https://github.com/Open-Weights/Definition" target="_blank">Open Weights Definition – Heather Meeker et al.</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">AI Engineering</th>
        <td>
            Refers to the process of building applications on top of foundation models. Many terms are being used to 
            describe the process of building applications on top of foundation models, including ML engineering, 
            MLOps, AIOps, LLMOps, etc.
        </td>
         <td>
             <ul>
               <li><a href="https://www.oreilly.com/library/view/ai-engineering/9781098166298/" target="_blank">AI Engineering (Book) – Chip Huyen, O'Reilly</a></li>
               <li><a href="https://www.youtube.com/watch?v=p7F4f42iZ-c&t=9s" target="_blank">What You MUST Know About AI Engineering | Chip Huyen</a></li>
             </ul>
         </td>
    </tr>
    <tr>
      <th scope="row"><a href="/ai-agent/">AI Agent</a></th>
        <td>
            An AI agent is a computer program powered by artificial intelligence (AI) that can perform tasks autonomously to assist human users, even without definite instructions. Unlike other AI-powered software, such as chatbots, AI agents can operate outside of a specific prompt-based context. They can go outside of their training data and take a look around at the world, so to speak, to find information. Then they can, on their own, take actions based on that information in pursuit of a larger goal.
        </td>
         <td>
             <ul>
               <li><a href="https://aws.amazon.com/what-is/ai-agents/" target="_blank">What are AI agents? - AWS</a></li>
               <li><a href="https://news.microsoft.com/source/features/ai/ai-agents-what-they-are-and-how-theyll-change-the-way-we-work/" target="_blank">AI agents: What they are and how they'll change the way we work - Microsoft Source</a></li>
             </ul>
         </td>
    </tr>
    <tr>
      <th scope="row"><a href="/skills/">Agent Skills</a></th>
      <td>
          Reusable capabilities that an AI agent can invoke to complete tasks reliably.
          See the dedicated page for a simple explanation, examples, and implementation references.
      </td>
      <td>
          <ul>
            <li><a href="/skills/">Agent Skills page</a></li>
          </ul>
      </td>
    </tr>
    <tr>
      <th scope="row">AI Gateway</th>
        <td>
            An AI Gateway or AI Router is a middleware layer between an application and one or more AI models/services. In general terms, it sits between your app and the underlying model providers, and helps decide how, where, and under what rules each AI request should be executed.
        </td>
         <td>
             <ul>
               <li><a href="https://github.com/BerriAI/litellm" target="_blank">LiteLLM – AI Gateway and model router</a></li>
               <li><a href="https://docs.konghq.com/hub/kong-inc/ai-proxy/" target="_blank">Kong AI Gateway / AI Proxy</a></li>
               <li><a href="https://portkey.ai/docs/gateway/overview" target="_blank">Portkey AI Gateway Overview</a></li>
             </ul>
         </td>
    </tr>
    <tr>
      <th scope="row">Agentic Workflow</th>
        <td>
            An agentic workflow is an AI-driven process where autonomous agents plan, make decisions, and execute tasks using tools and feedback loops. Rather than relying on rigid step-by-step instructions or simply answering questions, an agentic workflow is goal-oriented. The AI assesses context, self-corrects errors, and adapts to changes in real time.
        </td>
         <td>
              <ul>
                <li><a href="https://www.anthropic.com/research/agentic-design-patterns" target="_blank">Agentic Design Patterns – Anthropic</a></li>
                <li><a href="https://www.ibm.com/think/topics/agentic-workflows" target="_blank">What are agentic workflows? – IBM</a></li>
              </ul>
         </td>
    </tr>
    <tr>
      <th scope="row">Agent Loop</th>
        <td>
            A year ago, Simon Willison wrote one of the cleanest definitions of an agent that has stuck around: An LLM agent runs tools in a loop to achieve a goal.
        </td>
        <td>
            <ul>
              <li><a href="https://strandsagents.com/docs/user-guide/concepts/agents/agent-loop/" target="_blank">Agent Loop – Strands Agents</a></li>
              <li><a href="https://simonwillison.net/2023/Apr/25/dual-llm-pattern/" target="_blank">The Dual LLM Pattern for building AI agents – Simon Willison</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">Vibe Coding</th>
        <td>
            Vibe coding is a software development practice assisted by artificial intelligence (AI) where the software developer describes a project or task in a prompt to a large language model (LLM), which generates source code automatically.
            Básicamente, es crear código usando code assistant agents.
        </td>
         <td>
             <ul>
               <li><a href="https://www.merriam-webster.com/slang/vibe-coding" target="_blank">Vibe coding – Merriam-Webster</a></li>
               <li><a href="https://karpathy.ai/" target="_blank">Andrej Karpathy</a></li>
             </ul>
         </td>
    </tr>
    <tr>
      <th scope="row"><a href="/prompt-patterns/">Prompt Engineering</a></th>
        <td>
            It is the art of asking a Generative AI model questions in natural language so that the model responds 
            according to our needs.
        </td>
        <td>
            <ul>
              <li><a href="https://www.promptingguide.ai/" target="_blank">Prompt Engineering Guide – DAIR.AI</a></li>
              <li><a href="https://platform.openai.com/docs/guides/prompt-engineering" target="_blank">Prompt Engineering Best Practices – OpenAI</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">Prompt Context</th>
        <td>
            Prompt context is background information or details provided in a prompt that help guide an AI's response 
            to be more relevant and specific.
        </td>
        <td>
            <ul>
              <li><a href="https://learnprompting.org/docs/basics/context" target="_blank">Providing Context in Prompts – Learn Prompting</a></li>
              <li><a href="https://www.anthropic.com/research/anthropics-prompt-engineering-guide" target="_blank">Anthropic's Prompt Engineering Guide – Anthropic</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">Context Window</th>
        <td>
            The "context window" in GenAI refers to the amount of information a model can process and "remember" at one 
            time, like a short-term memory. It is measured in tokens, which are pieces of words, images, or video. 
            A larger context window allows the AI to handle longer conversations and larger documents by retaining more 
            of the input and output without forgetting the beginning
        </td>
        <td>
            <ul>
              <li><a href="https://www.anthropic.com/news/claude-3-5-sonnet" target="_blank">Claude 3.5 Sonnet and its 200K context window – Anthropic</a></li>
              <li><a href="https://research.google/blog/long-context-understanding-in-gemini/" target="_blank">Long Context Understanding in Gemini – Google Research</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">GenAI Token</th>
        <td>
            A token is the smallest unit into which text data (or not text) can be broken down for an AI model to process.
            Whether a transformer AI model is processing text, images, audio clips, videos or another modality, it will 
            translate the data into tokens. This process is known as tokenization. Large language models have varying 
            token limits, which dictate the amount of text they can process at once, combining both the input prompt 
            and the output completion. The token limit determines the model's "context window" the amount of information 
            it can consider at any one time. So the number of supported tokens of a model is frequently used as a 
            measure of the model power.
        </td>
        <td>
            <ul>
              <li><a href="https://platform.openai.com/tokenizer" target="_blank">OpenAI Tokenizer – interactive tokenization tool</a></li>
              <li><a href="https://huggingface.co/docs/transformers/tokenizer_summary" target="_blank">Summary of Tokenizers – Hugging Face</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row"><a href="/harness/">Harness Engineering</a></th>
        <td>
            Harness engineering refers to the practice of designing and building the scaffolding, tooling, and control 
            infrastructure that surrounds an AI agent or model during execution. A harness manages the lifecycle of 
            long-running agent tasks: orchestrating tool calls, handling retries and failures, enforcing timeouts, 
            capturing intermediate state, and providing observability. Rather than focusing on the model itself, 
            harness engineering focuses on the reliable, repeatable execution environment in which the model operates. In
            simple words: Harness Engineering is the discipline of designing the execution environment around an 
            autonomous AI agent. It defines which tools the agent can call, where it gets information, how it validates 
            its own decisions, and when it should stop. The guardrails of the AI agents.
        </td>
        <td>
            <ul>
              <li><a href="https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents" target="_blank">Effective Harnesses for Long-Running Agents – Anthropic</a></li>
              <li><a href="https://martinfowler.com/articles/harness-engineering.html" target="_blank">Harness Engineering – Martin Fowler</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">Ralph Loop</th>
        <td>
            The Ralph Loop is an architectural pattern for autonomous software agents that operate in a continuous cycle.
            The RALPH acronym represents the following phases: <strong>R</strong>ead (read context and current state), 
            <strong>A</strong>ct (execute actions or invoke tools), <strong>L</strong>oop (iterate until the goal is reached), 
            <strong>P</strong>roduce (generate an output or artifact) and <strong>H</strong>arness (control execution 
            within a supervised environment). It is particularly relevant for long-running tasks where the agent must 
            reason, act and self-correct iteratively with minimal human intervention.
        </td>
        <td>
            <ul>
              <li><a href="https://ghuntley.com/loop/" target="_blank">The Ralph Loop – Geoffrey Huntley</a></li>
              <li><a href="https://simonwillison.net/2023/Apr/25/dual-llm-pattern/" target="_blank">The Dual LLM Pattern for building AI agents – Simon Willison</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">LLM Temperature</th>
        <td>
            LLM temperature is a hyperparameter that controls the randomness and creativity of a model's responses by scaling the probability distribution of the predicted next word
        </td>
        <td>
            <ul>
              <li><a href="https://arxiv.org/html/2506.07295v1" target="_blank">https://arxiv.org/html/2506.07295v1</a></li>
              <li><a href="https://www.ibm.com/think/topics/llm-temperature" target="_blank">https://www.ibm.com/think/topics/llm-temperature</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row"><a href="/local-model/">Local Model</a></th>
        <td>
            A local Model or LLM (Large Language Model) is an AI model that you download and run directly on your own hardware (PC or local server). Unlike cloud-based AI assistants (like ChatGPT or Claude), a local LLM operates entirely offline—your data stays on your device, and no internet connection is required to process requests.
        </td>
        <td>
            <ul>
              <li><a href="https://ollama.com/" target="_blank">https://ollama.com/</a></li>
              <li><a href="https://tengine.ai/blog/a-guide-to-running-ai-models-locally-what-local-really-means" target="_blank">https://tengine.ai/blog/a-guide-to-running-ai-models-locally-what-local-really-means</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">KV Cache</th>
        <td>
            A Key-Value (KV) cache is a fundamental optimization technique used during Large Language Model (LLM) inference. It stores the intermediate Key (K) and Value (V) vectors of past tokens in the model's attention layers, preventing the model from recomputing them from scratch for every newly generated token
        </td>
        <td>
            <ul>
              <li><a href="https://huggingface.co/blog/not-lain/kv-caching" target="_blank">https://huggingface.co/blog/not-lain/kv-caching</a></li>
              <li><a href="https://arxiv.org/html/2603.20397v1" target="_blank">https://arxiv.org/html/2603.20397v1</a></li>
              <li><a href="https://magazine.sebastianraschka.com/p/coding-the-kv-cache-in-llms" target="_blank">https://magazine.sebastianraschka.com/p/coding-the-kv-cache-in-llms</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row"><a href="/llm-distillation/">LLM Distillation</a></th>
        <td>
            LLM Distillation is a specialized form of Knowledge Distillation (KD) that compresses large-scale LLMs into
            smaller, faster and more efficient models while preserving a significant portion of the performance. It enables
            lightweight models to approximate the capabilities of massive LLMs making them deployable on a broader range
            of applications and devices.
        </td>
        <td>
            <ul>
              <li><a href="https://arxiv.org/abs/2306.08543" target="_blank">Knowledge Distillation of Large Language Models – arXiv (2023)</a></li>
              <li><a href="https://huggingface.co/docs/transformers/model_doc/distilbert" target="_blank">DistilBERT: a distilled version of BERT – Hugging Face</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">AI Slop</th>
        <td>
            AI slop is a colloquial term for low-quality media content, including images, video, audio, text, and software,
            generated by artificial intelligence (AI) with seemingly little effort from a human interlocutor. Produced for
            mass consumption, without personal attention and touch.
        </td>
        <td>
            <ul>
              <li><a href="https://en.wikipedia.org/wiki/AI_slop" target="_blank">AI Slop – Wikipedia</a></li>
              <li><a href="https://simonwillison.net/2024/May/8/slop/" target="_blank">Slop is the new spam – Simon Willison</a></li>
              <li><a href="https://www.theguardian.com/technology/2024/may/19/ai-slop-artificial-intelligence-junk-content" target="_blank">AI slop: the term for AI-generated junk content – The Guardian</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">System Cards</th>
      <td>
        System cards are transparency documents published by artificial intelligence developers that explain how an AI model works, detailing its design, capabilities, usage limitations, and safety evaluations.
      </td>
      <td>
        <ul>
          <li><a href="https://openai.com/research/gpt-4v-system-card" target="_blank">GPT-4V(ision) System Card – OpenAI</a></li>
          <li><a href="https://cdn.openai.com/papers/gpt-4-system-card.pdf" target="_blank">GPT-4 System Card (PDF) – OpenAI</a></li>
        </ul>
      </td>
    </tr>
    <tr>
      <th scope="row">Model Cards</th>
      <td>
        A Model Card is a short, standardized document accompanying a trained machine learning model that provides benchmarked evaluation across different groups and environments, clarifying the model's intended use and performance characteristics.
      </td>
      <td>
        <ul>
          <li><a href="https://arxiv.org/abs/1810.03993" target="_blank">Model Cards for Model Reporting – Mitchell et al. (Google Research)</a></li>
          <li><a href="https://huggingface.co/docs/hub/model-cards" target="_blank">Model Cards – Hugging Face Docs</a></li>
        </ul>
      </td>
    </tr>
    <tr>
        <th scope="row">TODO</th>
        <td>
            TODO
        </td>
        <td>
               TODO 
        </td>
    </tr>
  </tbody>
</table>
