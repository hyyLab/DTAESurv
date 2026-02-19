# DTAESurv: A Denoising TransformerAutoEncoder for Cancer Survival Prediction

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.8%2B-green)](https://www.python.org/)
[![Pytorch](https://img.shields.io/badge/Pytorch-1.10%2B-orange)](https://pytorch.org/)

**DTAESurv** is a unified cancer survival prediction framework that integrates uncertainty-aware noise modeling with hierarchical representation learning for high-dimensional gene expression data.

---

## 📖 Abstract

Accurate cancer survival prediction is crucial for clinical decision-making yet remains challenging due to the high dimensionality and inherent noise of genomic data. Although deep learning models are capable of capturing complex nonlinear patterns, their application to high-dimensional genomic survival modeling often suffers from overfitting spurious correlations rather than learning robust prognostic signals. 

To address this issue, we propose **DTAESurv**, a unified framework that integrates uncertainty-aware noise modeling with hierarchical representation learning. Specifically, DTAESurv introduces an **uncertainty-aware adaptive swap noise mechanism** that explicitly models feature-wise statistical instability, including expression variance and inter-feature correlation. By selectively perturbing unstable features, the framework encourages **noise-invariant and robust representation learning**. To effectively model high-dimensional gene expression data, we further design a **subspace-based Transformer encoder** that projects features into multiple latent subspaces, enabling modular representation learning while maintaining parameter efficiency. 

DTAESurv is trained using a unified joint learning objective that tightly integrates reconstruction, mask prediction, and survival supervision in an end-to-end manner. Extensive experiments on seven cancer datasets demonstrate that the proposed framework consistently achieves competitive performance compared with state-of-the-art methods.

---

## 🚀 Framework Architecture

![DTAESurv Framework](assets/framework.png)

*Figure 1: The overall architecture of DTAESurv. The framework consists of (a) an uncertainty-aware adaptive swap noise module that selectively perturbs unstable features based on variance and correlation scores; (b) a subspace-based Transformer encoder that captures hierarchical feature interactions; and (c) a multi-task prediction head jointly optimized for reconstruction, noise localization (mask prediction), and survival analysis.*

---

## ✨ Key Contributions

1.  **Uncertainty-Aware Noise Modeling**: Unlike random corruption, we introduce an adaptive swap noise mechanism driven by feature-wise statistical instability (variance and correlation), acting as a dynamic regularization strategy.
2.  **Explicit Noise Localization**: A mask prediction objective explicitly supervises the model to localize uncertainty-induced perturbations, transforming denoising from an implicit task into an explicit supervised learning signal.
3.  **Subspace-Based Transformer**: A structure-aware attention mechanism projects high-dimensional features into multiple latent subspaces (e.g., 8 subspaces), capturing modular biological patterns while ensuring computational efficiency.
4.  **Biological Interpretability**: Extensive analyses, including cross-cancer functional enrichment and PPI network profiling, confirm that DTAESurv captures biologically coherent prognostic signals (e.g., distinguishing proliferative from immune-related mechanisms).

---

## 📂 Code & Data

The source code and pre-trained models will be released upon the acceptance of the paper.

- **Data**: The gene expression data used in this study relies on public datasets from UCSC Xena platform.
