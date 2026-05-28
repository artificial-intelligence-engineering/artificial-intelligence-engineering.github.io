# Langflow

<!-- markdownlint-disable MD030 -->

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./docs/static/img/langflow-logo-color-blue-bg.svg">
  <img src="./docs/static/img/langflow-logo-color-black-solid.svg" alt="Langflow logo">
</picture>

[![Release Notes](https://img.shields.io/github/release/langflow-ai/langflow?style=flat-square)](https://github.com/langflow-ai/langflow/releases)
[![PyPI - License](https://img.shields.io/badge/license-MIT-orange)](https://opensource.org/licenses/MIT)
[![PyPI - Downloads](https://img.shields.io/pypi/dm/langflow?style=flat-square)](https://pypistats.org/packages/langflow)
[![Twitter](https://img.shields.io/twitter/url/https/twitter.com/langflow-ai.svg?style=social&label=Follow%20%40Langflow)](https://twitter.com/langflow_ai)
[![YouTube Channel](https://img.shields.io/youtube/channel/subscribers/UCn2bInQrjdDYKEEmbpwblLQ?label=Subscribe)](https://www.youtube.com/@Langflow)
[![Discord Server](https://img.shields.io/discord/1116803230643527710?logo=discord&style=social&label=Join)](https://discord.gg/EqksyE2EX9)
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/langflow-ai/langflow)

[Langflow](https://langflow.org) is a powerful platform for building and deploying AI-powered agents and workflows. It provides developers with both a visual authoring experience and built-in API and MCP servers that turn every workflow into a tool that can be integrated into applications built on any framework or stack. Langflow comes with batteries included and supports all major LLMs, vector databases and a growing library of AI tools.

## Highlight features

- **Visual builder interface** to quickly get started and iterate.
- **Source code access** lets you customize any component using Python.
- **Interactive playground** to immediately test and refine your flows with step-by-step control.
- **Multi-agent orchestration** with conversation management and retrieval.
- **Deploy as an API** or export as JSON for Python apps.
- **Deploy as an MCP server** and turn your flows into tools for MCP clients.
- **Observability** with LangSmith, LangFuse and other integrations.
- **Enterprise-ready** security and scalability.

## Langflow Desktop

Langflow Desktop is the easiest way to get started with Langflow. All dependencies are included, so you don't need to manage Python environments or install packages manually. Available for Windows and macOS.

[Download Langflow Desktop](https://www.langflow.org/desktop)

## Quickstart

### Install locally

Requires Python 3.10 to 3.13 and [uv](https://docs.astral.sh/uv/getting-started/installation/) as the recommended package manager.

#### Install

From a fresh directory, run:

```shell
uv pip install langflow -U
```

#### Run

```shell
uv run langflow run
```

Langflow starts at `http://127.0.0.1:7860`.

## Other install options

### Run from source

If you cloned this repository and want to contribute, run this command from the repository root:

```shell
make run_cli
```

For more details, see [DEVELOPMENT.md](./DEVELOPMENT.md).

### Docker

Start a Langflow container with default settings:

```shell
docker run -p 7860:7860 langflowai/langflow:latest
```

Langflow is then available at `http://localhost:7860/`.

For configuration options, deployment guides, and environment variables, see the `docs/`, `docker/`, and `deploy/` directories.

---

# Technical architecture guide

This section provides a technical overview of Langflow's architecture, repository structure, runtime model, development workflow, deployment, persistence, and scaling considerations.

## Table of contents

- [System objective](#system-objective)
- [Architectural overview](#architectural-overview)
- [Repository structure](#repository-structure)
- [Architecture by layer](#architecture-by-layer)
- [Frontend](#frontend)
- [Backend platform layer](#backend-platform-layer)
- [Runtime execution core lfx](#runtime-execution-core-lfx)
- [Distribution layer](#distribution-layer)
- [Technical architecture diagram](#technical-architecture-diagram)
- [Detailed ascii diagrams](#detailed-ascii-diagrams)
- [Package dependency relationships](#package-dependency-relationships)
- [Local startup flow](#local-startup-flow)
- [Flow creation and save lifecycle](#flow-creation-and-save-lifecycle)
- [Flow execution lifecycle](#flow-execution-lifecycle)
- [Runtime component resolution](#runtime-component-resolution)
- [Custom component loading flow](#custom-component-loading-flow)
- [Frontend backend build pipeline](#frontend-backend-build-pipeline)
- [Logical production deployment](#logical-production-deployment)
- [Persistence architecture](#persistence-architecture)
- [Persistence diagram](#persistence-diagram)
- [Scaling architecture without Celery](#scaling-architecture-without-celery)
- [Scaling architecture with Celery](#scaling-architecture-with-celery)
- [Execution model](#execution-model)
- [Component model](#component-model)
- [Catalog and lazy loading](#catalog-and-lazy-loading)
- [Persistence and compatibility](#persistence-and-compatibility)
- [Extensibility](#extensibility)
- [Local development](#local-development)
- [Build and packaging](#build-and-packaging)
- [Docker and deployment](#docker-and-deployment)
- [Scaling considerations](#scaling-considerations)
- [Testing and quality](#testing-and-quality)
- [Observability and operations](#observability-and-operations)
- [Architectural tradeoffs](#architectural-tradeoffs)
- [How to add a new component](#how-to-add-a-new-component)
- [How to debug a flow end to end](#how-to-debug-a-flow-end-to-end)
- [How Celery fits with TaskService and JobQueueService](#how-celery-fits-with-taskservice-and-jobqueueservice)
- [Conclusion](#conclusion)

---

## System objective

Langflow is an AI-first platform for:

- building visual workflows
- composing agents, models, tools, and vector stores
- testing flows in a playground
- persisting flows as reusable artifacts
- exposing flows as APIs
- exposing flows as MCP-compatible tools and servers

A central design idea in the repository is that **saved flows are persistent production artifacts**. This makes compatibility and stable serialization important across the whole system.

---

## Architectural overview

Langflow is organized as a layered system:

1. **Frontend**
   - visual editor
   - flow management
   - playground
   - interaction UX

2. **Backend platform**
   - FastAPI server
   - auth
   - persistence
   - API layer
   - services and lifecycle

3. **Runtime core**
   - graph execution
   - component model
   - built-in components
   - execution primitives

4. **Distribution**
   - integrated package that ships frontend, backend, and runtime together

The repository guidance also describes the stack this way:

- `lfx` = executor core
- `langflow-base` = platform layer
- `langflow` = integrated distribution
- `src/frontend` = UI

---

## Repository structure

High-level layout:

```text
langflow/
├── src/
│   ├── backend/
│   │   └── base/langflow/
│   ├── frontend/
│   ├── lfx/
│   └── sdk/
├── docs/
├── deploy/
├── docker/
├── docker_example/
├── scripts/
├── Makefile
├── Makefile.frontend
├── pyproject.toml
├── package.json
├── uv.lock
└── .env.example
```

Important files:

- `README.md` — public product overview
- `AGENTS.md` — repository architecture guidance
- `DEVELOPMENT.md` — local development setup
- `DESIGN.md` — design notes
- `CONTRIBUTING.md` — contributor workflow
- `RELEASE.md` — release process

---

## Architecture by layer

## Frontend

Location:
- `src/frontend/`

Technology:
- React
- TypeScript
- i18n
- npm-based build

Frontend responsibilities include:

- visual flow editing
- node configuration
- flow and folder management
- playground interaction
- browsing examples and user flows
- consuming backend APIs

Frontend entrypoint:
- `src/frontend/src/index.tsx`

The frontend is developed separately, but in the final product build it is copied into the backend package and served from there.

---

## Backend platform layer

Location:
- `src/backend/base/langflow/`

This layer contains:

- FastAPI routes
- authentication
- database models
- Alembic migrations
- platform services
- lifecycle-managed objects
- runtime integration points

Responsibilities include:

- serving APIs
- loading and saving flows
- coordinating execution requests
- serving the embedded frontend
- handling environment and startup configuration
- exposing product-level capabilities
- managing persistence services
- integrating task execution backends
- tracing and telemetry hooks

Observed startup options include:

- `host`
- `port`
- `workers`
- `worker_timeout`
- `components_path`
- `env_file`
- `log_level`

This shows the backend is designed to run as a configurable server process.

---

## Runtime execution core lfx

Location:
- `src/lfx/src/lfx/`

This is the execution engine and component framework.

It contains:

- graph execution logic
- base component classes
- built-in components
- CLI execution tooling
- abstractions for models, agents, tools, vector stores, and control flow

Responsibilities include:

- interpreting a flow graph
- instantiating components
- routing data between nodes
- invoking external providers
- returning execution results to the backend

The `lfx.components` package includes many categories of integrations, including:

- model providers
- vector stores
- flow control primitives
- search and scraping components
- tools and toolkits
- cloud and SaaS integrations

---

## Distribution layer

The `langflow` package ties everything together.

It packages:

- backend
- compiled frontend
- runtime core

This enables the whole product to be started with a unified command:

```bash
uv run langflow run
```

This gives Langflow a packaged product distribution model instead of requiring users to manually run separate services.

---

## Technical architecture diagram

```text
                                      ┌──────────────────────┐
                                      │      End Users       │
                                      │  Browser / API / MCP │
                                      └──────────┬───────────┘
                                                 │
                           ┌─────────────────────┼─────────────────────┐
                           │                     │                     │
                           ▼                     ▼                     ▼
                 ┌────────────────┐   ┌────────────────────┐  ┌───────────────────┐
                 │ React Frontend │   │ External API Users │  │   MCP Clients      │
                 │ Canvas and UX  │   │ Trigger flows      │  │ Consume tools      │
                 └───────┬────────┘   └──────────┬─────────┘  └─────────┬─────────┘
                         │                       │                      │
                         └──────────────┬────────┴──────────────┬──────┘
                                        ▼                       ▼
                           ┌────────────────────────────────────────────┐
                           │        Langflow Platform Backend           │
                           │--------------------------------------------│
                           │ FastAPI routes                             │
                           │ Auth and API keys                          │
                           │ Flow persistence                           │
                           │ Services and lifecycle                     │
                           │ Database and storage services              │
                           │ File and env handling                      │
                           │ Deployment endpoints                       │
                           └─────────────────┬──────────────────────────┘
                                             │ invokes and delegates
                                             ▼
                           ┌────────────────────────────────────────────┐
                           │              lfx Runtime Core              │
                           │--------------------------------------------│
                           │ Graph execution                            │
                           │ Component model                            │
                           │ Built-in components                        │
                           │ Agent and model adapters                   │
                           │ Tool and vector store adapters             │
                           │ Flow controls                              │
                           │ CLI execution                              │
                           └─────────────────┬──────────────────────────┘
                                             │
                   ┌─────────────────────────┼──────────────────────────────┐
                   │                         │                              │
                   ▼                         ▼                              ▼
        ┌──────────────────┐     ┌──────────────────────┐      ┌──────────────────────┐
        │ LLM Providers    │     │ Vector Databases     │      │ External Tools and   │
        │ OpenAI Anthropic │     │ Chroma Pinecone etc  │      │ APIs                 │
        └──────────────────┘     └──────────────────────┘      └──────────────────────┘
```

---

## Detailed ascii diagrams

## Package dependency relationships

```text
                          ┌───────────────────────────────┐
                          │          langflow             │
                          │   distribution and app        │
                          └──────────────┬────────────────┘
                                         │
                   ┌─────────────────────┼─────────────────────┐
                   │                     │                     │
                   ▼                     ▼                     ▼
      ┌──────────────────────┐  ┌──────────────────────┐  ┌──────────────────────┐
      │   src/frontend       │  │ langflow-base        │  │        lfx           │
      │ React and TS UI      │  │ backend platform     │  │ runtime core         │
      └──────────┬───────────┘  └──────────┬───────────┘  └──────────┬───────────┘
                 │                         │                         │
                 │ HTTP and API           imports                   exposes
                 │                         │                         │
                 ▼                         ▼                         ▼
      ┌──────────────────────┐  ┌──────────────────────┐  ┌──────────────────────┐
      │ Browser runtime      │  │ FastAPI auth DB      │  │ Components and graph │
      │ Canvas playground    │  │ Services migrations  │  │ Engine and CLI       │
      └──────────────────────┘  └──────────────────────┘  └──────────────────────┘
```

---

## Local startup flow

```text
Developer
   │
   ├── make init
   │      │
   │      ├── check tools such as uv and npm
   │      ├── install Python dependencies
   │      ├── install frontend dependencies
   │      └── validate environment
   │
   ├── uv run langflow run
   │      │
   │      ├── parse CLI args
   │      ├── load env file
   │      ├── initialize backend services
   │      ├── initialize database and storage services
   │      ├── load configured custom components path
   │      ├── initialize API and server lifecycle
   │      └── serve embedded frontend and backend APIs
   │
   └── Browser opens local Langflow instance
```

---

## Flow creation and save lifecycle

```text
┌──────────────┐
│ User in UI   │
└──────┬───────┘
       │ drag and drop nodes
       ▼
┌──────────────────────┐
│ Frontend canvas      │
│ local graph state    │
└──────┬───────────────┘
       │ edit config and connect edges
       ▼
┌──────────────────────┐
│ Frontend serializer  │
│ graph to flow JSON   │
└──────┬───────────────┘
       │ save request
       ▼
┌──────────────────────┐
│ Backend API          │
│ validate and persist │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ Database or storage  │
│ persisted flow       │
└──────────────────────┘
```

---

## Flow execution lifecycle

```text
┌──────────────┐
│ User API MCP │
└──────┬───────┘
       │ execute flow
       ▼
┌────────────────────────────┐
│ Backend route or service   │
│ resolve flow and inputs    │
└──────────┬─────────────────┘
           │
           ▼
┌────────────────────────────┐
│ Load persisted flow JSON   │
└──────────┬─────────────────┘
           │ map to runtime graph
           ▼
┌────────────────────────────┐
│ lfx graph execution engine │
└──────────┬─────────────────┘
           │
           ├── instantiate components
           ├── resolve dependencies
           ├── evaluate control flow
           ├── call models tools vector DBs
           └── collect outputs
           │
           ▼
┌────────────────────────────┐
│ Execution result           │
│ data message response      │
└──────────┬─────────────────┘
           │
           ▼
┌────────────────────────────┐
│ Backend response adapter   │
└──────────┬─────────────────┘
           │
           ▼
┌────────────────────────────┐
│ UI playground or API caller│
└────────────────────────────┘
```

---

## Runtime component resolution

```text
Execution request
      │
      ▼
Need component X
      │
      ├── Is X already known in dynamic imports
      │       │
      │       ├── Yes -> import directly
      │       └── No
      │
      ▼
Scan undiscovered component modules
      │
      ├── import module lazily
      ├── inspect module dynamic imports
      ├── register discovered components
      └── cache discovered module
      │
      ▼
Resolve concrete component class
      │
      ├── module import
      ├── alias module fallback if needed
      ├── detect missing dependency errors
      └── cache in globals
      │
      ▼
Instantiate component and execute
```

---

## Custom component loading flow

```text
Developer creates Python component
        │
        ▼
┌─────────────────────────────┐
│ Custom component source     │
│ class Component or Custom   │
└──────────┬──────────────────┘
           │
           ▼
┌─────────────────────────────┐
│ components_path             │
│ configured in CLI or env    │
└──────────┬──────────────────┘
           │
           ▼
┌─────────────────────────────┐
│ Backend custom loader       │
│ langflow.custom or lfx.custom│
└──────────┬──────────────────┘
           │ validate build register
           ▼
┌─────────────────────────────┐
│ Runtime component catalog   │
└──────────┬──────────────────┘
           │
           ▼
┌─────────────────────────────┐
│ Available in UI and runtime │
└─────────────────────────────┘
```

---

## Frontend backend build pipeline

```text
┌──────────────────────┐
│ src/frontend         │
│ React and TS source  │
└──────────┬───────────┘
           │ npm run build
           ▼
┌──────────────────────┐
│ src/frontend/build   │
│ static assets        │
└──────────┬───────────┘
           │ copy
           ▼
┌────────────────────────────────────┐
│ src/backend/base/langflow/frontend │
│ embedded UI served by backend      │
└──────────┬─────────────────────────┘
           │ included in package app
           ▼
┌──────────────────────┐
│ langflow distribution│
└──────────────────────┘
```

---

## Logical production deployment

```text
                    ┌────────────────────────────┐
                    │        End Users           │
                    │ Browser API MCP calls      │
                    └─────────────┬──────────────┘
                                  │
                                  ▼
                    ┌────────────────────────────┐
                    │ Load Balancer or Reverse   │
                    │ Proxy optional             │
                    └─────────────┬──────────────┘
                                  │
                  ┌───────────────┼────────────────┐
                  │               │                │
                  ▼               ▼                ▼
      ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
      │ Langflow node 1 │ │ Langflow node 2 │ │ Langflow node N │
      │ Backend and UI  │ │ Backend and UI  │ │ Backend and UI  │
      └────────┬────────┘ └────────┬────────┘ └────────┬────────┘
               │                   │                   │
               └────────────┬──────┴────────────┬──────┘
                            ▼                   ▼
                 ┌──────────────────┐   ┌──────────────────┐
                 │ PostgreSQL       │   │ File or blob     │
                 │ relational state │   │ storage if used  │
                 └────────┬─────────┘   └────────┬─────────┘
                          │                      │
                          └──────────┬───────────┘
                                     ▼
                     ┌────────────────────────────────┐
                     │ External AI infrastructure     │
                     │ LLM APIs vector DBs tools      │
                     └────────────────────────────────┘
```

---

## Persistence architecture

Persistence in Langflow lives primarily in the **backend platform layer**.

The platform explicitly registers and uses services such as:

- `database_service`
- `storage_service`
- `variable_service`
- `state_service`
- `session_service`
- `store_service`
- `transaction_service`

This means persistence is not treated as a single monolithic concern. Instead, the repository models different kinds of persisted state separately.

### Main persistence categories

#### Relational persistence
This is where Langflow stores structured application state such as:

- flows
- users
- sessions
- metadata
- build records
- transactional application state

PostgreSQL is explicitly supported in the repository, including:
- PostgreSQL-specific environment and runtime support
- PostgreSQL version checks
- Alembic migrations
- database service factory registration

#### File and blob persistence
The presence of a `storage_service` strongly suggests a separate layer for:
- uploaded files
- artifacts
- document storage
- binary or unstructured assets

#### Variable and state persistence
Additional services indicate the system also models:
- persisted variables
- application state
- sessions
- stores
- transaction boundaries

### PostgreSQL support

The repository shows direct evidence of PostgreSQL support:

- development Docker setup installs the `postgresql` extra
- backend startup handles unsupported PostgreSQL version errors
- the database service factory is explicitly registered
- the backend layer contains models and Alembic migrations

So the most accurate statement is:

> Langflow uses the backend platform layer for persistence, and PostgreSQL is an explicitly supported relational persistence backend.

---

## Persistence diagram

```text
React Frontend
      │
      ▼
Langflow Backend Platform
      │
      ├── database_service ─────────► PostgreSQL
      │        │
      │        ├── flows
      │        ├── users
      │        ├── sessions
      │        ├── build metadata
      │        └── transactional state
      │
      ├── storage_service ──────────► file blob object storage
      │
      ├── variable_service ─────────► persisted variables and config
      │
      ├── state_service ────────────► application or runtime state
      │
      ├── session_service ──────────► user and run session state
      │
      ├── store_service ────────────► general storage abstractions
      │
      └── transaction_service ──────► transaction coordination
```

### Persistence flow example

```text
User saves flow
    │
    ▼
Frontend serializes graph
    │
    ▼
Backend API validates flow
    │
    ▼
database_service writes structured record
    │
    ├── flow definition and metadata -> PostgreSQL
    └── associated files if any      -> storage_service
```

---

## Scaling architecture without Celery

Langflow supports a local execution model without Celery.

In this mode, the platform uses:
- in-process async execution
- local queue management
- `JobQueueService`
- `AnyIOBackend`
- direct `asyncio` orchestration for some flows and streams

```text
                    ┌────────────────────────────┐
                    │        End Users           │
                    │ Browser API MCP calls      │
                    └─────────────┬──────────────┘
                                  │
                                  ▼
                    ┌────────────────────────────┐
                    │ Langflow Web Node          │
                    │ Backend API and UI         │
                    └─────────────┬──────────────┘
                                  │
                  ┌───────────────┼───────────────────────┐
                  │               │                       │
                  ▼               ▼                       ▼
      ┌─────────────────┐ ┌────────────────────┐ ┌────────────────────┐
      │ FastAPI routes  │ │ JobQueueService    │ │ In process runtime │
      │ auth persistence│ │ asyncio queues     │ │ lfx execution      │
      └────────┬────────┘ └─────────┬──────────┘ └─────────┬──────────┘
               │                    │                      │
               └────────────────────┴──────────────┬───────┘
                                                   ▼
                                   ┌──────────────────────────┐
                                   │ Models tools vector DBs  │
                                   │ external APIs            │
                                   └──────────────────────────┘
```

This mode is especially useful for:
- local development
- simple self-hosted installations
- lower concurrency environments

---

## Scaling architecture with Celery

Langflow also supports Celery as a distributed task backend.

Evidence in the repository includes:
- a `CeleryBackend`
- a Celery app definition
- task routing to `langflow.worker.tasks.*`
- result lookup and revocation via Celery

This means Langflow can scale some background and asynchronous work by decoupling task execution from the web API layer.

```text
                    ┌────────────────────────────┐
                    │        End Users           │
                    │ Browser API MCP calls      │
                    └─────────────┬──────────────┘
                                  │
                                  ▼
                    ┌────────────────────────────┐
                    │ Load Balancer optional     │
                    └─────────────┬──────────────┘
                                  │
                  ┌───────────────┼────────────────────────────┐
                  │               │                            │
                  ▼               ▼                            ▼
      ┌─────────────────┐ ┌─────────────────┐      ┌─────────────────┐
      │ Langflow Web 1  │ │ Langflow Web 2  │  ... │ Langflow Web N  │
      │ API UI auth     │ │ API UI auth     │      │ API UI auth     │
      └────────┬────────┘ └────────┬────────┘      └────────┬────────┘
               │                   │                        │
               └───────────────┬───┴───────────────┬────────┘
                               ▼                   ▼
                      ┌────────────────────────────────────┐
                      │ Celery broker and queue layer      │
                      │ Redis RabbitMQ or configured broker│
                      └────────────────┬───────────────────┘
                                       │
                    ┌──────────────────┼──────────────────┐
                    │                  │                  │
                    ▼                  ▼                  ▼
         ┌──────────────────┐ ┌──────────────────┐ ┌──────────────────┐
         │ Celery Worker 1  │ │ Celery Worker 2  │ │ Celery Worker N  │
         │ langflow tasks   │ │ langflow tasks   │ │ langflow tasks   │
         └────────┬─────────┘ └────────┬─────────┘ └────────┬─────────┘
                  │                    │                    │
                  └────────────────────┼────────────────────┘
                                       ▼
                       ┌────────────────────────────────┐
                       │ lfx execution and integrations │
                       │ models vector DBs tools APIs   │
                       └────────────────────────────────┘
```

This mode is better suited for:
- multiple concurrent background jobs
- heavier asynchronous processing
- isolating API responsiveness from worker load
- scaling workers independently from web nodes

---

## Execution model

Langflow centers execution around **flows as persisted graphs**.

A typical execution path is:

1. load a persisted flow definition
2. map it to runtime graph structures
3. resolve components
4. evaluate graph edges and dependencies
5. execute control flow and provider calls
6. collect outputs
7. surface the result to UI API or MCP clients

This allows the same flow artifact to be reused in multiple execution contexts.

---

## Component model

Components are the central abstraction in Langflow.

Observed traits include:

- display metadata
- typed inputs
- typed outputs
- execution methods
- UI configuration support

This means a component is simultaneously:

- a runtime node
- an editor building block
- a serializable artifact
- a configurable object
- an integration wrapper

Examples in the repository include:
- model components
- vector store components
- flow control components
- tools
- extractors and search components

---

## Catalog and lazy loading

Langflow manages a broad component catalog through a dynamic loading strategy.

Main ideas:

1. keep components grouped by category
2. use dynamic import mappings
3. discover component classes on demand
4. cache discovered modules
5. optionally rely on a generated component index for faster startup

Benefits:

- smaller startup cost
- fewer hard dependency failures on boot
- modular integration growth
- better operational flexibility

Costs:

- more import complexity
- trickier debugging
- extra compatibility burden

---

## Persistence and compatibility

A flow is not treated as temporary UI state. It is treated as a persistent artifact.

That implies:

- serialization stability matters
- deserialization must remain robust
- component changes must be backward compatible
- schema evolution must be conservative

This is one of the most important architectural constraints in the repository.

Persistence strengthens this requirement further, because:
- flows are stored in a real backend persistence layer
- sessions and variables may survive process restarts
- migrations and schema evolution directly affect user artifacts

---

## Extensibility

Langflow is designed to be extended through:

- custom components
- provider integrations
- subflows and reusable flows
- tool and agent composition

### Custom components
The backend and runtime expose utilities and abstractions for creating custom components. The configurable `components_path` makes external component loading a first-class mechanism.

### External integrations
The runtime ships adapters for:
- model providers
- vector stores
- search
- scraping
- tools
- cloud and SaaS services

### Reusable flows
The presence of subflow and flow tool style components indicates flows can be composed into higher-order workflows.

---

## Local development

Requirements from the repository docs include:

- `git`
- `make`
- `uv`
- Node.js `v22.12`
- npm `v10.9`

Recommended platforms:
- macOS
- Linux
- Windows via WSL or Dev Container

### Setup

```bash
make init
```

### Run Langflow

```bash
uv run langflow run
```

### Run frontend in development

```bash
make frontend
```

### Build frontend

```bash
make build_frontend
```

---

## Build and packaging

The repository uses both Python and frontend packaging workflows.

### Python side
- `pyproject.toml`
- `uv.lock`

### Frontend side
- `package.json`
- `package-lock.json`

### Coordination
- `Makefile`
- `Makefile.frontend`

The frontend build artifacts are copied into the backend package, so the final app is shipped as a unified distribution.

---

## Docker and deployment

Relevant deployment-related paths include:

- `docker/`
- `docker_example/`
- `deploy/`
- `render.yaml`

The development Dockerfile installs:

- Python via `uv`
- npm
- git
- build toolchain packages

The development setup also installs the `postgresql` extra, which is a strong signal that PostgreSQL is a first-class persistence backend in supported environments.

This supports reproducible local and containerized development.

---

## Scaling considerations

Langflow supports more than one execution mode for asynchronous and background work.

At the task execution layer, the repository shows a **hybrid model**:

- **Local mode** uses in-process task execution and queue management
- **Distributed mode** uses **Celery** as a task backend

This means Langflow can run in:

1. **Single-node mode**
   - web server
   - in-process async jobs
   - local queue management

2. **Distributed mode**
   - web or API nodes
   - broker-backed task dispatch
   - one or more Celery workers

### Task backend selection

The task service selects its backend from configuration.

- If Celery is enabled, Langflow uses `CeleryBackend`
- Otherwise it falls back to `AnyIOBackend`

### Important nuance

Celery is **not the only execution path** in Langflow.

The repository also contains:

- local `JobQueueService`
- `asyncio.Queue` based execution and event handling
- direct async streaming paths
- in-process task orchestration

So the most accurate statement is:

> Langflow supports Celery for distributed task execution and scaling, but the platform also supports local non-Celery execution paths.

### Practical scaling layers

#### Web and API scaling
Scale the FastAPI application horizontally behind a reverse proxy or load balancer.

#### Task execution scaling
Use Celery workers when background work needs to be distributed or isolated from web nodes.

#### Persistence scaling
Persistence is also part of scaling. In practical deployments, that means:
- using PostgreSQL as the relational backend
- sizing the database according to flows, sessions, and metadata load
- separating file or blob storage from relational storage where appropriate

#### Dependency scaling
External systems usually become the dominant scaling factor:

- LLM API throughput and rate limits
- vector database performance
- storage performance
- external tool latency

---

## Testing and quality

Repository signals include:

- frontend unit tests
- Playwright tests
- linting and formatting
- pre-commit hooks
- coverage configuration
- scripts for import and dependency health

This suggests the project is maintained as a contributor-friendly product codebase rather than a minimal prototype.

---

## Observability and operations

The repository highlights integrations such as:

- LangSmith
- LangFuse
- LangWatch
- Arize Phoenix
- Opik
- Traceloop
- OpenLayer

Operationally, the stack also exposes:

- logging configuration
- env file loading
- configurable startup parameters
- telemetry service
- tracing service

For AI workflows, observability is especially valuable for:

- execution tracing
- model and tool debugging
- output comparison
- agent behavior inspection

---

## Architectural tradeoffs

### Strengths
- clear separation between runtime and platform
- AI-first design
- extensible component system
- unified UI API and MCP story
- compatibility-aware persisted flow model
- explicit persistence architecture with database and storage layers
- optional Celery-based distributed task execution

### Costs
- monorepo complexity
- very large integration surface
- careful schema evolution required
- dynamic import complexity
- backward compatibility limits aggressive internal refactors
- Celery scaling introduces broker and worker operational complexity
- persistence architecture adds migration and operational responsibilities

---

## How to add a new component

The repository guidance says to place new built-in components in the `lfx` layer, under the appropriate category in:

- `src/lfx/src/lfx/components/<category>/`

### Recommended workflow

1. **Choose the correct component category**
   - models
   - vector stores
   - tools
   - flow controls
   - data processing
   - input output
   - search
   - files and knowledge
   - or another existing category

2. **Create the component class**
   Implement a new Python class that follows the repository's component model:
   - display metadata
   - typed inputs
   - typed outputs
   - execution methods

3. **Update the category package init**
   Add the component to the category `__init__.py`, preserving the module's dynamic import conventions.

4. **Do not break compatibility**
   Saved flows are long-lived artifacts. If your component is intended to be used in production flows:
   - avoid renaming the class casually
   - avoid changing output contracts recklessly
   - avoid removing fields used in existing flows

5. **Make UI metadata complete**
   Components are not runtime-only objects. They are also consumed by the visual editor, so ensure:
   - display name
   - description
   - icon
   - field order
   - input metadata
   are coherent.

6. **Rebuild the component index if needed**
   The repository includes:
   - `scripts/build_component_index.py`

   This index supports faster startup and deterministic component metadata packaging.

### Component addition diagram

```text
Decide component category
        │
        ▼
Create new component file in lfx components category
        │
        ▼
Add class metadata inputs outputs methods
        │
        ▼
Add to category dynamic imports
        │
        ▼
Validate runtime import and UI discovery
        │
        ▼
Run local app and test in canvas and playground
        │
        ▼
Rebuild component index if required
```

### Practical advice
- Put framework-agnostic execution logic in `lfx`
- Avoid pushing core runtime logic into the backend layer
- If the component wraps a third-party provider, keep the integration self-contained

---

## How to debug a flow end to end

A practical debugging path in Langflow usually crosses all major layers:

1. frontend flow authoring
2. backend API request
3. runtime graph execution
4. provider or tool integrations
5. response rendering or streaming

### Debugging workflow

#### Step 1: Validate the flow visually
Use the UI to confirm:
- the right nodes are connected
- inputs are configured correctly
- output node types make sense

#### Step 2: Confirm persistence
Because flows are persisted artifacts, make sure the flow you are executing is actually the saved version you expect.

#### Step 3: Run via playground
The playground is often the shortest loop to see:
- execution logs
- output shape
- component-level behavior

#### Step 4: Inspect backend logs
The backend contains:
- request handling
- lifecycle services
- queue and task coordination
- tracing hooks
- persistence services

So if the issue is not visible in the UI, check backend logs next.

#### Step 5: Trace runtime component loading
If the error is import related or provider related:
- verify the component resolves from `lfx.components`
- verify optional dependencies are installed
- inspect dynamic import behavior

#### Step 6: Check provider dependencies
Many components wrap external systems:
- OpenAI
- Anthropic
- vector stores
- scraping tools
- doc processing libraries

A flow failure can be caused by:
- missing package
- invalid credentials
- external API failure
- timeout
- incompatible library version

#### Step 7: Check task mode
If Celery is enabled, the failure may occur in:
- task dispatch
- broker connectivity
- Celery worker execution

If Celery is disabled, the same issue may instead occur in:
- local queue handling
- in-process async execution

#### Step 8: Check persistence and migrations
If the issue is about loading, saving, sessions, or startup:
- inspect database service configuration
- inspect migrations
- verify PostgreSQL compatibility and connectivity
- inspect storage service behavior for file-backed assets

### End to end debugging diagram

```text
UI flow issue reported
        │
        ▼
Check node graph and saved flow state
        │
        ▼
Run in playground
        │
        ├── Works -> issue may be API or deployment specific
        └── Fails
               │
               ▼
Inspect backend logs and request path
               │
               ▼
Inspect runtime component resolution
               │
               ├── import or dependency failure
               ├── invalid provider credentials
               ├── execution logic failure
               ├── queue or task failure
               ├── persistence or migration issue
               └── external system timeout
               │
               ▼
Use tracing telemetry and database inspection for deeper analysis
```

### Good places to inspect
- `src/backend/base/langflow/main.py`
- `src/backend/base/langflow/api/`
- `src/backend/base/langflow/services/`
- `src/backend/base/langflow/services/database/`
- `src/backend/base/langflow/services/storage/`
- `src/lfx/src/lfx/components/`
- `src/lfx/src/lfx/cli/serve_app.py`
- tracing service and telemetry service

---

## How Celery fits with TaskService and JobQueueService

Langflow uses a layered execution model for background tasks.

### Core pieces

#### TaskService
`TaskService` is the abstraction layer that decides how tasks are launched.

It selects between:
- `CeleryBackend`
- `AnyIOBackend`

based on runtime settings.

#### JobQueueService
`JobQueueService` manages local in-process queues and event managers for jobs.

This is particularly relevant when Celery is **not** enabled.

#### CeleryBackend
`CeleryBackend` wraps:
- task submission
- task result lookup
- task revocation

through Celery primitives like:
- `.delay()`
- `AsyncResult`

### Relationship between them

```text
Task requested
    │
    ▼
TaskService
    │
    ├── celery_enabled = true
    │        │
    │        ▼
    │   CeleryBackend
    │        │
    │        ├── send task to broker
    │        ├── worker executes task
    │        └── result tracked by Celery
    │
    └── celery_enabled = false
             │
             ▼
         AnyIOBackend plus JobQueueService
             │
             ├── create local queue
             ├── start asyncio task
             ├── stream or collect events
             └── manage local lifecycle
```

### Why both exist

This dual design gives Langflow flexibility:

- **local simplicity** when distributed workers are not needed
- **distributed scaling** when background work should be offloaded

### Practical interpretation

- `TaskService` is the policy and dispatch layer
- `JobQueueService` is the local queue execution and tracking layer
- `CeleryBackend` is the distributed task execution layer

### Celery integration diagram

```text
Client request
    │
    ▼
Backend route or service
    │
    ▼
TaskService
    │
    ├── Local mode
    │      │
    │      ▼
    │   JobQueueService
    │      │
    │      ▼
    │   asyncio task execution in process
    │
    └── Celery mode
           │
           ▼
        CeleryBackend
           │
           ▼
        Broker queue
           │
           ▼
        Celery worker
           │
           ▼
        Task result and status
```

### Persistence interaction

Celery-based execution does not replace persistence. It complements it.

Typical relationship:

```text
Web/API layer
    │
    ├── reads and writes application state -> PostgreSQL
    ├── reads and writes files            -> storage service
    └── dispatches background work        -> Celery when enabled
```

So:
- PostgreSQL stores structured state
- storage service stores file-like assets
- Celery handles distributed asynchronous work

### Operational implications

#### Local mode advantages
- easier development
- fewer moving parts
- no broker needed

#### Celery mode advantages
- worker pool scaling
- background isolation
- better concurrency handling for heavy jobs

#### Celery mode costs
- broker infrastructure
- worker fleet management
- queue visibility and operations overhead

---

## Conclusion

Langflow is structured around a clear principle:

> a visual flow should be designable, executable, deployable, and reusable without leaving the same component model

Its architecture is built on four core pillars:

- React frontend for authoring
- FastAPI backend for platform concerns
- `lfx` runtime for graph execution
- integrated distribution for shipping the complete product

It also supports:
- explicit persistence services
- PostgreSQL as a supported relational backend
- separate storage abstractions
- local in-process execution for simple and development scenarios
- Celery-backed distributed task execution for more scalable background processing

In practice, Langflow is not just a visual AI editor. It is a **composable execution platform for AI workflows, agents, tools, persistence-backed flow artifacts, and deployable runtime integrations**.

---

## Contributing

We welcome contributions from developers of all levels. If you'd like to contribute, please check our [contributing guidelines](./CONTRIBUTING.md) and help make Langflow more accessible.

## Security

For security information, see our [Security Policy](./SECURITY.md).

## Deployment

Langflow is open source and can be deployed to major cloud providers. For deployment guidance, see the documentation under `docs/` and `deploy/`.

## References used for this architectural section

- `AGENTS.md`
- `docs/agents/ARCHITECTURE.md`
- `DEVELOPMENT.md`
- `CONTRIBUTING.md`
- `Makefile`
- `Makefile.frontend`
- `src/frontend/src/index.tsx`
- `src/backend/base/langflow/__main__.py`
- `src/backend/base/langflow/main.py`
- `src/backend/base/langflow/core/celery_app.py`
- `src/backend/base/langflow/api/build.py`
- `src/backend/base/langflow/services/utils.py`
- `src/backend/base/langflow/services/task/service.py`
- `src/backend/base/langflow/services/task/backends/celery.py`
- `src/backend/base/langflow/services/job_queue/service.py`
- `src/backend/base/langflow/services/tracing/service.py`
- `src/backend/base/langflow/custom/__init__.py`
- `src/lfx/src/lfx/components/__init__.py`
- `src/lfx/src/lfx/cli/run.py`
- `src/lfx/src/lfx/cli/serve_app.py`
- `src/lfx/src/lfx/services/schema.py`
- `src/lfx/PLUGGABLE_SERVICES.md`
- `scripts/build_component_index.py`
- `docker/dev.Dockerfile`