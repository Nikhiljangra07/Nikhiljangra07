# Nikhil Jangra

**Applied AI engineer focused on LLM systems and evaluation.** I build with Python and TypeScript, design controlled experiments, and investigate where model behavior and software fail.

I built and operated **LoRa**, an analytical-reasoning assistant, through a public beta with approximately 40 testers. The beta has concluded and had no paying users. I am now seeking **full-time applied AI or evaluation engineering work in Metro Vancouver or remotely within Canada**.

[GitHub projects](https://github.com/Nikhiljangra07?tab=repositories) · [Hugging Face models](https://huggingface.co/Nikhil0097) · [LinkedIn](https://www.linkedin.com/in/nikhil-jangra-7b7b1221a) · [Email](mailto:nikhiljangra051@gmail.com)

## Selected work

| Project | What I built and measured |
|---|---|
| [LoRa backend](https://github.com/Nikhiljangra07/LoRa-EmotionalEngine-v1) | TypeScript/Express backend for a deployed beta, with a Python/FastAPI reasoning service, model routing, graph/vector memory, Supabase authentication, Stripe webhooks, and operational diagnostics. |
| [Cube](https://github.com/Nikhiljangra07/cube-program) | A 24-run study of staged inference and small-model behavior, with frozen protocols, model-assisted audits, negative results, and [statistical corrections](https://github.com/Nikhiljangra07/cube-program/blob/master/ERRATA_2026-10-14.md). The small-sample gain did not establish robust holdout improvement. |
| [quant-lab](https://github.com/Nikhiljangra07/quant-lab) | Qwen3-4B quantization experiments using vLLM and lm-eval. Measured quality, throughput, and memory; the registered all-Linear INT4 recipe failed its quality bar. Later recipes are explicitly exploratory. |
| [Voice emotion engine](https://github.com/Nikhiljangra07/voice-emotion-engine) | WavLM fine-tuning, speaker-separated evaluation, dimensional affect estimation, and real-time audio inference. [Checkpoint and model card](https://huggingface.co/Nikhil0097/wavlm-large-emotion-vad). |
| [divergence-formula](https://github.com/Nikhiljangra07/divergence-formula) | Synthetic-data preparation and LoRA SFT of Granite models to produce distinct strategies for a decision; separate DPO experiments and failure analysis. [Adapters](https://huggingface.co/Nikhil0097). |
| [Inspect numeric-grounding demo](https://github.com/Nikhiljangra07/inspect-grounding-eval) | Four Inspect examples with deterministic numeric-token and refusal checks. A small scorer demonstration, with its semantic limitations documented. |
| [Constellax](https://github.com/Nikhiljangra07/reasoningEngine) | Multi-agent generation, judging, and synthesis. An end-to-end experiment and its assessment, including a much cheaper single-model baseline that matched the tested result. |

## Engineering examples

**Operating an LLM application.** LoRa connected multiple services and model providers, with timeouts, bounded retries, circuit breaking, structured-output validation, and response guards. Its memory pipeline extracts structured information for graph/vector retrieval and uses an LLM verification step with code-level schema checks. I documented failure cases and design decisions. The public repository is the TypeScript backend; the Python service and frontend are separate projects.

**Measuring a tradeoff before shipping it.** In quant-lab, the registered W4A16 recipe increased single-stream throughput from 144 to 283 tokens/s on the tested setup, while GSM8K accuracy fell from 80.52% to 72.55%. It failed the declared quality bar. Exploratory MLP-only and NVFP4 variants have separate reports; they are not retrospective successes of the original protocol.

**Training and evaluating specialist models.** My WavLM checkpoint reports Test1 CCC of 0.705 / 0.714 / 0.626 for valence, arousal, and dominance against dataset annotations. These are dataset results, not evidence of reading a person's internal emotional state. The Granite BLEND2 adapter scored 4.90 versus Haiku 4.5's 4.75 on strategy distinctness in one 48-problem, single-judge evaluation, but lost on the overall score, 4.55 versus 4.72. Model cards document evaluation scope and usage restrictions.

## How I work

I use AI coding tools heavily for implementation and take responsibility for architecture, evaluation design, review, and verification. I work from recorded assumptions and explicit checks, and revise conclusions when the evidence changes. My repositories include experiments that failed and explanations of what they do and do not establish.

**Tools used across these projects:** Python, TypeScript, Node.js, Express, FastAPI, React, ChromaDB, FalkorDB, Supabase Auth, Stripe, Docker, Railway, RunPod, GitHub Actions; model APIs, retrieval, structured outputs, Inspect, vLLM, lm-eval, PyTorch, Transformers, TRL, and PEFT/LoRA.

*Profile updated October 27, 2026. Detailed project reports and their current corrections govern the summarized results above.*
