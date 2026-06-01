---
title: "Tools Table"
permalink: /tools/
layout: splash
---

<nav class="lxm-toc" aria-label="Tools navigation">
  <strong>Categories</strong>
  <ul>
    <li><a href="#category-code-assistant">Code Assistant Tools</a></li>
    <li><a href="#category-dev-frameworks">Dev Frameworks</a></li>
    <li><a href="#category-ai-assistants">AI Assistants</a></li>
    <li><a href="#category-workflow-automation">Workflow Automation</a></li>
  </ul>
</nav>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    var toc = document.querySelector(".lxm-toc");
    if (!toc) return;

    var links = toc.querySelectorAll("a[href^='#category-']");

    links.forEach(function (link) {
      link.addEventListener("click", function (event) {
        var hash = link.getAttribute("href");
        var target = document.querySelector(hash);
        if (!target) return;

        event.preventDefault();

        var stickyOffset = toc.offsetHeight + 12;
        var targetTop = target.getBoundingClientRect().top + window.pageYOffset;

        window.scrollTo({
          top: Math.max(0, targetTop - stickyOffset),
          behavior: "smooth"
        });

        if (history.pushState) {
          history.pushState(null, "", hash);
        } else {
          window.location.hash = hash;
        }
      });
    });
  });
</script>

<table class="lxm-table tools-table">
  <colgroup>
    <col style="width: 7%;">
    <col style="width: 7%;">
    <col style="width: 7%;">
    <col style="width: 55%;">
    <col style="width: 24%;">
  </colgroup>
  <thead>
    <tr>
      <th scope="col">Category</th>
      <th scope="col">Term</th>
      <th scope="col">Vendor</th>
      <th scope="col">Description</th>
      <th scope="col">Notes</th>
    </tr>
  </thead>
  <tbody>

    <!-- ── Code Assistant Tools ─────────────────────────────── -->
    <tr>
      <th scope="row" id="category-code-assistant">Code Assistant Tools</th>
      <td>Claude Code</td>
      <td>Anthropic</td>
      <td>
        Terminal-based agentic coding assistant powered by Claude models. Operates directly
        from the command line, reads and edits files, runs tests, and executes shell commands
        autonomously. Designed for long-horizon coding tasks and deep repository understanding
        without requiring an IDE plugin.
      </td>
      <td>
        <a href="https://claude.ai/code" target="_blank">🔗 claude.ai/code</a><br>
        <a href="https://www.anthropic.com/news/claude-code" target="_blank">📄 Anthropic announcement</a><br>
        <a href="https://www.youtube.com/results?search_query=claude+code+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Cursor</td>
      <td>Anysphere</td>
      <td>
        AI-first code editor forked from VS Code that embeds LLM-powered features at the
        core: inline multi-line completions (Tab), a sidebar chat aware of the full codebase,
        and an Agent mode that can autonomously create and refactor files. Supports OpenAI,
        Anthropic, and custom model endpoints.
      </td>
      <td>
        <a href="https://cursor.com" target="_blank">🔗 cursor.com</a><br>
        <a href="https://docs.cursor.com" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=cursor+ai+editor+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Devin</td>
      <td>Cognition AI</td>
      <td>
        Fully autonomous AI software engineer that can plan and complete end-to-end engineering
        tasks: cloning repos, writing code, running tests, fixing bugs, and opening pull requests.
        Operates inside an isolated sandboxed environment with access to a browser, terminal,
        and code editor, requiring only a high-level task description from the user.
      </td>
      <td>
        <a href="https://devin.ai" target="_blank">🔗 devin.ai</a><br>
        <a href="https://cognition.ai/blog/introducing-devin" target="_blank">📄 Introducing Devin</a><br>
        <a href="https://www.youtube.com/results?search_query=devin+ai+software+engineer+demo" target="_blank">▶ YouTube demos</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Antigravity</td>
      <td>Antigravity AI</td>
      <td>
        AI pair-programming assistant focused on reducing cognitive overhead for developers.
        Provides context-aware code generation, inline refactoring suggestions, and natural
        language-to-code translation while integrating tightly with the developer's existing
        workflow and version-control system.
      </td>
      <td>
        <a href="https://antigravity.dev" target="_blank">🔗 antigravity.dev</a><br>
        <a href="https://www.youtube.com/results?search_query=antigravity+ai+coding+assistant" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Codex (CLI)</td>
      <td>OpenAI</td>
      <td>
        OpenAI's command-line coding agent built on the GPT-4o / o-series models. Runs inside
        a sandboxed environment, reads the local repository, writes and edits files, executes
        shell commands, and iterates on test results. Designed as a lightweight terminal
        alternative to full IDE integrations, with configurable approval modes for autonomous
        or supervised operation.
      </td>
      <td>
        <a href="https://openai.com/codex" target="_blank">🔗 openai.com/codex</a><br>
        <a href="https://github.com/openai/codex" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=openai+codex+cli+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>GitHub Copilot</td>
      <td>Microsoft / GitHub</td>
      <td>
        Pioneer AI pair programmer deeply integrated into VS Code, Visual Studio, JetBrains,
        Neovim, and the GitHub web UI. Offers real-time line and block completions, a chat
        sidebar, slash commands for tests and docs, and Copilot Workspace for agentic
        multi-file editing across an entire repository. Powered by OpenAI Codex and GPT-4o.
      </td>
      <td>
        <a href="https://github.com/features/copilot" target="_blank">🔗 github.com/features/copilot</a><br>
        <a href="https://docs.github.com/en/copilot" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=github+copilot+tutorial+2024" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>OpenCode</td>
      <td>Open Source (sst/opencode)</td>
      <td>
        Open-source, terminal-based AI coding assistant written in Go. Connects to any
        OpenAI-compatible API (OpenAI, Anthropic, Ollama, etc.), provides an interactive
        TUI session for chatting with LLMs about code, and supports tool calls for reading
        files, running commands, and applying diffs. Designed for developers who prefer
        staying entirely in the terminal.
      </td>
      <td>
        <a href="https://opencode.ai" target="_blank">🔗 opencode.ai</a><br>
        <a href="https://github.com/sst/opencode" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=opencode+ai+terminal+coding" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Aider</td>
      <td>Paul Gauthier (OSS)</td>
      <td>
        Open-source, terminal-based AI pair programmer with first-class git integration.
        Automatically commits every accepted change with a meaningful message, supports
        adding multiple files to context, and works with GPT-4o, Claude 3.x, Gemini, and
        local models via LiteLLM. Benchmarks among the top open-source agents on SWE-bench.
      </td>
      <td>
        <a href="https://aider.chat" target="_blank">🔗 aider.chat</a><br>
        <a href="https://github.com/paul-gauthier/aider" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=aider+ai+coding+assistant+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Cline</td>
      <td>cline.bot (OSS)</td>
      <td>
        Open-source VS Code extension that acts as an autonomous coding agent inside the editor.
        Can create and edit files, execute terminal commands, interact with the browser via
        computer-use APIs, and use MCP (Model Context Protocol) servers to connect to external
        tools. Requires explicit user approval for each action, keeping the developer in control.
      </td>
      <td>
        <a href="https://cline.bot" target="_blank">🔗 cline.bot</a><br>
        <a href="https://github.com/cline/cline" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=cline+vscode+ai+agent+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Windsurf</td>
      <td>Codeium</td>
      <td>
        AI-first IDE (VS Code fork) developed by Codeium, featuring Cascade — an agentic AI
        flow that can browse the web, run terminal commands, and refactor across multiple files
        in a single session. Offers both a chat sidebar and inline completions powered by
        Codeium's proprietary and third-party frontier models.
      </td>
      <td>
        <a href="https://codeium.com/windsurf" target="_blank">🔗 codeium.com/windsurf</a><br>
        <a href="https://docs.codeium.com/windsurf/getting-started" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=windsurf+codeium+ide+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Amazon Q Developer</td>
      <td>AWS</td>
      <td>
        AWS-native AI coding assistant integrated into VS Code, JetBrains, Visual Studio, and
        the AWS Console. Provides inline completions, chat-based code generation, automated
        security scanning, and an agent for autonomous feature implementation. Especially
        proficient with AWS services, CDK, and cloud-native architectures.
      </td>
      <td>
        <a href="https://aws.amazon.com/q/developer/" target="_blank">🔗 aws.amazon.com/q/developer</a><br>
        <a href="https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=amazon+q+developer+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Continue</td>
      <td>Continue.dev (OSS)</td>
      <td>
        Open-source AI code assistant extension for VS Code and JetBrains. Lets developers
        bring their own models (OpenAI, Anthropic, Ollama, LM Studio, etc.) and configure
        custom context providers, slash commands, and model switching per task. Focuses on
        transparency and local-first privacy, with all configuration stored in a plain JSON file.
      </td>
      <td>
        <a href="https://continue.dev" target="_blank">🔗 continue.dev</a><br>
        <a href="https://github.com/continuedev/continue" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=continue+dev+ai+coding+extension" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Tabnine</td>
      <td>Tabnine Ltd.</td>
      <td>
        One of the earliest AI code completion tools, now offering a full chat assistant alongside
        whole-line and multi-line completions. Differentiates itself with strong enterprise privacy
        guarantees: self-hosted deployment options, no code retention, and SOC 2 compliance.
        Integrates with all major IDEs and supports fine-tuning on private codebases.
      </td>
      <td>
        <a href="https://www.tabnine.com" target="_blank">🔗 tabnine.com</a><br>
        <a href="https://docs.tabnine.com" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=tabnine+ai+code+completion+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>JetBrains AI Assistant</td>
      <td>JetBrains</td>
      <td>
        Native AI assistant built into all JetBrains IDEs (IntelliJ IDEA, PyCharm, GoLand, etc.).
        Provides context-aware code generation, refactoring, test generation, commit message
        suggestions, and an inline chat. Backed by JetBrains' own AI Service which proxies
        OpenAI and other models, giving users a seamless IDE-native experience without leaving
        the editor.
      </td>
      <td>
        <a href="https://www.jetbrains.com/ai/" target="_blank">🔗 jetbrains.com/ai</a><br>
        <a href="https://www.jetbrains.com/help/idea/ai-assistant.html" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=jetbrains+ai+assistant+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>

    <!-- ── Dev Frameworks ──────────────────────────────────── -->
    <tr>
      <th scope="row" id="category-dev-frameworks">Dev Frameworks</th>
      <td>LangChain</td>
      <td>LangChain, Inc. (OSS)</td>
      <td>
        The most widely adopted Python/TypeScript framework for composing LLM-powered applications.
        Provides chains, agents, memory, and tool-calling abstractions that wire together models,
        retrievers, vector stores, and external APIs. Acts as the de-facto standard glue layer for
        RAG pipelines, conversational agents, and multi-step reasoning workflows.
      </td>
      <td>
        <a href="https://www.langchain.com" target="_blank">🔗 langchain.com</a><br>
        <a href="https://python.langchain.com/docs/" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=langchain+tutorial+rag" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>LlamaIndex</td>
      <td>LlamaIndex, Inc. (OSS)</td>
      <td>
        Framework specialised in data ingestion, indexing, and retrieval for LLM applications.
        Provides connectors to 160+ data sources, multiple index types (vector, keyword, knowledge
        graph), and a high-level query engine for RAG. Also ships LlamaAgents for multi-service
        agentic orchestration and LlamaParse for high-fidelity document parsing.
      </td>
      <td>
        <a href="https://www.llamaindex.ai" target="_blank">🔗 llamaindex.ai</a><br>
        <a href="https://docs.llamaindex.ai" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=llamaindex+rag+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Haystack</td>
      <td>deepset (OSS)</td>
      <td>
        Production-focused Python framework for building LLM-powered search and RAG systems.
        Organises components (document stores, retrievers, readers, generators) into declarative
        pipelines. Ships with native connectors to major vector databases and LLM providers, and
        includes evaluation tools for measuring retrieval and generation quality end-to-end.
      </td>
      <td>
        <a href="https://haystack.deepset.ai" target="_blank">🔗 haystack.deepset.ai</a><br>
        <a href="https://docs.haystack.deepset.ai" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=haystack+deepset+rag+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Semantic Kernel</td>
      <td>Microsoft (OSS)</td>
      <td>
        Microsoft's enterprise-grade SDK (Python, C#, Java) for integrating LLMs into applications
        via plugins and planners. Provides a kernel that routes user intents to functions, manages
        memory, and chains skills together. Designed for large organisations that need auditability,
        extensibility, and integration with Azure AI and Microsoft 365 services.
      </td>
      <td>
        <a href="https://learn.microsoft.com/en-us/semantic-kernel/" target="_blank">🔗 microsoft.com/semantic-kernel</a><br>
        <a href="https://github.com/microsoft/semantic-kernel" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=semantic+kernel+microsoft+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>DSPy</td>
      <td>Stanford NLP (OSS)</td>
      <td>
        Declarative framework from Stanford for programming LLMs using composable modules instead
        of hand-crafted prompts. Signatures describe what a module does; optimisers (e.g., BootstrapFewShot,
        MIPRO) automatically tune prompts and few-shot examples to maximise a given metric.
        Enables reliable, reproducible pipelines where LLM behaviour is optimised, not guessed.
      </td>
      <td>
        <a href="https://dspy.ai" target="_blank">🔗 dspy.ai</a><br>
        <a href="https://github.com/stanfordnlp/dspy" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=dspy+stanford+llm+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Pydantic AI</td>
      <td>Pydantic (OSS)</td>
      <td>
        Type-safe agent framework from the creators of Pydantic. Defines agents with typed
        dependencies and structured output schemas validated at runtime, wrapping models from
        OpenAI, Anthropic, Gemini, Ollama, and others. Integrates with Logfire for tracing and
        is designed to bring the ergonomics of FastAPI-style development to LLM agent construction.
      </td>
      <td>
        <a href="https://ai.pydantic.dev" target="_blank">🔗 ai.pydantic.dev</a><br>
        <a href="https://github.com/pydantic/pydantic-ai" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=pydantic+ai+agent+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Smolagents</td>
      <td>Hugging Face (OSS)</td>
      <td>
        Lightweight, minimal-footprint agent library from Hugging Face. Agents write and execute
        Python code as their action language (CodeAgent) or call tools via JSON (ToolCallingAgent).
        Supports any model hosted on the Hub or via inference APIs, and is designed to minimise
        abstraction so that agent behaviour remains transparent and debuggable.
      </td>
      <td>
        <a href="https://huggingface.co/docs/smolagents" target="_blank">🔗 huggingface.co/docs/smolagents</a><br>
        <a href="https://github.com/huggingface/smolagents" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=smolagents+huggingface+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>LiteLLM</td>
      <td>BerriAI (OSS)</td>
      <td>
        Unified Python SDK and proxy server that translates calls to 100+ LLM provider APIs
        (OpenAI, Anthropic, Gemini, Mistral, Ollama, Bedrock, etc.) into a single interface.
        Handles model fallbacks, load balancing, cost tracking, and rate-limit retries, acting
        as the portability layer underneath almost every framework that needs multi-provider support.
      </td>
      <td>
        <a href="https://litellm.ai" target="_blank">🔗 litellm.ai</a><br>
        <a href="https://docs.litellm.ai" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=litellm+tutorial+llm+proxy" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>

    <!-- ── AI Assistants ───────────────────────────────────── -->
    <tr>
      <th scope="row" id="category-ai-assistants">AI Assistants</th>
      <td>OpenClaw</td>
      <td>OpenClaw (OSS)</td>
      <td>
        Personal AI assistant platform designed to run on the user's own devices and operate
        across many messaging channels. It behaves more like a persistent assistant runtime than
        a workflow builder: the system exposes a gateway, skills, onboarding flows, and multi-channel
        integrations so one assistant can live across WhatsApp, Telegram, Slack, Discord, and other endpoints.
      </td>
      <td>
        <a href="https://openclaw.ai" target="_blank">🔗 openclaw.ai</a><br>
        <a href="https://github.com/openclaw/openclaw" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=openclaw+ai+assistant" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>AnythingLLM</td>
      <td>Mintplex Labs (OSS)</td>
      <td>
        Self-hosted AI workspace and assistant platform that combines chat, document ingestion,
        RAG, agents, and model management in a single application. It is especially useful for
        building private knowledge assistants on top of local or remote models, with support for
        multiple vector databases, embedders, and enterprise-style workspace separation.
      </td>
      <td>
        <a href="https://anythingllm.com" target="_blank">🔗 anythingllm.com</a><br>
        <a href="https://docs.anythingllm.com" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=anythingllm+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Open WebUI</td>
      <td>Open WebUI (OSS)</td>
      <td>
        Open-source self-hosted AI interface for local and remote language models, commonly used
        as the front-end assistant layer on top of Ollama or OpenAI-compatible APIs. Beyond simple chat,
        it adds tools, knowledge bases, model switching, image support, and multi-user management,
        making it a practical general-purpose assistant hub for teams and homelabs.
      </td>
      <td>
        <a href="https://openwebui.com" target="_blank">🔗 openwebui.com</a><br>
        <a href="https://docs.openwebui.com" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=open+webui+ollama+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>LibreChat</td>
      <td>LibreChat (OSS)</td>
      <td>
        Open-source AI chat and assistant platform supporting multiple providers such as OpenAI,
        Anthropic, Gemini, Azure OpenAI, and local backends. It has evolved from a chat UI into
        a configurable assistant environment with tools, MCP integration, conversation management,
        and self-hosting options for organisations that want a private ChatGPT-style deployment.
      </td>
      <td>
        <a href="https://www.librechat.ai" target="_blank">🔗 librechat.ai</a><br>
        <a href="https://docs.librechat.ai" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=librechat+self+hosted+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>NotebookLM</td>
      <td>Google</td>
      <td>
        Source-grounded AI research assistant and thinking partner from Google. It is designed to
        analyse user-provided sources such as PDFs, notes, links, and documents, then generate
        summaries, study guides, Q&amp;A, briefings, and the popular Audio Overviews. It fits best as
        an assistant for research and knowledge work rather than as a workflow builder or developer framework.
      </td>
      <td>
        <a href="https://notebooklm.google/" target="_blank">🔗 notebooklm.google</a><br>
        <a href="https://support.google.com/notebooklm" target="_blank">📄 Help center</a><br>
        <a href="https://www.youtube.com/results?search_query=notebooklm+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Khoj</td>
      <td>Khoj, Inc. (OSS)</td>
      <td>
        Open-source personal AI assistant focused on searching and reasoning over a user's own
        notes, documents, conversations, and knowledge sources. It is positioned as a second brain:
        part semantic search engine, part assistant, with web access, local knowledge grounding,
        and agent-like capabilities for answering questions in personal context.
      </td>
      <td>
        <a href="https://khoj.dev" target="_blank">🔗 khoj.dev</a><br>
        <a href="https://docs.khoj.dev" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=khoj+ai+assistant+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Jan</td>
      <td>Menlo Research (OSS)</td>
      <td>
        Open-source desktop AI assistant built for local-first usage. It lets users run local or
        remote models behind a clean desktop interface, manage model downloads, and keep conversations
        on-device when desired. Jan is especially relevant as a consumer-friendly assistant shell for
        people who want ChatGPT-like UX on top of local models.
      </td>
      <td>
        <a href="https://jan.ai" target="_blank">🔗 jan.ai</a><br>
        <a href="https://github.com/menloresearch/jan" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=jan+ai+local+assistant+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Pipecat Cloud</td>
      <td>Daily</td>
      <td>
        Voice-first AI assistant platform oriented to real-time conversational agents across phone,
        browser, and multimodal channels. While Pipecat itself is a framework ecosystem, the hosted
        platform direction and reference stack are highly relevant for teams building always-on voice
        assistants, call agents, and realtime copilots that need streaming audio and tool invocation.
      </td>
      <td>
        <a href="https://www.pipecat.ai" target="_blank">🔗 pipecat.ai</a><br>
        <a href="https://docs.pipecat.ai" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=pipecat+voice+agent+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>

    <!-- ── Workflow Automation ─────────────────────────────── -->
    <tr>
      <th scope="row" id="category-workflow-automation">Workflow Automation</th>
      <td>n8n</td>
      <td>n8n GmbH (OSS)</td>
      <td>
        Open-source, self-hostable workflow automation platform with a visual node editor and
        native AI capabilities. Ships built-in LLM, vector store, and memory nodes that let
        teams build RAG pipelines, AI agents, and data-enrichment automations without code —
        while still allowing custom JavaScript/Python nodes for full flexibility. Acts as the
        open-source alternative to Zapier/Make for AI-centric automation.
      </td>
      <td>
        <a href="https://n8n.io" target="_blank">🔗 n8n.io</a><br>
        <a href="https://docs.n8n.io" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=n8n+ai+automation+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>LangFlow</td>
      <td>DataStax (OSS)</td>
      <td>
        Low-code visual builder for LLM workflows and agents built on top of LangChain. Provides
        a drag-and-drop canvas to wire together models, retrievers, tools, and output parsers,
        then exports flows as REST APIs or Python code. Suitable both as a rapid prototyping
        environment and as a deployed backend for production AI applications.
      </td>
      <td>
        <a href="https://langflow.org" target="_blank">🔗 langflow.org</a><br>
        <a href="https://docs.langflow.org" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=langflow+tutorial+rag+agents" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Flowise</td>
      <td>FlowiseAI (OSS)</td>
      <td>
        Open-source drag-and-drop UI for building LLM applications on top of LangChain and
        LlamaIndex. Allows users to visually compose chatbots, RAG pipelines, and agent flows
        and expose them instantly as APIs. Particularly popular for rapid prototyping of
        LangChain-based apps without writing Python, with self-hosting support for data privacy.
      </td>
      <td>
        <a href="https://flowiseai.com" target="_blank">🔗 flowiseai.com</a><br>
        <a href="https://docs.flowiseai.com" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=flowise+ai+rag+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Dify</td>
      <td>LangGenius (OSS)</td>
      <td>
        Open-source LLM application development platform combining a visual workflow builder,
        RAG pipeline, model management, and agent capabilities in a single product. Supports
        dozens of model providers and vector databases, offers an orchestration canvas for
        multi-step AI workflows, and ships a built-in monitoring dashboard for production apps.
      </td>
      <td>
        <a href="https://dify.ai" target="_blank">🔗 dify.ai</a><br>
        <a href="https://docs.dify.ai" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=dify+ai+workflow+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Rivet</td>
      <td>Ironclad (OSS)</td>
      <td>
        Visual AI programming environment for building and debugging complex LLM pipelines as
        interactive node graphs. Designed for teams, it supports subgraphs, input/output type
        checking, and live graph tracing so engineers can iterate on prompt chains and agent
        logic visually before embedding them in production applications via the Rivet SDK.
      </td>
      <td>
        <a href="https://rivet.ironcladapp.com" target="_blank">🔗 rivet.ironcladapp.com</a><br>
        <a href="https://github.com/Ironclad/rivet" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=rivet+ai+visual+programming+llm" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Make</td>
      <td>Make (formerly Integromat)</td>
      <td>
        Cloud-based visual automation platform that connects 1,500+ apps and services through
        a scenario builder. Includes native AI modules (OpenAI, Anthropic, image generation)
        allowing teams to embed LLM-powered steps — summarisation, classification, extraction —
        directly into business workflows without infrastructure management.
      </td>
      <td>
        <a href="https://www.make.com" target="_blank">🔗 make.com</a><br>
        <a href="https://www.make.com/en/help" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=make+automation+ai+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Zapier</td>
      <td>Zapier Inc.</td>
      <td>
        Widely adopted no-code automation platform connecting 6,000+ apps through trigger-action
        Zaps. Offers an AI layer (Zapier AI) with chatbot builders, AI Actions for natural language
        task execution, and direct integrations with ChatGPT and other LLMs, making it the
        accessible entry point for non-engineers automating AI-enhanced business processes.
      </td>
      <td>
        <a href="https://zapier.com" target="_blank">🔗 zapier.com</a><br>
        <a href="https://zapier.com/help" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=zapier+ai+automation+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Botpress</td>
      <td>Botpress Inc. (OSS)</td>
      <td>
        Open-source conversational AI platform with a visual flow studio for building chatbots
        and autonomous agents. Features an LLM-native core with built-in intent understanding,
        knowledge base Q&amp;A (RAG), and multi-channel deployment (web, WhatsApp, Slack, etc.).
        Supports custom AI tasks through code cards, making it suitable for both no-code and
        developer-led bot projects.
      </td>
      <td>
        <a href="https://botpress.com" target="_blank">🔗 botpress.com</a><br>
        <a href="https://botpress.com/docs" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=botpress+ai+chatbot+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>

  </tbody>
</table>

