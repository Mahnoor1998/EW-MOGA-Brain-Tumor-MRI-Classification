# EW-MOGA: Brain Tumor MRI Classification

**Paper:** *EW-MOGA: A Multi-Objective Genetic Algorithm with Independent Post-Hoc Explainability Audit for Brain Tumor MRI Classification*

**Authors:** Mahnoor Asghar, Muhammad Umer Mubarik

---

## Overview

This repository contains the complete implementation, experimental results, and LaTeX source for the EW-MOGA framework. EW-MOGA is a bi-objective NSGA-II algorithm that jointly optimizes classification accuracy and a composite SHAP-based explainability score for feature selection in brain tumor MRI classification. The framework introduces an independent post-hoc audit using Cross-Classifier Consistency (CCC) and Perturbation Robustness (PR) to verify explanation robustness.

## Key Contributions

- **Independent Post-Hoc Audit:** Separates optimization metrics from evaluation metrics to break circular evaluation in explainability-aware feature selection.
- **Composite Explainability Objective:** Integrates SCI (SHAP Consistency Index), FID (Feature Importance Deviation), and LFS (Local Faithfulness Score).
- **Cross-Domain Validation:** External validation on Wisconsin Breast Cancer dataset confirms generalization.
- **Ablation Study:** Full 7-variant ablation validates the three-component design.

## Repository Structure

```
EW-MOGA-Brain-Tumor-MRI-Classification/
├── paper/                  # LaTeX source files
│   ├── main.tex
│   ├── sections/
│   ├── figures/
│   └── references.bib
├── code/                   # Python implementation
│   ├── notebooks/          # Jupyter notebooks (experimental phases)
│   └── src/                # Source modules
├── data/                   # Dataset and preprocessing scripts
├── results/                # Output tables, charts, audit results
└── README.md
```

## Dataset

- **Brain Tumor MRI Dataset:** 3,762 instances, 13 statistical and texture-based features (Mean, Variance, Standard Deviation, Entropy, Skewness, Kurtosis, Contrast, Energy, ASM, Homogeneity, Dissimilarity, Correlation, Coarseness).
- **External Validation:** Wisconsin Breast Cancer Diagnostic dataset (569 instances, 30 features).

## Results Summary

| Metric | EW-MOGA | Best Baseline |
|--------|---------|---------------|
| Accuracy | 99.02% | 99.29% (Standard GA) |
| CCC | **0.621** | 0.338 (NSGA-II Parsimony) |
| PR | 0.965 | 0.931 (NSGA-II Parsimony) |

- **8.4× improvement** in CCC over accuracy-only baselines
- **0.27 pp accuracy cost** for the explainability gain
- **Ablation:** Full composite (SCI+FID+LFS) achieves highest CCC (0.722)

## Requirements

- Python 3.8+
- `numpy`, `pandas`, `scikit-learn`, `xgboost`, `shap`, `matplotlib`, `deap`
- LaTeX distribution (TeX Live / MiKTeX) for paper compilation

## Citation

If you use this code or framework, please cite:

```bibtex
@article{asghar2025ewmoga,
  title={EW-MOGA: A Multi-Objective Genetic Algorithm with Independent Post-Hoc Explainability Audit for Brain Tumor MRI Classification},
  author={Asghar, Mahnoor and Mubarik, Muhammad Umer},
  journal={Computers in Biology and Medicine},
  year={2025}
}
```

## Contact

- **Mahnoor Asghar:** mahnoorasgharfiver@gmail.com
- **Muhammad Umer Mubarik:** Umermubarik124@gmail.com
