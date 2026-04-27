# Credit Applicant Analysis Using Principal Component Analysis (PCA)

**Author:** Erin Weiss
[Portfolio](https://erin-weiss.github.io/index.html) | [LinkedIn](https://www.linkedin.com/in/erinweiss3/) | [GitHub](https://github.com/Erin-Weiss)

[View the Full Interactive Report](https://erin-weiss.github.io/articles/credit-pca.html) | [Live GitHub Page](https://erin-weiss.github.io/PCA-Credit-Analysis/)

---

## Objective

Identify the primary drivers of variance among 400 credit applicants by applying Principal Component Analysis (PCA) to six financial and demographic features: Income, Credit Limit, Rating, Cards, Age, and Education. The analysis produces a low-dimensional representation of the data that reveals latent structure in applicant profiles and can inform downstream segmentation or modeling.

---

## Dataset

| Property | Detail |
|----------|--------|
| Source | CreditShort.csv |
| Observations | 400 credit applicants |
| Features | Income, Limit, Rating, Cards, Age, Education |
| Target Variable | Unsupervised (no target) |

---

## Methodology

1. **Data Preparation** — Loaded and inspected the dataset for completeness and summary statistics.
2. **Standardization** — Applied `scale = TRUE` within `prcomp()` to normalize all features to unit variance, preventing high-magnitude variables from dominating the principal components.
3. **PCA Computation** — Extracted six principal components and their associated loading vectors.
4. **Variance Analysis** — Computed the Proportion of Variance Explained (PVE) for each component to determine dimensionality reduction potential.
5. **Visualization** — Generated biplots of PC1 vs. PC2 to examine variable correlations and applicant clustering in the reduced feature space.

---

## Results

| Component | Variance Explained | Cumulative | Key Drivers |
|-----------|-------------------|------------|-------------|
| PC1 | 45.88% | 45.88% | Income, Limit, Rating |
| PC2 | 17.61% | 63.49% | Cards, Age, Education (inverse) |

**Key findings:**

- PC1 captures a "financial capacity" axis — Income, Credit Limit, and Rating load heavily and positively, forming a tightly correlated cluster.
- PC2 captures a "demographic/behavioral" axis — Cards and Age load positively, while Education loads negatively, indicating an inverse relationship between education level and number of cards held.
- The first two components retain over 63% of total variance, providing a meaningful two-dimensional summary of the original six-feature space.
- Biplot analysis confirms clear separation between financial capacity variables and demographic variables, supporting the interpretability of the reduced representation.

---

## Tech Stack

| Category | Tool |
|----------|------|
| Language | R |
| Core Library | tidyverse |
| PCA Implementation | `prcomp()` (base R) |
| Reporting | Quarto (.qmd) rendered to HTML |

---

## Repository Structure

```
PCA-Credit-Analysis/
├── data/
│   └── CreditShort.csv                          # Source dataset
├── credit_pca_case_study.qmd                     # Quarto analysis notebook
├── docs/
│   ├── credit_pca_case_study_files/              # Rendered figures and assets
│   └── index.html                                # Rendered HTML report (GitHub Pages)
└── README.md
```

---

## How to Reproduce

```bash
git clone https://github.com/Erin-Weiss/PCA-Credit-Analysis.git
cd PCA-Credit-Analysis
```

Open `credit_pca_case_study.qmd` in RStudio and render with Quarto. The notebook contains the full analysis pipeline including data inspection, PCA computation, loading vector interpretation, biplot generation, and variance decomposition. Requires R with the `tidyverse` package installed.

---

## Future Work

- Apply PCA-transformed features as inputs to supervised models (e.g., logistic regression, random forest) for credit risk classification.
- Compare PCA results with alternative dimensionality reduction techniques such as t-SNE or UMAP.
- Extend the analysis to the full Credit dataset with additional features.
