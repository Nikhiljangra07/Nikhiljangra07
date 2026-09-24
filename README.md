# Nikhil Nikhil

**AI engineer. I ship LLM products to production.** Building and running [asklora.io](https://asklora.io), an analytical-reasoning assistant: Python/FastAPI + TypeScript/Node, model routing across OpenAI, Anthropic and Google, agents with tool calling, vector + graph RAG, Stripe billing, CI/CD, on-call. Public beta with ~40 users, spring 2026.

Open to AI engineering roles in Canada (Metro Vancouver or remote). 📫 nikhiljangra051@gmail.com · 🤗 [huggingface.co/Nikhil0097](https://huggingface.co/Nikhil0097) · [(https://www.linkedin.com/in/nikhil-jangra-7b7b1221a/)](https://linkedin.com/in/nikhil-7b7b1221a)

> Legal name is the single given name Nikhil, recorded as "Nikhil Nikhil" on official documents. Professionally I go by Nikhil Jangra.

## What I've shipped

| Project | What it is | Result |
|---|---|---|
| [LoRa](https://github.com/Nikhiljangra07/LoRa-EmotionalEngine-v1) · [asklora.io](https://asklora.io) | Production LLM product, Jun 2025 – present | 3 model calls → 1 behind a frozen output contract: **9–12s → 3–4s at ~$0.008/message**, measured on production p95s |
| [cube-program](https://github.com/Nikhiljangra07/cube-program) | 24-run pre-registered study of verification harnesses for small LLMs | Same Qwen3-4B weights **0/16 → 6/16** fully grounded; **5–2** vs the reasoning-trained sibling on a third-party holdout; two adversarial GPT audits published, one claim retracted |
| [voice-emotion-engine](https://github.com/Nikhiljangra07/voice-emotion-engine) | WavLM-large fine-tune for speech emotion + real-time Live Ear | **CCC 0.705 / 0.714 / 0.626** (V/A/D) on 46k unseen-speaker clips; 68.6% hybrid namer on real phone-mic audio |
| [divergence-formula](https://github.com/Nikhiljangra07/divergence-formula) | Fine-tuning Granite (3.4B; 32B/9B-active MoE) with LoRA/SFT/DPO | **4.90 vs 4.75** distinctness vs Claude Haiku 4.5, ties on decisiveness, loses overall 4.55 vs 4.72 (Gemini 2.5 Pro judge) |
| [Constellax](https://github.com/Nikhiljangra07/reasoningEngine) | Multi-agent reasoning engine (blind generators, aware judges, cross-model blender) | Ran end-to-end on an open problem; result correct but not novel, and published as such |
| [inspect-grounding-eval](https://github.com/Nikhiljangra07/inspect-grounding-eval) | Inspect (UK AISI) task, code-only certified-grounding scorer | 4/4 on Claude Haiku 4.5 incl. an explicit-refusal case |

## The projects, one paragraph each

**LoRa** — TypeScript/Node (Express) API, Python (FastAPI) reasoning microservice, React frontend, PostgreSQL (Supabase), Redis, ChromaDB, on Railway with Docker and GitHub Actions CI/CD. The LLM layer does the work: complexity-based routing across OpenAI, Anthropic (Claude) and Google (Gemini) models, timeouts and bounded retries, structured-output validation, a cooldown circuit breaker with a recovery lane (designed after diagnosing a live failure cascade in the logs), and a code-only guard on every reply. Memory stores no transcripts: at session end a pipeline summarizes, extracts facts, verifies them in code, and writes to graph and vector stores; 230 tests, fail-open at every stage. Auth, Stripe subscriptions with signature-verified webhooks, prompt-injection filtering, rate limiting, a live health dashboard with 17 metrics, an incident log. Evaluated with a blind 20-dimension benchmark across seven models, with the rubric's bias toward my own design disclosed alongside the scores. Deep mode runs five reasoning frameworks through the Python microservice under a 60-second budget.

**cube-program** (Jul–Aug 2026) — Can a verification harness substitute for scale at 4B? A five-stage harness (machine-verified fact extraction → code-computed comparisons → anchored reasoning → template assembly) took the same Qwen3-4B weights from 0/16 to 6/16 fully grounded answers against a one-pass control, and beat the reasoning-trained sibling 5–2 on a holdout written by a third model — with the harness frozen in git before the holdout existed. Every success bar was written before spend and every failed bar is published, including the pre-registered strict-band claim that did not transfer. Two adversarial GPT audits (8 + 10 findings) with dispositions; one pre-committed claim retracted after the second. Start with `INTERVIEW_PACK.md` for the claims and their qualifiers.

**voice-emotion-engine** (Mar–Aug 2026) — Fine-tuned WavLM-large on MSP-Podcast for valence/arousal/dominance: CCC 0.705 / 0.714 / 0.626 on 46k unseen-speaker clips, after a handcrafted 111-feature baseline capped valence at 0.35. Hybrid two-backbone emotion namer at 68.6% leave-one-speaker-out on real phone-mic audio; speaker diarization; a 19-input adversarial pass with zero crashes; 160+ tests. The Live Ear (Aug 2026) maps emotion from whatever is playing on the machine in real time, 5–8× real-time on Apple silicon, speech-gated with Silero VAD. A companion project steers a TTS model toward target emotions and benchmarks it fairly against ElevenLabs, Hume and OpenAI (130 judged clips; the headline result was retracted when a fairer test dissolved it). Model: [wavlm-large-emotion-vad](https://huggingface.co/Nikhil0097/wavlm-large-emotion-vad).

**divergence-formula** (Jun–Jul 2026) — Trained IBM Granite models (3.4B dense; 32B/9B-active hybrid Mamba+MoE) with LoRA SFT and DPO on 6,745 judge-gated synthetic rows to produce four distinct strategies for a hard decision instead of one blended answer. The shipped model scores 4.90 vs Claude Haiku 4.5's 4.75 on distinctness and ties it on decisiveness (Gemini 2.5 Pro judge, 48 held-out problems), while losing overall 4.55 vs 4.72. Eight rounds documented, including the DPO capacity-entanglement negative result on the 3.4B. Adapters: [refract-hsmall-blend2](https://huggingface.co/Nikhil0097/refract-hsmall-blend2) · [refract-granite-3.4b-v5](https://huggingface.co/Nikhil0097/refract-granite-3.4b-v5).

**Constellax** (2026) — Goal-blind generator agents search distant domains for structural analogies; goal-aware judges steer; a cross-family blender (Claude + DeepSeek R1) fuses proposals; a grounding stage turns them into testable math. ~139K lines of Python, 43 test files, FastAPI with 22 endpoints, fail-open on every external dependency. Ran end-to-end on an open problem from Hammond et al. (2025): 4 cycles, 218 cards, a do-calculus separation criterion validated in a toy model — then benchmarked against a single frontier prompt, which matched it in 30 seconds. That comparison, and the unflattering answer, are in `PIPELINE_ASSESSMENT.md`.

## How I work

Specs first, then build, then measure. Every repo here carries its run record, including the results that didn't hold. I use Claude Code heavily and treat it like any other tool: I own the architecture, read every diff, and nothing ships without tests or an eval gate.

**Stack:** Python, TypeScript, Node.js, Express, FastAPI, React, PostgreSQL, Redis, ChromaDB, Neo4j, Stripe, Docker, Railway, RunPod, GitHub Actions · OpenAI / Anthropic / Google / DeepSeek APIs, MCP, RAG, evals and LLM-as-judge · PyTorch, Transformers, TRL, LoRA/PEFT, SFT, DPO
