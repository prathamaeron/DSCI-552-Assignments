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

## Dependencies

- Python 3
- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn
