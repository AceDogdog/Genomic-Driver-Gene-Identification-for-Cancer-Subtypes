# 🧬 Genomic Driver Gene Identification for Cancer Subtypes
> **High-Dimensional Statistical Learning for Biomarker Discovery and Cancer Subtype Classification.**

![R](https://img.shields.io/badge/Language-R-blue?style=for-the-badge&logo=r)
![Statistics](https://img.shields.io/badge/Field-Biostatistics-green?style=for-the-badge)
![Method](https://img.shields.io/badge/Algorithm-LASSO%20%7C%20SCAD-orange?style=for-the-badge)

---

## 📖 Table of Contents
1. [Project Background](#-project-background)
2. [Statistical Challenges](#-statistical-challenges)
3. [Methodology](#-methodology)
4. [Feature Selection & Penalization](#-feature-selection--penalization)
5. [Key Findings](#-key-findings)

---

## 🌍 Project Background
Identifying driver genes is a fundamental task in genomic oncology, as it allows for the differentiation of cancer subtypes and the development of targeted therapies. However, genomic datasets are characterized by **Ultra-High Dimensionality** ($p \gg n$), where the number of genetic features far exceeds the number of available patient samples. 

This project implements sparsity-inducing regularization techniques to isolate a stable subset of "driver genes" that significantly contribute to cancer subtype variance.

---

## 📊 Statistical Challenges
- **The Curse of Dimensionality**: Handling datasets with tens of thousands of gene expressions (p > 20,000) against a limited sample size (n < 500).
- **Multicollinearity**: Managing highly correlated genetic pathways where traditional regression models fail to provide stable estimates.
- **Sparsity Assumption**: Operating under the biological assumption that only a small fraction of genes are true drivers of the disease.

---

## 🛠️ Methodology
### 1. Data Pre-processing
- **Normalization**: Applied Log2 transformation and Z-score scaling to standardize gene expression levels across heterogeneous samples.
- **Variance Filtering**: Removed low-variance genes to reduce computational noise and focus on informative signals.

### 2. Model Architecture
- **Penalized Likelihood Estimation**: Implemented a framework to optimize the bias-variance tradeoff in high-dimensional settings.
- **Cross-Validation**: Utilized k-fold cross-validation to select optimal tuning parameters ($\lambda$) for the regularization paths.

---

## 🧪 Feature Selection & Penalization
To achieve a parsimonious model, the project compares multiple shrinkage methods:
- **LASSO (Least Absolute Shrinkage and Selection Operator)**: Used for initial feature pruning to produce a sparse set of candidate genes.
- **SCAD (Smoothly Clipped Absolute Deviation)**: Implemented to overcome the estimation bias inherent in LASSO, ensuring that large coefficients are not overly penalized.
- **Stability Selection**: Conducted subsampling to identify genes that are consistently selected across different data partitions, ensuring biological relevance.

---

## 📈 Key Findings
- **Driver Gene Isolation**: Successfully reduced the feature space from over 20,000 genes to a refined panel of target biomarkers.
- **Predictive Accuracy**: The selected gene subset demonstrated high discriminatory power in classifying cancer subtypes, outperforming baseline models that used non-penalized methods.
- **Biological Validation**: Identified several genes that are well-documented in oncological literature as key regulators of cellular proliferation and apoptosis.

---

## 🏆 Conclusion
This project demonstrates the power of **Regularized Statistical Learning** in decoding complex biological systems. By effectively managing the "Small n, Large p" problem, the developed pipeline provides a robust tool for clinical biomarker discovery and precision medicine.

---
**Developed by**: Li Zongbo  
**Status**: Research Project - Genomic Data Analysis Suite
