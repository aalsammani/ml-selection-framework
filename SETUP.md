# Setup Guide

## Prerequisites

| Tool | Version | Download |
|---|---|---|
| Python | 3.8+ | https://www.python.org/downloads/ |
| pip | (bundled with Python) | Verify with `pip --version` |
| Git | any | https://git-scm.com/downloads |

---

## Installation

### Step 1 — Clone the Repository

```bash
git clone https://github.com/alsammani/ml-selection-framework.git
cd ml-selection-framework
```

### Step 2 — Create a Virtual Environment (Recommended)

```bash
python -m venv venv

# Activate on Linux / macOS
source venv/bin/activate

# Activate on Windows (Command Prompt)
venv\Scripts\activate

# Activate on Windows (PowerShell)
venv\Scripts\Activate.ps1
```

### Step 3 — Install Core Dependencies

Required for Notebooks 1, 2, and 5:

```bash
pip install -r requirements.txt
```

### Step 4 — Install Extended Dependencies (Optional)

Required for Notebooks 3, 4, and 6. All notebooks include graceful fallbacks
if these packages are absent, so this step is optional:

```bash
pip install -r requirements_extended.txt
```

Individual packages:

```bash
pip install statsmodels        # Notebook 4: ARIMA
pip install prophet            # Notebook 4: Prophet forecasting
pip install hmmlearn           # Notebook 3: Hidden Markov Models
pip install optuna             # Notebook 6: Bayesian HPO
pip install umap-learn         # Notebook 2: UMAP visualization
```

### Step 5 — Launch Jupyter

```bash
jupyter notebook
```

Navigate to the `notebooks/` folder in the browser tab that opens and click any notebook.
To run all cells: **Kernel > Restart & Run All**.

---

## Running in Google Colab

No local installation required:

1. Go to [colab.research.google.com](https://colab.research.google.com/)
2. Click **File > Open Notebook > GitHub**
3. Paste the repository URL
4. Select the notebook you want to run

Core packages (NumPy, pandas, sklearn, matplotlib, seaborn, scipy) are pre-installed in Colab.
For extended packages, add a cell at the top of the notebook:

```python
!pip install statsmodels prophet hmmlearn optuna umap-learn -q
```

---

## Verifying the Installation

Run this in a Python shell or Jupyter cell to confirm core packages are installed:

```python
import numpy, pandas, matplotlib, seaborn, sklearn, scipy
print(f"numpy     {numpy.__version__}")
print(f"pandas    {pandas.__version__}")
print(f"sklearn   {sklearn.__version__}")
print(f"scipy     {scipy.__version__}")
print("Core packages installed successfully.")
```

For extended packages:

```python
packages = ["statsmodels", "prophet", "hmmlearn", "optuna", "umap"]
for pkg in packages:
    try:
        mod = __import__(pkg)
        ver = getattr(mod, "__version__", "ok")
        print(f"{pkg:<15} {ver}")
    except ImportError:
        print(f"{pkg:<15} NOT INSTALLED  (pip install {pkg})")
```

---

## Troubleshooting

| Issue | Solution |
|---|---|
| `ModuleNotFoundError` for core package | Run `pip install -r requirements.txt` with venv active |
| `ModuleNotFoundError` for extended package | Run `pip install <package>` or see graceful fallback in notebook |
| Jupyter not found | Run `pip install jupyter notebook` |
| Plots not displaying | Add `%matplotlib inline` in the first code cell |
| Permission error on Linux / macOS | Run `pip install --user -r requirements.txt` |
| `prophet` install fails | Try `conda install -c conda-forge prophet` or see prophet docs |
| `hmmlearn` install fails | Try `pip install hmmlearn --no-build-isolation` |
| Slow UMAP on first run | Normal — UMAP compiles numba kernels on first call |
| Kernel dies during GBM training | Reduce `n_estimators` or use LightGBM instead |

---

## Recommended Notebook Order

| Notebook | Prerequisite knowledge |
|---|---|
| 1. Supervised Learning | Python basics, linear algebra basics |
| 2. Unsupervised Learning | Notebook 1 (optional but helpful) |
| 3. Probabilistic Models | Probability theory basics |
| 4. Time-Series | Notebook 1 (regression) |
| 5. Evaluation Framework | Notebooks 1 and 2 |
| 6. Advanced Methods | Notebooks 1, 2, and 5 recommended |

Notebooks 1 and 2 are fully self-contained and the best starting points.
Notebooks 3, 4, and 6 assume familiarity with standard supervised/unsupervised learning.
Notebook 5 (Evaluation) can be read independently as a standalone reference.
