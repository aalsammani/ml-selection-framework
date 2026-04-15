# Machine-Learning Algorithm Selection Framework

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3%2B-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg)](CONTRIBUTING.md)

**Companion repository to:**
> *A Reproducible Framework for Machine Learning Algorithm Selection: Theory, Algorithms, and Practice*
> 
> Abdallah Alsammani — Delaware State University

Six comprehensive Jupyter notebooks covering every major machine learning algorithm with rigorous mathematical foundations, working code, visualizations, and real-world case studies. Every notebook runs end-to-end with no external file dependencies.

---

## Notebooks

### Notebook 1 — Supervised Learning
`notebooks/Supervised_Learning_Complete_Guide.ipynb`

| # | Algorithm | Type | Case Study |
|---|---|---|---|
| 1 | Linear Regression (OLS, Ridge, Lasso, Elastic Net) | Regression | Diabetes progression |
| 2 | Logistic Regression | Classification | Breast cancer diagnosis |
| 3 | Decision Tree | Both | Iris species + overfitting curves |
| 4 | Random Forest | Both | Wine classification + insurance cost regression |
| 5 | Gradient Boosting | Both | DT vs RF vs GBM with learning curves |
| 6 | Stacking / Blending | Both | Multi-model ensemble on breast cancer |
| 7 | Support Vector Machine | Both | Iris — 3 kernels + decision boundaries |
| 8 | k-Nearest Neighbors | Both | Diabetes — optimal k + distance metrics |
| 9 | Naive Bayes | Classification | Wine multi-class |
| 10 | Full Model Comparison | Classification | All algorithms — ROC, PR, calibration, CV box plots |

### Notebook 2 — Unsupervised Learning
`notebooks/Unsupervised_Learning_Complete_Guide.ipynb`

| # | Algorithm | Task | Case Study |
|---|---|---|---|
| 1 | K-Means | Clustering | Customer segmentation (elbow + silhouette) |
| 2 | Hierarchical Clustering | Clustering | Iris recovery — 4 linkage methods + dendrogram |
| 3 | DBSCAN | Clustering | Moons / rings vs K-Means — k-distance plot |
| 4 | Gaussian Mixture Models | Probabilistic clustering | Iris soft clustering — BIC/AIC |
| 5 | PCA | Dimensionality reduction | Breast cancer 30 to 2 features — scree + loadings |
| 6 | t-SNE and UMAP | Visualization | Wine — perplexity / n_neighbors sensitivity |
| 7 | Isolation Forest + LOF | Anomaly detection | Simulated fraud detection |
| 8 | Apriori (from scratch) | Association rules | Grocery basket — lift, confidence, support |
| 9 | Full Clustering Comparison | Clustering | 4 algorithms x 3 geometries |

### Notebook 3 — Probabilistic Graphical Models
`notebooks/Probabilistic_Models_Guide.ipynb`

| # | Algorithm | Case Study |
|---|---|---|
| 1 | Bayesian Networks | Alarm network — exact inference by enumeration |
| 2 | Hidden Markov Models | Financial regime detection (bull / bear markets) |

### Notebook 4 — Time-Series Forecasting
`notebooks/Time_Series_Guide.ipynb`

| # | Algorithm | Case Study |
|---|---|---|
| 1 | ARIMA | Monthly sales — ADF test, model selection, walk-forward validation |
| 2 | Prophet | Weekly retail with changepoints and seasonality decomposition |
| 3 | Neural ODE | Irregularly sampled physiological signals |
| 4 | Walk-Forward Validation | Correct temporal CV protocol |

### Notebook 5 — Evaluation Framework
`notebooks/Evaluation_Framework_Guide.ipynb`

| # | Topic | Content |
|---|---|---|
| 1 | Classification metrics | Accuracy, F1, MCC, AUC-ROC, AUC-PR, Log Loss, ECE — imbalance failure demonstration |
| 2 | Regression metrics | MSE, RMSE, MAE, R2, sMAPE — residual plots |
| 3 | Cross-validation design | Stratified k-fold, nested CV, temporal CV — optimistic bias quantification |
| 4 | Statistical significance | Paired t-test, Wilcoxon, Friedman + Nemenyi, Bonferroni, Cohen's d |
| 5 | Fairness assessment | Demographic parity, equal opportunity, equalized odds — disparate impact |

### Notebook 6 — Advanced Methods
`notebooks/Advanced_Methods_Guide.ipynb`

| # | Topic | Content |
|---|---|---|
| 1 | Causal ML | ATE / CATE, T-Learner, Double ML (cross-fitting), CATE heterogeneity |
| 2 | Graph Neural Networks | Message passing, GCN layer implementation, ring vs chain demonstration |
| 3 | AutoML / HPO | Random search vs Optuna TPE — convergence + hyperparameter importance |
| 4 | Consolidated guide | Full algorithm taxonomy across all 6 notebooks |

---

## Quick Start

### Run Locally

```bash
# 1. Clone
git clone https://github.com/alsammani/ml-selection-framework.git
cd ml-selection-framework

# 2. Create and activate a virtual environment
python -m venv venv
source venv/bin/activate           # Linux / macOS
venv\Scripts\activate              # Windows

# 3. Install core dependencies (Notebooks 1, 2, 5)
pip install -r requirements.txt

# 4. Install optional extended dependencies (Notebooks 3, 4, 6)
pip install -r requirements_extended.txt

# 5. Launch Jupyter
jupyter notebook
```

Open any notebook from the `notebooks/` folder and select **Kernel > Restart & Run All**.

### Run in Google Colab

| Notebook | Link |
|---|---|
| 1. Supervised Learning | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alsammani/ml-selection-framework/blob/main/notebooks/Supervised_Learning_Complete_Guide.ipynb) |
| 2. Unsupervised Learning | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alsammani/ml-selection-framework/blob/main/notebooks/Unsupervised_Learning_Complete_Guide.ipynb) |
| 3. Probabilistic Models | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alsammani/ml-selection-framework/blob/main/notebooks/Probabilistic_Models_Guide.ipynb) |
| 4. Time-Series | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alsammani/ml-selection-framework/blob/main/notebooks/Time_Series_Guide.ipynb) |
| 5. Evaluation Framework | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alsammani/ml-selection-framework/blob/main/notebooks/Evaluation_Framework_Guide.ipynb) |
| 6. Advanced Methods | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alsammani/ml-selection-framework/blob/main/notebooks/Advanced_Methods_Guide.ipynb) |

> Replace `alsammani` with your GitHub username before publishing.

---

## Repository Structure

```
ml-selection-framework/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── SETUP.md
├── requirements.txt              # Core (Notebooks 1, 2, 5)
├── requirements_extended.txt     # Optional (Notebooks 3, 4, 6)
└── notebooks/
    ├── Supervised_Learning_Complete_Guide.ipynb
    ├── Unsupervised_Learning_Complete_Guide.ipynb
    ├── Probabilistic_Models_Guide.ipynb
    ├── Time_Series_Guide.ipynb
    ├── Evaluation_Framework_Guide.ipynb
    └── Advanced_Methods_Guide.ipynb
```

---

## Dependencies

**Core** (required for Notebooks 1, 2, 5 — all standard packages):

| Package | Version |
|---|---|
| Python | 3.8+ |
| NumPy | >= 1.21 |
| Pandas | >= 1.3 |
| Matplotlib | >= 3.4 |
| Seaborn | >= 0.11 |
| scikit-learn | >= 1.0 |
| SciPy | >= 1.7 |
| Jupyter / notebook | >= 1.0 / 6.4 |

**Extended** (optional, Notebooks 3, 4, 6 — graceful fallbacks if absent):

| Package | Notebook | Feature |
|---|---|---|
| `statsmodels` | 4 | ARIMA fitting and diagnostics |
| `prophet` | 4 | Decomposable trend-seasonality forecasting |
| `hmmlearn` | 3 | Hidden Markov Models |
| `optuna` | 6 | TPE-based hyperparameter optimization |
| `umap-learn` | 2 | UMAP dimensionality reduction |

---

## Algorithm Section Structure

Every algorithm in every notebook follows the same pattern:

1. **Mathematical Foundation** — formal equations with derivations and complexity bounds
2. **Key Hyperparameters** — what they control, recommended ranges
3. **When to Use / Avoid** — conditions from the companion paper
4. **Case Study** — working code on a scikit-learn dataset
5. **Interpretation** — what the output means and next steps

No dataset downloads or API keys are required. All data comes from `sklearn.datasets` or is generated synthetically.

---

## Citation

```bibtex
@article{alsammani2026mlselection,
  title       = {A Reproducible Framework for Machine Learning Algorithm Selection:
                 Theory, Algorithms, and Practice},
  author      = {Alsammani, Abdallah},
  year        = {2026},
  institution = {Delaware State University}
}
```

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for issue reporting and pull request guidelines.

## License

MIT License. See [LICENSE](LICENSE) for details.
