## Overview

Sofuu is an early-stage, bootstrapped, open-core project founded and built by **Priyanshu Boruah**, who publishes and develops the project under the public identity **Haruhito**.

Sofuu is an ultra-lightweight, AI-native **JavaScript/TypeScript runtime** designed to make building and running AI applications simpler, faster, and more self-contained. Instead of requiring developers to assemble a runtime, AI SDKs, agent frameworks, MCP tooling, vector utilities, memory systems, and an HTTP server from many separate packages, Sofuu brings these capabilities together inside a single native runtime.

The goal is to make an AI backend feel closer to using one runtime than maintaining a large collection of dependencies and services.

## What Sofuu Provides

Sofuu runs JavaScript and TypeScript and provides AI capabilities directly through its runtime.

The current runtime includes:

- LLM streaming
- LLM completion APIs
- AI agents and tool loops
- MCP client and server support
- Vector mathematics
- Embeddings
- Persistent local memory
- Encrypted local storage
- HTTP server capabilities
- JavaScript/TypeScript scripting
- Interactive AI agent CLI
- Native embedding support
- Cross-platform releases
- Developer tooling for running, evaluating, and bundling scripts

The main idea is that these capabilities should work together through one consistent runtime and API rather than requiring a separate framework for every part of an AI application.

## Runtime Architecture

Sofuu is built around **QuickJS and libuv with a Rust shell**.

QuickJS provides the JavaScript execution environment, while libuv provides the underlying event-loop and asynchronous I/O infrastructure. The native layer connects the JavaScript runtime to Sofuu's AI, networking, storage, vector, and system capabilities.

The runtime is designed around:

- Small binaries
- Fast startup
- Low runtime overhead
- Local-first execution
- Native system integration
- Cross-platform portability
- AI capabilities as runtime primitives rather than external packages

The current public website targets a binary of approximately **3 MB** and reports approximately **3 ms startup time** on laptop, server, and edge hardware.

## AI-Native Runtime

AI functionality is a first-class part of Sofuu rather than an external framework layered on top of a conventional JavaScript runtime.

The runtime exposes APIs such as:

```ts
sofuu.ai.stream(prompt, config)
sofuu.ai.complete(prompt, config)
sofuu.ai.embed(text)
sofuu.agent.run(task, options)
```

This allows applications to stream model output, run agentic tool loops, generate embeddings, and build AI workflows directly from JavaScript or TypeScript.

Sofuu also provides an interactive agent through:

```bash
sofuu chat
```

and applications can be executed directly with:

```bash
sofuu run app.ts
```

## Built-In Agent Capabilities

Sofuu includes an agent tool belt that can be used from the interactive agent and from scripts.

The current tool set includes capabilities such as:

- `read`
- `write`
- `edit`
- `grep`
- `glob`
- `list_dir`
- `bash`
- web search
- persistent memory

The goal is to make common agent workflows available through the runtime itself rather than requiring developers to construct a separate agent stack.

## MCP Support

Sofuu includes built-in **Model Context Protocol (MCP)** client and server capabilities.

MCP is treated as a native runtime capability so that applications and agents can communicate with external tools and services without requiring developers to install and maintain a separate MCP framework.

This makes Sofuu suitable for building AI applications where model reasoning, tool use, local resources, and external services need to work together.

## Local-First Architecture

Sofuu is designed with a local-first approach.

Sessions, vector memory, and key-value data can be stored in encrypted files on the user's machine. Local operations do not require network access, while remote model calls only use the network when a configured remote provider is selected.

This architecture is intended to give developers more control over:

- Local data
- AI sessions
- Persistent memory
- Network access
- Deployment environments
- Edge and offline-capable workflows

## Vector Mathematics and Embeddings

Sofuu includes native vector operations using CPU SIMD capabilities.

The runtime supports operations such as:

- Cosine similarity
- Dot products
- L2 distance

These operations can use **NEON** and **AVX2** vector units where supported.

Sofuu also provides offline 768-dimensional hash embeddings by default. This allows basic vector operations without requiring a model file or network connection.

## HTTP Server

Sofuu includes an HTTP server directly in the runtime.

This means an AI application can stream model output over HTTP without requiring a separate web server or additional runtime dependency.

For example, an application can use the AI streaming API and expose the generated output through an HTTP endpoint directly from the same Sofuu process.

Sofuu also handles streaming work such that slow model responses do not block the JavaScript server loop.

## Cross-Platform Deployment

Sofuu is intended to run consistently across:

- macOS
- Linux
- Windows

The public installer detects the platform, verifies the SHA-256 checksum, and adds `sofuu` to the user's PATH.

The project also exposes native integration paths for application ecosystems including Swift and Kotlin.

The objective is to make the same runtime and application model usable across laptops, servers, edge hardware, and applications that embed Sofuu.

## Developer Experience

Sofuu is designed around a minimal installation and execution model.

A developer can install Sofuu with:

```bash
curl -fsSL https://sofuu.xyz/install | sh
```

and then run:

```bash
sofuu chat
```

or:

```bash
sofuu run app.ts
```

Sofuu also provides commands for inline evaluation and bundling.

The runtime is intended to eliminate unnecessary setup and reduce the amount of infrastructure a developer needs before they can start building an AI backend.

## Open-Core Model

Sofuu follows an **open-core** model.

The core Sofuu runtime is open source and released under the MIT license. The runtime, core developer experience, and fundamental capabilities are developed publicly.

The open-source core is intended to remain useful on its own rather than acting as a restricted demonstration of a proprietary product.

The commercial layer can instead be built around the core through future services such as:

- Hosted Sofuu infrastructure
- Managed AI runtimes
- Cloud deployments
- Enterprise features
- Managed agents and MCP infrastructure
- Enterprise authentication and administration
- Observability and operational tooling
- Premium support
- Other hosted or managed services

This keeps the runtime open while allowing future commercial products and services to grow around it.

## Development Status

Sofuu is currently an **early-stage, bootstrapped project in active development**.

The runtime, documentation, source code, and development work are being developed publicly through the Sofuu GitHub organization.

The project is intentionally being built in public so developers can inspect the implementation, experiment with the runtime, provide feedback, and contribute as the project evolves.

## Project Identity

Sofuu is publicly developed by **Haruhito**, the public identity used by founder **Priyanshu Boruah**.

The relationship between the public identity and legal/real identity is intentionally documented so that the project, its founder, website, and source repository can be independently verified.

The project website is:

**https://sofuu.xyz**

The source code and organization are hosted under:

**https://github.com/sofuu-runtime**

## Short GitHub Organization Description

> Sofuu is an early-stage, bootstrapped, open-core AI-native JavaScript/TypeScript runtime built by Haruhito (Priyanshu Boruah), bringing AI streaming, agents, MCP, vector operations, encrypted memory, and HTTP capabilities into a lightweight native runtime.

## Recommended GitHub Organization README

```md
# Sofuu (素風)

Sofuu is an early-stage, bootstrapped, open-core **AI-native JavaScript/TypeScript runtime** built by **Haruhito (Priyanshu Boruah)**.

It is designed to make building and running AI applications simpler and more self-contained by bringing AI streaming, agents, MCP, vector operations, encrypted local memory, HTTP serving, and developer tooling directly into one lightweight runtime.

## What Sofuu Includes

- LLM streaming and completion
- AI agents and tool loops
- MCP client and server
- SIMD-accelerated vector math
- Offline embeddings
- Encrypted local memory and storage
- Built-in HTTP server
- JavaScript and TypeScript execution
- Interactive AI agent CLI
- Native embedding support
- Cross-platform builds for macOS, Linux, and Windows

## Runtime

Sofuu uses QuickJS with libuv and a Rust shell.

The runtime is designed for fast startup, small binaries, local-first execution, and deployment across laptops, servers, and edge hardware.

Current public targets are approximately:

- ~3 MB binary
- ~3 ms startup

## Quick Start

```bash
curl -fsSL https://sofuu.xyz/install | sh

sofuu chat
sofuu run app.ts
```

## Open Core

Sofuu is open-core.

The core runtime is MIT-licensed and developed publicly. Future hosted, managed, cloud, and enterprise services can form the commercial layer around the open-source runtime without restricting the fundamental open-source runtime itself.

## Links

- Website: https://sofuu.xyz
- Source: https://github.com/sofuu-runtime/sofuu

Sofuu is actively developed in public.
```

## Important Consistency Note

The GitHub organization README should be updated to match the current project architecture.

The current GitHub organization page contains older wording describing Sofuu as being **built in C** with a **~1.1 MB binary**, while the current Sofuu website and main repository describe the current runtime as **QuickJS + libuv with a Rust shell** and approximately **3 MB**.

Those statements should not remain inconsistent.

The recommended current wording is:

> **Sofuu is an ultra-lightweight, open-core AI-native JavaScript/TypeScript runtime built around QuickJS, libuv, and a Rust native shell.**

The GitHub organization README should also avoid claiming only macOS/Linux support if the current release and website support macOS, Linux, and Windows.

## Project Positioning

The clearest way to describe Sofuu is:

> **Sofuu is a lightweight JavaScript/TypeScript runtime where AI capabilities are built into the runtime itself.**

Rather than being another AI SDK, agent framework, or hosted AI platform, Sofuu aims to provide the underlying runtime layer for AI applications.

The long-term vision is to make it possible to build an AI backend with a single lightweight runtime instead of combining a conventional JavaScript runtime with many independent AI packages, agent frameworks, MCP libraries, vector databases, memory systems, and web-server dependencies.

---

**Sofuu core is MIT open source.**

**Built by Haruhito (Priyanshu Boruah).**
