---
title: "AI Agent"
permalink: /ai-agent/
layout: single
author_profile: false
toc: true
toc_sticky: true
toc_label: "Table of Contents"
---

## What Is an AI Agent?

An AI agent is a computer program powered by artificial intelligence (AI) that can perform tasks autonomously to assist human users, even without definite instructions.

Unlike other AI-powered software, such as chatbots, AI agents can operate outside of a specific prompt-based context. They can go outside of their training data and take a look around at the world, so to speak, to find information. Then they can, on their own, take actions based on that information in pursuit of a larger goal.

## Key Characteristics

- **Autonomy:** Can execute tasks with limited or no step-by-step human direction.
- **Goal orientation:** Works toward an objective instead of only answering one isolated prompt.
- **Environment interaction:** Can gather external information before deciding what to do next.
- **Action capability:** Can take actions (for example, calling tools or services) based on observed context.

## AI Agent Types (IBM Classification)

Based on IBM's classification, there are five core AI agent types: simple reflex, model-based reflex, goal-based, utility-based, and learning agents.

| Agent Type | Decision Style | Best Fit | Typical Limitation |
| --- | --- | --- | --- |
| Simple reflex agent | Condition-action rules from current input only | Stable, repetitive environments | No memory of past state |
| Model-based reflex agent | Rules + internal state model | Partially observable environments | Model quality affects decisions |
| Goal-based agent | Plans actions to reach a target objective | Navigation, task planning, routing | Planning cost can increase latency |
| Utility-based agent | Chooses action with highest utility score | Trade-offs across multiple objectives | Utility design can be complex |
| Learning agent | Improves policy from feedback and experience | Dynamic or uncertain environments | Needs data, feedback loops, and tuning |

## Simple Reflex Agents

Simple reflex agents are the most basic type. They map a current observation directly to an action using predefined condition-action rules.

![Simple Reflex Agents diagram](/assets/images/ai-agents-simple-reflex.png)

- They do not reason about history or future consequences.
- They work well when the environment is predictable and rules are clear.
- Typical examples include thermostats and basic traffic-signal control.

## Model-Based Reflex Agents

Model-based reflex agents extend reflex behavior with an internal model of the world.

![Model-based Reflex Agents diagram](/assets/images/ai-agents-model-based-reflex.png)

- They still use rules, but also keep track of state from prior observations.
- They perform better than simple reflex agents when not all information is visible at once.
- A common example is a robot that combines current sensor input with remembered obstacle positions.

## Goal-Based Agents

Goal-based agents choose actions by evaluating which steps move them closer to a defined objective.

![Goal-Based Agents diagram](/assets/images/ai-agents-goal-based.png)

- They are proactive: not only reacting, but planning toward a goal.
- They compare possible actions before acting.
- A navigation robot reaching a specific destination is a standard example.

## Utility-Based Agents

Utility-based agents optimize decisions with a utility function, not only binary goal completion.

![Utility-Based Agents diagram](/assets/images/ai-agents-utility-based.png)

- They score alternatives and pick the option with the highest expected value.
- They are useful when there are multiple objectives and trade-offs (for example speed vs. safety).
- Autonomous driving decisions are a common example of utility-based reasoning.

## Learning Agents

Learning agents improve over time by updating behavior from feedback and new data.

![Learning Agents diagram](/assets/images/ai-agents-learning.png)

- They adapt to changing environments and uncertainty.
- A common structure includes a performance element, learning element, critic, and problem generator.
- They are strongest when rules cannot be fully predefined in advance.

## Classification Notes

- These five types are often combined in practical systems.
- Modern multi-agent systems can assign different agent types to different subtasks.
- Source classification: [Types of AI agents - IBM](https://www.ibm.com/think/topics/ai-agent-types)

## AI Agents Development

The AI agents ecosystem includes SDKs, frameworks, and managed services. The following table summarizes well-known options for building and operating AI agents in production.

| Tool | Type | Who builds | Ecosystem lock-in | Time to production | Enterprise governance |
| --- | --- | --- | --- | --- | --- |
| Nexus | Platform + service | Business teams | None (4,000+ integrations) | Days to weeks | SOC 2 II, ISO 27001, ISO 42001, GDPR |
| Microsoft Agent Framework | Open-source SDK | Engineers (Python/C#) | Azure/Microsoft | Weeks to months | Azure baseline, custom build required |
| LangChain / LangGraph | Open-source framework | Engineers (Python/JS) | None | Weeks to months | Custom build required |
| CrewAI | Open-source framework | Engineers (Python) | None | Weeks to months | Enterprise tier available |
| Google Vertex AI Agents | Managed cloud service | Engineers + low-code | Google Cloud | Weeks to months | Google Cloud baseline |
| AWS Bedrock Agents | Managed cloud service | Engineers | AWS | Weeks to months | AWS baseline |
| Anthropic Claude Agent SDK | SDK | Engineers (Python) | Anthropic models | Weeks to months | Custom build required |
| OpenAI Agents SDK | SDK | Engineers (Python) | OpenAI models | Weeks to months | Custom build required |
| Copilot Studio | Low-code builder | Business teams + IT | Microsoft | Weeks | Microsoft compliance layer |
| Dify | Open-source platform | Technical users | None (self-hosted) | Weeks | Custom build required |

### AI Agent Development Paradigm: Agent Loop

A language model can answer questions. An agent can do things. The agent loop is what makes that difference possible.

When a model receives a request it cannot fully address with its training alone, it needs to reach out into the world: read files, query databases, call APIs, execute code. The agent loop is the orchestration layer that enables this. It manages the cycle of reasoning and action that allows a model to tackle problems requiring multiple steps, external information, or real-world side effects.

This is the foundational concept in Strands. Everything else builds on top of it.

#### How the Loop Works

The agent loop operates on a simple principle: invoke the model, check if it wants to use a tool, execute the tool if so, then invoke the model again with the result. Repeat until the model produces a final response.

![AI Agent Loop diagram](/assets/images/ai-agent-loop.png)

The diagram shows the recursive structure at the heart of the loop. The model reasons, selects a tool, the tool executes, and the result feeds back into the model for another round of reasoning. This cycle continues until the model decides it has enough information to respond.

What makes this powerful is the accumulation of context. Each iteration through the loop adds to the conversation history. The model sees not just the original request, but every tool it has called and every result it has received. This accumulated context enables sophisticated multi-step reasoning.

## Notes

- [What are AI agents? - AWS](https://aws.amazon.com/what-is/ai-agents/)
- [AI agents: What they are and how they'll change the way we work - Microsoft Source](https://news.microsoft.com/source/features/ai/ai-agents-what-they-are-and-how-theyll-change-the-way-we-work/)
- [AAIF - Agentic AI Foundation](https://aaif.io/)


