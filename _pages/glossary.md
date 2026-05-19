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
      <th scope="row">AI Engineering</th>
        <td>
            Refers to the process of building applications on top of foundation models. Many terms are being used to 
            describe the process of building applications on top of foundation models, including ML engineering, 
            MLOps, AIOps, LLMOps, etc.
        </td>
        <td>
            <ul>
              <li><a href="https://www.oreilly.com/library/view/ai-engineering/9781098166298/" target="_blank">AI Engineering (Book) – Chip Huyen, O'Reilly</a></li>
              <li><a href="https://huyenchip.com/2024/04/11/ai-engineering.html" target="_blank">What is AI Engineering? – Chip Huyen</a></li>
            </ul>
        </td>
    </tr>
    <tr>
      <th scope="row">Prompt Engineering</th>
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
      <th scope="row">Harness Engineering</th>
        <td>
            Harness engineering refers to the practice of designing and building the scaffolding, tooling, and control 
            infrastructure that surrounds an AI agent or model during execution. A harness manages the lifecycle of 
            long-running agent tasks: orchestrating tool calls, handling retries and failures, enforcing timeouts, 
            capturing intermediate state, and providing observability. Rather than focusing on the model itself, 
            harness engineering focuses on the reliable, repeatable execution environment in which the model operates.
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