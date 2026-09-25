# DSCI 552 Homework 2

Homework 2 contains a regression analysis of a Combined Cycle Power Plant
dataset and selected exercises from *Introduction to Statistical Learning*
(ISLR).

## Repository Structure

```text
assignment-02/
├── README.md
├── Homework2.pdf
├── data/
│   ├── Folds5x2_pp.xlsx
│   ├── Folds5x2_pp.ods
│   ├── Readme.txt
│   └── Readme.txt~
├── notebooks/
│   ├── Aggarwal_Pratham_HW2_CCPP.ipynb
│   └── Aggarwal_Pratham_HW2_ISLR.ipynb
└── submission/
```

## Part 1: Combined Cycle Power Plant

`Aggarwal_Pratham_HW2_CCPP.ipynb` uses the UCI Combined Cycle Power Plant
dataset. The data contain 9,568 hourly observations collected from 2006 to
2011 while the plant operated at full load.

The goal is to predict net hourly electrical energy output (`PE`) from:

- `AT`: Ambient Temperature
- `AP`: Ambient Pressure
- `RH`: Relative Humidity
- `V`: Exhaust Vacuum

The notebook includes:

- Exploratory plots and summary statistics
- Simple and multiple linear regression
- Studentized-residual outlier checks
- Cubic and interaction regression models
- A 70/30 train/test comparison using mean squared error (MSE)
- Backward elimination of quadratic and interaction terms
- KNN regression with raw and standardized predictors
- Selection of `k` from 1 through 100

The best evaluated model was standardized KNN regression with `k = 4`:

| Model | Train MSE | Test MSE |
|---|---:|---:|
| Multiple linear regression | 20.5808 | 21.2399 |
| Selected quadratic/interactions regression | 17.8908 | 18.6600 |
| KNN, raw features, `k = 5` | 10.6008 | 15.7268 |
| KNN, standardized features, `k = 4` | 8.5914 | 14.3057 |

## Part 2: ISLR Exercises

`Aggarwal_Pratham_HW2_ISLR.ipynb` contains written solutions to:

- **ISLR 2.4.1:** Comparing flexible and inflexible statistical learning
    methods using bias-variance reasoning.
- **ISLR 2.4.7:** Computing Euclidean distances and KNN predictions for a
    three-predictor classification example.

For ISLR 2.4.7, the nearest observation to $(0,0,0)$ is Green, so the $K=1$
prediction is Green. The three-neighbor majority vote is Red. A highly
nonlinear Bayes decision boundary favors a small value of $K$ because it
requires a more flexible local decision rule.

## Running the Notebooks

1. Open either notebook in Jupyter or VS Code.
2. Select a Python 3 kernel with the required packages installed.
3. Run the code cells from top to bottom.

The CCPP notebook reads `../data/Folds5x2_pp.xlsx` relative to the
`notebooks` directory. The ISLR notebook is markdown-based and does not
require a dataset or kernel to view its solutions.

## Dependencies

- Python 3
- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn
- statsmodels
