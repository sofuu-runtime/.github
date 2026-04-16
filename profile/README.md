<div align="center">
  <img src="https://raw.githubusercontent.com/sofuu-runtime/sofuu/main/sofuu-landing/public/favicon.ico" width="100" alt="Sofuu Logo">
  <h1>Sofuu (素風)</h1>
  <p><b>A completely reimagined, ultra-lightweight JavaScript runtime built in C.</b></p>
  <p>Designed from day one for local AI development, edge IoT, and raw performance.</p>

  <a href="https://sofuu.xyz">Website</a> •
  <a href="https://sofuu.xyz/docs">Documentation</a> •
  <a href="https://github.com/sofuu-runtime">GitHub</a>
</div>

***

### ⚡ Why Sofuu?

Modern JavaScript runtimes have grown massive. We built Sofuu natively in C to strip away the bulk, achieving a ~1.1MB binary size and ~3ms startup times. 

It drops the legacy browser APIs and massive package ecosystems you don't need, and directly integrates the tools you *actually* want today:

*   **🧠 Automatic AI Streaming:** Native integrations with local/cloud LLMs without `npm install openai`.
*   **🔌 Built-in MCP:** Model Context Protocol Server & Client running directly over stdio at the C level.
*   **🧮 Hardware SIMD Math:** Connected JavaScript directly to your CPU's vector registers (NEON/AVX2) for instant embedding searches and cosine similarity.
*   **🌐 Zero-Dependency Web Server:** An asynchronous HTTP multiplexer directly over raw OS sockets.

### 📦 Quick Start

Install the runtime globally on macOS or Linux (x86_64 / arm64):

```bash
curl -fsSL https://sofuu.xyz/install | sh
