# Nick Altstein

**AI Infrastructure, Agent Security & Quantitative Systems Engineer — New York, NY**

[![Live Sandbox](https://img.shields.io/badge/LIVE_SANDBOX-AuditGPT_Blast--Radius_Simulator-38BDF8?style=flat-square)](https://sandbox.auditgpt.ai)
[![PropStein Terminal](https://img.shields.io/badge/PRODUCTION-propstein.com-10B981?style=flat-square)](https://propstein.com)
[![GitHub](https://img.shields.io/badge/GitHub-NickAltstein-0B0D11?style=flat-square&logo=github)](https://github.com/NickAltstein)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Nick_Altstein-222733?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/nickaltstein/)
[![Email](https://img.shields.io/badge/Email-nickaltstein%40gmail.com-222733?style=flat-square)](mailto:nickaltstein@gmail.com)

I design and ship **deterministic execution boundaries, cryptographic verification primitives, and high-throughput quantitative pipelines** for autonomous AI systems. 

Rather than relying on probabilistic LLM "judge" guardrails that add 500ms+ of latency and fail under indirect prompt injection, my infrastructure enforces **fail-closed AST/JSON-RPC policy gates**, **RFC-8785 canonical state hashing**, **Ed25519 execution receipts**, and **SQLite time-travel trace replay**.

---

## ⚡ Interactive Proof: Agent Blast-Radius Simulator (`sandbox.auditgpt.ai`)

* **[Launch Interactive Blast-Radius Simulator → sandbox.auditgpt.ai](https://sandbox.auditgpt.ai)** — Test the client-side deterministic agent firewall directly in your browser with zero setup, zero token cost, and sub-2ms WebCrypto verification.
  * **[Deep-Link Exploit #1: Halted Production `DROP TABLE` Mutation](https://sandbox.auditgpt.ai/?scenario=prod-drop-table&step=1)** — Inspect a live intercepted MCP `postgres.execute_sql` frame blocked fail-closed with a 90/100 blast-radius score.
  * **[Deep-Link Exploit #2: 1-Byte Ledger Tamper Detection](https://sandbox.auditgpt.ai/?scenario=poisoned-pr&step=2&tamper=1)** — Watch how mutating a single byte in the historical tool trace invalidates the Ed25519 receipt and SHA-256 Merkle root.
* **Powered by [Receiptd](https://github.com/NickAltstein/receiptd)** — Open-source runtime authorization & cryptographic evidence layer. Sub-2ms fail-closed `PreToolUse` hooks, Ed25519 execution receipts, and offline hash-chain verification for Claude Code & MCP agents.
* **Trace Replay & Observability via [INFINI](https://github.com/NickAltstein/infini)** — SQLite + FTS5 deterministic agent trace runtime, portable `Loopfile` specification, denial-of-wallet circuit breakers, and CI regression gating (`infini-guard`).
* **Platform Defense**: [auditgpt.ai](https://auditgpt.ai) — Adversarial pre-merge stress testing & ASTI v1.1 CI/CD gate.

---

## Systems Architecture Matrix

| System / Repository | Primary Engineering Domain | Core Primitives & Verification Guarantees | Stack & Runtime | Status / Live Artifact |
| :--- | :--- | :--- | :--- | :--- |
| **[Receiptd](https://github.com/NickAltstein/receiptd)** | Zero-Trust Agent Authorization & Evidence Layer | MCP interception, Policy-as-Code AST gates, Ed25519 execution receipts, binary SHA-256 Merkle audit trees | Python 3.12, TypeScript, WebCrypto, RFC-8785 JCS | [Repo](https://github.com/NickAltstein/receiptd) · [Live Sandbox](https://sandbox.auditgpt.ai) |
| **[INFINI](https://github.com/NickAltstein/infini)** | Deterministic Agent Trace & Replay Engine | Portable `Loopfile` spec, SQLite + FTS5 state persistence, cross-runtime trace diffing, denial-of-wallet circuit breakers | Python, SQLite (FTS5), Next.js Observatory UI, MCP | [Repo](https://github.com/NickAltstein/infini) · `infini-guard` CI (1.85ms overhead) |
| **[birkin-sandbox](https://github.com/NickAltstein/birkin-sandbox)** | Interactive WebCrypto Blast-Radius Simulator | Client-side deterministic firewall simulator & time-travel debugger powered by WebCrypto Ed25519 & RFC-8785 | Next.js App Router, TypeScript, Tailwind, Playwright | [Repo](https://github.com/NickAltstein/birkin-sandbox) · [sandbox.auditgpt.ai](https://sandbox.auditgpt.ai) |

---

## Also Built — Quantitative Market Infrastructure

### [`PropStein`](https://propstein.com) — Quantitative Pricing & Cryptographic CLV Engine
* **Architecture:** Event-driven quantitative market pipeline with segregated execution (`/v1/edges`) and anomaly-quarantine (`/v1/diagnostics`) boundaries, backed by a native TypeScript `@modelcontextprotocol/sdk` server.
* **Key Capability:** Commits every published edge to a 3-hash RFC-8785 SHA-256 verification chain (Opening Projection → Pre-Kickoff Closing Snapshot → Boxscore Settlement) with idempotent GitHub Actions cron dispatching (`.cache/sent_edge_alerts.json`) and 118 passing `pytest` contract assertions.
* **Live System:** [propstein.com](https://propstein.com) (286 Production Health & Pricing Checks)

---

## Featured Systems — Technical Breakdown

### 1. [`receiptd`](https://github.com/NickAltstein/receiptd) — Open Agent Authorization & Evidence Layer
* **Architecture:** Pre-execution gatekeeper and tamper-evident audit ledger for Model Context Protocol (MCP) and Claude Code tool-calling agents.
* **Key Capability:** Evaluates JSON-RPC 2.0 tool arguments against strict YAML/AST policy rules, blocks unauthorized mutations fail-closed with exit code 2, and emits offline-verifiable Ed25519 receipts linked via an append-only SHA-256 hash chain.
* **Quickstart:** `pip install git+https://github.com/NickAltstein/receiptd && receiptd init --claude-code`

### 2. [`infini`](https://github.com/NickAltstein/infini) — Portable Agent Workflow Spec & Time-Travel Replay CLI
* **Architecture:** SQLite-backed orchestration and observability runtime eliminating external Redis/Kafka dependencies for deterministic agent debugging.
* **Key Capability:** Records every tool call, environment state, and filesystem assertion into a signed `.trace` ledger; supports cross-engine trace diffing, honeypot server testing, denial-of-wallet loop analysis, and automated PR auditing via the `infini-guard` GitHub Action.
* **Benchmark:** Measured 1.85ms per-step overhead across 1,000 steps (`benchmarks/results.json`).

### 3. [`birkin-sandbox`](https://github.com/NickAltstein/birkin-sandbox) — Interactive MCP Blast-Radius Simulator
* **Architecture:** Zero-install client-side deterministic firewall simulator and time-travel debugger powered by WebCrypto `Ed25519` (with resilient `HMAC-SHA256` fallback) and RFC-8785 canonical JSON serialization.
* **Key Capability:** Allows engineers to trigger indirect prompt-injection and destructive SQL scenarios, toggle policy-as-code gates in real time, fork trace frames at $T+N$ with zero upstream LLM token overhead, and test 1-byte cryptographic tamper detection.

---

## Core Engineering Philosophy

1. **Fail-Closed By Default:** Security boundaries and pricing gates must never degrade open. Unhandled schema exceptions, missing cryptographic contexts, or out-of-bounds statistical anomalies (`>12.0%` synthetic divergence) automatically quarantine or halt execution.
2. **Deterministic Reproducibility Over Vibes:** Every state transition must be canonicalized (`RFC-8785`), content-addressed (`SHA-256`), and replayable from local SQLite traces without burning upstream LLM tokens.
3. **Zero-Bloat Production Verification:** Systems ship with automated contract harnesses (`pytest`, Playwright, GitHub Actions CI gates) verifying cryptographic integrity, float-precision boundaries, and security headers before deployment.

---

## Technical Stack

* **Languages & Runtimes:** Python 3.12, TypeScript, JavaScript (ES6+), SQL, Bash, Node.js
* **AI & Agent Infrastructure:** Model Context Protocol (MCP), Policy-as-Code Engines, Deterministic Trace Replay, Multi-Agent Evaluation
* **Cryptography & Verification:** Ed25519 Digital Signatures, RFC-8785 (JCS) Canonicalization, SHA-256 Hash-Chaining, Binary Merkle Trees, WebCrypto API
* **Data & Backend Systems:** FastAPI, Next.js App Router, PostgreSQL, SQLite (FTS5), Supabase, Upstash Redis, Docker, GitHub Actions CI/CD, Pytest
