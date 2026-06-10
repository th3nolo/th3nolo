<h1 align="center">th3nolo</h1>
<p align="center">Backend systems architect. I build the backend layers where a wrong number costs money: AI document pipelines, DeFi automation, Rust/WASM cryptography. I take the time to build systems that keep running without me.</p>

<p align="center">
  <a href="https://th3nolo.com">Website</a> &bull;
  <a href="https://www.linkedin.com/in/th3nolo/">LinkedIn</a> &bull;
  <a href="https://www.upwork.com/freelancers/~01ce9b85323e9b2d50">Upwork</a>
</p>

---

## What I've built

**Financial document AI pipeline (2026, in production)**
- Tech lead on a compliance platform; sole owner of the OCR service that turns Arabic and English audited financials into verified structured data
- Two AI channels read every page in parallel and vote. Deterministic checks (assets = liabilities + equity, section totals, cross-year) decide what gets trusted; anything uncertain goes to a human
- Accuracy went from 34% to 94% on real statements. A 22-page audited filing takes 97 seconds and costs $0.30–$0.42 per company
- TypeScript, Python/FastAPI, PostgreSQL, LLM vision + OCR, Hedera

**DeFi position automation (2024–2026)**
- Protected 84 smart-wallet positions on Aave V3 for 18 months, where a missed health check means instant liquidation. Wrote the Solidity wallet factory solo and deployed it to Arbitrum
- More than $2M in collateral flow, zero liquidations. In historical stress tests the protection logic survives all 7 major crashes 2021–2025
- Rust, Solidity, TypeScript, Go, React, PostgreSQL

**Threshold cryptography network (2025)**
- Built the cryptography and backend of a consent-verification network: 7-of-10 threshold decryption, BLS aggregate signatures, Merkle proofs anchored to Hedera
- 3.63M real device IDs hashed, Merkle-batched, and pinned in 63 seconds; three independent nodes verify every consent
- SDKs shipped in Dart, TypeScript, Java, and Rust
- Rust, WASM, BLS12-381, NATS

## Public code

- [wdk-browser-extension-starter-public](https://github.com/th3nolo/wdk-browser-extension-starter-public) - Manifest V3 Chrome/Brave wallet on Tether's Wallet Development Kit: AES-256-GCM local vault, background-only key authority, transaction review that decodes ERC-20, Uniswap, Aave, bridge, and Safe calldata across seven chains. 290 tests, MIT
- [aave-v3-data](https://github.com/th3nolo/aave-v3-data) - Aave V3 reserve data for 13 networks, published daily by GitHub Actions to GitHub Pages; running unattended since July 2025 with no servers and no API keys
- [colab-inference](https://github.com/th3nolo/colab-inference) - turns Colab's free T4 GPU into a local OpenAI-compatible LLM API
- [downloadtomarkdown.com](https://downloadtomarkdown.com) - live document-conversion SaaS, built solo: scanned PDFs, images, and DOCX in, clean Markdown out

## Tech stack

| Category | Technologies |
|---|---|
| Languages | Rust, TypeScript, Python, Go, Solidity, Dart |
| AI/ML | Multi-model pipelines, OCR, document extraction, LLM integration |
| Backend | FastAPI, Node.js, NestJS, Express, WebSockets |
| Smart contracts | Solidity, Hardhat, Foundry |
| Data | PostgreSQL |
| Infrastructure | Docker, Google Cloud, WASM, Hedera |

<details>
<summary><strong>Education</strong></summary>

Computer Science (2015-2021)

</details>

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=th3nolo&color=blueviolet&style=flat-square&label=Profile+Views" alt="Profile views" />
</div>
