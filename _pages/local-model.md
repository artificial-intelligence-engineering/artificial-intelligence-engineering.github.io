---
title: "Local Model"
permalink: /local-model/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

## What Is a Local Model?

A **Local Model** (or Local LLM) is an AI model that you download and run directly on your own hardware — a personal computer, workstation, or on-premises server — rather than consuming it through a cloud API.

Unlike cloud-based assistants such as ChatGPT or Claude, a local LLM operates entirely **offline**:

- Your data never leaves your device.
- No internet connection is required to process requests.
- You have full control over the model version, parameters, and runtime configuration.

This makes local models especially relevant for privacy-sensitive use cases, regulated industries, air-gapped environments, and developers who want to iterate quickly without API costs or rate limits.

---

## Cloud API vs. Local Model

| Dimension | Cloud API (e.g. ChatGPT) | Local Model (e.g. Ollama + Llama 3) |
|---|---|---|
| **Data privacy** | Data sent to vendor servers | Data stays on your device |
| **Internet required** | Yes | No |
| **Cost** | Per-token billing | One-time hardware cost |
| **Setup complexity** | Minimal (API key) | Moderate (download + runtime) |
| **Model customisation** | Limited | Full control (fine-tune, quantise) |
| **Latency** | Network-dependent | Hardware-dependent |
| **Model size limit** | Unlimited (vendor-managed) | Constrained by VRAM / RAM |

---

## How It Works

Local models rely on a **runtime** that loads model weights into memory and exposes either a CLI or a local HTTP endpoint (usually OpenAI-compatible, so existing tooling keeps working).

Typical stack:

```
Your app / IDE extension
        ↓
Local runtime (Ollama, LM Studio, llama.cpp…)
        ↓
Quantised model weights (.gguf, .safetensors…)
        ↓
CPU / GPU / NPU on your hardware
```

**Quantisation** is key: it compresses full-precision weights (FP32/FP16) down to 4-bit or 8-bit integers, allowing large models to run on consumer GPUs or even CPU-only machines with acceptable quality loss.

---

## Popular Runtimes and Tools

| Tool | Description | Link |
|---|---|---|
| **Ollama** | The simplest way to run models locally. One `ollama run llama3` command, OpenAI-compatible API out of the box. | [ollama.com](https://ollama.com/) |
| **LM Studio** | Cross-platform desktop app with GUI, model browser, and built-in chat. Great for non-technical users. | [lmstudio.ai](https://lmstudio.ai/) |
| **llama.cpp** | Low-level C++ inference engine. Maximum portability, runs on CPU and GPU, basis for many other tools. | [github.com/ggerganov/llama.cpp](https://github.com/ggerganov/llama.cpp) |
| **Jan** | Open-source, offline-first ChatGPT alternative with local model management. | [jan.ai](https://jan.ai/) |
| **Tengine** | Privacy-first local AI assistant with a clean UI. | [tengine.ai](https://tengine.ai/) |
| **GPT4All** | Curated collection of models optimised for consumer hardware, with chat UI. | [gpt4all.io](https://gpt4all.io/) |

---

## Popular Local Models

| Model | Creator | Strengths | Typical Size |
|---|---|---|---|
| **Llama 3 / 3.1 / 3.2** | Meta | General purpose, strong reasoning | 8B – 70B |
| **Llama 4 Scout** | Meta | First natively multimodal open-weight model | 8B – 70B |
| **Mistral / Mixtral** | Mistral AI | Fast, efficient, great for coding | 7B – 8x7B |
| **Mistral Small 3.1** | Mistral AI | VLM with long context, fits on consumer laptop | 8B |
| **Gemma 2 / 3** | Google | Compact, instruction-tuned | 2B – 27B |
| **Gemma 4** | Google | Widest language coverage, Apache 2.0 | 2B – 27B |
| **Phi-3 / Phi-4** | Microsoft | Small but surprisingly capable, optimized for edge/on-device | 3.8B – 14B |
| **Qwen 2.5** | Alibaba | Multilingual, coding-focused | 0.5B – 72B |
| **Qwen3** | Alibaba | Flagship with switchable thinking/non-thinking modes, Apache 2.0 | 8B – 72B |
| **DeepSeek-R1 (distilled)** | DeepSeek | Reasoning-optimised | 7B – 70B |
| **DeepSeek V4** | DeepSeek | Mixture-of-Experts, million-token context, MIT license, near-frontier performance | 7B – 70B |
| **Nemotron 3 Super** | NVIDIA | Hybrid MoE with million-token context, strong agentic coding | 8B – 70B |
| **GLM 5.1** | Zhipu | First open model to top SWE-Bench Pro, MIT license | 10B – 130B |
| **Kimi K2.6** | Moonshot AI | Competitive on coding, far less costly per token, Modified MIT | 8B – 70B |
| **CodeLlama / StarCoder2** | Meta / BigCode | Code generation specialist, transparent models | 7B – 34B |
| **OLMo 2** | AI2 | Most complete open-source reproducibility, Apache 2.0 | 7B – 13B |
| **Falcon 3** | TII UAE | Lightweight family built for single GPU | 1B – 12B |
| **GPT-OSS 20B** | OpenAI | Optimized for edge devices. | 20B |
| **GPT-OSS 120B** | OpenAI | Designed for powerful desktops, laptops, and data centers. | 120B |

Model weights are distributed primarily through [Hugging Face](https://huggingface.co/models) and the [Ollama model library](https://ollama.com/library).

---

## Hardware Requirements

The main constraint is memory. A rule of thumb:

> **Model GB ≈ (parameters × bits-per-weight) / 8**
>
> A 7B model at 4-bit quantisation ≈ **~4 GB VRAM/RAM**

| Scenario | Recommended setup |
|---|---|
| Casual use (7B–13B, 4-bit) | 8–16 GB unified RAM (Apple Silicon) or 8 GB VRAM GPU |
| Developer workstation (13B–34B) | 24–48 GB VRAM (RTX 3090/4090, A6000) |
| Production server (70B+) | Multi-GPU or high-RAM CPU server |

Apple Silicon Macs (M1/M2/M3/M4) are a popular choice for local models because they share memory between CPU and GPU, making 32–128 GB configurations viable.

---

## Key Use Cases

- **Privacy-first assistants** — process confidential documents without sending data to third parties.
- **Offline development** — code completion and documentation in air-gapped or low-connectivity environments.
- **Cost optimisation** — replace high-volume API calls with a local inference endpoint.
- **Regulated industries** — healthcare, finance, or legal use cases with strict data residency requirements.
- **Research and experimentation** — full control over weights, fine-tuning, and model surgery.
- **Edge and IoT** — run small models on embedded hardware or single-board computers.

---

## Getting Started in 3 Steps (Ollama)

```bash
# 1. Install Ollama (macOS / Linux)
curl -fsSL https://ollama.com/install.sh | sh

# 2. Pull and run a model
ollama run llama3.2

# 3. Use the OpenAI-compatible local API
curl http://localhost:11434/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{"model":"llama3.2","messages":[{"role":"user","content":"Hello!"}]}'
```

Windows users can download the installer from [ollama.com/download](https://ollama.com/download).

---

## Hybrid Architecture: Combining Local and Online LLMs

As local models mature, a powerful pattern has emerged: **combining local models for simple tasks with online APIs for complex reasoning**. This hybrid approach achieves 70–85% cost reduction compared to 100% API usage while maintaining near-API-quality outputs.

### Architectural Paradigms

#### **Stratified Inference (Layered Routing)**

The most popular and mature pattern. Classification routes each request by task complexity:

```
Request
  ├─ Simple (30-40% of requests)
  │   └─→ Local Model (Llama 3.2 7B)  — $0 cost
  ├─ Medium (40-50% of requests)
  │   └─→ Local Model (Llama 3.2 70B) — $0 (more VRAM)
  └─ Complex (10-20% of requests)
      └─→ Online API (GPT-4o, Claude 3.5)  — Pay only this
```

**Popular tools:**
- **LiteLLM** — Router supporting 50+ models (local + APIs) with automatic fallback
- **LangChain Router Runnable** — Conditional routing based on input features
- **LlamaIndex Router Selector** — Similar, optimized for RAG
- **Marooqe** — Specialized routing for cost optimization

**Typical savings:** 70–85% reduction in API costs.

---

#### **Cascading Inference (Fallback Pattern)**

More conservative: try local first, **fallback to online if confidence is low or request times out**:

```
Request
  ├─ Local Model (fast, free)
  │   ├─ ✓ Confident (score > 0.8)
  │   │   └─→ Return result
  │   └─ ✗ Not confident or timeout
  │       └─→ Online API (fallback)
  │           └─→ Return improved result
```

**Implementation:**
- Ollama local endpoint → conditional fallback in LangChain
- LM Studio → compatible with OpenAI API, easy to swap
- vLLM → local server with batch inference and structured output

**Advantage:** Safer than stratified (guarantees minimum quality). Typical cost savings: 40–60%.

---

#### **Speculative Decoding with Verification**

High-performance pattern (popularized by DeepSeek, now adopted by Anthropic). A draft model speculates tokens; a verifier approves or rejects:

```
[Draft Model] (local, 7B)
  ├─ Generate ~5-10 tokens speculatively
  └─→ [Verifier Model] (online, GPT-4o)
      ├─ ✓ Approve tokens → emit
      └─ ✗ Reject → request correction
```

**Advantage:** 2–3x speedup with better quality than draft alone.
**Cost:** ~30–40% more than online-only, but 3x better output.

---

#### **Mixture of Experts (MoE) Native**

MoE models (Mixtral 8x7B, Qwen 2.5 MoE 16x) activate only relevant experts:

```
Input: "What's 2+2?"
  └─→ [MoE Router] → Activate only "Math Expert" (1 of 8)
      └─→ Inference on 1/8 of model (~1B params equivalent)
          └─→ Output: "4" with 12.5% of normal cost
```

**Advantage:** Native, no external routing needed.

---

### Modern Tech Stack (Production 2026)

#### **Local Inference Layer**

| Tool | Speed | Best for |
|---|---|---|
| **Ollama** | ⭐⭐⭐ | Quick start, development |
| **vLLM** | ⭐⭐⭐⭐⭐ | Production, high throughput |
| **llama.cpp** | ⭐⭐⭐⭐ | Edge, low overhead |
| **TensorRT-LLM** | ⭐⭐⭐⭐⭐ | NVIDIA datacenter |
| **MLX** | ⭐⭐⭐⭐ | Apple Silicon (M1/M2+) |

**Production recommendation:** `vLLM` for batch + async, `Ollama` for development.

---

#### **Routing & Orchestration**

| Framework | Specialty |
|---|---|
| **LiteLLM** | Multi-provider abstraction + intelligent fallback |
| **LangChain** | RAG + multi-step workflows with conditional routing |
| **LlamaIndex** | Indexing + smart routing by query type |
| **Marooqe** | Pure cost optimization (ML-based) |
| **Braintrust** | Evaluation + cost optimization together |

---

#### **Quantization & Compression**

To fit models on consumer hardware:

| Technique | Model Size Reduction | Quality | Speed |
|---|---|---|---|
| **4-bit (GGUF)** | 34B → 8 GB | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| **8-bit** | 34B → 16 GB | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| **LoRA / QLoRA** | Fine-tunes with 5% VRAM | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| **Pruning (50%)** | 13B → 7B | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| **Distillation** | 70B → 13B | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |

**Best practice:** Use pre-quantized models from Hugging Face; don't quantize yourself.

---

### Popular Routing Patterns (Code Examples)

#### **Pattern A: Confidence-Based Cascading**

```python
from langchain.chat_models import ChatOllama, ChatOpenAI
from langchain.schema import HumanMessage

async def hybrid_inference(query: str):
    # 1. Try local first
    local_model = ChatOllama(model="llama3.2:7b", temperature=0)
    local_response = local_model.invoke([HumanMessage(content=query)])
    
    # 2. Evaluate confidence
    confidence = estimate_confidence(local_response)
    
    if confidence > 0.8:
        return local_response.content  # Confident
    
    # 3. Fallback to online if needed
    online_model = ChatOpenAI(model="gpt-4o", temperature=0)
    online_response = online_model.invoke([HumanMessage(content=query)])
    return online_response.content
    
def estimate_confidence(response):
    if "I don't know" in response.content.lower():
        return 0.3
    if len(response.content) < 50:
        return 0.5
    return 0.85
```

---

#### **Pattern B: LLM-as-Judge Routing**

```python
from langchain.chains import LLMChain

async def route_by_complexity(query: str):
    router = ChatOpenAI(model="gpt-4-mini")  # Fast + cheap
    
    complexity = classify_complexity(router, query)
    
    if complexity == "simple":
        return await ChatOllama(model="llama3.2:7b").agenerate([query])
    elif complexity == "medium":
        return await ChatOllama(model="llama3.2:70b").agenerate([query])
    else:
        return await ChatOpenAI(model="gpt-4o").agenerate([query])
```

---

#### **Pattern C: LiteLLM Fallback (Simplest)**

```python
from litellm import acompletion

async def hybrid_completion(message: str):
    response = await acompletion(
        model="ollama/llama3.2:7b",
        messages=[{"role": "user", "content": message}],
        fallback=[
            "ollama/llama3.2:70b",  # Try larger local model
            "gpt-4-mini",            # Fallback to cloud
            "claude-3-sonnet"        # Last resort
        ],
        timeout=5
    )
    return response.choices[0].message.content
```

---

### Real-World Use Cases & Benchmarks

**Customer Support Chatbot:**
- FAQ & routing → Llama 3.2 7B local (4 GB VRAM)
- Sentiment + summarization → Llama 3.2 70B quantized (16 GB)
- Complex resolution → Claude 3.5 Sonnet API
- **Result:** 82% resolved locally, 18% escalated.
  - **Cost:** $0.003 per query vs. $0.015 (100% API)

**Code Generation IDE Plugin:**
- Line completions → StarCoder2 3B (Ollama)
- Function generation → StarCoder2 15B (local, 8 GB)
- Refactoring + debugging → Claude Opus API
- **Result:** 70% of edits generated locally.
  - **Cost:** $0.001/edit vs. $0.008 (100% API)

**Content Generation Platform:**
```
Blog outline      → Local (Mistral 7B)
Draft generation  → Local (Llama 70B quantized)
SEO optimization  → GPT-4o (only if local fails)
Final review      → Local (Q&A validation)

Cost per article: $0.05 vs. $0.40 (100% API)
Latency: 30s (vs 45s online)
```

---

### Key Architectural Decisions

#### **Where to Host Local Models?**

| Option | Latency | Cost | Best for |
|---|---|---|---|
| **User Device** | 0ms net | $0 infra | Maximum privacy, edge |
| **On-premises** | 10–50ms | ~$10k setup | Sensitive data (HIPAA) |
| **Company Datacenter** | 5–20ms | $1k–5k/mo | High throughput, scalable |
| **Cloud GPU Spot** | 20–100ms | $0.1–0.5/GPU/h | Flexible, auto-scaling |

**Current consensus:** On-premises datacenter + cloud GPU spot for peak load.

---

#### **Routing Model (How to Decide?)**

1. **Rule-based** (hardcoded)
   - ✅ Simple, predictable
   - ❌ Brittle, doesn't evolve
   - Example: `if len(query) < 50 → local`

2. **LLM-as-Judge** (use model to classify)
   - ✅ Flexible, adapts to new tasks
   - ❌ +1 API call, adds latency
   - Example: GPT-4-mini classifies → local or online

3. **ML Classifier** (trained on history)
   - ✅ Fast, no latency, optimized
   - ❌ Requires historical data + training
   - Example: Marooqe, Braintrust

4. **Hybrid** (rules + ML fallback)
   - ✅ Best of both
   - ❌ More complexity
   - Example: FAQs → rule; else → classifier

**Recommendation:** Start with **rule-based**, migrate to **ML classifier** after 6 months of production data.

---

#### **Fallback Chain**

```python
fallback_chain = [
    "ollama/local-7b",           # Free, 100ms
    "ollama/local-70b",          # Free, 500ms
    "gpt-4-mini",                # $0.00015/k tokens
    "gpt-4o",                    # $0.003/k tokens
    "claude-3-haiku",            # Final fallback
]
```

---

### Recommended Tech Stack (Production MVP)

```
Your App (FastAPI / Node.js)
         ↓
    ┌────┴────┐
    │          │
[LiteLLM]  [LangChain]
    │          │
    └────┬─────┘
         ↓
[Inference Layer]
├─ Local: vLLM on RTX 4090 (datacenter)
├─ Local: Ollama (fallback)
└─ Online: LiteLLM + OpenAI SDK
         ↓
[HF Models (quantized)] + [API Keys]
```

**Essential components:**
- **LiteLLM** — Abstraction + routing
- **vLLM** — Local service (or Ollama for quick start)
- **Redis** — Response caching (30–40% typical hit rate)
- **Prometheus + Grafana** — Metrics (cost, latency, quality)
- **Braintrust / MLflow** — Evaluation + A/B testing

---

### Key Metrics to Monitor

```yaml
Costs:
  - Cost per request (target: <$0.01 local, <$0.05 online)
  - % requests served locally (target: 70–80%)
  - ROI: hardware vs. API savings

Quality:
  - Human eval score (local vs. online)
  - Task completion rate
  - User satisfaction (CSAT)

Speed:
  - P50 / P95 / P99 latency
  - Local vs. online latency delta
  - Time-to-first-token (TTFT)

Operations:
  - Model uptime (99.5% target)
  - GPU memory utilization
  - Queue depth during peak load
```

---

### 12-Month Roadmap

**Months 1–2:** MVP with local models
```bash
ollama pull llama3.2:7b
python -m fastapi run inference_server.py
```

**Months 3–4:** Add online fallback (LiteLLM)
```python
# Automatic fallback on timeout
```

**Months 5–6:** Instrument metrics, A/B testing
```
- Braintrust evaluations
- Datadog + custom dashboards
```

**Months 7–9:** Migrate to vLLM (production), optimize routing
```
- ML classifier instead of rule-based
- Response caching
```

**Months 10–12:** Fine-tune local model + distillation
```
- LoRA fine-tune on domain-specific data
- Distillation: 70B → 13B
```

---

### Emerging Tools to Watch (H2 2026)

- **Griptape** — Autonomous agents framework, local-first
- **Modal Labs** — Serverless GPU, perfect for fallback
- **Replicate** — Model serving without ops overhead
- **Together AI** — Open model inference optimized
- **Baseten** — Model versioning + deployment

---

## Videos and Talks

- [▶ Run Llama 3 Locally – Ollama Tutorial (Matt Williams)](https://www.youtube.com/watch?v=90ozfdsQOKo)
- [▶ Local LLMs Are Getting REALLY Good (Fireship)](https://www.youtube.com/watch?v=Wjrdr0NU4Sk)
- [▶ How to Run AI Locally with Ollama (NetworkChuck)](https://www.youtube.com/watch?v=Oe4F4hDCX3E)
- [▶ llama.cpp Explained – Run Any LLM on CPU (Yannic Kilcher)](https://www.youtube.com/watch?v=pIkHnlOEiQM)
- [▶ LM Studio – Local AI Made Easy (David Ondrej)](https://www.youtube.com/watch?v=ybi5-dn5yeo)

---

## Further Reading

- [A Guide to Running AI Models Locally — What "Local" Really Means (Tengine Blog)](https://tengine.ai/blog/a-guide-to-running-ai-models-locally-what-local-really-means)
- [Ollama Official Documentation](https://ollama.com/)
- [Hugging Face — Local Inference Guide](https://huggingface.co/docs/transformers/main/en/main_classes/model)
- [llama.cpp — GitHub](https://github.com/ggerganov/llama.cpp)
- [The Local AI Landscape (Simon Willison)](https://simonwillison.net/2025/Jan/7/local-models/)


