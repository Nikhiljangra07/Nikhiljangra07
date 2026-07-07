# Nikhil Jangra

**AI and ML systems designer.** I design and build AI systems end-to-end — product architecture,
multi-agent pipelines, model training, and evaluation methodology. I don't write code:
AI-assisted development tools handle implementation; the design, judgment, and verification
are mine.

My approach draws on cognitive science — appraisal theory, gist-based memory, mood-congruent
retrieval — translated into working architecture.

## The arc

**Text → voice → trained models.** I built an analytical-reasoning product, discovered where
text-only emotional signal hits its ceiling, proved the voice axis works, and then trained
specialist models that beat a frontier model on their target objective.

### 🧭 [LoRa](https://github.com/Nikhiljangra07/LoRa-EmotionalEngine-v1) — production AI product
Analytical reasoning partner ("analysis, not validation"). Solo-built 5-service architecture:
TypeScript/Express core, Python math-reasoning microservice, graph + vector memory with **zero
conversation storage** (ChromaDB emotion-anchored retrieval + FalkorDB fact anchors), Supabase
auth, Stripe, security hardening, live ops dashboard. Ran as a public beta at asklora.io in
spring 2026.

### 🌌 [Constellax](https://github.com/Nikhiljangra07/reasoningEngine) — autonomous divergent reasoning
Goal-**blind** wandering agents search distant domains for structural analogies; goal-aware judges
steer; a cross-model-family blender fuses proposals into testable math. Ran end-to-end on a real
open research problem (multi-agent collusion detection) — full run record and a deliberately
balanced strengths/weaknesses audit in the repo. Work in progress; the wandering-room pipeline is
the part that works today.

### 🔱 [divergence-formula](https://github.com/Nikhiljangra07/divergence-formula) — training divergent models
Distilled Constellax's core operation into a trainable criterion, then trained two open models to
**refract** hard decisions into 4 distinct viable strategies: a 3.4B dense proof-of-concept and a
32B/9B-active hybrid MoE that **beats Claude Haiku 4.5 on distinctness (4.90 vs 4.75)** on a
neutral-judge benchmark. Eight documented rounds including the negative results (capacity
entanglement, DPO refutation). Total budget: ~$175.

### 🎙️ [voice-emotion-engine](https://github.com/Nikhiljangra07/voice-emotion-engine) — speech emotion + TTS steering
Fine-tuned WavLM-large for dimensional emotion (Valence/Arousal/Dominance): **CCC 0.705 valence on
46k held-out unseen-speaker clips** — the axis the handcrafted-feature literature says is
unrecoverable from audio (my own handcrafted pipeline: 0.06 → 0.35; fine-tune: 0.705). Second
project in-repo: emotional TTS steering with a fair benchmark vs ElevenLabs — honest mixed results.

## How I work

- **Evidence over claims** — every repo carries its full run records, benchmarks, and decision logs,
  including the experiments that failed and the results that weren't novel.
- **Specialists over generalists** — small models beating frontier models in one lane, on purpose.
- **Meticulous ops** — CI on every push, secrets-scanned histories, resumable pipelines, verified
  backups.

## Stack

TypeScript · Node.js · Python · FastAPI · PyTorch · Transformers/PEFT · ChromaDB · FalkorDB ·
Neo4j · Anthropic SDK · Stripe · Supabase · Railway · RunPod

## About

Self-taught. Based in Vancouver.

📫 nikhiljangra051@gmail.com
