---
title: "Benchmarks Table"
permalink: /benchmarks/
layout: splash
---

<table style="width:100%; table-layout:fixed;">
  <colgroup>
    <col style="width:22%;">
    <col style="width:43%;">
    <col style="width:35%;">
  </colgroup>
  <thead>
    <tr>
      <th scope="col">Benchmark</th>
      <th scope="col">Focus</th>
      <th scope="col">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">MMLU</th>
      <td>
        Evaluates broad knowledge and reasoning across many academic and professional subjects.
      </td>
      <td>
        <a href="https://arxiv.org/abs/2009.03300" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">Humanity's Last Exam</th>
      <td>
        Evaluates frontier models on expert-level academic reasoning and knowledge across more than 100 subjects. It is a multimodal benchmark with 2,500 challenging closed-ended questions designed to avoid benchmark saturation.
      </td>
      <td>
        <a href="https://agi.safe.ai/" target="_blank">Website</a><br>
        <a href="https://arxiv.org/abs/2501.14249" target="_blank">Paper</a><br>
        <a href="https://huggingface.co/datasets/cais/hle" target="_blank">Dataset</a>
      </td>
    </tr>
    <tr>
      <th scope="row">HellaSwag</th>
      <td>
        Measures commonsense reasoning by selecting the most plausible ending for a grounded scenario.
      </td>
      <td>
        <a href="https://rowanzellers.com/hellaswag/" target="_blank">Project Page</a><br>
        <a href="https://arxiv.org/abs/1905.07830" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">GSM8K</th>
      <td>
        Evaluates grade-school math word-problem solving and multi-step numerical reasoning.
      </td>
      <td>
        <a href="https://arxiv.org/abs/2110.14168" target="_blank">Paper</a><br>
        <a href="https://huggingface.co/datasets/openai/gsm8k" target="_blank">Dataset</a>
      </td>
    </tr>
    <tr>
      <th scope="row">TruthfulQA</th>
      <td>
        Tests factual truthfulness and resistance to generating common misconceptions.
      </td>
      <td>
        <a href="https://arxiv.org/abs/2109.07958" target="_blank">Paper</a><br>
        <a href="https://github.com/sylinrl/TruthfulQA" target="_blank">Repository</a>
      </td>
    </tr>
    <tr>
      <th scope="row">ARC (Challenge)</th>
      <td>
        Assesses science question answering and reasoning over grade-school level knowledge.
      </td>
      <td>
        <a href="https://arxiv.org/abs/1803.05457" target="_blank">Paper</a><br>
        <a href="https://allenai.org/data/arc" target="_blank">Dataset</a>
      </td>
    </tr>
    <tr>
      <th scope="row">BIG-bench Hard (BBH)</th>
      <td>
        Stress-tests difficult reasoning tasks selected from BIG-bench for stronger discrimination.
      </td>
      <td>
        <a href="https://arxiv.org/abs/2210.09261" target="_blank">Paper</a><br>
        <a href="https://github.com/suzgunmirac/BIG-Bench-Hard" target="_blank">Repository</a>
      </td>
    </tr>
    <tr>
      <th scope="row">MATH</th>
      <td>
        Evaluates advanced mathematical reasoning on competition-style problems.
      </td>
      <td>
        <a href="https://arxiv.org/abs/2103.03874" target="_blank">Paper</a><br>
        <a href="https://github.com/hendrycks/math" target="_blank">Repository</a>
      </td>
    </tr>
    <tr>
      <th scope="row">BIG-bench</th>
      <td>
        Evaluates broad and diverse emergent capabilities across many challenging language tasks.
      </td>
      <td>
        <a href="https://github.com/google/BIG-bench" target="_blank">Repository</a><br>
        <a href="https://arxiv.org/abs/2206.04615" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">MT-Bench</th>
      <td>
        Measures multi-turn instruction-following quality and chat performance, often with LLM-as-a-judge.
      </td>
      <td>
        <a href="https://arxiv.org/abs/2306.05685" target="_blank">Paper</a><br>
        <a href="https://github.com/lm-sys/FastChat/tree/main/fastchat/llm_judge" target="_blank">Implementation</a>
      </td>
    </tr>
    <tr>
      <th scope="row">GPQA</th>
      <td>
        Evaluates graduate-level domain knowledge and difficult reasoning in science-focused questions.
      </td>
      <td>
        <a href="https://arxiv.org/abs/2311.12022" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">DROP</th>
      <td>
        Tests reading comprehension with discrete reasoning over passages (counts, arithmetic, and comparisons).
      </td>
      <td>
        <a href="https://allenai.org/data/drop" target="_blank">Dataset</a><br>
        <a href="https://arxiv.org/abs/1903.00161" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">SQuAD</th>
      <td>
        Evaluates extractive question answering and reading comprehension on Wikipedia passages.
      </td>
      <td>
        <a href="https://rajpurkar.github.io/SQuAD-explorer/" target="_blank">Dataset</a><br>
        <a href="https://arxiv.org/abs/1606.05250" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">HumanEval</th>
      <td>
        Measures code generation quality by checking functional correctness of generated Python functions.
      </td>
      <td>
        <a href="https://github.com/openai/human-eval" target="_blank">Repository</a>
      </td>
    </tr>
    <tr>
      <th scope="row">SWE-bench</th>
      <td>
        Tests software engineering ability by solving real GitHub issues in open-source repositories.
      </td>
      <td>
        <a href="https://www.swebench.com/" target="_blank">Leaderboard</a><br>
        <a href="https://arxiv.org/abs/2310.06770" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">DeepSWE</th>
      <td>
        Evaluates frontier coding agents on original, long-horizon software engineering tasks. It is designed to differentiate top models with contamination-free tasks, diverse repositories and languages, and behavior-based verification.
      </td>
      <td>
        <a href="https://deepswe.datacurve.ai/" target="_blank">Website</a><br>
        <a href="https://deepswe.datacurve.ai/blog/deepswe" target="_blank">Methodology Blog</a><br>
        <a href="https://github.com/datacurve-ai/deep-swe" target="_blank">Repository</a>
      </td>
    </tr>
    <tr>
      <th scope="row">ProgramBench</th>
      <td>
        Evaluates whether language models and coding agents can rebuild programs from scratch given only a compiled binary and its documentation, reproducing the original program's behavior with a complete codebase.
      </td>
      <td>
        <a href="https://programbench.com/" target="_blank">Website</a><br>
        <a href="https://arxiv.org/abs/2605.03546" target="_blank">Paper</a><br>
        <a href="https://github.com/facebookresearch/ProgramBench" target="_blank">Repository</a>
      </td>
    </tr>
    <tr>
      <th scope="row">MCP-Atlas</th>
      <td>
        Evaluates AI agents' tool-use capabilities on real-world tasks across 36 Model Context Protocol servers, using a standardized Dockerized environment and LLM-as-judge scoring with pass rate and coverage metrics.
      </td>
      <td>
        <a href="https://scale.com/leaderboard/mcp_atlas" target="_blank">Leaderboard</a><br>
        <a href="https://static.scale.com/uploads/674f4cc7a74e35bcaae1c29a/MCP_Atlas.pdf" target="_blank">Paper</a><br>
        <a href="https://github.com/scaleapi/mcp-atlas" target="_blank">Repository</a>
      </td>
    </tr>
    <tr>
      <th scope="row">Tool-Decathlon</th>
      <td>
        Evaluates language agents' general tool use in diverse, realistic, and long-horizon task environments. Toolathlon features 600+ tools based on real-world software environments and tasks that require extended sequences of tool calls.
      </td>
      <td>
        <a href="https://toolathlon.xyz/" target="_blank">Website</a><br>
        <a href="https://arxiv.org/abs/2510.25726" target="_blank">Paper</a><br>
        <a href="https://github.com/hkust-nlp/Toolathlon" target="_blank">Repository</a>
      </td>
    </tr>
    <tr>
      <th scope="row">Terminal-Bench</th>
      <td>
        Evaluates AI agents in terminal environments, measuring terminal mastery across long-horizon tasks in software engineering, machine learning, security, data science, and related domains.
      </td>
      <td>
        <a href="https://www.tbench.ai/" target="_blank">Website</a><br>
        <a href="https://www.tbench.ai/leaderboard" target="_blank">Leaderboard</a><br>
        <a href="https://www.tbench.ai/benchmarks/terminal-bench-2" target="_blank">Terminal-Bench 2.0</a>
      </td>
    </tr>
    <tr>
      <th scope="row">NL2RepoBench</th>
      <td>
        Evaluates LLMs and coding agents on long-horizon 0-to-1 software tasks that require generating a complete, runnable code repository from scratch. The benchmark consists of 104 tasks, each with its own testing environment.
      </td>
      <td>
        <a href="https://github.com/multimodal-art-projection/NL2RepoBench" target="_blank">Repository</a><br>
        <a href="https://github.com/multimodal-art-projection/NL2RepoBench#readme" target="_blank">README</a>
      </td>
    </tr>
    <tr>
      <th scope="row">MMMU</th>
      <td>
        Assesses multimodal understanding and reasoning with image-plus-text tasks across disciplines.
      </td>
      <td>
        <a href="https://mmmu-benchmark.github.io/" target="_blank">Project Page</a><br>
        <a href="https://arxiv.org/abs/2311.16502" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">HELM</th>
      <td>
        Provides holistic evaluation across scenarios and metrics such as accuracy, calibration, and robustness.
      </td>
      <td>
        <a href="https://crfm.stanford.edu/helm/latest/" target="_blank">Dashboard</a><br>
        <a href="https://arxiv.org/abs/2211.09110" target="_blank">Paper</a>
      </td>
    </tr>
    <tr>
      <th scope="row">LMArena</th>
      <td>
        LMArena (formerly known as Chatbot Arena) is a popular, crowdsourced AI evaluation platform where users compare
        different artificial intelligence models through blind, head-to-head battles.
      </td>
      <td>
        <a href="https://lmarena.ai/" target="_blank">Website</a><br>
        <a href="https://www.youtube.com/results?search_query=lmarena+chatbot+arena" target="_blank">YouTube tutorials</a>
      </td>
    </tr>
  </tbody>
</table>
