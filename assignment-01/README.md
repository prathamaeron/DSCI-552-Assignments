# DSCI 552 Homework 1

## Vertebral Column Data Set

This assignment uses the UCI Vertebral Column Data Set to classify patients as
Normal or Abnormal using k-nearest neighbors (KNN).

## Repository Structure

```text
assignment-01/
├── README.md
├── data/
│   ├── column_2C.dat
│   ├── column_2C_weka.arff
│   ├── column_3C.dat
│   └── column_3C_weka.arff
└── notebooks/
    └── Aggarwal_Pratham_HW1.ipynb
```

## Data

The analysis uses `column_2C.dat`, which contains 310 observations. Each
observation has six biomechanical features:

1. Pelvic incidence
2. Pelvic tilt
3. Lumbar lordosis angle
4. Sacral slope
5. Pelvic radius
6. Degree of spondylolisthesis

The class labels are encoded as:

- `NO` -> `0` (Normal)
- `AB` -> `1` (Abnormal)

The `column_3C` files contain a three-class version of the data and are not
used for the binary classification analysis in this assignment.

## Assignment Tasks Implemented

The notebook includes:

- Class-colored scatterplots for all pairs of independent variables
- Class-colored boxplots for each independent variable
- The required training/test split:
  - First 70 Class 0 observations for training
  - First 140 Class 1 observations for training
  - Remaining observations for testing
- Euclidean KNN using majority polling
- Train and test error rates for `k` values from 208 down to 1 in steps of 3
- Confusion matrix and classification metrics at the best `k`
- A learning curve using training-set sizes from 10 through 210
- KNN using Manhattan, Minkowski, Chebyshev, and Mahalanobis distances
- Weighted KNN using Euclidean, Manhattan, and Chebyshev distances
- A comparison table of the best test errors for the different metrics

## Results

For the Euclidean KNN evaluation, the best value was:

```text
k* = 4
Test error = 0.060
```

The corresponding confusion matrix is reported in the notebook using the
format `[[TN, FP], [FN, TP]]`:

```text
[[25,  5],
 [ 1, 69]]
```

The corresponding metrics are:

```text
True positive rate: 0.986
True negative rate: 0.833
Precision: 0.932
F1-score: 0.958
```

At the full training-set size of 210 observations, the learning-curve
analysis selected `k = 6` and obtained a best test error rate of `0.080`.

The test-error comparison for the distance metrics is:

| Metric | Best `k` | Test error |
|---|---:|---:|
| Euclidean | 4 | 0.06 |
| Manhattan | 6 | 0.11 |
| Minkowski (`log10(p) = 0.6`) | 6 | 0.06 |
| Chebyshev | 16 | 0.08 |
| Mahalanobis | 1 | 0.17 |
| Weighted Euclidean | 6 | 0.10 |
| Weighted Manhattan | 26 | 0.10 |
| Weighted Chebyshev | 16 | 0.11 |

## Observations

From the scatterplots and boxplots, I observed that the Normal and Abnormal
classes are not completely separated by any single feature. Some combinations
of features show clearer differences between the two classes, so using all six
measurements together makes more sense than relying on only one feature.

For the basic Euclidean KNN model, I obtained the best test error of 0.06 at
`k = 4`. The learning curve does not reach this same value at `N = 210`
because that experiment uses a different candidate set for `k`: `1, 6, 11,
...`. Since `k = 4` is not included, the result at `N = 210` is 0.08 with
`k = 6`.

Among the alternative distance metrics, I found that the Minkowski model with
`log10(p) = 0.6` performed as well as the Euclidean model. Mahalanobis distance
performed worse on this split, with a test error of 0.17. The weighted models
also did not improve on the best unweighted Euclidean test error.

The lowest training error rate at the selected test-optimal values of `k` was
0.000. This occurred for Mahalanobis at `k = 1` and for the weighted models.
This result should be interpreted carefully because a training observation is
also one of its own nearest neighbors. In weighted KNN, its distance is zero,
so it dominates the vote. For this reason, I used the test error and the
learning curve as the more meaningful measures for comparing how well the
models generalize.

## Running the Notebook

1. Open `notebooks/Aggarwal_Pratham_HW1.ipynb` in Jupyter or VS Code.
2. Select a local Python kernel with the required packages installed.
3. Run the cells from top to bottom.

The notebook expects to be run from the `notebooks` directory so that paths
such as `../data/column_2C.dat` resolve correctly.
## Dependencies

- Python 3
- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn
