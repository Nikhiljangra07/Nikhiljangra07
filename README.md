# Nikhil Nikhil

**AI systems engineer — LLM applications, evaluation methodology, and specialist model training.**
I work AI-natively: architecture, evaluation, and verification are mine; AI coding tools accelerate
implementation. Nothing ships without passing tests, benchmarks, or an evaluation gate — and every
repo below carries its full run record, failures included.

**Open to AI engineering roles (Canada, work-authorized).** 📫 nikhiljangra051@gmail.com · 🤗 [huggingface.co/Nikhil0097](https://huggingface.co/Nikhil0097)

## Proof, compressed

| Claim | Number | Where |
|---|---|---|
| Verification harness lifts a 4B model on strict grounding | **0/16 → 6/16 certified-clean, p≈0.008** | [cube-program](https://github.com/Nikhiljangra07/cube-program) |
| Fine-tuned 32B MoE edges Claude Haiku 4.5 on its one target metric | **4.90 vs 4.75** on strategy distinctness (blind judge) | [divergence-formula](https://github.com/Nikhiljangra07/divergence-formula) |
| Valence from voice — the axis handcrafted features can't reach | **CCC 0.06 → 0.35 → 0.705** (46k held-out clips) | [voice-emotion-engine](https://github.com/Nikhiljangra07/voice-emotion-engine) |
| Production LLM pipeline, 3 calls → 1 behind a frozen contract | **9–12s → 3–4s at ~$0.008/msg** | [LoRa](https://github.com/Nikhiljangra07/LoRa-EmotionalEngine-v1) |

## Projects

### 📐 [cube-program](https://github.com/Nikhiljangra07/cube-program) — pre-registered, externally audited evaluation study
Can architecture substitute for scale in small LLMs? 23 runs. Success criteria frozen in runbooks
before any compute was spent; the eval harness git-frozen before the third-party-authored holdout
existed; two LLM-judge families at 97.9% agreement; independent adversarial audit — all 8 findings
and dispositions published. The grounding result held (0/16 → 6/16 certified-clean, paired p≈0.008;
5–2 on the holdout). The pre-registered transfer claim **failed** — reported at equal weight, with
the residual failure diagnosed. Total spend ~$207.

### 🧭 [LoRa](https://github.com/Nikhiljangra07/LoRa-EmotionalEngine-v1) — production AI product, built and operated solo
Analytical reasoning partner ("analysis, not validation"), public beta at [asklora.io](https://asklora.io)
spring 2026. Five-service architecture: TypeScript/Express core, Python/FastAPI reasoning
microservice, ChromaDB + FalkorDB graph-vector memory with **zero conversation storage**, Supabase
auth, Stripe billing, live ops dashboard with 17 operational counters. Reliability layer:
complexity-based model routing, cooldown circuit breaker with recovery lane, structured-output
validation with a second-model verification gate. Evaluated by a 20-dimension blind benchmark
across 7 models — rubric-bias disclosure published alongside the scores. 100+-entry decision log.

### 🎙️ [voice-emotion-engine](https://github.com/Nikhiljangra07/voice-emotion-engine) — dimensional speech emotion
Fine-tuned WavLM-large on MSP-Podcast: **CCC 0.705 / 0.714 / 0.626 (V/A/D)**, speaker-independent
on 46k held-out clips. Hybrid two-backbone emotion namer: **68.6%** on 175 real phone-mic clips,
leave-one-speaker-out — the contaminated 72.6% variant excluded and disclosed. Real-time layer
(VAD gating, causal smoothing: label flicker 44–52% → 12–16%), ECAPA diarization, adversarial
robustness pass (19 hostile inputs: zero crashes, zero NaN). Companion: emotional TTS steering
benchmarked fairly vs ElevenLabs — honest mixed results.
Model: [wavlm-large-emotion-vad](https://huggingface.co/Nikhil0097/wavlm-large-emotion-vad).

### 🔱 [divergence-formula](https://github.com/Nikhiljangra07/divergence-formula) — training divergent specialist models
Distilled a multi-agent system's core operation into a trainable criterion, then fine-tuned two
open models to **refract** hard decisions into 4 distinct viable strategies: a 3.4B dense
proof-of-concept and a 32B/9B-active hybrid Mamba+MoE that edges Claude Haiku 4.5 on the single metric it was
trained for — strategy distinctness, 4.90 vs 4.75 (blind neutral judge). Eight documented training rounds including the negative results (capacity
entanglement, DPO refutation — the failed adapter is published as evidence). Budget ~$175.
Models: [refract-hsmall-blend2](https://huggingface.co/Nikhil0097/refract-hsmall-blend2) ·
[refract-granite-3.4b-v5](https://huggingface.co/Nikhil0097/refract-granite-3.4b-v5).

### 🌌 [Constellax](https://github.com/Nikhiljangra07/reasoningEngine) — autonomous divergent reasoning (WIP)
Goal-blind wandering agents search distant domains for structural analogies; goal-aware judges
steer; a cross-model-family blender fuses proposals into testable math. Ran end-to-end on a real
open research problem — full run record and a deliberately balanced strengths/weaknesses audit in
the repo. The wandering-room pipeline is the part that works today.

## How I work

- **Verification before claims** — pre-registration, frozen harnesses, blind judges, external audit;
  contaminated results get excluded and said so.
- **Failures are data** — negative results published at equal weight with wins, in every repo.
- **Specialists over generalists** — training small open models to win one narrow, measured lane,
  and stating exactly which lane and by how much.
- **Production discipline** — CI on every push, incident logs with root causes, resumable pipelines,
  security hardening, fail-open degradation.

## Stack

Python · TypeScript/Node.js · PyTorch · Transformers/PEFT/TRL · FastAPI · Express ·
ChromaDB · FalkorDB · Neo4j · Supabase · Stripe · Anthropic SDK · Docker · Railway · RunPod · GitHub Actions

---
*Vancouver, BC · self-taught · everything above is public and reproducible*
