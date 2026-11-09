<p align="center">
  <img src="https://sofuu.xyz/docs/sofuu-logo.png" width="118" alt="Sofuu Logo">
</p>

# Sofuu (素風)

> **A general-purpose runtime for AI — built to run anywhere from servers to smart devices.**

A sovereign, ultra-compact systems engine combining in-process/plugin local LLM inference, autonomous agent loops, encrypted cognitive vector memory (CMA v2 / QTSQ), native MCP, and physical robotics/drone control in a single **$\le 10\text{ MiB}$ standalone native binary**.

Zero background daemons. Zero Python environments. Zero external vector databases.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-0.3.0--beta.2-orange.svg)](https://github.com/sofuu-runtime/sofuu/releases)
[![Binary Size](https://img.shields.io/badge/binary-%E2%89%A4%205.5%20MB-emerald.svg)](https://sofuu.xyz)
[![Cold Start](https://img.shields.io/badge/cold%20start-22.5%20ms-blue.svg)](BENCHMARKS.md)

---

### Quick Install

```bash
# One-line install (Linux & macOS)
curl -fsSL https://sofuu.xyz/install | sh

# Or run via npm
npx sofuu
```

---

### Highlights

- **Single $\le 10\text{ MiB}$ Native Binary**: Shipped as an ultra-compact executable with a 22.5 ms median cold start (4.85 ms on Raspberry Pi 5) and ~12.4 MB idle RSS.
- **Two-Tier Language Substrate**: High-level AI cognition and orchestration in TypeScript/JavaScript (QuickJS + libuv) paired with **Kaze (風)** — a deterministic, fuel-metered domain DSL for physical devices and robotics.
- **Cognitive Vector Memory (CMA v2)**: On-device encrypted (`.qtsq`, AES-256-GCM) associative memory with HNSW graph indexing, BM25 rare-token re-ranking, and offline 768-dim 0-byte embeddings.
- **Dual-Track Local Inference**: Built-in multi-format engine (GGUF, SafeTensors, PyTorch, NumPy) plus turnkey production acceleration via `sofuu plugin add llamacpp`.
- **Autonomous Agents & Prompt Sovereignty**: Multi-step reasoning loops with budget controls, crash-resilient WAL, and 100% developer prompt sovereignty.
- **Robotics, Drones & MAVLink v2**: Zero-dependency MAVLink streaming codec, 1 Hz dead-man switch, Linux GPIO pulse timers, and an R7 deterministic safety veto gate.
- **Native MCP Client & Server**: Direct Model Context Protocol over stdio and Streamable HTTP.
- **Standalone Agent Compiler**: `sofuu compile app.ts -o agent` packages TypeScript code and vector memory into a single signed binary.
- **Embeddable C ABI (`libsofuu`)**: Zero-JIT architecture providing native Swift (iOS/macOS) and Kotlin (Android) integration.

---

### 10-Second Quick Start

```bash
# 1. Immediate terminal assistant with persistent memory
sofuu chat

# 2. Run a TypeScript script natively (zero build step)
sofuu run agent.ts

# 3. Add production-grade local inference acceleration
sofuu plugin add llamacpp
```

```ts
// agent.ts — native AI in TypeScript
import { ai, memory, agent } from "sofuu";

const brain = memory.open("./brain.qtsq", 768);
brain.remember(ai.embedLocal("runtime config"), "Sofuu executes AI natively with zero daemons.");

const [match] = brain.recall(ai.embedLocal("daemons"), 1);
console.log("Recalled from vector brain:", match.text);
```

---

### Architecture

- **Engine Core:** Safe Rust (`crates/sofuu-core`) with isolated C FFI bridges (`crates/sofuu-ffi`).
- **JavaScript Engine:** Embedded QuickJS (ES2023, JIT-free) + libuv async event loop.
- **Physical VM:** Clean-room 4-byte bytecode VM for the Kaze scripting language (`crates/sofuu-core/src/sfs/`).
- **SIMD & Metal:** Hand-tuned ARM NEON, AVX2, and Apple Metal Performance Shaders.
- **Security:** Deterministic R7 firewall covering tools, filesystem jail, network allowlist, secrets masking, and hardware actuation vetoes.

---

### License

- Core Runtime: [MIT License](LICENSE)
- QTSQ Vector Memory Engine: [Apache-2.0 License](LICENSES/QTSQ-FORMAT.txt)
- Built in public by **Haruhito**.
