# ML Selection Framework: Companion Notebooks

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19599148.svg)](https://doi.org/10.5281/zenodo.19599148)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**Companion repository for the article**

> A. Alsammani, *Machine Learning Algorithm Selection: A Unified Framework from Classical Methods to Foundation Models*, submitted to the *Journal of Intelligent & Fuzzy Systems*, 2026.

The repository contains six Jupyter notebooks that illustrate the methods, selection guidelines, and evaluation protocol described in the article. They are educational examples: the article reports no experimental results, and the numbers produced by the notebooks are illustrations, not evidence for the article's recommendations.

---

## Repository contents

All files are at the top level of the repository (there is no `notebooks/` subfolder).

```
ml-selection-framework/
├── README.md
├── SETUP.md                                   # detailed installation and troubleshooting
├── CONTRIBUTING.md
├── LICENSE
├── requirements.txt                           # core packages (Notebooks 1, 2, 5)
├── requirements_extended.txt                  # optional packages (Notebooks 3, 4, 6)
├── Supervised_Learning_Complete_Guide.ipynb   # Notebook 1
├── Unsupervised_Learning_Complete_Guide.ipynb # Notebook 2
├── Probabilistic_Models_Guide.ipynb           # Notebook 3
├── Time_Series_Guide.ipynb                    # Notebook 4
├── Evaluation_Framework_Guide.ipynb           # Notebook 5
├── Advanced_Methods_Guide.ipynb               # Notebook 6
└── model_comparison.png                       # figure written by Notebook 1
```

| # | Notebook | Topics | Data |
|---|---|---|---|
| 1 | `Supervised_Learning_Complete_Guide.ipynb` | Linear models (OLS, Ridge, Lasso, Elastic Net), logistic regression, decision trees, random forests, gradient boosting, stacking, SVM, k-NN, naive Bayes, model comparison | Diabetes, Breast Cancer Wisconsin, Iris, Wine (scikit-learn); synthetic insurance-style data |
| 2 | `Unsupervised_Learning_Complete_Guide.ipynb` | k-means, hierarchical clustering, DBSCAN, Gaussian mixtures, PCA, Isolation Forest/LOF, Apriori, clustering comparison; t-SNE and UMAP are explained in text only (no code example) | Iris, Breast Cancer (scikit-learn); synthetic data |
| 3 | `Probabilistic_Models_Guide.ipynb` | Bayesian networks (exact inference by enumeration), hidden Markov models | Synthetic data |
| 4 | `Time_Series_Guide.ipynb` | ARIMA, Prophet, Neural ODE concepts (illustrated with a parametric ODE fit; no PyTorch required), walk-forward validation | Synthetic data |
| 5 | `Evaluation_Framework_Guide.ipynb` | Classification and regression metrics, stratified and nested cross-validation, paired tests including the Nadeau–Bengio corrected resampled *t*-test, Wilcoxon and Friedman tests with Bonferroni correction, group-fairness metrics | Breast Cancer, Diabetes, Iris (scikit-learn); synthetic data |
| 6 | `Advanced_Methods_Guide.ipynb` | Causal ML (T-learner, double ML with cross-fitting), graph neural network message passing (NumPy), hyperparameter optimization (random search vs. Optuna TPE), consolidated selection guide | Breast Cancer (scikit-learn); synthetic data |

**Data.** The scikit-learn datasets above ship with scikit-learn and need no download; all other data are generated inside the notebooks with fixed random seeds. No notebook requires network access, API keys, or local data files. (Version 1.0.0 tried to download an insurance CSV from a third-party URL that no longer exists and therefore always used its synthetic fallback; the download attempt has been removed and the same synthetic data are now generated directly.)

---

## Quick start

Requires Python 3 and Git. Tested with Python 3.12 on Windows 11 using the commands below (see [Tested environment](#tested-environment)).

```bash
git clone https://github.com/aalsammani/ml-selection-framework.git
cd ml-selection-framework

python -m venv venv
source venv/bin/activate        # Linux / macOS
# venv\Scripts\activate         # Windows (Command Prompt or PowerShell)

pip install -r requirements.txt            # core: enough for Notebooks 1, 2, 5
pip install -r requirements_extended.txt   # optional: statsmodels, prophet, hmmlearn, optuna, umap-learn

jupyter notebook
```

Open a notebook from the repository folder and choose **Kernel > Restart Kernel and Run All Cells**.

To run every notebook without opening a browser:

```bash
jupyter nbconvert --to notebook --execute --output-dir executed *.ipynb
```

Without the extended packages, all six notebooks still run to completion: each optional import is wrapped in `try/except`, a missing package triggers an installation hint, and the analyses that need it (ARIMA and Prophet in Notebook 4, the hidden Markov model in Notebook 3, Optuna in Notebook 6) are skipped. Notebook 2 imports `umap-learn` but contains no UMAP code cell, so nothing is skipped there. PyTorch and PyTorch Geometric are not required.

See [SETUP.md](SETUP.md) for Google Colab instructions and troubleshooting.

---

## Tested environment

All six notebooks were executed end to end with `jupyter nbconvert --execute` (nbclient 0.11) in fresh virtual environments created with the commands above, on Windows 11 with Python 3.12.12, in October 2026:

| Environment | Result |
|---|---|
| `requirements.txt` + `requirements_extended.txt` | 6/6 notebooks completed without errors (a few minutes in total) |
| `requirements.txt` only | 6/6 notebooks completed without errors; optional sections skipped as described above |

Principal package versions resolved at the time: numpy 2.5.4, pandas 3.1.0, scikit-learn 1.9.1, scipy 1.18.1, matplotlib 3.11.2, seaborn 0.13.2, statsmodels 0.15.0, prophet 1.5.0, hmmlearn 0.3.3, optuna 5.0.0, umap-learn 0.5.12. The requirement files specify minimum versions only, so newer releases may be installed; other Python versions are expected to work but were not tested.

---

## Archived version and citation

Version 1.0.0 of this repository is archived on Zenodo: <https://doi.org/10.5281/zenodo.19599148>. The concept DOI <https://doi.org/10.5281/zenodo.19599147> always resolves to the most recent archived version.

```bibtex
@misc{alsammani2026mlframework,
  author    = {Alsammani, Abdallah},
  title     = {Machine Learning Selection Framework},
  howpublished = {Zenodo software repository},
  version   = {1.0.0},
  year      = {2026},
  doi       = {10.5281/zenodo.19599148},
  note      = {Companion repository for ``Machine Learning Algorithm Selection: A Unified Framework from Classical Methods to Foundation Models''}
}
```

---

## Contributing and license

See [CONTRIBUTING.md](CONTRIBUTING.md) for reporting issues and submitting changes. The code is released under the MIT License; see [LICENSE](LICENSE).
