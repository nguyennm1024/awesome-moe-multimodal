# 🔥 Awesome-MoE-Multimodal

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A curated list of papers on **Mixture of Experts for Multimodal Intelligence**, maintained to accompany our survey paper.

> **Survey Paper:** *Mixture of Experts for Multimodal Intelligence: A Survey*
> William Nguyen, Dang Nguyen, Hieu Tran
> Aitomatic, Inc. · University of California, Los Angeles · University of Massachusetts Amherst

If you find this repository helpful, please consider citing our survey and giving a ⭐!

---

## 📌 News

- **[2026/03]** Major update: synced with survey v2 — added 60+ new models from 2025–2026, fixed model categorizations, added audio/3D/unified sections.
- **[2026/03]** Repository created and initial paper collection released.

---

## 📑 Citation

```bibtex
@article{nguyen2026moemultimodal,
  title={Mixture of Experts for Multimodal Intelligence: A Survey},
  author={Nguyen, William and Nguyen, Dang and Tran, Hieu},
  journal={arXiv preprint},
  year={2026}
}
```

---

## 📋 Table of Contents

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
  - [3D Understanding](#3d-understanding-s44)
- [Multimodal Generation](#-multimodal-generation)
  - [Image Generation](#image-generation-s51)
  - [Video Generation](#video-generation-s52)
  - [Audio Generation](#audio-generation-s53)
  - [3D Generation](#3d-generation-s54)
  - [Any-to-Any Generation](#any-to-any-generation-s55)
- [Unified Understanding & Generation](#-unified-understanding--generation)
- [System Optimization](#-system-optimization)
- [Benchmarks](#-benchmarks)
- [Related Surveys](#-related-surveys)
- [Star History](#-star-history)
- [Contributing](#contributing)

---

## 🏗 MoE Foundation Models

Base sparse language models that underpin multimodal MoE systems.

| Model | Params (Total / Active) | Experts | Venue | Paper |
|:------|:------------------------|:--------|:------|:------|
| GShard | 600B / — | 2048 | ICLR 2021 | [arXiv](https://arxiv.org/abs/2006.16668) |
| Switch Transformer | 1.6T / — | 2048 | JMLR 2022 | [arXiv](https://arxiv.org/abs/2101.03961) |
| ST-MoE | — / — | — | — | [arXiv](https://arxiv.org/abs/2202.08906) |
| Mixtral 8×7B | 47B / 13B | 8 | — | [arXiv](https://arxiv.org/abs/2401.04088) |
| Mixtral 8×22B | 141B / 39B | 8 | — | [arXiv](https://arxiv.org/abs/2401.04088) |
| DeepSeekMoE | 145B / 22B | 64+2 | ACL 2024 | [arXiv](https://arxiv.org/abs/2401.06066) |
| DeepSeek-V2 | 236B / 21B | 160+2 | — | [arXiv](https://arxiv.org/abs/2405.04434) |
| DeepSeek-V3 | 671B / 37B | 256+1 | — | [arXiv](https://arxiv.org/abs/2412.19437) |
| Qwen-MoE | 14.3B / 2.7B | 60+4 | — | [GitHub](https://github.com/QwenLM/Qwen) |
| DBRX | 132B / 36B | 16 | — | [Blog](https://www.databricks.com/blog/introducing-dbrx-new-state-art-open-llm) |
| Qwen3-235B-A22B | 235B / 22B | 128 | — | [arXiv](https://arxiv.org/abs/2505.09388) |
| Llama 4 Scout | 109B / 17B | 16 | — | [Blog](https://ai.meta.com/blog/llama-4-multimodal-intelligence/) |
| Llama 4 Maverick | 400B / 17B | 128 | — | [Blog](https://ai.meta.com/blog/llama-4-multimodal-intelligence/) |
| GLM-4.5 | 355B / 32B | — | — | [arXiv](https://arxiv.org/abs/2507.10652) |
| OLMoE | 7B / 1B | 64 | — | [arXiv](https://arxiv.org/abs/2409.02060) |
| JetMoE | 8B / 2B | 8 | — | [arXiv](https://arxiv.org/abs/2404.07413) |

---

## 🧱 Architecture Placement

### MoE in Vision Encoders (§3.1)

MoE applied inside the visual encoder (e.g., ViT layers replaced with MoE FFN).

| Model | MoE Location | Params / Active | Venue | Paper |
|:------|:-------------|:----------------|:------|:------|
| V-MoE | ViT FFN layers | 15B / ~2B | NeurIPS 2021 | [arXiv](https://arxiv.org/abs/2106.05974) |
| LIMoE | Shared vision-language encoder | — / — | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2206.02770) |
| SoftMoE | ViT slot-based soft routing | — / — | ICLR 2024 | [arXiv](https://arxiv.org/abs/2308.00951) |
| M³ViT | Multimodal ViT with MoE | — / — | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2210.14358) |
| MoVA | Vision expert adapter | — / — | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2404.13046) |
| LiMoE | LiDAR+image encoder MoE | — / — | CVPR 2025 | — |

### MoE in Cross-Modal Connectors (§3.2)

MoE in the projection/adapter bridging vision encoder and LLM.

| Model | MoE Location | Params / Active | Venue | Paper |
|:------|:-------------|:----------------|:------|:------|
| VLMo | Modality-expert FFN | 562M / 375M | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2111.02358) |
| MoE-LLaVA | MLP connector MoE | 5.3B / 3.6B | TMM 2025 | [arXiv](https://arxiv.org/abs/2401.15947) |
| MoCLE | Cluster-conditional LoRA experts | 7.4B / 6.8B | ICLR 2024 | [arXiv](https://arxiv.org/abs/2312.12379) |
| Omni-SMoLA | Soft MoE LoRA adapter | 5.0B / — | CVPR 2024 | [arXiv](https://arxiv.org/abs/2312.00968) |
| LLaVA-MoLE | Sparse LoRA experts | — / — | arXiv 2024 | [arXiv](https://arxiv.org/abs/2401.16160) |
| MoAI | Mixture of visual adapters | — / — | CVPR 2024 | — |
| CuMo | Co-upcycled encoder+connector MoE | 8.3B / 7.8B | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2405.05949) |

### MoE in LLM Backbones (§3.3)

MoE replacing FFN layers in the language model backbone for multimodal tasks.

| Model | Params / Active | Experts | Routing | Venue | Paper |
|:------|:----------------|:--------|:--------|:------|:------|
| DeepSeek-VL2 | 27B / 4.5B | 64+2 | Top-6 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.10302) |
| Aria | 25.3B / 3.9B | 66 | Top-6 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2410.05993) |
| Gemini 1.5 | — / — | — | — | arXiv 2024 | [arXiv](https://arxiv.org/abs/2403.05530) |
| MM1-MoE | 64B / 3B | 64 | Top-2 | ECCV 2024 | [arXiv](https://arxiv.org/abs/2403.09611) |
| Uni-MoE | 13–37B / 9–11B | 4–8 | Top-2 | TPAMI 2025 | [arXiv](https://arxiv.org/abs/2405.11273) |
| Kimi-VL | 16B / 2.8B | 384 | — | arXiv 2025 | — |
| Qwen3-VL-30B | 30B / 3B | — | — | arXiv 2025 | — |
| Qwen3-VL-235B | 235B / 22B | 128 | — | arXiv 2025 | — |
| GLM-4.5V | 106B / 12B | — | — | arXiv 2025 | — |
| Llama 4 Maverick | 400B / 17B | 128 | — | Blog 2025 | — |

### MoE in Generation Decoders (§3.4)

MoE in diffusion denoisers or autoregressive decoders (no LLM backbone).

| Model | Task | Params / Active | Venue | Paper |
|:------|:-----|:----------------|:------|:------|
| eDiff-I | Text-to-Image | ~9B / ~3B | arXiv 2022 | [arXiv](https://arxiv.org/abs/2211.01324) |
| RAPHAEL | Text-to-Image | — / — | NeurIPS 2023 | [arXiv](https://arxiv.org/abs/2305.18295) |
| DiT-MoE | Text-to-Image | 16B / ~3B | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.11633) |
| EC-DIT | Text-to-Image | 97B / — | ICLR 2025 | [arXiv](https://arxiv.org/abs/2410.02098) |
| CogVideoX | Text-to-Video | — / — | ICLR 2025 | [arXiv](https://arxiv.org/abs/2408.06072) |

### Full-Stack MoE (§3.5)

MoE applied across multiple components (encoder + connector + backbone + decoder).

| Model | Components | Params / Active | Venue | Paper |
|:------|:-----------|:----------------|:------|:------|
| MoMa | Early-fusion full-stack | — / — | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.21770) |
| Uni-MoE | Multi-component | 13–37B / 9–11B | TPAMI 2025 | [arXiv](https://arxiv.org/abs/2405.11273) |
| DeepSeek-VL2 | Encoder + backbone | 27B / 4.5B | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.10302) |
| MoME | Encoder + backbone | 7B / 7B | NeurIPS 2024 | — |

### Routing Strategies (§3.6)

Key routing mechanism papers.

| Method | Type | Key Property | Venue | Paper |
|:-------|:-----|:-------------|:------|:------|
| Sparsely-Gated MoE | Top-k (token choice) | Original sparse gating | ICLR 2017 | [arXiv](https://arxiv.org/abs/1701.06538) |
| Switch Transformer | Top-1 (token choice) | Single expert per token | JMLR 2022 | [arXiv](https://arxiv.org/abs/2101.03961) |
| Expert Choice | Expert choice | Perfect load balance | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2202.09368) |
| SoftMoE | Soft / fully differentiable | No discrete assignment | ICLR 2024 | [arXiv](https://arxiv.org/abs/2308.00951) |
| Hash Routing | Hash / fixed | Deterministic | EMNLP 2021 | [arXiv](https://arxiv.org/abs/2106.04426) |
| Aux-loss-free | Bias-based balancing | No auxiliary loss | arXiv 2024 | — |
| ReMoE | ReLU-based continuous | Fully differentiable | arXiv 2025 | — |
| DirMoE | Dirichlet VAE routing | Disentangled selection/weight | arXiv 2026 | — |

---

## 🔍 Multimodal Understanding

### Image Understanding (§4.1)

| Model | Params / Active | MMMU | MMBench | Venue | Paper |
|:------|:----------------|:-----|:--------|:------|:------|
| VLMo | 562M / 375M | — | — | NeurIPS 2022 | [arXiv](https://arxiv.org/abs/2111.02358) |
| VL-MoE | 5.2B / 1.3B | — | — | EMNLP 2023 | — |
| MoE-LLaVA (Phi-2) | 5.3B / 3.6B | — | 65.2 | TMM 2025 | [arXiv](https://arxiv.org/abs/2401.15947) |
| MoCLE | 7.4B / 6.8B | — | 67.4 | ICLR 2024 | [arXiv](https://arxiv.org/abs/2312.12379) |
| Omni-SMoLA | 5.0B / — | — | — | CVPR 2024 | [arXiv](https://arxiv.org/abs/2312.00968) |
| LLaVA-MoLE | 7.4B / 6.8B | — | 68.5 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2401.16160) |
| CuMo | 8.3B / 7.8B | 39.1 | 73.0 | NeurIPS 2024 | [arXiv](https://arxiv.org/abs/2405.05949) |
| MoME | 7.0B / 7.0B | — | — | NeurIPS 2024 | — |
| Octavius | 14.4B / 13B | — | — | ICLR 2024 | — |
| MM1-MoE | 64B / 3B | 38.6 | 70.8 | ECCV 2024 | [arXiv](https://arxiv.org/abs/2403.09611) |
| Aria | 25.3B / 3.9B | 54.9 | 80.3 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2410.05993) |
| Awaker2.5-VL | 10.8B / — | — | 83.7 | arXiv 2024 | — |
| DeepSeek-VL2 | 27B / 4.5B | 51.1 | 83.1 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.10302) |
| LLaVA-MoD | 2.2B / 2.0B | — | 68.9 | ICLR 2025 | — |
| CL-MoE | 7.2B / — | — | — | CVPR 2025 | — |
| Kimi-VL | 16B / 2.8B | 57.0 | 83.1 | arXiv 2025 | — |
| Qwen3-VL-30B-A3B | 30B / 3B | 59.8 | 77.9 | arXiv 2025 | — |
| Qwen3-VL-235B-A22B | 235B / 22B | **72.9** | **88.3** | arXiv 2025 | — |
| Llama 4 Maverick | 400B / 17B | 73.4 | — | Blog 2025 | — |
| GLM-4.5V | 106B / 12B | 75.4 | 88.2 | arXiv 2025 | — |
| Yuan3.0 Flash | 40B / 3.7B | — | — | arXiv 2026 | — |

### Video Understanding (§4.2)

| Model | Key Capability | Venue | Paper |
|:------|:---------------|:------|:------|
| Aria | Image+video, 66 experts | arXiv 2024 | [arXiv](https://arxiv.org/abs/2410.05993) |
| Uni-MoE | Multi-modal video QA | TPAMI 2025 | [arXiv](https://arxiv.org/abs/2405.11273) |
| Qwen3-VL | Long video reasoning | arXiv 2025 | — |
| GLM-4.5V | Video+chain-of-thought | arXiv 2025 | — |
| SPMTrack | Temporal MoE (TMoE) for tracking | arXiv 2025 | — |

### Audio-Visual Understanding (§4.3)

| Model | Modalities | Key Innovation | Venue | Paper |
|:------|:-----------|:---------------|:------|:------|
| MoHAVE | Audio+Video | MoE fusion of AV streams | arXiv 2025 | [arXiv](https://arxiv.org/abs/2502.10447) |
| FuseMoE | Audio+Image+Text | Laplace gating for multimodal fusion | NeurIPS 2024 | — |
| Flex-MoE | EHR+Image+Text+Time-series | Flexible missing-modality MoE | NeurIPS 2024 | — |
| Llama-SMoP | Speech+Text | Sparse MoE of prompts | arXiv 2025 | [arXiv](https://arxiv.org/abs/2505.14336) |
| Qwen3-Omni | Audio+Image+Video+Text | Omni understanding | arXiv 2025 | — |

### 3D Understanding (§4.4)

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| LiMoE | LiDAR+image 3D perception | CVPR 2025 | — |
| I2MoE | Image-to-3D scene understanding | arXiv 2025 | — |
| Octavius | Image+3D QA | ICLR 2024 | — |
| M³-JEPA | 3D joint embedding MoE | ICML 2025 | — |
| MMoE | Multi-modal interaction experts for 3D | EMNLP 2024 | — |

---

## 🎨 Multimodal Generation

### Image Generation (§5.1)

| Model | Params / Active | Experts | Routing | Venue | Paper |
|:------|:----------------|:--------|:--------|:------|:------|
| eDiff-I | ~9B / ~3B | 3 | Timestep-based | arXiv 2022 | [arXiv](https://arxiv.org/abs/2211.01324) |
| RAPHAEL | — / — | 6+4 | Top-1 (space+text) | NeurIPS 2023 | [arXiv](https://arxiv.org/abs/2305.18295) |
| Switch-DiT | — / — | — | — | ECCV 2024 | — |
| DiT-MoE | 16B / ~3B | 8–32 | Top-2 | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.11633) |
| MoESD | — / — | 3 | Top-1 | arXiv 2024 | — |
| EC-DIT | 97B / — | — | Expert choice | ICLR 2025 | [arXiv](https://arxiv.org/abs/2410.02098) |
| Dense2MoE | 12B / 5.2B | — | — | ICCV 2025 | [arXiv](https://arxiv.org/abs/2510.09094) |
| Expert Race | — / — | — | Competitive | ICML 2025 | — |
| DiffMoE | — / — | — | Adaptive capacity | ICLR 2026 | — |
| ProMoE | — / — | 14 | Prompt-guided | ICLR 2026 | — |

### Video Generation (§5.2)

| Model | Task | Key Innovation | Venue | Paper |
|:------|:-----|:---------------|:------|:------|
| CogVideoX | Text-to-Video | Expert transformer DiT | ICLR 2025 | [arXiv](https://arxiv.org/abs/2408.06072) |
| JavisDiT++ | Text-to-Video | Multi-scale spatial-temporal MoE | ICLR 2026 | — |
| UniVerse-1 | Text-to-Video | Universe video MoE | arXiv 2025 | — |
| MoRE | Video generation | Mixture of Residual Experts | arXiv 2025 | — |
| MoC | Video generation | Mixture of Contexts (sparse attention) | ICLR 2026 | — |

### Audio Generation (§5.3)

| Model | Task | Key Innovation | Venue | Paper |
|:------|:-----|:---------------|:------|:------|
| StyleMoE | Text-to-Speech | Style mixture of experts | arXiv 2024 | [arXiv](https://arxiv.org/abs/2406.03637) |
| AudioGenie | Text-to-Audio | Multi-expert audio generation | ACM MM 2025 | — |
| MoST | Speech+Text | Modality-aware MoE for ASR/TTS | arXiv 2026 | [arXiv](https://arxiv.org/abs/2601.10272) |

### 3D Generation (§5.4)

| Model | Task | Venue | Paper |
|:------|:-----|:------|:------|
| 3D-MoE | Text-to-3D / 3D-QA | arXiv 2025 | — |
| MoE-GS | 3D Gaussian Splatting | arXiv 2025 | — |

### Any-to-Any Generation (§5.5)

| Model | Modalities | Key Innovation | Venue | Paper |
|:------|:-----------|:---------------|:------|:------|
| MoDE | Action+Image | MoE diffusion for robot policies | ICLR 2025 | — |
| Ming-Omni | Image+Video+Audio+Text | Fully unified omni generation | arXiv 2025 | — |
| UTAMoE | Image+Video+Audio+Text | Unified token-aligned MoE | arXiv 2025 | — |

---

## 🔗 Unified Understanding & Generation

Models that handle both understanding and generation in a single MoE architecture.

| Model | Paradigm | Params / Active | Venue | Paper |
|:------|:---------|:----------------|:------|:------|
| MoMa | Shared backbone + modality MoE | — / — | arXiv 2024 | [arXiv](https://arxiv.org/abs/2407.21770) |
| Uni-MoE | Decoupled encoding + MoE backbone | 13–37B / 9–11B | TPAMI 2025 | [arXiv](https://arxiv.org/abs/2405.11273) |
| DeepSeek-VL2 | Decoupled encoding + MoE backbone | 27B / 4.5B | arXiv 2024 | [arXiv](https://arxiv.org/abs/2412.10302) |
| BAGEL | Decoupled encoding + MoE backbone | — / — | arXiv 2025 | — |
| Ming-Omni | Fully unified autoregressive MoE | — / — | arXiv 2025 | — |
| UTAMoE | Fully unified autoregressive MoE | — / — | arXiv 2025 | — |
| LaViDa | Language + Vision diffusion MoE | — / — | arXiv 2025 | — |
| EMMA | End-to-end multimodal MoE agent | — / — | arXiv 2025 | — |

---

## ⚙️ System Optimization

### Training Infrastructure

| System | Key Contribution | Venue | Paper |
|:-------|:-----------------|:------|:------|
| FastMoE | Fast MoE training on commodity hardware | arXiv 2021 | [arXiv](https://arxiv.org/abs/2103.13262) |
| DeepSpeed-MoE | ZeRO + expert parallelism | ICML 2022 | — |
| Tutel | Adaptive expert parallelism | MLSys 2023 | — |
| MegaBlocks | Efficient sparse MoE kernels | MLSys 2023 | — |

### Inference Optimization

| Method | Key Technique | Venue | Paper |
|:-------|:--------------|:------|:------|
| Expert Offloading | CPU-GPU expert paging | arXiv 2023 | [arXiv](https://arxiv.org/abs/2312.17238) |
| Pre-gated MoE | Speculation-based inference | — | — |
| Expert Caching | Reuse hot experts across steps | — | — |

---

## 📊 Benchmarks

### Understanding

| Benchmark | Task | Modality | Link |
|:----------|:-----|:---------|:-----|
| MMMU | Multi-discipline reasoning | Image+Text | [Link](https://mmmu-benchmark.github.io/) |
| MMBench | Comprehensive VLM evaluation | Image+Text | [Link](https://opencompass.org.cn/leaderboard-multimodal) |
| GQA | Compositional VQA | Image+Text | [Link](https://cs.stanford.edu/people/doersch/gqa/) |
| TextVQA | OCR-dependent VQA | Image+Text | [Link](https://textvqa.org/) |
| SEEDBench | Multi-granularity evaluation | Image+Video+Text | [Link](https://github.com/AILab-CVC/SEED-Bench) |
| VideoMME | Video understanding | Video+Text | [Link](https://video-mme.github.io/) |
| MME | Multi-modal evaluation | Image+Text | [Link](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models/tree/Evaluation) |
| ScanQA | 3D scene question answering | 3D+Text | [Link](https://github.com/ATR-DBI/ScanQA) |
| AIR-Bench | Audio instruction following | Audio+Text | [Link](https://github.com/OFA-Sys/AIR-Bench) |
| AVQA | Audio-visual QA | Audio+Video+Text | [Link](https://mn.cs.tsinghua.edu.cn/avqa/) |

### Generation

| Benchmark | Task | Modality | Link |
|:----------|:-----|:---------|:-----|
| GenEval | Text-to-image compositional evaluation | Image+Text | [Link](https://github.com/djghosh13/geneval) |
| FID / CLIP Score | Image quality & alignment | Image+Text | — |
| VBench | Video generation quality | Video+Text | [Link](https://github.com/Vchitect/VBench) |
| FVD | Video fidelity | Video | — |

### Unified

| Benchmark | Task | Modality | Link |
|:----------|:-----|:---------|:-----|
| SEED-Bench-2 | Unified U&G evaluation | Image+Text | [Link](https://github.com/AILab-CVC/SEED-Bench) |
| MM-Vet | Integrated multimodal capabilities | Image+Text | [Link](https://github.com/yuweihao/MM-Vet) |

---

## 📚 Related Surveys

| Title | Year | Paper |
|:------|:-----|:------|
| A Survey on Mixture of Experts in Large Language Models | 2024 | [arXiv](https://arxiv.org/abs/2407.06204) |
| A Comprehensive Survey of Mixture-of-Experts | 2025 | [arXiv](https://arxiv.org/abs/2503.07137) |
| Unified Multimodal Understanding and Generation Models: A Survey | 2025 | [arXiv](https://arxiv.org/abs/2505.02567) |
| A Survey on Inference Optimization for MoE Models | 2024 | [arXiv](https://arxiv.org/abs/2412.14219) |
| Mixture-of-Experts Models in Vision | 2025 | [arXiv](https://arxiv.org/abs/2601.15021) |

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=nguyennm1024/Awesome-MoE-Multimodal&type=Date)](https://star-history.com/#nguyennm1024/Awesome-MoE-Multimodal&Date)

---

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to add papers, fix errors, or suggest improvements.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
