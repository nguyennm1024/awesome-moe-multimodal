# Awesome-MoE-Multimodal

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A curated list of papers on **Mixture of Experts for Multimodal Intelligence**, maintained to accompany our survey paper.

> **Survey Paper:** *Mixture of Experts for Multimodal Intelligence: A Survey*
> William Nguyen, Dang Nguyen, Hieu Tran
> Aitomatic, Inc. · University of California, Los Angeles · University of Massachusetts Amherst

If you find this repository helpful, please consider citing our survey and giving a star!

---

## News

- **[2026/03]** Full sync with survey v3 — updated all 278 entries, fixed venues/URLs from Semantic Scholar cleanup.
- **[2026/03]** Major update: synced with survey v2 — added 60+ new models from 2025–2026, fixed model categorizations, added audio/3D/unified sections.
- **[2026/03]** Repository created and initial paper collection released.

---

## Citation

```bibtex
@article{nguyen2026moemultimodal,
  title={Mixture of Experts for Multimodal Intelligence: A Survey},
  author={Nguyen, William and Nguyen, Dang and Tran, Hieu},
  journal={arXiv preprint},
  year={2026}
}
```

---

## Table of Contents

- [MoE Foundation Models](#-moe-foundation-models)
- [Architecture Placement](#-architecture-placement)
  - [MoE in Vision Encoders](#moe-in-vision-encoders-s31)
  - [MoE in Cross-Modal Connectors](#moe-in-cross-modal-connectors-s32)
  - [MoE in LLM Backbones](#moe-in-llm-backbones-s33)
  - [MoE in Generation Decoders](#moe-in-generation-decoders-s34)
  - [Full-Stack MoE](#full-stack-moe-s35)
  - [Routing Strategies](#routing-strategies-s36)
- [Multimodal Understanding](#-multimodal-understanding)
  - [Image Understanding](#image-understanding-s41)
  - [Video Understanding](#video-understanding-s42)
  - [Audio-Visual Understanding](#audio-visual-understanding-s43)
  - [3D and Point Cloud Understanding](#3d-and-point-cloud-understanding-s44)
  - [Cross-Modal Retrieval and Alignment](#cross-modal-retrieval-and-alignment-s45)
- [Multimodal Generation](#-multimodal-generation)
  - [Image Generation](#image-generation-s51)
  - [Video Generation](#video-generation-s52)
  - [Audio and Speech Generation](#audio-and-speech-generation-s53)
  - [3D Generation](#3d-generation-s54)
  - [Any-to-Any Generation](#any-to-any-generation-s55)
- [Unified Understanding & Generation](#-unified-understanding--generation)
- [System Optimization](#-system-optimization)
  - [Training Infrastructure](#training-infrastructure)
  - [Inference Optimization](#inference-optimization)
  - [Scaling Laws and Theory](#scaling-laws-and-theory)
- [Domain Applications](#-domain-applications)
  - [Autonomous Driving](#autonomous-driving)
  - [Robotics and Embodied AI](#robotics-and-embodied-ai)
  - [Healthcare and Medical](#healthcare-and-medical)
  - [Speech and Audio Processing](#speech-and-audio-processing)
- [Benchmarks](#-benchmarks)
- [Related Surveys](#-related-surveys)
- [Star History](#-star-history)
- [Contributing](#contributing)

---

## MoE Foundation Models

Base sparse language models that underpin multimodal MoE systems.

| Model | Params (Total / Active) | Experts | Venue | Paper |
|:------|:------------------------|:--------|:------|:------|
| Deep MoE (Eigen) | — | — | arXiv 2014 | [arXiv](https://arxiv.org/abs/1312.4314) |
| Sparsely-Gated MoE (Shazeer) | — | 131,072 | ICLR 2017 | [arXiv](https://arxiv.org/abs/1701.06538) |
| GShard | 600B / — | 2048 | ICLR 2021 | [arXiv](https://arxiv.org/abs/2006.16668) |
| BASE Layers | 110B / — | 128 | ICML 2021 | [arXiv](https://arxiv.org/abs/2103.16716) |
| Hash Layers | 4.5B / — | — | NeurIPS 2021 | [arXiv](https://arxiv.org/abs/2106.04426) |
| Switch Transformer | 1.6T / — | 2048 | JMLR 2022 | [arXiv](https://arxiv.org/abs/2101.03961) |
| ST-MoE | 269B / — | 32 | arXiv 2022 | [arXiv](https://arxiv.org/abs/2202.08906) |
| Expert Choice Routing | 143B / 10B | 64 | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2202.09368) |
| Sparse Upcycling | 26B / — | 32 | ICLR 2023 | [arXiv](https://arxiv.org/abs/2212.05055) |
| MoE Instruction Tuning | 259B / 32B | 64 | ICLR 2024 | [arXiv](https://arxiv.org/abs/2305.14705) |
| Mixtral 8x7B / 8x22B | 47B–141B / 13–39B | 8 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2401.04088) |
| DeepSeekMoE | 145B / 22B | 64+2 | ACL 2024 | [arXiv](https://arxiv.org/abs/2401.06066) |
| DeepSeek-V2 | 236B / 21B | 160+2 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2405.04434) |
| DeepSeek-V3 | 671B / 37B | 256+1 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.19437) |
| JetMoE | 8B / 2B | 8 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2404.07413) |
| OLMoE | 7B / 1B | 64 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2409.02060) |
| OpenMoE | 34B / 6.8B | 32 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2402.01739) |
| Skywork-MoE | 146B / — | 16 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2406.06563) |
| Hunyuan-Large | 389B / 52B | 16+1 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2411.02265) |
| DBRX | 132B / 36B | 16 | Blog 2024 | [Blog](https://www.databricks.com/blog/introducing-dbrx-new-state-art-open-llm) |
| Grok-1 | 314B / — | 8 | Blog 2024 | [GitHub](https://github.com/xai-org/grok-1) |
| Soft MoE | up to 54.1B / — | 128 | ICLR 2024 | [arXiv](https://arxiv.org/abs/2308.00951) |
| Aux-Loss-Free Routing | 3B / — | 64+2 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2408.15664) |
| Mixture of A Million Experts | — / — | 1M | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.04153) |
| Qwen3 235B-A22B | 235B / 22B | 128 | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.09388) |
| GLM-4.5 | 355B / 32B | 160+1 | arXiv 2025 | [arXiv](https://arxiv.org/abs/2508.06471) |
| ReMoE | 5.73B / ~1B | 8 | ICLR 2025 | [arXiv](https://arxiv.org/abs/2412.14711) |
| DirMoE | 185M / — | 8 | ICLR 2026 | [arXiv](https://arxiv.org/abs/2602.09001) |

---

## Architecture Placement

### MoE in Vision Encoders (§3.1)

MoE applied inside the visual encoder (e.g., ViT layers replaced with MoE FFN).

| Model | MoE Location | Params / Active | Venue | Paper |
|:------|:-------------|:----------------|:------|:------|
| V-MoE | ViT FFN layers | 15B / ~2B | NeurIPS 2021 | [arXiv](https://arxiv.org/abs/2106.05974) |
| LIMoE | Shared vision-language encoder | 5.6B / 675M | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2206.02770) |
| M³ViT | Multimodal ViT multi-task MoE | ~86M / — | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2210.14793) |
| SoftMoE | ViT slot-based soft routing | up to 54.1B / — | ICLR 2024 | [arXiv](https://arxiv.org/abs/2308.00951) |
| MoVA | Mixture of vision expert adapters | ~10B / — | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2404.13046) |
| MoNE | Mixture of nested experts for visual tokens | same as baseline / — | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2407.19985) |
| Routers in Vision MoE | Empirical routing study | — / — | TMLR 2024 | [arXiv](https://arxiv.org/abs/2401.15969) |
| LiMoE | LiDAR + image encoder MoE | 85.8M / — | CVPR 2025 | [arXiv](https://arxiv.org/abs/2501.04004) |
### MoE in Cross-Modal Connectors (§3.2)

MoE in the projection/adapter bridging vision encoder and LLM.

| Model | MoE Location | Params / Active | Venue | Paper |
|:------|:-------------|:----------------|:------|:------|
| VLMo | Modality-expert FFN | 562M / 375M | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2111.02358) |
| Omni-SMoLA | Soft MoE low-rank adapters | 5.0B / — | CVPR 2024 | [arXiv](https://arxiv.org/abs/2312.00968) |
| MoCLE | Cluster-conditional LoRA experts | 7.4B / 6.8B | ICLR 2024 | [arXiv](https://arxiv.org/abs/2312.12379) |
| LLaVA-MoLE | Sparse LoRA experts in connector | 7.4B / 6.8B | arXiv 2024 | [arXiv](https://arxiv.org/abs/2401.16160) |
| Mixture of LoRA Experts | Systematic LoRA-MoE framework | ~865M / — | ICLR 2024 | [arXiv](https://arxiv.org/abs/2404.13628) |
| MoAI | Mixture of visual adapters | ~7B / — | ECCV 2024 | [arXiv](https://arxiv.org/abs/2403.07508) |
| CuMo | Co-upcycled encoder+connector MoE | 8.3B / 7.8B | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2405.05949) |
| Awaker2.5-VL | Parameter-efficient LoRA-MoE | 10.8B / — | arXiv 2024 | [arXiv](https://arxiv.org/abs/2411.10669) |
### MoE in LLM Backbones (§3.3)

MoE replacing FFN layers in the language model backbone for multimodal tasks.

| Model | Params / Active | Experts | Routing | Venue | Paper |
|:------|:----------------|:--------|:--------|:------|:------|
| VL-MoE | 5.2B / 1.3B | 32 | Top-2 | EMNLP 2023 | [arXiv](https://arxiv.org/abs/2303.07226) |
| MM1-MoE | 64B / 3B | 64 | Top-2 | ECCV 2024 | [arXiv](https://arxiv.org/abs/2403.09611) |
| Gemini 1.5 | — / — | — | — | arXiv 2024 | [arXiv](https://arxiv.org/abs/2403.05530) |
| DeepSeek-VL2 | 27B / 4.5B | 64+2 | Top-6 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.10302) |
| Aria | 24.9B / 3.9B | 66 | Top-6 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2410.05993) |
| MoE-LLaVA | 5.3B / 3.6B | 4 | Top-2 | TMM 2025 | [arXiv](https://arxiv.org/abs/2401.15947) |
| Uni-MoE | 13–37B / 9–11B | 4–8 | Top-2 | TPAMI 2025 | [arXiv](https://arxiv.org/abs/2405.11273) |
| LLaVA-MoD | 2.2B / 2.0B | 4 | Top-2 | ICLR 2025 | [arXiv](https://arxiv.org/abs/2408.15881) |
| Kimi-VL | 16B / 3.2B | — | — | arXiv 2025 | [arXiv](https://arxiv.org/abs/2504.07491) |
| Qwen3-VL | 30B–235B / 3–22B | 128 | Top-K | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.21631) |
| GLM-4.5V | 106B / 12B | 128+1 | Aux-loss-free | arXiv 2025 | [arXiv](https://arxiv.org/abs/2507.01006) |
| Llama 4 Maverick | 400B / 17B | 128 | Top-1 | Blog 2025 | [Blog](https://ai.meta.com/blog/llama-4-multimodal-intelligence/) |
| ~~AsyMoE~~ (withdrawn) | — / — | — | — | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.12715) |
| SMAR | 47B / 13B | 8 | Soft KL-div modality-aware | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.06406) |
| Yuan3.0 Flash | 40B / 3.7B | 32 | Top-2 | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.01718) |
### MoE in Generation Decoders (§3.4)

MoE in diffusion denoisers or autoregressive decoders.

| Model | Task | Params / Active | Venue | Paper |
|:------|:-----|:----------------|:------|:------|
| eDiff-I | Text-to-Image | ~9B / ~3B | arXiv 2022 | [arXiv](https://arxiv.org/abs/2211.01324) |
| RAPHAEL | Text-to-Image | 3B / — | NeurIPS 2023 | [arXiv](https://arxiv.org/abs/2305.18295) |
| Switch-DiT | Text-to-Image | 36M–749M / — | ECCV 2024 | [arXiv](https://arxiv.org/abs/2403.09176) |
| DiT-MoE | Text-to-Image | 16B / ~3B | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.11633) |
| EC-DIT | Text-to-Image | 97B / 8.3B | ICLR 2025 | [arXiv](https://arxiv.org/abs/2410.02098) |
| CogVideoX | Text-to-Video | 5B / — | ICLR 2025 | [arXiv](https://arxiv.org/abs/2408.06072) |
### Full-Stack MoE (§3.5)

MoE applied across multiple components (encoder + connector + backbone + decoder).

| Model | MoE Components | Params / Active | Venue | Paper |
|:------|:---------------|:----------------|:------|:------|
| MoMa | Early-fusion + modality-expert groups | 7.1B / 1.4B | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.21770) |
| MoME | Vision encoder + LLM backbone | 7B / 7B | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2407.12709) |
| DeepSeek-VL2 | Encoder + backbone | 27B / 4.5B | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.10302) |
| Uni-MoE | Encoder + connector + backbone | 13–37B / 9–11B | TPAMI 2025 | [arXiv](https://arxiv.org/abs/2405.11273) |
### Routing Strategies (§3.6)

Key routing mechanism papers cited in the survey's routing analysis.

| Method | Type | Key Property | Venue | Paper |
|:-------|:-----|:-------------|:------|:------|
| Sparsely-Gated MoE | Top-k (token choice) | Original sparse gating | ICLR 2017 | [arXiv](https://arxiv.org/abs/1701.06538) |
| Hash Routing | Hash / fixed | Deterministic | NeurIPS 2021 | [arXiv](https://arxiv.org/abs/2106.04426) |
| BASE Layers | Linear assignment | Optimal dispatch | ICML 2021 | [arXiv](https://arxiv.org/abs/2103.16716) |
| Switch Transformer | Top-1 (token choice) | Single expert per token | JMLR 2022 | [arXiv](https://arxiv.org/abs/2101.03961) |
| Expert Choice | Expert choice | Perfect load balance | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2202.09368) |
| SoftMoE | Soft / fully differentiable | No discrete assignment | ICLR 2024 | [arXiv](https://arxiv.org/abs/2308.00951) |
| Aux-loss-free | Bias-based balancing | No auxiliary loss | arXiv 2024 | [arXiv](https://arxiv.org/abs/2408.15664) |
| ReMoE | ReLU-based continuous | Fully differentiable | ICLR 2025 | [arXiv](https://arxiv.org/abs/2412.14711) |
| SMAR | Soft modality-aware KL | Preserves language capability | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.06406) |
| IDA-MoE | Input domain-aware | Decoupled routing from task | ACM MM 2025 | [arXiv](https://arxiv.org/abs/2510.16448) |
| CL-MoE Dual-Router | Instance + task routing | Continual VQA | CVPR 2025 | [arXiv](https://arxiv.org/abs/2503.00413) |
| DirMoE | Dirichlet VAE routing | Disentangled selection/weight | ICLR 2026 | [arXiv](https://arxiv.org/abs/2602.09001) |

---

## Multimodal Understanding

### Image Understanding (§4.1)

| Model | Params / Active | MMMU | MMBench | Venue | Paper |
|:------|:----------------|:-----|:--------|:------|:------|
| VLMo | 562M / 375M | — | — | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2111.02358) |
| VL-MoE | 5.2B / 1.3B | — | — | EMNLP 2023 | [arXiv](https://arxiv.org/abs/2303.07226) |
| MoCLE | 7.4B / 6.8B | — | 67.4 | ICLR 2024 | [arXiv](https://arxiv.org/abs/2312.12379) |
| Omni-SMoLA | 5.0B / — | — | — | CVPR 2024 | [arXiv](https://arxiv.org/abs/2312.00968) |
| LLaVA-MoLE | 7.4B / 6.8B | — | 68.5 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2401.16160) |
| Octavius | 14.4B / 13B | — | — | ICLR 2024 | [arXiv](https://arxiv.org/abs/2311.02684) |
| MM1-MoE | 64B / 3B | 38.6 | 70.8 | ECCV 2024 | [arXiv](https://arxiv.org/abs/2403.09611) |
| CuMo | 8.3B / 7.8B | 39.1 | 73.0 | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2405.05949) |
| Aria | 24.9B / 3.9B | 54.9 | 80.3 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2410.05993) |
| Awaker2.5-VL | 10.8B / — | — | 83.7 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2411.10669) |
| DeepSeek-VL2 | 27B / 4.5B | 51.1 | 83.1 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.10302) |
| MoVA | ~10B / — | — | 70.4 | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2404.13046) |
| MoME | 7B / — | — | — | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2407.12709) |
| MoE-LLaVA (Phi-2) | 5.3B / 3.6B | — | 65.2 | TMM 2025 | [arXiv](https://arxiv.org/abs/2401.15947) |
| LLaVA-MoD | 2.2B / 2.0B | — | 68.9 | ICLR 2025 | [arXiv](https://arxiv.org/abs/2408.15881) |
| CL-MoE | 7.2B / — | — | — | CVPR 2025 | [arXiv](https://arxiv.org/abs/2503.00413) |
| SPMTrack | 115M–1.3B / — | — | — | CVPR 2025 | [arXiv](https://arxiv.org/abs/2503.18338) |
| Kimi-VL | 16B / 3.2B | 57.0 | 83.1 | arXiv 2025 | [arXiv](https://arxiv.org/abs/2504.07491) |
| Qwen3-VL-30B-A3B | 30B / 3B | 59.8 | 77.9 | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.21631) |
| Qwen3-VL-235B-A22B | 235B / 22B | **72.9** | **88.3** | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.21631) |
| GLM-4.5V | 106B / 12B | 75.4 | 88.2 | arXiv 2025 | [arXiv](https://arxiv.org/abs/2507.01006) |
| Llama 4 Maverick | 400B / 17B | 73.4 | — | Blog 2025 | [Blog](https://ai.meta.com/blog/llama-4-multimodal-intelligence/) |
| ~~AsyMoE~~ (withdrawn) | — / — | — | — | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.12715) |
| AnyExperts | — / — | 49.11 | 79.73 | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.18314) |
| Yuan3.0 Flash | 40B / 3.7B | — | — | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.01718) |
### Video Understanding (§4.2)

| Model | Key Capability | Venue | Paper |
|:------|:---------------|:------|:------|
| Aria | Image+video, 66 experts | arXiv 2024 | [arXiv](https://arxiv.org/abs/2410.05993) |
| Uni-MoE | Multi-modal video QA | TPAMI 2025 | [arXiv](https://arxiv.org/abs/2405.11273) |
| SPMTrack | Temporal MoE (TMoE) for visual tracking | CVPR 2025 | [arXiv](https://arxiv.org/abs/2503.18338) |
| Qwen3-VL | Long video reasoning up to 256K tokens | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.21631) |
| GLM-4.5V | Video + chain-of-thought MoE reasoning | arXiv 2025 | [arXiv](https://arxiv.org/abs/2507.01006) |
### Audio-Visual Understanding (§4.3)

| Model | Modalities | Key Innovation | Venue | Paper |
|:------|:-----------|:---------------|:------|:------|
| AVMOE | Audio+Video+Text | Unimodal + cross-modal adapter experts | NeurIPS 2024 | [arXiv](https://openreview.net/forum?id=SNmuKbU0am) |
| FuseMoE | Audio+Image+Text (clinical) | Laplace-gated fleximodal fusion | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2402.03226) |
| Flex-MoE | EHR+Image+Text+Time-series | Dual-router for missing modalities | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2410.08245) |
| MMoE | Audio+Video+Text | Multimodal interaction experts (EMNLP) | EMNLP 2024 | [arXiv](https://arxiv.org/abs/2311.09580) |
| EVA-MoE | Audio+Visual speech | Robust AVSR with MoE | arXiv 2024 | [arXiv](https://arxiv.org/abs/2409.12370) |
| MoHAVE | Audio+Video | Hierarchical MoE for AV speech recognition | arXiv 2025 | [arXiv](https://arxiv.org/abs/2502.10447) |
| Llama-SMoP | Speech+Text | Sparse MoE projectors for AVSR | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.14336) |
| Qwen3-Omni | Audio+Image+Video+Text | Omni understanding + generation | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.17765) |
| Massively Multimodal FM | 10+ modalities | Dependency-aware MoE router | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.25678) |
| I2MoE | Multimodal (medical) | Interpretable interaction-aware MoE | ICML 2025 | [arXiv](https://arxiv.org/abs/2505.19190) |
### 3D and Point Cloud Understanding (§4.4)

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| Octavius | Image + 3D point cloud QA | ICLR 2024 | [arXiv](https://arxiv.org/abs/2311.02684) |
| LiMoE | LiDAR + image 3D perception | CVPR 2025 | [arXiv](https://arxiv.org/abs/2501.04004) |
| Point-MoE | 3D semantic segmentation multi-dataset | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.23926) |
| PointMoDE | 3D self-supervised learning | IJCAI 2025 | [arXiv](https://arxiv.org/abs/2410.09886) |
| Uni3D-MoE | Multi-modal 3D scene understanding | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.21079) |
| MoE3D (understanding) | Multi-modal 3D visual grounding | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.22103) |
| 3D-MoE | 3D vision + pose diffusion | arXiv 2025 | [arXiv](https://arxiv.org/abs/2501.16698) |
| M³-JEPA | 3D joint embedding MoE alignment | ICML 2025 | [arXiv](https://arxiv.org/abs/2409.05929) |
| MoME (multi-modal expert fusion) | LiDAR + camera sensor fusion | CVPR 2025 | [arXiv](https://arxiv.org/abs/2503.19776) |
| MP-LLM (brain MRI) | 3D brain MRI VQA | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.25889) |
| EMC² | Edge 3D object detection (LiDAR) | ICCV 2025 | [arXiv](https://arxiv.org/abs/2507.04123) |
| CBDES MoE | BEV 3D perception for autonomous driving | arXiv 2025 | [arXiv](https://arxiv.org/abs/2508.07838) |
### Cross-Modal Retrieval and Alignment (§4.5)

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| MMoE (interaction) | Multimodal sarcasm/humor detection | EMNLP 2024 | [arXiv](https://arxiv.org/abs/2311.09580) |
| M³-JEPA | Cross-modal latent alignment | ICML 2025 | [arXiv](https://arxiv.org/abs/2409.05929) |
| Multi-level MoE | Multimodal entity linking | KDD 2025 | [arXiv](https://arxiv.org/abs/2507.07108) |
| Learning to Route | Per-sample adaptive routing | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.12227) |
| GNN-MoE | Context-aware patch routing | arXiv 2025 | [arXiv](https://arxiv.org/abs/2412.08193) |
| MCMoE | Missing modality action quality assessment | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.17397) |
| HMVLM | Human motion-vision-language via MoE LoRA | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.01463) |
| MM-MoLRE | Multimodal sentiment/emotion MoE | ICME 2025 | [arXiv](https://arxiv.org/abs/2505.14143) |
| MisTERe | Multimodal emotion recognition in conversations | arXiv 2026 | [arXiv](https://arxiv.org/abs/2602.23300) |

---

## Multimodal Generation

### Image Generation (§5.1)

| Model | Params / Active | Experts | Routing | Venue | Paper |
|:------|:----------------|:--------|:--------|:------|:------|
| eDiff-I | ~9B / ~3B | 3 | Timestep-based | arXiv 2022 | [arXiv](https://arxiv.org/abs/2211.01324) |
| RAPHAEL | 3B / — | 6+4 per layer | Space-MoE + Time-MoE | NeurIPS 2023 | [arXiv](https://arxiv.org/abs/2305.18295) |
| Switch-DiT | 36M–749M / — | 3 | Top-2 timestep | ECCV 2024 | [arXiv](https://arxiv.org/abs/2403.09176) |
| DiT-MoE | 16B / ~3B | 8–32 | Top-2 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.11633) |
| MoESD | ~0.9B / — | 3 | Top-1 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.11002) |
| Mixture of Efficient Diffusion Experts | ~400M / — | 2 | Auto interval selection | ECCV 2024 | [arXiv](https://arxiv.org/abs/2409.15557) |
| EC-DIT | 97B / 8.3B | 64 | Expert choice | ICLR 2025 | [arXiv](https://arxiv.org/abs/2410.02098) |
| Dense2MoE | 12B / 5.2B | — | — | ICCV 2025 | [arXiv](https://arxiv.org/abs/2510.09094) |
| DICE | ~16.5B / 3.1B | 16+2 | Parallel diffusion MoE | ICCV 2025 | [arXiv](https://arxiv.org/abs/2411.16786) |
| Expert Race | 2.8B / 0.7B | 32 | Competitive | ICML 2025 | [arXiv](https://arxiv.org/abs/2503.16057) |
| FaceMoGLE | ~12B / — | — | Global + local | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.00428) |
| TimeStep Master | ~860M / — | 8 | Asymmetric timestep LoRA | ICML 2025 | [arXiv](https://arxiv.org/abs/2503.07416) |
| DiffMoE | 2B / 0.5B | 16 | Adaptive capacity | ICLR 2026 | [arXiv](https://arxiv.org/abs/2503.14487) |
| ProMoE | 1.6B / 0.7B | 14 | Prototype-guided | ICLR 2026 | [arXiv](https://arxiv.org/abs/2510.24711) |
### Video Generation (§5.2)

| Model | Task | Key Innovation | Venue | Paper |
|:------|:-----|:---------------|:------|:------|
| CogVideoX | Text-to-Video | Expert transformer DiT | ICLR 2025 | [arXiv](https://arxiv.org/abs/2408.06072) |
| UniVerse-1 | Audio+Video | Expert stitching of video+audio models | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.06155) |
| MoRE (video) | Video generation | Mixture of Residual Experts | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.08840) |
| MoC | Long video generation | Mixture of Contexts (sparse attention) | ICLR 2026 | [arXiv](https://arxiv.org/abs/2508.21058) |
| JavisDiT++ | Joint audio-video | Modality-specific FFN experts | ICLR 2026 | [arXiv](https://arxiv.org/abs/2602.19163) |
### Audio and Speech Generation (§5.3)

| Model | Task | Key Innovation | Venue | Paper |
|:------|:-----|:---------------|:------|:------|
| StyleMoE | Text-to-Speech | Style mixture of experts | NeurIPS-W 2024 | [arXiv](https://arxiv.org/abs/2406.03637) |
| Lightweight TTS MoE | Zero-shot TTS | Mixture of adapters | Interspeech 2024 | [arXiv](https://arxiv.org/abs/2407.01291) |
| MoE-TTS | Description-based TTS | Out-of-domain text understanding MoE | arXiv 2025 | [arXiv](https://arxiv.org/abs/2508.11326) |
| UniMoE-Audio | Speech+Music | Dynamic-capacity MoE, Top-P routing | arXiv 2025 | [arXiv](https://arxiv.org/abs/2510.13344) |
| AudioGenie | Multi-type audio | Training-free multi-agent MoE | ACM MM 2025 | [arXiv](https://arxiv.org/abs/2505.22053) |
| MoST | Speech+Text | Modality-aware MoE (MAMoE) | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.10272) |
| MoE Adapter (Audio LLM) | Audio understanding | Sparse MoE adapters, gradient decoupling | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.02967) |
### 3D Generation (§5.4)

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| 3D-MoE | Text-to-3D + pose diffusion | arXiv 2025 | [arXiv](https://arxiv.org/abs/2501.16698) |
| MoRE (3D) | 3D visual geometry reconstruction | arXiv 2025 | [arXiv](https://arxiv.org/abs/2510.27234) |
| MoE-GS | Dynamic Gaussian splatting | arXiv 2025 | [arXiv](https://arxiv.org/abs/2510.19210) |
| MoE3D (reconstruction) | Feed-forward 3D reconstruction | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.05208) |
### Any-to-Any Generation (§5.5)

| Model | Modalities | Key Innovation | Venue | Paper |
|:------|:-----------|:---------------|:------|:------|
| MoDE | Action+Image (robotics) | Noise-conditioned MoE diffusion policy | ICLR 2025 | [arXiv](https://arxiv.org/abs/2412.12953) |
| UTAMoE | Image+Video+Audio+Text | Task-aware hierarchical MoE | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.03591) |
| Ming-Omni | Image+Video+Audio+Text | Modality-specific routers, omni generation | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.09344) |

---

## Unified Understanding & Generation

Models that handle both understanding and generation in a single MoE architecture.

| Model | Paradigm | Params / Active | Venue | Paper |
|:------|:---------|:----------------|:------|:------|
| MoMa | Early-fusion + modality-expert groups | 7.1B / 1.4B | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.21770) |
| MoME | Dual MoE (vision encoder + LLM) | ~7B / — | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2407.12709) |
| Uni-MoE | Unified 5-modality MoE backbone | 13–37B / 9–11B | TPAMI 2025 | [arXiv](https://arxiv.org/abs/2405.11273) |
| BAGEL | Mixture-of-Transformer-Experts (MoT) | 14B / 7B | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.14683) |
| EMMA | MoE visual encoder for U+G | ~4B / — | arXiv 2025 | [arXiv](https://arxiv.org/abs/2512.04810) |
| UTAMoE | Task-aware hierarchical routing | 3B / — | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.03591) |
| Ming-Omni | Modality-specific routers | — / 2.8B | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.09344) |
| LaViDa-O | Elastic Mixture-of-Transformers | 10.4B / 6.4–10.4B | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.19244) |
| LLaDA-MoE | Sparse MoE diffusion language model | 7B / 1.4B | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.24389) |

---

## System Optimization

### Training Infrastructure

| System | Key Contribution | Venue | Paper |
|:-------|:-----------------|:------|:------|
| FastMoE | Fast MoE training on commodity hardware | arXiv 2021 | [arXiv](https://arxiv.org/abs/2103.13262) |
| DeepSpeed-MoE | ZeRO + expert parallelism + PR-MoE | ICML 2022 | [arXiv](https://arxiv.org/abs/2201.05596) |
| Tutel | Adaptive expert parallelism + pipelining | MLSys 2023 | [arXiv](https://arxiv.org/abs/2206.03382) |
| MegaBlocks | Block-sparse MoE kernels, no token dropping | MLSys 2023 | [arXiv](https://arxiv.org/abs/2211.15841) |
| Scaling Laws Native MM | Scaling laws for native multimodal MoE | ICCV 2025 | [arXiv](https://arxiv.org/abs/2504.07951) |
### Inference Optimization

| Method | Key Technique | Venue | Paper |
|:-------|:--------------|:------|:------|
| Expert Offloading | LRU CPU-GPU expert paging + prefetch | arXiv 2023 | [arXiv](https://arxiv.org/abs/2312.17238) |
| AnyExperts | Budget-aware dynamic routing | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.18314) |
| MoE-Inference-Bench | Comprehensive inference benchmarking | SC'25 2025 | [arXiv](https://arxiv.org/abs/2508.17467) |
| MoE-CAP | Cost-accuracy-performance benchmarking | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.11415) |
| MoDES | Dynamic expert skipping (GMLG) | CVPR 2026 | [arXiv](https://arxiv.org/abs/2511.15690) |
### Scaling Laws and Theory

| Paper | Key Finding | Venue | Paper |
|:------|:------------|:------|:------|
| Joint MoE Scaling Laws | MoE can be memory-efficient with right config | ICML 2025 | [arXiv](https://arxiv.org/abs/2502.05172) |
| Comprehensive MoE Scaling | 446 experiments; optimal activation ratio | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.23678) |
| Greater Leverage Scaling | Compute-optimal granularity and sparsity | arXiv 2025 | [arXiv](https://arxiv.org/abs/2507.17702) |
| Routing Mamba | MoE routing for state space models | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.18145) |
| Learning to Specialize | Joint gating-expert training in decentralized settings | arXiv 2025 | [arXiv](https://arxiv.org/abs/2306.08586) |
| GapEval | Quantifying understanding-generation gap in UMMs | arXiv 2026 | [arXiv](https://arxiv.org/abs/2602.02140) |

---

## Domain Applications

### Autonomous Driving

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| SafePathNet | Safe motion planning with MoE | ICRA 2023 | [arXiv](https://arxiv.org/abs/2211.02131) |
| DriveMoE | Vision-Language-Action MoE for AD | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.16278) |
| ExpertAD | Enhancing AD systems with MoE | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.11740) |
| ARTEMIS | Autoregressive trajectory planning MoE | IEEE RA-L 2025 | [arXiv](https://arxiv.org/abs/2504.19580) |
| STR2 | Generalizing motion planners with MoE | ICRA 2025 | [arXiv](https://arxiv.org/abs/2410.15774) |
| TrajMoE | Scene-adaptive trajectory planning + RL | arXiv 2025 | [arXiv](https://arxiv.org/abs/2512.07135) |
| EMC² | Edge MoE for 3D object detection | ICCV 2025 | [arXiv](https://arxiv.org/abs/2507.04123) |
| CBDES MoE | BEV perception with heterogeneous experts | arXiv 2025 | [arXiv](https://arxiv.org/abs/2508.07838) |
### Robotics and Embodied AI

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| MoDE | Diffusion policy for multi-task manipulation | ICLR 2025 | [arXiv](https://arxiv.org/abs/2412.12953) |
| AdaMoE | Action-specialized VLA MoE | arXiv 2025 | [arXiv](https://arxiv.org/abs/2510.14300) |
| MoE-DP | MoE-enhanced diffusion policy | arXiv 2025 | [arXiv](https://arxiv.org/abs/2511.05007) |
| MoSE | Skill-by-skill MoE embodied learning | arXiv 2025 | [arXiv](https://arxiv.org/abs/2507.07818) |
| MoWM | Mixture-of-World-Models for embodied planning | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.21797) |
| SMP | Skill mixture-of-experts diffusion policy | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.21251) |
| MoE-ACT | Surgical imitation learning MoE | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.21971) |
| DIBM | Diverse skill behavior models with MoE | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.12397) |
| TMoW | Test-time mixture of world models | ICLR 2026 | [arXiv](https://arxiv.org/abs/2601.22647) |
| CogMoE | Cognitive load prediction (EEG/ECG/EDA) | ICLR 2026 | [openreview](https://openreview.net/forum?id=UtbSWdWv0F) |
### Healthcare and Medical

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| FuseMoE | Clinical multimodal fusion (fleximodal) | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2402.03226) |
| Flex-MoE | Healthcare prediction (ADNI, MIMIC-IV) | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2410.08245) |
| MedMoE | Medical vision-language understanding | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.08356) |
| MoE-Health | Robust multimodal healthcare prediction | ACM BCB 2025 | [arXiv](https://arxiv.org/abs/2508.21793) |
| MP-LLM | 3D brain MRI VQA with hierarchical MoE | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.25889) |
| I2MoE | Interpretable interaction-aware MoE (medical) | ICML 2025 | [arXiv](https://arxiv.org/abs/2505.19190) |
### Speech and Audio Processing

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| Multilingual MoE ASR | Multi-lingual teacher with sparse MoE | arXiv 2021 | [arXiv](https://arxiv.org/abs/2112.05820) |
| LR-MoE | Language-routing MoE for code-switching ASR | Interspeech 2023 | [arXiv](https://arxiv.org/abs/2307.05956) |
| Multilingual DistilWhisper | Multi-task speech via language-specific experts | ICASSP 2024 | [arXiv](https://arxiv.org/abs/2311.01070) |
| SC-MoE | Switch Conformer MoE for streaming ASR | Interspeech 2024 | [arXiv](https://arxiv.org/abs/2406.18021) |
| CollabMoE | LID-based collaborative MoE for CS-ASR | arXiv 2024 | [arXiv](https://arxiv.org/abs/2409.02050) |
| Boosting CS ASR MoE | Speech-conditioned LLM + MoE | arXiv 2024 | [arXiv](https://arxiv.org/abs/2409.15905) |
| EVA-MoE | Robust audiovisual ASR MoE | arXiv 2024 | [arXiv](https://arxiv.org/abs/2409.12370) |
| Whisper MixSAE | Unsupervised speaker diarization | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.01963) |
| MoE Deepfake Detection | Speech deepfake detection | arXiv 2024 | [arXiv](https://arxiv.org/abs/2409.16077) |
| JambaTalk | Speech-driven 3D talking head | arXiv 2024 | [arXiv](https://arxiv.org/abs/2408.01627) |
| BLR-MoE | Boosted language-routing MoE ASR | ICASSP 2025 | [arXiv](https://arxiv.org/abs/2501.12602) |
| DLG-MoE | Dynamic language group MoE for CS-ASR | ICASSP 2025 | [arXiv](https://arxiv.org/abs/2407.18581) |
| CAMEL | Cross-attention MoE for CS-ASR | ICASSP 2025 | [arXiv](https://arxiv.org/abs/2412.12760) |
| VersaBand | Song generation with prompt-based MoE | arXiv 2025 | [arXiv](https://arxiv.org/abs/2504.19062) |
| Speaker Diarization MoE | MoE for speaker diarization | arXiv 2025 | [arXiv](https://arxiv.org/abs/2506.14750) |
| SparseMERIT Speech | MoE speech emotion recognition + generation | arXiv 2025 | [arXiv](https://arxiv.org/abs/2509.08470) |

---

## Benchmarks

### Understanding

| Benchmark | Task | Modality | Year | Paper |
|:----------|:-----|:---------|:-----|:------|
| GQA | Compositional VQA | Image+Text | 2019 | [arXiv](https://arxiv.org/abs/1902.09506) |
| TextVQA | OCR-dependent VQA | Image+Text | 2019 | [arXiv](https://arxiv.org/abs/1904.08920) |
| ScienceQA | Multi-modal science QA | Image+Text | 2022 | [arXiv](https://arxiv.org/abs/2209.09513) |
| AVQA | Audio-visual QA | Audio+Video+Text | 2022 | [arXiv](https://arxiv.org/abs/2203.14072) |
| ScanQA | 3D scene question answering | 3D+Text | 2022 | [arXiv](https://arxiv.org/abs/2112.10482) |
| MME | Multi-modal evaluation | Image+Text | 2023 | [arXiv](https://arxiv.org/abs/2306.13394) |
| POPE | Hallucination evaluation | Image+Text | 2023 | [arXiv](https://arxiv.org/abs/2305.10355) |
| Multi3DRefer | 3D spatial grounding | 3D+Text | 2023 | [arXiv](https://arxiv.org/abs/2309.05251) |
| MMMU | Multi-discipline reasoning | Image+Text | 2024 | [arXiv](https://arxiv.org/abs/2311.16502) |
| MMBench | Comprehensive VLM evaluation | Image+Text | 2024 | [arXiv](https://arxiv.org/abs/2307.06281) |
| MMMU-Pro | Robust multi-discipline benchmark | Image+Text | 2024 | [arXiv](https://arxiv.org/abs/2409.02813) |
| SEEDBench | Multi-granularity evaluation | Image+Video+Text | 2024 | [arXiv](https://arxiv.org/abs/2307.16125) |
| MVBench | Comprehensive video understanding | Video+Text | 2024 | [arXiv](https://arxiv.org/abs/2311.17005) |
| AIR-Bench | Audio instruction following | Audio+Text | 2024 | [arXiv](https://arxiv.org/abs/2402.07729) |
| OCRBench | OCR in large multimodal models | Image+Text | 2024 | [arXiv](https://arxiv.org/abs/2305.07895) |
| VideoMME | Video understanding (short/med/long) | Video+Text | 2025 | [arXiv](https://arxiv.org/abs/2405.21075) |
| MMVU | Expert-level video understanding | Video+Text | 2025 | [arXiv](https://arxiv.org/abs/2501.12380) |
### Generation

| Benchmark | Task | Modality | Year | Paper |
|:----------|:-----|:---------|:-----|:------|
| GenEval | Text-to-image compositional eval | Image+Text | 2023 | [arXiv](https://arxiv.org/abs/2310.11513) |
| T2I-CompBench | Compositional text-to-image | Image+Text | 2023 | [arXiv](https://arxiv.org/abs/2307.06350) |
### Unified and Efficiency

| Benchmark | Task | Venue | Paper |
|:----------|:-----|:------|:------|
| MoE-Inference-Bench | MoE inference efficiency evaluation | SC'25 2025 | [arXiv](https://arxiv.org/abs/2508.17467) |
| MoE-CAP | Cost-accuracy-performance of sparse MoE | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.11415) |
| GapEval | Understanding vs. generation gap in UMMs | arXiv 2026 | [arXiv](https://arxiv.org/abs/2602.02140) |

---

## Related Surveys

| Title | Year | Paper |
|:------|:-----|:------|
| A Review of Sparse Expert Models in Deep Learning | 2022 | [arXiv](https://arxiv.org/abs/2209.01667) |
| A Survey on Mixture of Experts in Large Language Models | 2024 | [arXiv](https://arxiv.org/abs/2407.06204) |
| A Survey on Inference Optimization for MoE Models | 2024 | [arXiv](https://arxiv.org/abs/2412.14219) |
| Next Token Prediction Towards Multimodal Intelligence | 2024 | [arXiv](https://arxiv.org/abs/2412.18619) |
| Multi-modal Generative AI: Survey | 2024 | [arXiv](https://arxiv.org/abs/2409.14993) |
| A Comprehensive Survey of Mixture-of-Experts | 2025 | [arXiv](https://arxiv.org/abs/2503.07137) |
| Unified Multimodal Understanding and Generation Models: A Survey | 2025 | [arXiv](https://arxiv.org/abs/2505.02567) |
| Mixture of Experts in Large Language Models | 2025 | [arXiv](https://arxiv.org/abs/2507.11181) |
| Mixture of Experts Models in Vision (survey) | 2025 | [arXiv](https://arxiv.org/abs/2601.15021) |

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=nguyennm1024/Awesome-MoE-Multimodal&type=Date)](https://star-history.com/#nguyennm1024/Awesome-MoE-Multimodal&Date)

---

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to add papers, fix errors, or suggest improvements.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
