# 💳 Credit Analysis PCA Analysis

**Author:** Erin Weiss  
👉 [**R Credit Analysis PCA Project (Interactive HTML Report)**](https://erin-weiss.github.io/articles/credit-pca.html)

---

## 📘 Overview

This project performs a **Principal Component Analysis (PCA)** on a credit applicant dataset containing 400 observations.  
The goal is to understand how key financial and demographic variables—**Income, Credit Limit, Rating, Cards, Age, and Education**—relate to one another and drive variation across applicants.

This analysis uncovers underlying patterns in applicant financial behavior and provides a dimensionality-reduced view of the dataset.

---

## ⚙️ Approach

Using **R**, I conducted a full PCA workflow to identify the strongest contributors to variance.  
Key steps included:

- Importing and examining the *CreditShort* dataset  
- Performing PCA with standardized variables (`scale = TRUE`)  
- Interpreting **loading vectors** for all principal components  
- Creating **biplots** to visualize applicants and variable correlations  
- Computing the **Proportion of Variance Explained (PVE)**  
- Summarizing insights from PC1 and PC2  

---

## 📊 Key Insights

- **PC1 explains ~46%** of total variance, driven by **Income**, **Credit Limit**, and **Rating**  
- **PC2 explains ~18%**, driven by **Cards** and **Age**, and negatively associated with **Education**  
- Combined, the first two components explain **~63%** of the variation  
- **Income, Limit, Rating** form a strong positive correlation cluster  
- **Education** and **Cards** show a negative correlation  
- PCA reveals clear separation between financial capacity variables and demographic/behavioral variables  

---

## 🧰 Tools Used

- **Language:** R  
- **Libraries:**  
  - `tidyverse`  
- **Reporting:** Quarto (`.qmd`) → HTML

---

## 🔗 Links

- **Live Github Page:** [Github Page](https://erin-weiss.github.io/PCA-Credit-Analysis/)
- **GitHub Repository:** [View Source Code](https://github.com/Erin-Weiss/PCA-Credit-Analysis)
- **Portfolio Page:** [View on Portfolio](https://erin-weiss.github.io/articles/credit-pca.html)

