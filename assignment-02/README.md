# DSCI 552 Homework 2

Homework 2 combines a regression analysis of the Combined Cycle Power Plant
(CCPP) data with written exercises from *An Introduction to Statistical
Learning* (ISLR).

## Contents

```text
assignment-02/
├── README.md
├── Homework2.pdf
├── data/
│   ├── Folds5x2_pp.xlsx
│   ├── Folds5x2_pp.ods
│   └── Readme.txt
└── notebooks/
    ├── Aggarwal_Pratham_HW2_CCPP.ipynb
    └── Aggarwal_Pratham_HW2_ISLR.ipynb
```

## Part 1: Combined Cycle Power Plant

`Aggarwal_Pratham_HW2_CCPP.ipynb` uses 9,568 hourly observations collected
from 2006 to 2011 while the plant operated at full load. It predicts net
hourly electrical energy output (`PE`) from ambient temperature (`AT`),
ambient pressure (`AP`), relative humidity (`RH`), and exhaust vacuum (`V`).

The notebook covers exploratory plots and summary statistics, simple and
multiple linear regression, studentized-residual outlier checks, cubic and
interaction models, backward elimination of quadratic/interaction terms, and
KNN regression with raw and standardized predictors. Models are compared
using a 70/30 train/test split and mean squared error (MSE); KNN uses candidate
values of \(k\) from 1 through 100.

### Results

The best evaluated model was standardized KNN regression with \(k=4\):

| Model | Train MSE | Test MSE |
|---|---:|---:|
| Multiple linear regression | 20.5808 | 21.2399 |
| Selected quadratic/interaction regression | 17.8908 | 18.6600 |
| KNN, raw features (\(k=5\)) | 10.6008 | 15.7268 |
| KNN, standardized features (\(k=4\)) | 8.5914 | 14.3057 |

## Part 2: ISLR Exercises

`Aggarwal_Pratham_HW2_ISLR.ipynb` contains written solutions to:

- **2.4.1:** How the relative sample size, number of predictors,
  nonlinearity, and irreducible error affect the benefit of a flexible
  method.
- **2.4.7:** Euclidean distances and KNN predictions for a
  three-predictor classification example. The nearest neighbor predicts
  Green, the three-neighbor majority predicts Red, and a highly nonlinear
  Bayes decision boundary favors a smaller \(K\).

## Running the Notebooks

Open either notebook in Jupyter or VS Code and select a Python kernel with
the repository dependencies installed. Run the CCPP notebook with its working
directory set to `assignment-02/notebooks/`, so
`../data/Folds5x2_pp.xlsx` resolves. The ISLR notebook is markdown-based and
does not require execution.

Install shared dependencies from the repository root using:

```bash
python -m pip install -r requirements.txt
```
