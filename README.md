<h1 align="center">Manuel Parra</h1>

<p align="center">
  <strong>Forward deployed AI engineer · lead IC</strong><br>
  I work with clients to put document AI and model inference into production, and I build the backend around it.<br>
  Remote from UTC-4. English and Spanish. Open to senior and lead IC roles.
</p>

<p align="center">
  <a href="https://th3nolo.com">th3nolo.com</a> ·
  <a href="https://th3nolo.com/articles">Engineering notes</a> ·
  <a href="https://th3nolo.com/open-source">Open-source log</a> ·
  <a href="https://th3nolo.com/cv">CV</a> ·
  <a href="https://www.linkedin.com/in/th3nolo/">LinkedIn</a>
</p>

---

Most of my client work is private, so the results below link to case studies and write-ups. The public projects further down are code you can clone and run.

### Measured results

| System | Result | Source |
|---|---|---|
| Financial document AI, Arabic and English audited statements | 34% → 94% on an internal extraction and calculation evaluation. One 22-page filing in 97 s for USD 0.30 to 0.42 | [case study](https://th3nolo.com/projects/financial-document-ai) |
| LangGraph RAG chat, JEV-first routing | 0.981 vs 0.957 accuracy on 322 labeled messages | [note](https://th3nolo.com/articles/how-routing-a-langgraph-rag-chat-with-jev-got-me-98-accuracy) |
| Small-model fine-tune (LoRA), training-data repair | Valid plans 1/81 → 75/81, strict pairwise F1 0.01 → 0.88 on 81 development cases | [note](https://th3nolo.com/articles/what-i-learned-fine-tuning-a-small-model) |
| GLM-5.2-504B on 8× RTX PRO 6000 (vLLM, SM120) | 240K-token context after a sparse-attention layer fix | [note](https://th3nolo.com/articles/glm-5-2-blackwell-sm120) |

### Public projects

| Project | What it does | |
|---|---|---|
| [quake-reunite](https://github.com/th3nolo/quake-reunite) | Search API and map for people and aid centers after the June 2026 La Guaira earthquake. Mistral OCR and Gemma 4 on Cerebras read WhatsApp lists, hospital-list photos, and PDFs, then merge duplicate people across sources. [Live](https://venezuel.help/) | Python |
| [openrouter-mcp](https://github.com/th3nolo/openrouter-mcp) | Stateless MCP 2026-07-28 server and CLI for OpenRouter. 13 tools, 1 resource, HTTP and stdio. | TypeScript |
| [sqlbench-harness](https://github.com/th3nolo/sqlbench-harness) | Benchmark for LLM-generated SQL on BIRD, KaggleDBQA, Defog SQL-Eval, and Spider 2.0. Treats benchmark text as untrusted prompt input. Reports accuracy, errors, tokens, and cost. | Python |
| [verifiable-exchange-demo](https://github.com/th3nolo/verifiable-exchange-demo) | Limit-order engine. Anyone can replay its history from signed orders, Merkle proofs, and on-chain anchors. [Live demo](https://exchange.th3nolo.com) | Rust |
| [dep-age-gate](https://github.com/th3nolo/dep-age-gate) | Refuses dependency versions younger than 72 hours. Lockfile audit, pre-commit hook, and GitHub Action. | Python |

### Upstream contributions

- My PR #85 to the OpenClaw installer was merged ([commit bfc0bd9](https://github.com/Nicell/clawd.bot/commit/bfc0bd96882ce91faf34be107b6b8ff73bc1b189)). It rewrote the Windows install checks, and three of those functions still run in the live `install.ps1`.
- In [hiero-sdk-js](https://th3nolo.com/open-source), I showed that the published `@hashgraph/sdk` still pulled in protobufjs 8.0.0 (GHSA-xq3m-2v4x-88gg, a remote code execution bug) after the upstream fix. The issue was closed as completed.
- In [openai/codex#34801](https://github.com/openai/codex/issues/34801), I traced broken image thumbnails to the desktop app fetching signed URLs without the Bearer token.
- I also reproduced 19 bugs in Codex, Claude Code, and OpenCode. The [open-source log](https://th3nolo.com/open-source) has the evidence for each one.

### Latest engineering notes

<!-- NOTES:START -->
- [How routing a LangGraph RAG chat with JEV got me 98% accuracy](https://th3nolo.com/articles/how-routing-a-langgraph-rag-chat-with-jev-got-me-98-accuracy) · 2026-09-27
- [What I learned fine-tuning a small model: mistakes you can avoid](https://th3nolo.com/articles/what-i-learned-fine-tuning-a-small-model) · 2026-09-16
- [Building a strict stateless MCP 2026-07-28 server for OpenRouter](https://th3nolo.com/articles/openrouter-stateless-mcp-2026-07-28) · 2026-08-31
- [Building a Verifiable Exchange: Signed Orders, Replayable Execution, and On-Chain Anchors](https://th3nolo.com/articles/verifiable-exchange-signed-log-onchain-anchors) · 2026-08-27
- [Serving GLM-5.2-504B on RTX PRO 6000: the vLLM sparse attention fix on SM120](https://th3nolo.com/articles/glm-5-2-blackwell-sm120) · 2026-07-04
<!-- NOTES:END -->

<sub>Python · TypeScript · Rust · Go · Solidity. FastAPI, NestJS, PostgreSQL, vLLM, Docker, GitHub Actions</sub>
