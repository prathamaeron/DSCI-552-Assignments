# DSCI 552 Homework 2

## Combined Cycle Power Plant Data Set

This assignment uses the UCI Combined Cycle Power Plant Data Set to predict
net hourly electrical energy output using four ambient operating variables.
The analysis focuses on exploratory data analysis, linear regression, and
k-nearest neighbors (KNN) regression.

## Repository Structure

```text
assignment-02/
├── README.md
├── Homework2.pdf
├── data/
│   ├── Folds5x2_pp.xlsx
│   ├── Folds5x2_pp.ods
│   └── Readme.txt
└── notebooks/
    └── Aggarwal_Pratham_HW2.ipynb
```

## Data

The data contain 9,568 observations and five columns. Each row represents an
hourly measurement collected from a Combined Cycle Power Plant over six years
(2006-2011) at full load.

The predictor variables are:

1. `AT` - Ambient Temperature
2. `AP` - Ambient Pressure
3. `RH` - Relative Humidity
4. `V` - Exhaust Vacuum

The response variable is:

- `PE` - Net hourly electrical energy output

The analysis uses the first sheet of `Folds5x2_pp.xlsx`.

## Assignment Tasks Implemented

The notebook includes:

- Data loading and inspection
- Pairwise scatterplots for all variables
- Summary statistics, including means, medians, ranges, quartiles, and IQRs
- Simple linear regression models for each predictor
- Outlier checks using internally studentized residuals
- Multiple linear regression using all four predictors
- Comparison of simple and multiple regression coefficients
- Cubic regression models to assess nonlinear associations
- A full model with all pairwise interaction terms
- A 70/30 train/test comparison of ordinary and expanded regression models
- Backward elimination of insignificant quadratic and interaction terms
- KNN regression using raw and standardized predictors
- Selection of `k` from 1 through 100 using test MSE
- Train/test error plots against `1/k`
- Comparison of the best KNN model with the best linear regression model

## Results

All four predictors have statistically significant associations with `PE` in
the simple regression models and in the multiple regression model at the 5%
significance level. `AT` and `V` have the strongest negative relationships
with `PE`, while `AP` has a positive coefficient and `RH` has a weaker
negative relationship.

Using the 70/30 train/test split, the regression-model results are:

| Model | Train MSE | Test MSE |
|---|---:|---:|
| Multiple linear regression | 20.5808 | 21.2399 |
| Selected quadratic/interactions regression | 17.8908 | 18.6600 |

For KNN regression, the best results are:

| Feature representation | Best `k` | Train MSE | Test MSE |
|---|---:|---:|---:|
| Raw features | 5 | 10.6008 | 15.7268 |
| Standardized features | 4 | 8.5914 | 14.3057 |

The best overall model is KNN with standardized features and `k = 4`. Its
test MSE is approximately 23.3% lower than the selected
quadratic/interactions regression model. This suggests that KNN captures
local nonlinear patterns that are not fully represented by the parametric
regression models.

## Observations

The scatterplots show a strong negative relationship between `PE` and both
`AT` and `V`. The relationship with `RH` is weaker and negative, while the
relationship with `AP` is positive. The predictors also have relationships
with one another, which helps explain why simple and multiple regression
coefficients differ in magnitude.

The expanded regression model improves on ordinary multiple regression, but
standardized KNN has the lowest test error among the evaluated models. The
training MSE is lower than the test MSE for each model, as expected. Test MSE
is therefore used as the primary metric for comparing generalization
performance.

## Running the Notebook

1. Open `notebooks/Aggarwal_Pratham_HW2.ipynb` in Jupyter or VS Code.
2. Select a local Python kernel with the required packages installed.
3. Run the cells from top to bottom.

The notebook expects to be run from the `notebooks` directory so that the path
`../data/Folds5x2_pp.xlsx` resolves correctly.

## Dependencies

- Python 3
- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn
- statsmodels
