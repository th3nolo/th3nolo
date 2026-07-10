<h1 align="center">Manuel Parra</h1>

<p align="center">
  <strong>Lead software engineer · applied AI & inference systems</strong><br>
  I build backend-heavy systems for messy inputs, expensive mistakes, and real operating constraints.
</p>

<p align="center">
  <a href="https://th3nolo.com">Website</a> &bull;
  <a href="https://th3nolo.com/articles">Engineering notes</a> &bull;
  <a href="https://www.linkedin.com/in/th3nolo/">LinkedIn</a>
</p>

---

## Current work

**Large-model inference on Blackwell**

- Serving and profiling open-weight models on RTX PRO 6000 Blackwell systems with vLLM, SGLang, TensorRT-LLM, and NVIDIA Dynamo.
- Current work covers the GLM-5.2 504B-parameter MoE checkpoint, sparse attention, NVFP4/W4A16 checkpoints, tensor and decode-context parallelism, KV-cache pressure, CUDA/NCCL failures, and scale-to-zero workers.
- Validated correct sparse-attention output and cold prompts through 240K tokens on an 8-GPU GCP `g4-standard-384` worker. [Read the investigation →](https://th3nolo.com/articles/glm-5-2-blackwell-sm120)

**Document extraction as infrastructure**

- Building a backend-agnostic extraction service for OCR, layout parsing, normalization, provenance, deterministic validation, and human review.
- Jobs are idempotent, resumable, shard-aware, and versioned so every value can be traced to its source document and parser/model configuration.
- Current performance target: 3,000 documents in 300 seconds without coupling the extraction runtime to one product backend.

**Gemini Nano reverse engineering**

- Reconstructing Chrome's on-device Gemini Nano v3 path from a 3.98 GB `weights.bin`: tensor offsets, Gemma-family architecture, INT4 group layout, FP16 scale/zero side tables, and the layer-0 forward pass.
- Instrumenting Chrome/WebGPU with CDP and Frida, then comparing dequantized tensors against runtime behavior. Text generation remains gated on activation-stability checks; plausible output is not treated as proof.

**Multi-tenant AI systems**

- Designing control planes that provision isolated agent workers per tenant, encrypt credentials, enforce scoped access, meter usage, and share normalized ingestion without sharing tenant state.
- The useful work is around the model: contracts, retries, observability, evaluation, evidence, and failure recovery.

## Shipped systems

**ConTrust Suite — multi-tenant construction reporting**

- Lead engineer and architect for a production platform that converts jobsite documents and SharePoint files into normalized reporting data across owner, contractor, and subcontractor boundaries.
- Row-level security, schema-per-tenant isolation, scoped credentials, raw-value retention, validation flags, and source-file evidence feed seven reporting workflows.
- FastAPI, React/Vite, PDF workers, Pydantic, PostgreSQL, AI reporting.

**Financial document AI**

- Owned the OCR/extraction service for Arabic and English audited financial statements.
- Parallel extraction channels vote; accounting identities, section totals, and cross-year checks decide what is accepted and what is routed to a human.
- Internal extraction accuracy improved from 34% to 94% on production statements, with processing at approximately $0.30–$0.42 per company.

**DeFi position protection**

- Built the Solidity wallet factory and backend automation used across 84 Aave V3 smart-wallet positions over 18 months.
- More than $2M in collateral flow with zero liquidations; the protection logic also survives seven historical 2021–2025 crash scenarios.
- Solidity, Rust, TypeScript, Go, React, PostgreSQL, Arbitrum.

**Threshold cryptography and consent verification**

- Built a 7-of-10 threshold-decryption network using BLS aggregate signatures and Merkle proofs anchored to Hedera.
- Batched and pinned 3.63M hashed device identifiers in 63 seconds; three independent nodes verify each consent record.
- Rust, WASM, BLS12-381, NATS; SDKs in Dart, TypeScript, Java, and Rust.

## Public work

- [Venezuel.help](https://venezuel.help) / [quake-reunite](https://github.com/th3nolo/quake-reunite) — earthquake-response search and 3D map for La Guaira. FastAPI, SQLite, Gemma 4 on Cerebras, Mistral OCR, MapLibre, and a ten-minute ingestion/reconciliation loop.
- [sqlbench-harness](https://github.com/th3nolo/sqlbench-harness) — audited execution harness for LLM-generated SQL across BIRD, KaggleDBQA, Defog SQL-Eval, and Spider 2.0, with result accuracy, token use, cost, and fairness classification.
- [wdk-browser-extension-starter-public](https://github.com/th3nolo/wdk-browser-extension-starter-public) — Chrome/Brave wallet starter using Tether WDK: encrypted local vault, service-worker key custody, decoded transaction review across seven chains, and 290 tests.
- [aave-v3-data](https://github.com/th3nolo/aave-v3-data) — Aave V3 reserve data for 13 networks, published daily by GitHub Actions with no application server or API keys.
- [colab-inference](https://github.com/th3nolo/colab-inference) — exposes a Colab T4 as a local OpenAI-compatible inference endpoint.
- [downloadtomarkdown.com](https://downloadtomarkdown.com) — scanned PDFs, images, and DOCX to Markdown; built and operated solo.

## Technical surface

| Area | Tools and systems |
|---|---|
| Languages | Python, TypeScript, Rust, Go, Solidity, Dart |
| Inference | vLLM, SGLang, TensorRT-LLM, NVIDIA Dynamo, NVFP4/W4A16, CUDA, NCCL |
| Applied AI | OCR, document intelligence, RAG, agent systems, multimodal extraction, evaluation |
| Backend and data | FastAPI, Node.js, NestJS, PostgreSQL, MongoDB, SQLite, WebSockets |
| Cryptography | Solidity, Foundry, Hardhat, Ethers.js, BLS12-381, Merkle proofs, WASM |
| Infrastructure | Docker, Google Cloud, GitHub Actions, scale-to-zero workers |

I care about reproducible measurements, source evidence, deterministic validation, and systems that keep running after the first demo.

<details>
<summary><strong>Education</strong></summary>

Computer Science, 2015–2021

</details>
