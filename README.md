# Ezel

![Stewie](https://media.giphy.com/media/XDj6WniRi65ZS8vnrC/giphy.gif)

Computer Engineering, Hacettepe University. Backend Architecture at Jotform (part-time). Mostly vision-language models, sometimes embedded systems, occasionally Swift.

---

### Active

**Urban VQA.** Fine-tuning Qwen3.5-4B as a vision-language model on a custom urban-perception dataset: NAIP aerial tiles, Mapillary streetview frames, and NYC PLUTO parcel metadata as ground truth. ~27K samples stratified across 14 task topics through a custom batch sampler. Full bf16 fine-tune via Unsloth — the 5090's 32 GB has the headroom over QLoRA. Picked the 4B variant over 9B because edge inference is the eventual target. Currently sweeping LoRA rank/alpha, learning rate, and warmup ratio against per-topic accuracy.

**NOTA.** *When the Right Answer Is Missing: Probing Hallucination in Medical Reasoning Models via NOTA Evaluation.* Accepted to a CVPR 2026 workshop (Paper ID 17). Evaluates 17+ open and closed VLMs on chest X-ray VQA (ReXVQA) with adversarial *None-of-the-Above* variants spliced into the answer set. Most models hallucinate. A few hallucinate with calibrated confidence. The interesting failures are in the second group.

**CanFeather.** ESP32 + MCP2515 mounted to the X179 connector of a 2024 Model Y RWD. Injects forged frames onto the vehicle CAN bus to probe activation gating for region-locked features. Frame definitions are audited by a multi-agent LLM pipeline against the available DBC files before anything goes out on the wire — three independent passes have to agree before a transmission is allowed.

**Vanta Client.** BYOK multi-provider LLM client for iOS. Live on the App Store at $4.99 one-time. OpenAI, Anthropic, Gemini, OpenRouter, plus on-device llama.cpp inference. MCP tool support, persistent memory, RAG over user documents. Swift, no server backend — keys and conversations never leave the device.

**Murmur.** Voice journaling app with an AI companion (*Luna*). STT via Groq's Whisper endpoint, voice via ElevenLabs Conversational AI, backend on Supabase with three edge functions split by failure mode — `therapy`, `enhance`, `safeguard`. iOS 26, Liquid Glass.

**EzeLLM2.** 356M-parameter GPT-style decoder, trained from scratch in PyTorch on a single workstation. Optimization writeup on Medium — gradient accumulation, mixed-precision pitfalls, dataloader bottlenecks, all the one-GPU-from-zero standards and what worked.

---

### Setup

```
GPU         RTX 5090 · 32 GB · Blackwell sm_120 · CUDA 13.x
Inference   vLLM (built from source for sm_120) serving Qwen3.5-27B-AWQ,
            wired into Claude Code for agentic work
Workstation Ubuntu 24.04
Gaming OS   Windows 11 IoT Enterprise LTSC + open-source debloat
Lab         hucvl-ws1 · Hacettepe Computer Vision Laboratory
```

---

### Archive

- **EzeLLM** — predecessor transformer; pretraining notes and weights are up.
- **VigilEye** — social-media user classifier; Reddit primary, Twitter partial.
- **EchoSee** — LLM-driven home assistant; STT, TTS, function calling, modular.
- **Turkish Strings / Turkish Fast Tokenizer** — corpus and BPE tokenizer for a language the big labs underweight.
- **LlamaLike** — pretraining experiment from an earlier model generation.

---

### Elsewhere

[huggingface.co/TerminatorPower](https://huggingface.co/TerminatorPower)

[![streak](https://github-readme-streak-stats.herokuapp.com/?user=EzeLLM&theme=dark&hide_border=true)](https://git.io/streak-stats)
