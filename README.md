# Protein Tissue Specificity Prediction via Supervised Learning

## Project Overview
This project focuses on the classification of human tissue types based on transcriptomic protein expression profiles. Using data derived from the **Human Protein Atlas**, the goal is to predict the tissue origin of a sample based on its molecular signature.

This work demonstrates the application of **High-Dimensional Statistics** and **Machine Learning** to bioinformatics, addressing the "$p \gg n$" problem (feature space significantly larger than sample size) typical in omics data.

## Key Results
* **Best Model Accuracy:** **99.15%** (Support Vector Machine)
* **Dimensionality Reduction:** Reduced feature space from **4,269** genes down to **923** key biomarkers using Lasso penalization.

## Methodology

### 1. Data Preprocessing
* **Dataset:** Expression levels of >4,000 proteins across 53 tissue types (e.g., Liver, Kidney, Brain).
* **Cleaning:** Parsing of custom-separated data and removal of non-numeric metadata.
* **Standardization:** Applied `StandardScaler` to normalize expression levels.

### 2. Feature Selection (Sparse Modeling)
Given the high dimensionality of the data, a **Lasso (L1-penalized) Logistic Regression** was implemented.
* The L1 penalty forces coefficients of non-informative genes to zero.
* **Result:** Efficient identification of a subset of 923 genes sufficient to discriminate between tissue types.

### 3. Classification Models
Two supervised learning algorithms were benchmarked on the selected features:
1.  **Support Vector Machine (SVM):** Using a linear kernel.
    * *Performance:* **99.15% Accuracy**.
    * *Analysis:* Linear boundaries proved highly effective in the reduced high-dimensional space.
2.  **K-Nearest Neighbors (KNN):** With $k=3$.
    * *Performance:* **93.84% Accuracy**.

## Tools & Libraries
* **Python**
* **Scikit-learn** (SVC, KNeighborsClassifier, LogisticRegression, SelectFromModel)
* **Pandas / NumPy** for data manipulation.
* **Seaborn** for visualization.

## Repository Structure
* `analysis_notebook.ipynb`: Jupyter Notebook containing the full pipeline (Data loading, Lasso selection, Model evaluation).
* `tissue_data.zip`: Compressed dataset containing the protein expression profiles.

## References
* Methodology inspired by the Human Protein Atlas and advanced statistical learning courses (University of Strasbourg, Master Statistics).

