# Introduction to Causal Tracing and Activation Patching in Mechanistic Interpretability

## Scope of This Guide

This guide focuses on **mechanistic interpretability** centered around:

-   Causal interventions
-   Activation patching
-   Path patching
-   Circuit discovery
-   Causal tracing (primarily in language models, with extensions to multimodal models)

This document provides a shortlist of researchers strongly associated with this style of work, along with their key papers.

---

## Key Researchers and Their Contributions

### 1. Activation / Causal Patching & Best Practices

These researchers are the "methods & hygiene" people for activation/causal patching.

#### Neel Nanda

-   Co-author on both best-practices and how-to papers for activation patching
-   Runs very influential educational posts and annotated paper walkthroughs for mech-interp (e.g., IOI circuit walkthrough)
-   Resources: [Neel Nanda's Blog](https://www.neelnanda.io/) and [Mechanistic Interpretability Quickstart Guide](https://www.neelnanda.io/mechanistic-interpretability/quickstart)

#### Stefan Heimersheim

-   Co-author of "How to use and interpret activation patching" (2024), a practical guide to doing causal/activation patching right
-   Paper: [arXiv:2404.16014](https://arxiv.org/abs/2404.16014)

#### Fred Zhang

-   First author of "Towards Best Practices of Activation Patching in Language Models: Metrics and Methods" (ICLR-style work)
-   Systematically studies how different corruption/metric choices affect activation patching results
-   Paper: [arXiv:2406.08219](https://arxiv.org/abs/2406.08219)

---

### 2. Path Patching & Circuit Localization

Path patching is a specific technique for testing hypotheses about which paths in the computation graph carry a behavior, providing a more structured approach to causal propagation tracing.

#### Nicholas Goldowsky-Dill

-   Lead author of "Localizing Model Behavior with Path Patching"
-   Introduces path patching—a way to test hypotheses about which paths in the computation graph carry a behavior
-   Paper: [arXiv:2404.15719](https://arxiv.org/abs/2404.15719)

#### Chris MacLeod, Lucas Sato, Aryaman Arora

-   Co-authors on the same path-patching paper
-   Active in broader circuit discovery work

---

### 3. Causal Tracing & Editing Factual Mechanisms

#### Kevin Meng, David Bau, Alex Andonian, Yonatan Belinkov

-   Authors of "Locating and Editing Factual Associations in GPT" (ROME paper)
-   Introduce causal tracing to find where factual knowledge lives and then directly edit it
-   Paper: [arXiv:2202.05262](https://arxiv.org/abs/2202.05262)
-   **Note**: This is the direct ancestor of the BLIP paper—same style of intervention, but on text-only GPT-like models

---

### 4. Causal Mediation & Causal Interpretability Theory

These researchers focus on the theoretical foundations and large-model causal mechanisms.

#### Jesse Vig, Sebastian Gehrmann, Yonatan Belinkov, Stuart Shieber et al.

-   "Investigating Gender Bias in Language Models Using Causal Mediation Analysis" (NeurIPS 2020) is the classic causal-mediation paper in NLP interpretability
-   Paper: [arXiv:2004.14985](https://arxiv.org/abs/2004.14985)

#### Atticus Geiger, Thomas Icard, Christopher Potts, Noah Goodman, Zhengxuan Wu

-   Work on causal abstraction and "Interpretability at Scale: Identifying Causal Mechanisms in Alpaca"
-   Scales causal-mechanistic ideas to larger LLMs
-   Paper: [arXiv:2305.08809](https://arxiv.org/abs/2305.08809)

---

### 5. Automated Circuit Discovery & Pipelines

#### Arthur Conmy, Augustine N. Mavor-Parker, Aengus Lynch, Adrià Garriga-Alonso

-   Authors of "Towards Automated Circuit Discovery for Mechanistic Interpretability" (NeurIPS 2023 Spotlight)
-   Turn the human "patch things, see what breaks" workflow into a more automated pipeline (ACDC)
-   Paper: [arXiv:2304.14997](https://arxiv.org/abs/2304.14997)
-   **Key for**: Scaling causal-patch-style experiments beyond hand-crafted circuits

---

### 6. Vision-Language / Multimodal Mechanistic Interpretability

#### For Causal Tracing in Multimodal Models

**Vedant Palit, Rohan Pandey, Aryaman Arora, Paul Pu Liang**

-   Authors of "Towards Vision-Language Mechanistic Interpretability: A Causal Tracing Tool for BLIP"
-   Adapts causal tracing tools to BLIP for VQA and studies where visual information actually matters
-   Paper: [arXiv:2403.03186](https://arxiv.org/abs/2403.03186)

#### Broader Multimodal Causal/Mechanistic Interpretability

**Zeyu Weng et al.**

-   "Understanding and Mitigating Bias in Vision-Language Models" uses causal mediation analysis to study bias pathways in VLMs

**Emerging Work**

-   There are emerging survey/overview efforts on mechanistic methods for multimodal foundation models

---

### 7. Field-Level Overviews & "Who's Who"

Key resources for understanding the community:

#### Chris Olah et al.

-   Foundational "circuits" and mech-interp essays
-   [Transformer Circuits](https://transformer-circuits.pub/)

#### Open Problems in Mechanistic Interpretability (2025)

**Co-authors include:** Lee Sharkey, Bilal Chughtai, Nicholas Goldowsky-Dill, Stefan Heimersheim, Arthur Conmy, Neel Nanda, David Bau, Atticus Geiger, and others.

-   Paper: [arXiv:2501.16496](https://arxiv.org/abs/2501.16496)
-   This paper doubles as a "roster" of active researchers in this area
-   Great way to discover more names and sub-directions (features, parameter-space mech-interp, sparse circuits, etc.)

---

## How to Practically Use This List

For researchers interested in causal propagation tracing, activation patching, and path patching:

### Step 1: Start with Methods Papers

1. **Zhang & Nanda** — "Towards Best Practices of Activation Patching in Language Models: Metrics and Methods" ([arXiv:2406.08219](https://arxiv.org/abs/2406.08219))
2. **Heimersheim & Nanda** — "How to use and interpret activation patching" ([arXiv:2404.16014](https://arxiv.org/abs/2404.16014))
3. **Goldowsky-Dill et al.** — "Localizing Model Behavior with Path Patching" ([arXiv:2404.15719](https://arxiv.org/abs/2404.15719))

### Step 2: Read a "Big Circuit" Case Study

-   **Wang et al.** — "Interpretability in the Wild: A Circuit for Indirect Object Identification in GPT-2 small" ([arXiv:2211.00593](https://arxiv.org/abs/2211.00593))

### Step 3: Connect to Your Context

1. **Meng et al.** — "Locating and Editing Factual Associations in GPT" (causal tracing origin) ([arXiv:2202.05262](https://arxiv.org/abs/2202.05262))
2. **Palit et al.** — "Towards Vision-Language Mechanistic Interpretability: A Causal Tracing Tool for BLIP" ([arXiv:2403.03186](https://arxiv.org/abs/2403.03186))
