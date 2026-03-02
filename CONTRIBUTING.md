# Contributing to Awesome-MoE-Multimodal

Thank you for your interest in contributing to this curated list! We welcome contributions from the community to help keep this list comprehensive and up-to-date.

## How to Add a Paper

1. **Fork** this repository.
2. **Edit** `README.md` to add the paper in the appropriate section(s).
3. **Submit** a Pull Request with a clear description of the addition.

### Paper Entry Format

Each paper entry should follow this table format:

```markdown
| [Paper Title](https://arxiv.org/abs/XXXX.XXXXX) | Model Name | YYYY/MM | Total Params | Active Params | [Code](https://github.com/...) | Venue |
```

**Required fields:**
- **Title**: The full paper title, hyperlinked to the arXiv page or official publication.
- **Model**: The short model name (e.g., MoE-LLaVA, DeepSeek-VL2).
- **Date**: Publication date in `YYYY/MM` format.
- **Params**: Total parameter count (if available, use `-` otherwise).
- **Active**: Number of active parameters per token (if applicable).
- **Code**: Link to the official GitHub repository. Use `-` if no code is available.
- **Venue**: Publication venue (e.g., NeurIPS 2024, CVPR 2024). Use `-` for preprints.

### Placement Guidelines

- Add the paper to **all relevant sections** (by MoE placement, by task, by modality).
- Place new entries in **chronological order** within each section.
- Ensure the paper is relevant to **Mixture of Experts in multimodal learning**.

## What We Accept

- Papers that use or study Mixture of Experts architectures in multimodal contexts.
- Papers on MoE foundation models that are commonly used as backbones for multimodal systems.
- Relevant surveys and benchmarks.
- New datasets specifically designed for evaluating MoE multimodal models.

## What We Do NOT Accept

- Papers unrelated to Mixture of Experts or multimodal learning.
- Blog posts, tutorials, or non-peer-reviewed content (arXiv preprints are accepted).
- Duplicate entries.
- Promotional or advertising content.

## Fixing Errors

If you find an error (broken link, wrong venue, incorrect parameter count), please:

1. Open an **Issue** describing the error.
2. Or submit a **Pull Request** with the correction.

## Code of Conduct

- Be respectful and constructive in all interactions.
- Ensure all information is accurate and verifiable.
- Do not add fabricated or unverified papers.

## Questions?

If you have questions about whether a paper fits, please open an Issue for discussion before submitting a PR.

Thank you for helping make this resource better for everyone!
