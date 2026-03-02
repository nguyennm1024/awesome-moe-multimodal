# 🔥 Awesome-MoE-Multimodal

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A curated list of papers on **Mixture of Experts for Multimodal Understanding and Generation**.

If you find this repository helpful, please consider citing our survey and giving a ⭐!

---

## 📌 News

- **[2026/03]** Repository created and initial paper collection released.
- **[2026/03]** Added 60+ papers covering MoE in vision encoders, cross-modal connectors, LLM backbones, generation decoders, and full-stack designs.

---

## 📑 Citation

If you find this work useful, please cite our survey:

```bibtex
@article{moe_multimodal_survey_2026,
  title={A Survey on Mixture of Experts for Multimodal Understanding and Generation},
  year={2026}
}
```

---

## 📋 Table of Contents

- [Papers by MoE Placement](#papers-by-moe-placement)
  - [MoE in Vision Encoders](#moe-in-vision-encoders)
  - [MoE in Cross-Modal Connectors](#moe-in-cross-modal-connectors)
  - [MoE in LLM Backbones](#moe-in-llm-backbones)
  - [MoE in Generation Decoders](#moe-in-generation-decoders)
  - [Full-Stack / Unified MoE](#full-stack--unified-moe)
- [Papers by Task](#papers-by-task)
  - [Multimodal Understanding](#multimodal-understanding)
  - [Multimodal Generation](#multimodal-generation)
  - [Unified Understanding & Generation](#unified-understanding--generation)
- [Papers by Modality](#papers-by-modality)
  - [Image + Text](#image--text)
  - [Video + Text](#video--text)
  - [Audio + Text](#audio--text)
  - [3D + Text](#3d--text)
- [MoE Foundation Models](#moe-foundation-models)
- [Datasets & Benchmarks](#datasets--benchmarks)
- [Related Surveys](#related-surveys)
- [Star History](#-star-history)
- [Contributing](#contributing)

---

## Papers by MoE Placement

### MoE in Vision Encoders

Models that integrate Mixture of Experts directly into the visual backbone (e.g., ViT with MoE layers).

| Title | Model | Date | Params | Active | Code | Venue |
|:------|:------|:-----|:-------|:-------|:-----|:------|
| [Scaling Vision with Sparse Mixture of Experts](https://arxiv.org/abs/2106.05974) | V-MoE | 2021/06 | 15B | ~3.7B | - | NeurIPS 2022 |
| [Multimodal Contrastive Learning with LIMoE: the Language-Image Mixture of Experts](https://arxiv.org/abs/2206.02770) | LIMoE | 2022/06 | - | - | [Code](https://github.com/kyegomez/LIMoE) | NeurIPS 2022 |
| [From Sparse to Soft Mixtures of Experts](https://arxiv.org/abs/2308.00951) | Soft MoE | 2023/08 | - | - | [Code](https://github.com/fkodom/soft-mixture-of-experts) | ICLR 2024 |
| [Mobile V-MoEs: Scaling Down Vision Transformers via Sparse Mixture-of-Experts](https://arxiv.org/abs/2309.04354) | Mobile V-MoE | 2023/09 | - | 54M FLOPs | - | - |
| [Sparse Upcycling: Training Mixture-of-Experts from Dense Checkpoints](https://arxiv.org/abs/2212.05055) | Sparse Upcycling | 2022/12 | - | - | - | ICLR 2023 |
| [ViMoE: An Empirical Study of Designing Vision Mixture-of-Experts](https://arxiv.org/abs/2410.15732) | ViMoE | 2024/10 | - | - | - | - |
| [CuMo: Scaling Multimodal LLM with Co-Upcycled Mixture-of-Experts](https://arxiv.org/abs/2405.05949) | CuMo | 2024/05 | - | - | [Code](https://github.com/SHI-Labs/CuMo) | NeurIPS 2024 |
| [MoVA: Adapting Mixture of Vision Experts to Multimodal Context](https://arxiv.org/abs/2404.13046) | MoVA | 2024/04 | - | - | [Code](https://github.com/TempleX98/MoVA) | NeurIPS 2024 |

### MoE in Cross-Modal Connectors

Models that place MoE in the adapter/connector between vision encoder and LLM backbone.

| Title | Model | Date | Params | Active | Code | Venue |
|:------|:------|:-----|:-------|:-------|:-----|:------|
| [VLMo: Unified Vision-Language Pre-Training with Mixture-of-Modality-Experts](https://arxiv.org/abs/2111.02358) | VLMo | 2021/11 | - | - | [Code](https://github.com/microsoft/unilm/tree/master/vlmo) | NeurIPS 2022 |
| [Omni-SMoLA: Boosting Generalist Multimodal Models with Soft Mixture of Low-rank Experts](https://arxiv.org/abs/2312.00968) | Omni-SMoLA | 2023/12 | ~50-100B | - | - | CVPR 2024 |
| [Mixture of Cluster-conditional LoRA Experts for Vision-language Instruction Tuning](https://arxiv.org/abs/2312.12379) | MoCLE | 2023/12 | - | - | [Code](https://github.com/gyhdog99/MoCLE) | - |
| [LLaVA-MoLE: Sparse Mixture of LoRA Experts for Mitigating Data Conflicts in Instruction Finetuning MLLMs](https://arxiv.org/abs/2401.16160) | LLaVA-MoLE | 2024/01 | - | - | [Code](https://github.com/forwchen/LLaVA-MoLE) | - |
| [CuMo: Scaling Multimodal LLM with Co-Upcycled Mixture-of-Experts](https://arxiv.org/abs/2405.05949) | CuMo | 2024/05 | - | - | [Code](https://github.com/SHI-Labs/CuMo) | NeurIPS 2024 |

### MoE in LLM Backbones

Models that use MoE layers in the language model backbone for multimodal tasks.

| Title | Model | Date | Params | Active | Code | Venue |
|:------|:------|:-----|:-------|:-------|:-----|:------|
| [MoE-LLaVA: Mixture of Experts for Large Vision-Language Models](https://arxiv.org/abs/2401.15947) | MoE-LLaVA | 2024/01 | 6.7B | ~3B | [Code](https://github.com/PKU-YuanGroup/MoE-LLaVA) | TMM 2025 |
| [DeepSeek-VL2: Mixture-of-Experts Vision-Language Models for Advanced Multimodal Understanding](https://arxiv.org/abs/2412.10302) | DeepSeek-VL2 | 2024/12 | 27B | 4.5B | [Code](https://github.com/deepseek-ai/DeepSeek-VL2) | - |
| [MM1: Methods, Analysis & Insights from Multimodal LLM Pre-training](https://arxiv.org/abs/2403.09611) | MM1 | 2024/03 | 64B (MoE) | - | - | ECCV 2024 |
| [Gemini: A Family of Highly Capable Multimodal Models](https://arxiv.org/abs/2312.11805) | Gemini | 2023/12 | - | - | - | - |
| [Gemini 1.5: Unlocking multimodal understanding across millions of tokens of context](https://arxiv.org/abs/2403.05530) | Gemini 1.5 | 2024/03 | - | - | - | - |
| [Uni-MoE: Scaling Unified Multimodal LLMs with Mixture of Experts](https://arxiv.org/abs/2405.11273) | Uni-MoE | 2024/05 | - | - | [Code](https://uni-moe.github.io/) | - |
| [MoME: Mixture of Multimodal Experts for Generalist Multimodal Large Language Models](https://arxiv.org/abs/2407.12709) | MoME | 2024/07 | - | - | - | NeurIPS 2024 |
| [MoMa: Efficient Early-Fusion Pre-training with Mixture of Modality-Aware Experts](https://arxiv.org/abs/2407.21770) | MoMa | 2024/07 | - | - | - | - |
| [Mini-Gemini: Mining the Potential of Multi-modality Vision Language Models](https://arxiv.org/abs/2403.18814) | Mini-Gemini | 2024/03 | 2B-34B | - | [Code](https://github.com/JIA-Lab-research/MGM) | - |

### MoE in Generation Decoders

Models that apply MoE in the decoder/diffusion model for multimodal generation tasks.

| Title | Model | Date | Params | Active | Code | Venue |
|:------|:------|:-----|:-------|:-------|:-----|:------|
| [eDiff-I: Text-to-Image Diffusion Models with an Ensemble of Expert Denoisers](https://arxiv.org/abs/2211.01324) | eDiff-I | 2022/11 | - | - | - | CVPR 2023 |
| [RAPHAEL: Text-to-Image Generation via Large Mixture of Diffusion Paths](https://arxiv.org/abs/2305.18295) | RAPHAEL | 2023/05 | 3B | - | - | NeurIPS 2023 |
| [Scaling Diffusion Transformers to 16 Billion Parameters](https://arxiv.org/abs/2407.11633) | DiT-MoE | 2024/07 | 16.5B | 3.1B | [Code](https://github.com/feizc/DiT-MoE) | - |
| [EC-DIT: Scaling Diffusion Transformers with Adaptive Expert-Choice Routing](https://arxiv.org/abs/2410.02098) | EC-DIT | 2024/10 | 97B | - | - | - |
| [CogVideoX: Text-to-Video Diffusion Models with An Expert Transformer](https://arxiv.org/abs/2408.06072) | CogVideoX | 2024/08 | - | - | [Code](https://github.com/THUDM/CogVideo) | ICLR 2025 |
| [Dense2MoE: Restructuring Diffusion Transformer to MoE for Efficient Text-to-Image Generation](https://arxiv.org/abs/2510.09094) | FLUX.1-MoE | 2025/10 | 12B | 5.2B | - | - |
| [Style Mixture of Experts for Expressive Text-To-Speech Synthesis](https://arxiv.org/abs/2406.03637) | StyleMoE | 2024/06 | - | - | - | - |

### Full-Stack / Unified MoE

Models that integrate MoE across multiple components or support both understanding and generation in a unified framework.

| Title | Model | Date | Params | Active | Code | Venue |
|:------|:------|:-----|:-------|:-------|:-----|:------|
| [VLMo: Unified Vision-Language Pre-Training with Mixture-of-Modality-Experts](https://arxiv.org/abs/2111.02358) | VLMo | 2021/11 | - | - | [Code](https://github.com/microsoft/unilm/tree/master/vlmo) | NeurIPS 2022 |
| [MoME: Mixture of Multimodal Experts for Generalist Multimodal Large Language Models](https://arxiv.org/abs/2407.12709) | MoME | 2024/07 | - | - | - | NeurIPS 2024 |
| [Uni-MoE: Scaling Unified Multimodal LLMs with Mixture of Experts](https://arxiv.org/abs/2405.11273) | Uni-MoE | 2024/05 | - | - | [Code](https://uni-moe.github.io/) | - |
| [Janus: Decoupling Visual Encoding for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2410.13848) | Janus | 2024/10 | - | - | [Code](https://github.com/deepseek-ai/Janus) | CVPR 2025 |
| [CuMo: Scaling Multimodal LLM with Co-Upcycled Mixture-of-Experts](https://arxiv.org/abs/2405.05949) | CuMo | 2024/05 | - | - | [Code](https://github.com/SHI-Labs/CuMo) | NeurIPS 2024 |
| [MoMa: Efficient Early-Fusion Pre-training with Mixture of Modality-Aware Experts](https://arxiv.org/abs/2407.21770) | MoMa | 2024/07 | - | - | - | - |

---

## Papers by Task

### Multimodal Understanding

Papers focused on visual question answering, image captioning, document understanding, and multimodal reasoning.

| Title | Model | Date | Task | Modality | Code | Venue |
|:------|:------|:-----|:-----|:---------|:-----|:------|
| [Scaling Vision with Sparse Mixture of Experts](https://arxiv.org/abs/2106.05974) | V-MoE | 2021/06 | Image Classification | Image | - | NeurIPS 2022 |
| [Multimodal Contrastive Learning with LIMoE: the Language-Image Mixture of Experts](https://arxiv.org/abs/2206.02770) | LIMoE | 2022/06 | Image-Text Retrieval | Image+Text | [Code](https://github.com/kyegomez/LIMoE) | NeurIPS 2022 |
| [VLMo: Unified Vision-Language Pre-Training with Mixture-of-Modality-Experts](https://arxiv.org/abs/2111.02358) | VLMo | 2021/11 | VQA, Retrieval | Image+Text | [Code](https://github.com/microsoft/unilm/tree/master/vlmo) | NeurIPS 2022 |
| [From Sparse to Soft Mixtures of Experts](https://arxiv.org/abs/2308.00951) | Soft MoE | 2023/08 | Image Classification | Image | [Code](https://github.com/fkodom/soft-mixture-of-experts) | ICLR 2024 |
| [Omni-SMoLA: Boosting Generalist Multimodal Models with Soft Mixture of Low-rank Experts](https://arxiv.org/abs/2312.00968) | Omni-SMoLA | 2023/12 | VQA, Captioning | Image+Text | - | CVPR 2024 |
| [MoCLE: Mixture of Cluster-conditional LoRA Experts for Vision-language Instruction Tuning](https://arxiv.org/abs/2312.12379) | MoCLE | 2023/12 | Instruction Following | Image+Text | [Code](https://github.com/gyhdog99/MoCLE) | - |
| [MoE-LLaVA: Mixture of Experts for Large Vision-Language Models](https://arxiv.org/abs/2401.15947) | MoE-LLaVA | 2024/01 | VQA, Reasoning | Image+Text | [Code](https://github.com/PKU-YuanGroup/MoE-LLaVA) | TMM 2025 |
| [LLaVA-MoLE: Sparse Mixture of LoRA Experts for Mitigating Data Conflicts in Instruction Finetuning MLLMs](https://arxiv.org/abs/2401.16160) | LLaVA-MoLE | 2024/01 | Instruction Following | Image+Text | [Code](https://github.com/forwchen/LLaVA-MoLE) | - |
| [MM1: Methods, Analysis & Insights from Multimodal LLM Pre-training](https://arxiv.org/abs/2403.09611) | MM1 | 2024/03 | VQA, Captioning | Image+Text | - | ECCV 2024 |
| [Mini-Gemini: Mining the Potential of Multi-modality Vision Language Models](https://arxiv.org/abs/2403.18814) | Mini-Gemini | 2024/03 | VQA, Reasoning | Image+Text | [Code](https://github.com/JIA-Lab-research/MGM) | - |
| [MoVA: Adapting Mixture of Vision Experts to Multimodal Context](https://arxiv.org/abs/2404.13046) | MoVA | 2024/04 | VQA, Document Understanding | Image+Text | [Code](https://github.com/TempleX98/MoVA) | NeurIPS 2024 |
| [CuMo: Scaling Multimodal LLM with Co-Upcycled Mixture-of-Experts](https://arxiv.org/abs/2405.05949) | CuMo | 2024/05 | VQA, Reasoning | Image+Text | [Code](https://github.com/SHI-Labs/CuMo) | NeurIPS 2024 |
| [Uni-MoE: Scaling Unified Multimodal LLMs with Mixture of Experts](https://arxiv.org/abs/2405.11273) | Uni-MoE | 2024/05 | VQA, Multi-modal QA | Multi-modal | [Code](https://uni-moe.github.io/) | - |
| [MoME: Mixture of Multimodal Experts for Generalist Multimodal Large Language Models](https://arxiv.org/abs/2407.12709) | MoME | 2024/07 | VQA, Captioning | Image+Text | - | NeurIPS 2024 |
| [Gemini: A Family of Highly Capable Multimodal Models](https://arxiv.org/abs/2312.11805) | Gemini | 2023/12 | VQA, Reasoning, Captioning | Multi-modal | - | - |
| [Gemini 1.5: Unlocking multimodal understanding across millions of tokens of context](https://arxiv.org/abs/2403.05530) | Gemini 1.5 | 2024/03 | Long-Context Reasoning | Multi-modal | - | - |
| [DeepSeek-VL2: Mixture-of-Experts Vision-Language Models for Advanced Multimodal Understanding](https://arxiv.org/abs/2412.10302) | DeepSeek-VL2 | 2024/12 | VQA, OCR, Chart Understanding | Image+Text | [Code](https://github.com/deepseek-ai/DeepSeek-VL2) | - |
| [ViMoE: An Empirical Study of Designing Vision Mixture-of-Experts](https://arxiv.org/abs/2410.15732) | ViMoE | 2024/10 | Image Classification, Segmentation | Image | - | - |
| [Mobile V-MoEs: Scaling Down Vision Transformers via Sparse Mixture-of-Experts](https://arxiv.org/abs/2309.04354) | Mobile V-MoE | 2023/09 | Image Classification | Image | - | - |

### Multimodal Generation

Papers focused on text-to-image, text-to-video, text-to-audio, and text-to-3D generation.

| Title | Model | Date | Task | Modality | Code | Venue |
|:------|:------|:-----|:-----|:---------|:-----|:------|
| [eDiff-I: Text-to-Image Diffusion Models with an Ensemble of Expert Denoisers](https://arxiv.org/abs/2211.01324) | eDiff-I | 2022/11 | Text-to-Image | Image+Text | - | CVPR 2023 |
| [RAPHAEL: Text-to-Image Generation via Large Mixture of Diffusion Paths](https://arxiv.org/abs/2305.18295) | RAPHAEL | 2023/05 | Text-to-Image | Image+Text | - | NeurIPS 2023 |
| [Scaling Diffusion Transformers to 16 Billion Parameters](https://arxiv.org/abs/2407.11633) | DiT-MoE | 2024/07 | Text-to-Image | Image+Text | [Code](https://github.com/feizc/DiT-MoE) | - |
| [EC-DIT: Scaling Diffusion Transformers with Adaptive Expert-Choice Routing](https://arxiv.org/abs/2410.02098) | EC-DIT | 2024/10 | Text-to-Image | Image+Text | - | - |
| [CogVideoX: Text-to-Video Diffusion Models with An Expert Transformer](https://arxiv.org/abs/2408.06072) | CogVideoX | 2024/08 | Text-to-Video | Video+Text | [Code](https://github.com/THUDM/CogVideo) | ICLR 2025 |
| [Dense2MoE: Restructuring Diffusion Transformer to MoE for Efficient Text-to-Image Generation](https://arxiv.org/abs/2510.09094) | FLUX.1-MoE | 2025/10 | Text-to-Image | Image+Text | - | - |
| [Style Mixture of Experts for Expressive Text-To-Speech Synthesis](https://arxiv.org/abs/2406.03637) | StyleMoE | 2024/06 | Text-to-Speech | Audio+Text | - | - |
| [MoST: Mixing Speech and Text with Modality-Aware Mixture of Experts](https://arxiv.org/abs/2601.10272) | MoST | 2025/01 | TTS, ASR | Audio+Text | - | - |

### Unified Understanding & Generation

Papers that address both understanding and generation in a single model.

| Title | Model | Date | Tasks | Modality | Code | Venue |
|:------|:------|:-----|:------|:---------|:-----|:------|
| [VLMo: Unified Vision-Language Pre-Training with Mixture-of-Modality-Experts](https://arxiv.org/abs/2111.02358) | VLMo | 2021/11 | VQA, Retrieval | Image+Text | [Code](https://github.com/microsoft/unilm/tree/master/vlmo) | NeurIPS 2022 |
| [Janus: Decoupling Visual Encoding for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2410.13848) | Janus | 2024/10 | Understanding + Generation | Image+Text | [Code](https://github.com/deepseek-ai/Janus) | CVPR 2025 |
| [Janus-Pro: Unified Multimodal Understanding and Generation with Data and Model Scaling](https://arxiv.org/abs/2501.17811) | Janus-Pro | 2025/01 | Understanding + Generation | Image+Text | [Code](https://github.com/deepseek-ai/Janus) | - |
| [Uni-MoE: Scaling Unified Multimodal LLMs with Mixture of Experts](https://arxiv.org/abs/2405.11273) | Uni-MoE | 2024/05 | VQA, Multi-modal QA | Multi-modal | [Code](https://uni-moe.github.io/) | - |
| [MoME: Mixture of Multimodal Experts for Generalist Multimodal Large Language Models](https://arxiv.org/abs/2407.12709) | MoME | 2024/07 | VQA, Captioning | Image+Text | - | NeurIPS 2024 |
| [MoMa: Efficient Early-Fusion Pre-training with Mixture of Modality-Aware Experts](https://arxiv.org/abs/2407.21770) | MoMa | 2024/07 | Multi-modal | Image+Text | - | - |
| [Mini-Gemini: Mining the Potential of Multi-modality Vision Language Models](https://arxiv.org/abs/2403.18814) | Mini-Gemini | 2024/03 | Understanding + Generation | Image+Text | [Code](https://github.com/JIA-Lab-research/MGM) | - |

---

## Papers by Modality

### Image + Text

| Title | Model | Date | MoE Placement | Code | Venue |
|:------|:------|:-----|:--------------|:-----|:------|
| [Scaling Vision with Sparse Mixture of Experts](https://arxiv.org/abs/2106.05974) | V-MoE | 2021/06 | Vision Encoder | - | NeurIPS 2022 |
| [VLMo: Unified Vision-Language Pre-Training with Mixture-of-Modality-Experts](https://arxiv.org/abs/2111.02358) | VLMo | 2021/11 | Multi-component | [Code](https://github.com/microsoft/unilm/tree/master/vlmo) | NeurIPS 2022 |
| [Multimodal Contrastive Learning with LIMoE: the Language-Image Mixture of Experts](https://arxiv.org/abs/2206.02770) | LIMoE | 2022/06 | Vision Encoder | [Code](https://github.com/kyegomez/LIMoE) | NeurIPS 2022 |
| [eDiff-I: Text-to-Image Diffusion Models with an Ensemble of Expert Denoisers](https://arxiv.org/abs/2211.01324) | eDiff-I | 2022/11 | Generation Decoder | - | CVPR 2023 |
| [From Sparse to Soft Mixtures of Experts](https://arxiv.org/abs/2308.00951) | Soft MoE | 2023/08 | Vision Encoder | [Code](https://github.com/fkodom/soft-mixture-of-experts) | ICLR 2024 |
| [RAPHAEL: Text-to-Image Generation via Large Mixture of Diffusion Paths](https://arxiv.org/abs/2305.18295) | RAPHAEL | 2023/05 | Generation Decoder | - | NeurIPS 2023 |
| [Omni-SMoLA: Boosting Generalist Multimodal Models with Soft Mixture of Low-rank Experts](https://arxiv.org/abs/2312.00968) | Omni-SMoLA | 2023/12 | Connector | - | CVPR 2024 |
| [MoCLE: Mixture of Cluster-conditional LoRA Experts for Vision-language Instruction Tuning](https://arxiv.org/abs/2312.12379) | MoCLE | 2023/12 | Connector | [Code](https://github.com/gyhdog99/MoCLE) | - |
| [MoE-LLaVA: Mixture of Experts for Large Vision-Language Models](https://arxiv.org/abs/2401.15947) | MoE-LLaVA | 2024/01 | LLM Backbone | [Code](https://github.com/PKU-YuanGroup/MoE-LLaVA) | TMM 2025 |
| [LLaVA-MoLE: Sparse Mixture of LoRA Experts for Mitigating Data Conflicts in Instruction Finetuning MLLMs](https://arxiv.org/abs/2401.16160) | LLaVA-MoLE | 2024/01 | Connector | [Code](https://github.com/forwchen/LLaVA-MoLE) | - |
| [MM1: Methods, Analysis & Insights from Multimodal LLM Pre-training](https://arxiv.org/abs/2403.09611) | MM1 | 2024/03 | LLM Backbone | - | ECCV 2024 |
| [Mini-Gemini: Mining the Potential of Multi-modality Vision Language Models](https://arxiv.org/abs/2403.18814) | Mini-Gemini | 2024/03 | LLM Backbone | [Code](https://github.com/JIA-Lab-research/MGM) | - |
| [MoVA: Adapting Mixture of Vision Experts to Multimodal Context](https://arxiv.org/abs/2404.13046) | MoVA | 2024/04 | Vision Encoder | [Code](https://github.com/TempleX98/MoVA) | NeurIPS 2024 |
| [CuMo: Scaling Multimodal LLM with Co-Upcycled Mixture-of-Experts](https://arxiv.org/abs/2405.05949) | CuMo | 2024/05 | Vision Encoder + Connector | [Code](https://github.com/SHI-Labs/CuMo) | NeurIPS 2024 |
| [MoME: Mixture of Multimodal Experts for Generalist Multimodal Large Language Models](https://arxiv.org/abs/2407.12709) | MoME | 2024/07 | Multi-component | - | NeurIPS 2024 |
| [MoMa: Efficient Early-Fusion Pre-training with Mixture of Modality-Aware Experts](https://arxiv.org/abs/2407.21770) | MoMa | 2024/07 | Full-Stack | - | - |
| [DiT-MoE: Scaling Diffusion Transformers to 16 Billion Parameters](https://arxiv.org/abs/2407.11633) | DiT-MoE | 2024/07 | Generation Decoder | [Code](https://github.com/feizc/DiT-MoE) | - |
| [EC-DIT: Scaling Diffusion Transformers with Adaptive Expert-Choice Routing](https://arxiv.org/abs/2410.02098) | EC-DIT | 2024/10 | Generation Decoder | - | - |
| [Janus: Decoupling Visual Encoding for Unified Multimodal Understanding and Generation](https://arxiv.org/abs/2410.13848) | Janus | 2024/10 | Full-Stack | [Code](https://github.com/deepseek-ai/Janus) | CVPR 2025 |
| [ViMoE: An Empirical Study of Designing Vision Mixture-of-Experts](https://arxiv.org/abs/2410.15732) | ViMoE | 2024/10 | Vision Encoder | - | - |
| [DeepSeek-VL2: Mixture-of-Experts Vision-Language Models for Advanced Multimodal Understanding](https://arxiv.org/abs/2412.10302) | DeepSeek-VL2 | 2024/12 | LLM Backbone | [Code](https://github.com/deepseek-ai/DeepSeek-VL2) | - |
| [Janus-Pro: Unified Multimodal Understanding and Generation with Data and Model Scaling](https://arxiv.org/abs/2501.17811) | Janus-Pro | 2025/01 | Full-Stack | [Code](https://github.com/deepseek-ai/Janus) | - |
| [Dense2MoE: Restructuring Diffusion Transformer to MoE for Efficient Text-to-Image Generation](https://arxiv.org/abs/2510.09094) | FLUX.1-MoE | 2025/10 | Generation Decoder | - | - |

### Video + Text

| Title | Model | Date | MoE Placement | Code | Venue |
|:------|:------|:-----|:--------------|:-----|:------|
| [CogVideoX: Text-to-Video Diffusion Models with An Expert Transformer](https://arxiv.org/abs/2408.06072) | CogVideoX | 2024/08 | Generation Decoder | [Code](https://github.com/THUDM/CogVideo) | ICLR 2025 |
| [Gemini: A Family of Highly Capable Multimodal Models](https://arxiv.org/abs/2312.11805) | Gemini | 2023/12 | LLM Backbone | - | - |
| [Gemini 1.5: Unlocking multimodal understanding across millions of tokens of context](https://arxiv.org/abs/2403.05530) | Gemini 1.5 | 2024/03 | LLM Backbone | - | - |
| [Uni-MoE: Scaling Unified Multimodal LLMs with Mixture of Experts](https://arxiv.org/abs/2405.11273) | Uni-MoE | 2024/05 | LLM Backbone | [Code](https://uni-moe.github.io/) | - |

### Audio + Text

| Title | Model | Date | MoE Placement | Code | Venue |
|:------|:------|:-----|:--------------|:-----|:------|
| [Style Mixture of Experts for Expressive Text-To-Speech Synthesis](https://arxiv.org/abs/2406.03637) | StyleMoE | 2024/06 | Generation Decoder | - | - |
| [MoST: Mixing Speech and Text with Modality-Aware Mixture of Experts](https://arxiv.org/abs/2601.10272) | MoST | 2025/01 | LLM Backbone | - | - |
| [MoE Adapter for Large Audio Language Models](https://arxiv.org/abs/2601.02967) | MoE-Adapter | 2025/01 | Connector | - | - |
| [Uni-MoE: Scaling Unified Multimodal LLMs with Mixture of Experts](https://arxiv.org/abs/2405.11273) | Uni-MoE | 2024/05 | LLM Backbone | [Code](https://uni-moe.github.io/) | - |
| [Gemini: A Family of Highly Capable Multimodal Models](https://arxiv.org/abs/2312.11805) | Gemini | 2023/12 | LLM Backbone | - | - |

### 3D + Text

| Title | Model | Date | MoE Placement | Code | Venue |
|:------|:------|:-----|:--------------|:-----|:------|
| [3D-MoE: A Mixture-of-Experts Multi-modal LLM for 3D Vision and Pose](https://arxiv.org/abs/2501.16698) | 3D-MoE | 2025/01 | LLM Backbone | - | - |

---

## MoE Foundation Models

These are the base MoE language models that underpin many multimodal MoE systems.

| Title | Model | Date | Total Params | Active Params | Code | Venue |
|:------|:------|:-----|:-------------|:--------------|:-----|:------|
| [GShard: Scaling Giant Models with Conditional Computation and Automatic Sharding](https://arxiv.org/abs/2006.16668) | GShard | 2020/06 | 600B | - | - | ICLR 2021 |
| [Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity](https://arxiv.org/abs/2101.03961) | Switch Transformer | 2021/01 | 1.6T | - | - | JMLR 2022 |
| [Mixtral of Experts](https://arxiv.org/abs/2401.04088) | Mixtral 8x7B | 2024/01 | 47B | 13B | [Code](https://github.com/mistralai/mistral-inference) | - |
| Mixtral 8x22B | Mixtral 8x22B | 2024/04 | 141B | 39B | [Code](https://github.com/mistralai/mistral-inference) | - |
| [DeepSeekMoE: Towards Ultimate Expert Specialization in Mixture-of-Experts Language Models](https://arxiv.org/abs/2401.06066) | DeepSeekMoE | 2024/01 | 145B | ~16B | [Code](https://github.com/deepseek-ai/DeepSeek-MoE) | ACL 2024 |
| [DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model](https://arxiv.org/abs/2405.04434) | DeepSeek-V2 | 2024/05 | 236B | 21B | [Code](https://github.com/deepseek-ai/DeepSeek-V2) | - |
| [DeepSeek-V3 Technical Report](https://arxiv.org/abs/2412.19437) | DeepSeek-V3 | 2024/12 | 671B | 37B | [Code](https://github.com/deepseek-ai/DeepSeek-V3) | - |
| Qwen1.5-MoE-A2.7B | Qwen-MoE | 2024/03 | 14.3B | 2.7B | [Code](https://github.com/QwenLM/Qwen) | - |
| [Qwen2.5 Technical Report](https://arxiv.org/abs/2412.15115) | Qwen2.5 | 2024/12 | - | - | [Code](https://github.com/QwenLM/Qwen2.5) | - |
| [Qwen3 Technical Report](https://arxiv.org/abs/2505.09388) | Qwen3-MoE | 2024/05 | 235B | - | [Code](https://github.com/QwenLM/Qwen3) | - |
| [DBRX](https://www.databricks.com/blog/introducing-dbrx-new-state-art-open-llm) | DBRX | 2024/03 | 132B | 36B | [Code](https://huggingface.co/databricks/dbrx-instruct) | - |
| [Grok-1](https://x.ai/news/grok-os) | Grok-1 | 2024/03 | 314B | ~78B | [Code](https://github.com/xai-org/grok-1) | - |
| [JetMoE: Reaching Llama2 Performance with 0.1M Dollars](https://arxiv.org/abs/2404.07413) | JetMoE | 2024/04 | 8B | ~2B | [Code](https://github.com/myshell-ai/JetMoE) | - |
| [OpenMoE: An Early Effort on Open Mixture-of-Experts Language Models](https://arxiv.org/abs/2402.01739) | OpenMoE | 2024/02 | 34B | - | [Code](https://github.com/XueFuzhao/OpenMoE) | - |
| [OLMoE: Open Mixture-of-Experts Language Models](https://arxiv.org/abs/2409.02060) | OLMoE | 2024/09 | 7B | 1B | [Code](https://github.com/allenai/OLMoE) | - |
| [Skywork-MoE: A Deep Dive into Training Techniques for Mixture-of-Experts Language Models](https://arxiv.org/abs/2406.06563) | Skywork-MoE | 2024/06 | 146B | - | [Code](https://github.com/SkyworkAI/Skywork-MoE) | - |
| [Snowflake Arctic](https://github.com/Snowflake-Labs/snowflake-arctic) | Arctic | 2024/04 | 480B | 17B | [Code](https://github.com/Snowflake-Labs/snowflake-arctic) | - |

---

## Datasets & Benchmarks

Common benchmarks used for evaluating MoE multimodal models.

| Benchmark | Task | Modality | Link |
|:----------|:-----|:---------|:-----|
| VQAv2 | Visual Question Answering | Image+Text | [Link](https://visualqa.org/) |
| GQA | Visual Reasoning & QA | Image+Text | [Link](https://cs.stanford.edu/people/doersch/gqa/) |
| TextVQA | Text-based Visual QA | Image+Text | [Link](https://textvqa.org/) |
| MMMU | Massive Multi-discipline Multimodal Understanding | Image+Text | [Link](https://mmmu-benchmark.github.io/) |
| MMBench | Comprehensive Multi-modal Evaluation | Image+Text | [Link](https://opencompass.org.cn/leaderboard-multimodal) |
| MME | Multi-modal Evaluation | Image+Text | [Link](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models/tree/Evaluation) |
| POPE | Object Hallucination Evaluation | Image+Text | [Link](https://github.com/AoiDragon/POPE) |
| ScienceQA | Science Question Answering | Image+Text | [Link](https://scienceqa.github.io/) |
| SEED-Bench | Multi-modal Comprehension | Image+Video+Text | [Link](https://github.com/AILab-CVC/SEED-Bench) |
| ImageNet | Image Classification | Image | [Link](https://www.image-net.org/) |
| COCO (FID) | Image Generation Quality | Image+Text | [Link](https://cocodataset.org/) |
| GenEval | Text-to-Image Generation Evaluation | Image+Text | [Link](https://github.com/djghosh13/geneval) |
| VBench | Video Generation Benchmark | Video+Text | [Link](https://github.com/Vchitect/VBench) |
| SuperGLUE | Natural Language Understanding | Text | [Link](https://super.gluebenchmark.com/) |

---

## Related Surveys

| Title | Date | Link |
|:------|:-----|:-----|
| A Comprehensive Survey of Mixture-of-Experts: Algorithms, Theory, and Applications | 2025/03 | [arXiv](https://arxiv.org/abs/2503.07137) |
| A Survey on Mixture of Experts in Large Language Models | 2024/07 | [arXiv](https://arxiv.org/abs/2407.06204) |
| Mixture of Experts in Large Language Models | 2024/07 | [arXiv](https://arxiv.org/abs/2507.11181) |
| A Survey on Inference Optimization Techniques for Mixture of Experts Models | 2024/12 | [arXiv](https://arxiv.org/abs/2412.14219) |
| The Rise of Sparse Mixture-of-Experts: A Survey from Algorithmic Perspectives | 2025/02 | [arXiv](https://arxiv.org/abs/2602.08019) |
| Mixture-of-Experts Models in Vision: Routing, Optimization, and Generalization | 2025/01 | [arXiv](https://arxiv.org/abs/2601.15021) |
| Unified Multimodal Understanding and Generation Models: Advances, Challenges, and Opportunities | 2024/05 | [arXiv](https://arxiv.org/abs/2505.02567) |
| Multimodal Alignment and Fusion: A Survey | 2024/11 | [arXiv](https://arxiv.org/abs/2411.17040) |

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=nguyennm1024/Awesome-MoE-Multimodal&type=Date)](https://star-history.com/#YOUR_USERNAME/Awesome-MoE-Multimodal&Date)

---

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to add papers, fix errors, or suggest improvements.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
