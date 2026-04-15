# Contributing to the ML Algorithm Selection Framework

Thank you for your interest in contributing. This project aims to be the most rigorous, accurate, and accessible ML reference repository on GitHub, aligned with the companion research paper.

---

## How to Contribute

### Reporting Issues

Open an issue at the repository if you find:

- **Math errors** — incorrect equations, wrong derivations, inconsistent notation with the paper
- **Code errors** — cells that produce errors, incorrect sklearn API usage, deprecated parameters
- **Interpretation errors** — misleading or inaccurate explanations of algorithm behavior
- **Outdated content** — deprecated sklearn parameters or APIs (target: scikit-learn >= 1.0)
- **Suggestions** — better case studies, clearer visualizations, missing algorithms from the paper

### Submitting Changes

1. **Fork** the repository
2. **Create a branch** with a descriptive name:
   ```bash
   git checkout -b fix/svm-kernel-math
   git checkout -b feat/add-catboost-section
   git checkout -b docs/improve-gnn-explanation
   ```
3. **Make your changes** and verify all cells run without errors
4. **Commit** with a clear, structured message:
   ```bash
   git commit -m "Fix: correct SVM soft-margin dual formulation in Notebook 1"
   git commit -m "Add: CatBoost section with ordered boosting explanation"
   ```
5. **Push** and open a **Pull Request** with a description of what changed and why

---

## Contribution Priority

| Type | Priority | Notes |
|---|---|---|
| Fix math / derivation errors | High | Must match notation in the companion paper |
| Fix broken or incorrect code | High | All cells must run top-to-bottom without errors |
| Fix misleading interpretations | High | Explanations must be technically defensible |
| Improve clarity of explanations | Medium | Follow the What / Math / When / Case Study / Interpretation structure |
| Add missing algorithms from the paper | Medium | GNNs, Causal ML variants, Neural ODE extensions |
| Improve visualizations | Low | Must add information not conveyed by existing plots |
| Add new case studies | Low | Must use sklearn datasets or synthetic data — no downloads |
| Translations | Low | Contact maintainers first to coordinate |

---

## Code Style

### Python

```python
# Use descriptive variable names
X_train, X_test, y_train, y_test = train_test_split(...)   # correct
x, xt, y, yt = train_test_split(...)                        # avoid

# Section headers in code cells
# -- Load Data ----------------------------------------------------------
# -- Train Model --------------------------------------------------------
# -- Evaluate -----------------------------------------------------------

# Keep each code cell focused on one logical task
# One cell: load and split data
# Next cell: train and evaluate
# Next cell: visualize

# Always include print() for key results so output is visible
print(f"Test AUC-ROC: {auc_score:.4f}")

# Use SEED = 42 and np.random.seed(SEED) at the top of every notebook
```

### Markdown Cells

- Use LaTeX for all math: `$\hat{y}$` not `y_hat`, `$$\mathcal{L}$$` for display equations
- Follow the algorithm section template:
  1. Mathematical Foundation (equations + complexity)
  2. Key Hyperparameters (table with recommended ranges)
  3. When to Use / Avoid (two-row table with conditions)
  4. Case Study (working code)
  5. Interpretation (bullets explaining the output)
- Include tables for structured comparisons — avoid long prose lists

### Notation Consistency

All notation must match the companion paper (see Appendix B: Notation Summary):

| Symbol | Meaning |
|---|---|
| $n$ | Number of training samples |
| $d$ | Input feature dimensionality |
| $K$ | Number of classes or HMM states |
| $k$ | Number of clusters or components |
| $\mathbf{w} \in \mathbb{R}^d$ | Weight (parameter) vector |
| $\mathcal{L}$ | Loss function |
| $\hat{R}(f)$ | Empirical risk |
| $R(f)$ | Expected risk |

---

## Testing Requirements

Before submitting a pull request, verify that:

- [ ] All cells in the modified notebook run top-to-bottom with **Kernel > Restart & Run All** (no errors)
- [ ] No local file paths are used — all data from `sklearn.datasets` or generated synthetically
- [ ] Random seeds are fixed (`SEED = 42`, `np.random.seed(SEED)`, `random_state=SEED`)
- [ ] Print output is informative but not excessively verbose (no more than ~30 lines per cell)
- [ ] Visualizations have axis labels, titles, and legends
- [ ] Optional-package imports use `try/except` with a clear install instruction in the fallback
- [ ] Math notation matches the companion paper

---

## Code of Conduct

- Be respectful and constructive in all interactions
- Focus feedback on the content, not the contributor
- Assume good intent when someone asks a question or submits a rough draft
- Attribute ideas and code correctly

---

Thank you for helping make rigorous machine learning education more accessible.
