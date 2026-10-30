# DSCI 552 Homework 5

Homework 5 studies regularized regression and interpretable decision trees. It
combines a Communities and Crime regression problem with a compact acute
inflammations classification task, highlighting model selection, sparsity, and
interpretability.

## Contents

```text
assignment-05/
├── README.md
├── Homework5.pdf
├── data/
│   ├── communities.data
│   ├── communities.names
│   ├── diagnosis.data
│   └── diagnosis.names
└── notebooks/
    ├── Aggarwal_Pratham_HW5_CaC.ipynb
    └── Aggarwal_Pratham_HW5_AI.ipynb
```

## Part 1: LASSO and Boosting for Regression

`Aggarwal_Pratham_HW5_CaC.ipynb` analyzes the Communities and Crime dataset,
which records community-level demographic, socioeconomic, and policing features
alongside a violent-crime rate target. The notebook starts by parsing the
`.names` metadata file, loading the raw data, and checking missing values.

It then covers:

- **Exploratory analysis:** correlation heatmaps, coefficient-of-variation
  screening, and scatter/box plots for the strongest candidate predictors.
- **Baseline regression:** ordinary least squares as a benchmark.
- **Regularized linear models:** ridge regression and LASSO, including
  standardization choices and coefficient shrinkage.
- **Dimension reduction:** principal components regression as a comparison to
  penalized linear methods.
- **Boosted trees:** an XGBoost regression model with regularization to compare
  a nonlinear tree-based approach against the linear models.

The workflow emphasizes how correlated predictors, missing values, and model
complexity affect performance and interpretation in a high-dimensional
regression setting.

## Part 2: Decision Trees as Interpretable Models

`Aggarwal_Pratham_HW5_AI.ipynb` analyzes the Acute Inflammations dataset, a
small classification problem with six clinical indicators and a joint diagnosis
label for bladder inflammation and nephritis.

The notebook fits a decision tree to the full dataset, converts it into
IF-THEN-style rules, and then applies cost-complexity pruning to obtain a more
interpretable and stable tree. The emphasis is on balancing prediction accuracy
with model simplicity: the final pruned tree is easier to inspect while still
capturing the decision logic behind the diagnoses.

## Running the Notebooks

Open either notebook in Jupyter or VS Code and run it with the working
directory set to `assignment-05/notebooks/`, so the relative `../data` path
resolves correctly. The data files are stored in `assignment-05/data/`.

Install the shared project dependencies from the repository root with:

```bash
python -m pip install -r requirements.txt
```
