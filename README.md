# Choosing the Right Kernel: An SVM Tutorial

A machine learning tutorial demonstrating how different **SVM kernel functions** Linear,
Polynomial, RBF, and a custom Laplacian  change decision boundary behaviour and
generalisation performance, using the **UCI Wine Recognition Dataset**.

**GitHub:** https://github.com/VineethDoddaballapuraRaju24089093/ml_assinment_2

---

## Contents

| File | Description |
|------|-------------|
| `svm_kernel_tutorial.ipynb` | Full Jupyter notebook with code, figures and explanations |
| `SVM_Kernel_Tutorial.pdf` | Tutorial document (< 2000 words) |
| `figures/` | Pre-generated PNG figures (150 dpi) see Figure Index below |
| `README.md` | This file |
| `LICENSE` | MIT License |

---

## Quick Start

```bash
# Clone the repository
git clone https://github.com/VineethDoddaballapuraRaju24089093/ml_assinment_2.git
cd ml_assinment_2

# Install pinned dependencies (Python 3.8+ recommended)
pip install -r requirements.txt

# Launch the notebook
jupyter notebook svm_kernel_tutorial.ipynb
```

No external datasets are required the Wine dataset is bundled with scikit-learn.

> **Note on figures:** The `figures/` directory contains pre-generated PNG files committed
> to the repository, so the PDF tutorial renders correctly without running the notebook.
> Running the notebook regenerates all figures in place.

---

## Requirements

```
scikit-learn>=1.3
matplotlib>=3.7
numpy>=1.24
pandas>=2.0
seaborn>=0.12
jupyter>=1.0
```

---

## What You Will Learn

By working through this tutorial you will be able to:

- Explain what a support vector machine does and why the **margin** matters
- Describe the **kernel trick** and when to reach for Linear, Polynomial, or RBF kernels
- Understand scikit-learn's **one-vs-one multi-class strategy** used by SVC
- Tune the **C** and **gamma** hyperparameters correctly using `GridSearchCV`
- State **Mercer's condition** and verify it numerically with numpy
- Implement a **custom Laplacian (L1-RBF) kernel** using scikit-learn's `precomputed` API

---

## Figure Index

All figures are saved to `figures/` when the notebook is run.

| File | Figure | Section |
|------|--------|---------|
| `fig1_margin.png` | Decision boundary, margin & support vectors (toy data) | s2 |
| `fig2_kernels_boundary.png` | Decision boundaries for three kernels on the Moons dataset | s4 |
| `fig3_wine_scatter.png` | Wine dataset scatter: Alcohol vs Flavanoids | s5 |
| `fig4_accuracy_comparison.png` | Train/test accuracy comparison  five kernel configurations | s8 |
| `fig5_rbf_heatmap.png` | RBF accuracy heatmap: C vs gamma | s9 |
| `fig6_standardisation_effect.png` | Effect of skipping StandardScaler (try-it exercise) | s6 |
| `fig7_all_kernels_comparison.png` | All kernels compared including custom Laplacian | s13 |
| `fig8_confusion_matrix.png` | Confusion matrix for the best-tuned RBF SVM | s11 |

---

## Tutorial vs Notebook

The **PDF tutorial** (`SVM_Kernel_Tutorial.pdf`) covers the core narrative (sections 1–9)
and is written for a general audience. It stays under 2000 words and is designed to be
read standalone with all figures embedded.

The **Jupyter notebook** (`svm_kernel_tutorial.ipynb`) goes further and includes all
intermediate steps:

- Section 6: **Try-it-yourself exercise** what happens if you forget to standardise?
  (Figure 6, not in the PDF)
- Sections 12–13: Mercer's condition and a custom Laplacian kernel built from scratch
- Numerical PSD verification of the Gram matrix via eigenvalue decomposition
- Manual stratified cross-validation for the precomputed kernel (GridSearchCV does not
  support varying-gamma precomputed kernels, so this is handled by hand)

---

## Accessibility

The following steps have been taken to make this tutorial accessible:

### Figures
- All figures use a **colourblind-friendly palette** (Wong, 2011) with distinct
  shapes/markers so that colour is never the only visual channel carrying information.
  For example, the three wine cultivars use blue circles, orange squares, and green
  triangles distinguishable by shape alone.
- The heatmap (Figure 5) uses the **cividis** colormap, which is perceptually uniform and
  readable under deuteranopia and protanopia (Nuñez et al., 2018). Numeric values are
  printed in every cell so the chart is readable in greyscale.
- Every figure code cell prints a descriptive **alt-text caption** to the cell output,
  summarising what the figure shows for readers using screen readers or who cannot
  see the image.
- All figure titles are prefixed with their figure number (e.g. "Figure 3") so
  cross-references in the text are unambiguous.

### Notebook
- Markdown cells use **semantic heading structure** (H2/H3) for screen-reader
  compatibility.
- The table of contents in Cell 0 uses **anchor links** to each section heading.
- A **Figure Index table** in Cell 0 maps every figure number to its section,
  so a reader can navigate directly to any figure.

### PDF
- Body font: minimum **12pt**, high-contrast black-on-white text.
- Figure labels and annotations: minimum **9pt**.
- All figures include **descriptive alt-text captions** in the figure caption text.
- Figure numbering is consistent with the notebook Figure Index.

---

## References

- Cortes, C. & Vapnik, V. (1995). Support-vector networks. *Machine Learning*, 20(3), 273–297.
- Aeberhard, S. et al. (1992). Wine Data Set. UCI Machine Learning Repository.
- Pedregosa, F. et al. (2011). Scikit-learn. *JMLR*, 12, 2825–2830.
- Hsu, C-W., Chang, C-C. & Lin, C-J. (2016). A practical guide to SVC. NTU.
- Schölkopf, B. & Smola, A. J. (2002). *Learning with Kernels*. MIT Press.
- Wong, B. (2011). Points of view: Color blindness. *Nature Methods*, 8(6), 441.
- Nuñez, J.R. et al. (2018). Optimizing colormaps with consideration for color vision
  deficiency. *PLOS ONE*, 13(7), e0199239.

---

## License

This project is licensed under the **MIT License**  see [LICENSE](LICENSE) for details.
You are free to use, adapt, and redistribute this tutorial and code with attribution.
