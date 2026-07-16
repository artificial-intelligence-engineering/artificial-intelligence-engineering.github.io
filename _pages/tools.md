---
title: "Tools Table"
permalink: /tools/
layout: splash
---

<nav class="lxm-toc" aria-label="Tools navigation">
  <strong>Categories</strong>
  <ul>
    <li><a href="#category-code-assistant">Code Assistant</a></li>
    <li><a href="#category-dev-frameworks">Dev Frameworks</a></li>
    <li><a href="#category-ai-assistants">AI Assistants</a></li>
    <li><a href="#category-workflow-automation">Workflow Automation</a></li>
    <li><a href="#category-useful-resources">Useful Resources</a></li>
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
      <th scope="row" id="category-code-assistant">Code Assistant</th>
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
    <tr>
      <th scope="row"></th>
      <td>Terax AI</td>
      <td>Crynta (OSS)</td>
      <td>
        Lightweight (7 MB), terminal-first AI-native dev workspace built with Tauri and TypeScript.
        Designed as a portable, self-contained development environment that integrates LLM capabilities
        directly into a code editor running in the terminal. Perfect for developers who want a minimal,
        fast, all-in-one workspace without IDE bloat.
      </td>
      <td>
        <a href="https://github.com/crynta/terax-ai" target="_blank">🔗 github.com/crynta/terax-ai</a><br>
        <a href="https://github.com/crynta/terax-ai#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=terax+ai+terminal+editor" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Open SWE</td>
      <td>LangChain (OSS)</td>
      <td>
        Open-source software engineering agent stack focused on autonomous issue solving and
        SWE-style workflows. Designed to run end-to-end coding tasks with repository context,
        tool usage, and iterative fix-and-test loops.
      </td>
      <td>
        <a href="https://github.com/langchain-ai/open-swe" target="_blank">🔗 github.com/langchain-ai/open-swe</a><br>
        <a href="https://github.com/langchain-ai/open-swe#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=open+swe+langchain" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>OpenHands</td>
      <td>OpenHands (OSS)</td>
      <td>
        Open-source AI software engineer platform that can inspect codebases, modify files,
        execute commands, and iterate on development tasks from natural-language instructions.
        Frequently used for autonomous bug fixing, feature implementation, and agent benchmarks.
      </td>
      <td>
        <a href="https://github.com/OpenHands/OpenHands" target="_blank">🔗 github.com/OpenHands/OpenHands</a><br>
        <a href="https://github.com/OpenHands/OpenHands#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=openhands+ai+agent" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Mini SWE Agent</td>
      <td>Mini SWE Agent (OSS)</td>
      <td>
        Lightweight SWE-agent style framework for running coding agents with a minimal setup.
        Aims to provide a simpler, faster environment for software-task automation and agent
        experimentation compared to heavier full-platform stacks.
      </td>
      <td>
        <a href="https://mini-swe-agent.com/latest/" target="_blank">🔗 mini-swe-agent.com/latest</a><br>
        <a href="https://mini-swe-agent.com" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=mini+swe+agent+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Webwright</td>
      <td>Microsoft (OSS)</td>
      <td>
        Open-source coding and automation project from Microsoft focused on reliable developer
        workflows, combining agent-style execution with practical engineering utilities.
      </td>
      <td>
        <a href="https://github.com/microsoft/Webwright" target="_blank">🔗 github.com/microsoft/Webwright</a><br>
        <a href="https://github.com/microsoft/Webwright#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=microsoft+webwright+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>CodeGraph</td>
      <td>colbymchenry (OSS)</td>
      <td>
        Open-source coding assistant project focused on codebase-aware workflows and developer
        productivity through graph-oriented code understanding and automation patterns.
      </td>
      <td>
        <a href="https://github.com/colbymchenry/codegraph" target="_blank">🔗 github.com/colbymchenry/codegraph</a><br>
        <a href="https://github.com/colbymchenry/codegraph#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=codegraph+coding+assistant+tutorial" target="_blank">▶ YouTube tutorials</a>
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
    <tr>
      <th scope="row"></th>
      <td>LM Studio</td>
      <td>Element Labs Inc. (OSS)</td>
      <td>
        LM Studio is a popular desktop application that allows you to discover, download, and run
        large language models (LLMs) directly on your local consumer hardware. It provides an intuitive,
        user-friendly interface that lets you run models completely offline.
      </td>
      <td>
        <a href="https://lmstudio.ai" target="_blank">🔗 lmstudio.ai</a><br>
        <a href="https://github.com/lmstudio-ai/lmstudio" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=lmstudio+local+llm+tutorial" target="_blank">▶ YouTube tutorials</a>
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
    <tr>
      <th scope="row"></th>
      <td>NanoBoot</td>
      <td>HKUDS (OSS)</td>
      <td>
        Lightweight, open-source AI agent framework designed for tools, chats, and workflows.
        Supports multiple LLM providers (OpenAI, Anthropic, Claude, Codex) and is optimised for
        building minimal-footprint assistants that integrate with external tools and act on user requests
        without requiring heavy infrastructure or complex orchestration overhead.
      </td>
      <td>
        <a href="https://github.com/HKUDS/nanobot" target="_blank">🔗 github.com/HKUDS/nanobot</a><br>
        <a href="https://github.com/HKUDS/nanobot#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=nanobot+ai+agent" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Odysseus</td>
      <td>pewdiepie-archdaemon (OSS)</td>
      <td>
        Open-source AI assistant project focused on agentic workflows and practical integration patterns
        for building helpful assistants.
      </td>
      <td>
        <a href="https://github.com/pewdiepie-archdaemon/odysseus" target="_blank">🔗 github.com/pewdiepie-archdaemon/odysseus</a><br>
        <a href="https://github.com/pewdiepie-archdaemon/odysseus#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=odysseus+ai+assistant" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>OpenNotebook</td>
      <td><a href="https://github.com/lfnovo" target="_blank">@lfnovo (OSS)</a></td>
      <td>
        An Open Source implementation of Notebook LM with more flexibility and features.
      </td>
      <td>
        <a href="https://github.com/lfnovo/open-notebook" target="_blank">🔗 github.com/lfnovo/open-notebook</a><br>
        <a href="https://www.open-notebook.ai/" target="_blank">🔗 open-notebook.ai</a>
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
      <td>LiteLLM</td>
      <td>BerriAI (OSS)</td>
      <td>
        Unified LLM gateway and proxy that provides an OpenAI-compatible interface across many
        model providers. Adds routing, fallback, caching, budgets, usage tracking, and policy
        controls, making it a practical orchestration layer for multi-model workflow automation.
      </td>
      <td>
        <a href="https://github.com/BerriAI/litellm" target="_blank">🔗 github.com/BerriAI/litellm</a><br>
        <a href="https://docs.litellm.ai" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=litellm+gateway+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>AI6x</td>
      <td>API7 (OSS)</td>
      <td>
        Open-source AI gateway focused on secure, governable access to LLM services. Designed
        to centralize auth, rate limiting, observability, and policy enforcement for AI traffic,
        helping teams run production agent workflows with stronger operational controls.
      </td>
      <td>
        <a href="https://github.com/api7/aisix" target="_blank">🔗 github.com/api7/aisix</a><br>
        <a href="https://github.com/api7/aisix#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=api7+aisix+ai+gateway" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Envoy AI Gateway</td>
      <td>Envoy Proxy (OSS)</td>
      <td>
        AI-focused gateway built on Envoy for managing and standardizing LLM inference traffic.
        Supports provider abstraction, traffic controls, resiliency, observability, and governance
        capabilities required for enterprise-grade AI workflow automation.
      </td>
      <td>
        <a href="https://github.com/envoyproxy/ai-gateway" target="_blank">🔗 github.com/envoyproxy/ai-gateway</a><br>
        <a href="https://github.com/envoyproxy/ai-gateway#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=envoy+ai+gateway+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Open Connector</td>
      <td>Oomol Lab (OSS)</td>
      <td>
        Open-source connector framework for integrating external apps, APIs, and services into
        automated workflows. Useful for building reusable integration blocks that feed data and
        actions into AI pipelines and agent orchestration layers.
      </td>
      <td>
        <a href="https://github.com/oomol-lab/open-connector" target="_blank">🔗 github.com/oomol-lab/open-connector</a><br>
        <a href="https://github.com/oomol-lab/open-connector#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=oomol+open+connector" target="_blank">▶ YouTube tutorials</a>
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
    <tr>
      <th scope="row"></th>
      <td>VoltAgent</td>
      <td>VoltAgent (OSS)</td>
      <td>
        Open-source framework for building and orchestrating AI agent workflows with emphasis on
        developer experience, modularity, and production-ready integrations for tool-driven agents.
      </td>
      <td>
        <a href="https://voltagent.dev/" target="_blank">🔗 voltagent.dev</a><br>
        <a href="https://github.com/voltagent/voltagent/" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=voltagent+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>WorkflowBuilder</td>
      <td>SynergyCodes (OSS)</td>
      <td>
        Open-source visual workflow editor component oriented to building automation and process
        pipelines in web applications, useful as a customizable orchestration layer.
      </td>
      <td>
        <a href="https://github.com/synergycodes/workflowbuilder" target="_blank">🔗 github.com/synergycodes/workflowbuilder</a><br>
        <a href="https://github.com/synergycodes/workflowbuilder#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=workflowbuilder+synergycodes+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Conductor OSS</td>
      <td>conductor-oss (OSS)</td>
      <td>
        Distributed workflow orchestration engine for microservices and long-running processes.
        Commonly used to coordinate complex task graphs, retries, and event-driven automations.
      </td>
      <td>
        <a href="https://docs.conductor-oss.org/" target="_blank">🔗 docs.conductor-oss.org</a><br>
        <a href="https://github.com/conductor-oss/conductor" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=conductor+oss+workflow+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Sim</td>
      <td>Sim Studio AI (OSS)</td>
      <td>
        Open-source platform for AI workflow and agent experimentation focused on composing,
        running, and iterating multi-step flows with reusable building blocks.
      </td>
      <td>
        <a href="https://github.com/simstudioai/sim" target="_blank">🔗 github.com/simstudioai/sim</a><br>
        <a href="https://github.com/simstudioai/sim#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=simstudioai+sim+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Windmill</td>
      <td>Windmill Labs (OSS)</td>
      <td>
        Open-source developer platform for internal tools and workflow automation with support for
        scripts, scheduling, queues, and API-driven orchestration across teams.
      </td>
      <td>
        <a href="https://www.windmill.dev/" target="_blank">🔗 windmill.dev</a><br>
        <a href="https://github.com/windmill-labs/windmill" target="_blank">📄 GitHub repo</a><br>
        <a href="https://www.youtube.com/results?search_query=windmill+dev+workflow+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Ynode</td>
      <td>iamyureka (OSS)</td>
      <td>
        Open-source node-based workflow builder aimed at creating automation pipelines through a
        visual graph approach, suitable for rapid prototyping and custom process orchestration.
      </td>
      <td>
        <a href="https://github.com/iamyureka/ynode" target="_blank">🔗 github.com/iamyureka/ynode</a><br>
        <a href="https://github.com/iamyureka/ynode#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=ynode+workflow+builder+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>

    <!-- ── Useful Resources ─────────────────────────────────── -->
    <tr>
      <th scope="row" id="category-useful-resources">Useful Resources</th>
      <td>codebase-memory-mcp</td>
      <td>DeusData (OSS)</td>
      <td>
        High-performance code intelligence MCP server. Indexes codebases into a persistent knowledge graph
        — average repo in milliseconds. 158 languages, sub-ms queries, 99% fewer tokens. Single static
        binary, zero dependencies.
      </td>
      <td>
        <a href="https://github.com/DeusData/codebase-memory-mcp" target="_blank">🔗 github.com/DeusData/codebase-memory-mcp</a><br>
        <a href="https://github.com/DeusData/codebase-memory-mcp#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://arxiv.org/abs/2603.27277" target="_blank">📄 Codebase-Memory: Tree-Sitter-Based Knowledge Graphs for LLM Code Exploration via MCP</a><br>
        <a href="https://deusdata.github.io/codebase-memory-mcp/" target="_blank">📘 Quick Start / usage guide</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>RODA MCP Server</td>
      <td>AWS Labs (OSS)</td>
      <td>
        Model Context Protocol (MCP) server for discovering and exploring datasets from the
        Registry of Open Data on AWS. Enables natural-language dataset search, metadata inspection,
        license-aware discovery, and early fit evaluation through S3 structure preview and file
        sampling for eligible public datasets.
      </td>
      <td>
        <a href="https://github.com/awslabs/mcp/tree/main/src/roda-mcp-server" target="_blank">🔗 github.com/awslabs/mcp/tree/main/src/roda-mcp-server</a><br>
        <a href="https://aws.amazon.com/blogs/opensource/introducing-mcp-server-for-registry-of-open-data-on-aws/" target="_blank">📄 AWS Open Source Blog announcement</a><br>
        <a href="https://registry.opendata.aws/" target="_blank">📘 Registry of Open Data on AWS</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Agents Towards Production</td>
      <td>Nir Diamant (OSS)</td>
      <td>
        The true value of this repository is not that it teaches you how to build an agent that
        answers questions. It addresses the four real production pain points:<br><br>
        🔐 Agent Security (with LlamaFirewall and Apex)<br><br>
        🧠 Agent Memory (with Redis)<br><br>
        📊 Observability (with Qualifire)<br>
        🧪 Evaluation (intelligent).
      </td>
      <td>
        <a href="https://github.com/NirDiamant/agents-towards-production" target="_blank">🔗 github.com/NirDiamant/agents-towards-production</a><br>
        <a href="https://github.com/NirDiamant/agents-towards-production#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=agents+towards+production+nir+diamant" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>AI Engineering From Scratch</td>
      <td>rohitg00 (OSS)</td>
      <td>
        Open-source learning repository focused on practical AI engineering fundamentals, including
        end-to-end concepts, implementation patterns, and hands-on examples for building AI systems.
      </td>
      <td>
        <a href="https://github.com/rohitg00/ai-engineering-from-scratch" target="_blank">🔗 github.com/rohitg00/ai-engineering-from-scratch</a><br>
        <a href="https://github.com/rohitg00/ai-engineering-from-scratch#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=ai+engineering+from+scratch+rohitg00" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Web Quality Skills</td>
      <td>Addy Osmani (Google)</td>
      <td>
        Curated roadmap of practical web engineering skills for building high-quality web products,
        covering performance, accessibility, testing, and reliability best practices.
      </td>
      <td>
        <a href="https://github.com/addyosmani/web-quality-skills" target="_blank">🔗 github.com/addyosmani/web-quality-skills</a><br>
        <a href="https://github.com/addyosmani/web-quality-skills#readme" target="_blank">📄 GitHub README</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>LiteRT.js</td>
      <td>Google AI Edge (OSS)</td>
      <td>
        Web runtime for LiteRT (formerly TensorFlow Lite) that runs `.tflite` models directly
        in the browser. Supports WebGPU acceleration on compatible browsers, XNNPack-accelerated
        CPU execution, and integration with existing TensorFlow.js pipelines.
      </td>
      <td>
        <a href="https://github.com/google-ai-edge/LiteRT/tree/main/litert/js" target="_blank">🔗 github.com/google-ai-edge/LiteRT/tree/main/litert/js</a><br>
        <a href="https://ai.google.dev/edge/litert/web" target="_blank">📄 Official docs</a><br>
        <a href="https://www.youtube.com/results?search_query=LiteRT.js+tutorial" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>LLMs-from-scratch</td>
      <td>rasbt (OSS)</td>
      <td>
        Open-source educational resource that builds large language models from first principles,
        combining theory and hands-on implementations for deep understanding of LLM internals.
      </td>
      <td>
        <a href="https://github.com/rasbt/LLMs-from-scratch" target="_blank">🔗 github.com/rasbt/LLMs-from-scratch</a><br>
        <a href="https://github.com/rasbt/LLMs-from-scratch#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.youtube.com/results?search_query=rasbt+llms+from+scratch" target="_blank">▶ YouTube tutorials</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>SkillSpector</td>
      <td>NVIDIA (OSS)</td>
      <td>
        Security scanner for AI agent skills. Detect vulnerabilities, malicious patterns, and security risks.
      </td>
      <td>
        <a href="https://github.com/nvidia/skillspector" target="_blank">🔗 github.com/nvidia/skillspector</a><br>
        <a href="https://github.com/nvidia/skillspector#readme" target="_blank">📄 GitHub README</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>llm-checker</td>
      <td>Pavelevich (OSS)</td>
      <td>
        Advanced CLI tool that scans your hardware and estimates which LLM or sLLM models are viable to run locally.
        Useful for quickly determining resource fit (RAM/VRAM) and selecting the most realistic local model options,
        with built-in Ollama integration.
      </td>
      <td>
        <a href="https://github.com/Pavelevich/llm-checker" target="_blank">🔗 github.com/Pavelevich/llm-checker</a><br>
        <a href="https://github.com/Pavelevich/llm-checker#readme" target="_blank">📄 GitHub README</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Codex-LB</td>
      <td>Slawomir Baran Johansen (OSS)</td>
      <td>
        Load balancer for ChatGPT accounts with usage tracking, dashboard, and OpenAI-compatible endpoints.
      </td>
      <td>
        <a href="https://soju06-codex-lb-43.mintlify.app/introduction" target="_blank">🔗 https://soju06-codex-lb-43.mintlify.app/introduction</a><br>
        <a href="https://github.com/Soju06/codex-lb" target="_blank">📄 https://github.com/Soju06/codex-lb</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>Ponytail</td>
      <td>Dietrich Gebert (OSS)</td>
      <td>
        Ponytail is an open-source AI coding tool and plugin that programs the AI to "think like a lazy senior developer." It enforces a "less code is more" philosophy to prevent technical debt, saving time and API costs by urging the AI to reuse existing functions rather than writing new code.
      </td>
      <td>
        <a href="https://github.com/DietrichGebert/ponytail" target="_blank">🔗 github.com/DietrichGebert/ponytail</a><br>
        <a href="https://github.com/DietrichGebert/ponytail#readme" target="_blank">📄 GitHub README</a><br>
        <a href="https://www.linkedin.com/in/dietrich-gebert-b3a314a9/" target="_blank">👤 Author profile</a>
      </td>
    </tr>
    <tr>
      <th scope="row"></th>
      <td>gentleman-ai</td>
      <td>Gentleman Programming (OSS)</td>
      <td>
        Gentle-AI (part of the Gentleman Programming ecosystem) is an open-source CLI/TUI configurator that upgrades existing AI coding agents (like Claude Code, OpenCode, Cursor, and Windsurf) into full-fledged, disciplined engineering environments.
      </td>
      <td>
        <a href="https://github.com/Gentleman-Programming/gentle-ai" target="_blank">🔗 github.com/Gentleman-Programming/gentle-ai</a><br>
        <a href="https://github.com/Gentleman-Programming/gentle-ai#readme" target="_blank">📄 GitHub README</a>
      </td>
    </tr>

  </tbody>
</table>
