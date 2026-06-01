---
title: "Tools Table"
permalink: /tools/
layout: splash
---

<nav class="lxm-toc" aria-label="Tools navigation">
  <strong>Categories</strong>
  <ul>
    <li><a href="#category-code-assistant">Code Assistant Tools</a></li>
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

  </tbody>
</table>

