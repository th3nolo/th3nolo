<h1 align="center">Manuel Parra</h1>

<p align="center">
  <strong>Forward deployed AI engineer · LLM fine-tuning · lead IC</strong><br>
  I work with clients to put document AI and model inference into production, and I build the backend around it.<br>
  I also fine-tune and serve open-weight models on my own GPUs: synthetic data, LoRA SFT and GRPO, held-out evaluation.<br>
  Remote from UTC-4. English and Spanish. Open to senior and lead IC roles.
</p>

<p align="center">
  <a href="https://th3nolo.com">th3nolo.com</a> ·
  <a href="https://th3nolo.com/articles">Engineering notes</a> ·
  <a href="https://th3nolo.com/open-source">Open-source log</a> ·
  <a href="https://th3nolo.com/cv">CV</a> ·
  <a href="https://huggingface.co/th3nolo">Hugging Face</a> ·
  <a href="https://www.linkedin.com/in/th3nolo/">LinkedIn</a>
</p>

---

Most of my client work is private, so the results below link to case studies and write-ups. The public projects further down are code you can clone and run.

### AI engineering: measured results

| System | Result | Source |
|---|---|---|
| Financial document AI, Arabic and English audited statements | 34% → 94% on an internal extraction and calculation evaluation. One 22-page filing in 97 s for USD 0.30 to 0.42 | [case study](https://th3nolo.com/projects/financial-document-ai) |
| semgate: permission gate for coding agents, TypeSafe Jev judge | 0 of 47 harmful-allow base cases on a 355-case set (95% upper bound 6.2%). 83.0% of benign actions auto-allowed (95% CI 78.4% to 87.5%) | [evals](https://github.com/th3nolo/semgate/blob/main/EVALS.md) |
| LangGraph RAG chat, JEV-first routing | 0.981 vs 0.957 accuracy on 322 labeled messages | [note](https://th3nolo.com/articles/how-routing-a-langgraph-rag-chat-with-jev-got-me-98-accuracy) |

### ML and LLM fine-tuning

This is separate from the client work above. I generate training data, fine-tune open-weight models with LoRA (SFT and GRPO), evaluate them on held-out splits, and tune inference on my own GPUs. The weights, data and code are public.

| Work | Result | Links |
|---|---|---|
| TabCrew: Qwen3.5-0.8B LoRA that groups browser tabs. SFT on 3,030 synthetic sessions, 1 epoch on one RTX 3080 | Held-out test: 369/369 valid JSON, 332/369 (90.0%) exact grouping. p50 2.21 s per session | [model](https://huggingface.co/th3nolo/tabcrew-qwen3.5-0.8b-lora-mixed-sft) · [code](https://github.com/th3nolo/tabcrew-training) · [note](https://th3nolo.com/articles/what-i-learned-fine-tuning-a-small-model) |
| SFT vs SFT + GRPO baseline on 705 sessions | 55.6% vs 54.3% exact grouping on 81 validation sessions: the short GRPO stage gave no reliable gain. The later 3,030-session SFT run reached 95.1% on the same 81 sessions | [model](https://huggingface.co/th3nolo/tabcrew-qwen3.5-0.8b-lora-early-705) |
| Training-data repair (continued LoRA SFT) | Valid plans 1/81 → 75/81, strict pairwise F1 0.01 → 0.88 on 81 development cases | [note](https://th3nolo.com/articles/what-i-learned-fine-tuning-a-small-model) |
| Synthetic data pipeline: an author model writes each session, a blind regroup keeps only sessions where both groupings agree | 4,471 sessions with per-teacher provenance. Local Qwen3-4B-AWQ on SGLang: 185 → 274 tok/s after raising the KV pool from 8K to 16K tokens | [dataset](https://huggingface.co/datasets/th3nolo/tabcrew-synthetic-tab-sessions) · [recipes](https://github.com/th3nolo/tabcrew-training/tree/main/recipes/speed) |
| GLM-5.2-504B on 8× RTX PRO 6000 (vLLM, SM120) | 240K-token context after a sparse-attention layer fix | [note](https://th3nolo.com/articles/glm-5-2-blackwell-sm120) |

All TabCrew models and data: [Hugging Face collection](https://huggingface.co/collections/th3nolo/tabcrew-6ada8965cb27d41ff3edb29e).

### Public projects

| Project | What it does | |
|---|---|---|
| [semgate](https://github.com/th3nolo/semgate) | Permission gate for coding agents. Deterministic rules decide the certain cases, a typed Jev judge handles the rest, and every doubt goes to the human. Hooks into Claude Code, Codex, OpenCode, Gemini CLI, Antigravity, Copilot CLI, and more. 2,958 tests and TLA+ models. Host hook behavior measured with [hookconf](https://github.com/th3nolo/hookconf). | Python |
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

<sub>Python · TypeScript · Rust · Go · Solidity. PyTorch, Transformers, PEFT, TRL, vLLM, SGLang, FastAPI, NestJS, PostgreSQL, Docker, GitHub Actions</sub>
