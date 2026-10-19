# DSCI 552 Homework 1

This assignment uses the UCI Vertebral Column Data Set to classify patients
as Normal or Abnormal using k-nearest neighbors (KNN).

## Contents

```text
assignment-01/
├── README.md
├── Homework1.pdf
├── data/
│   ├── column_2C.dat
│   ├── column_2C_weka.arff
│   ├── column_3C.dat
│   └── column_3C_weka.arff
├── notebooks/
│   └── Aggarwal_Pratham_HW1.ipynb
└── submission/
    ├── Aggarwal_Pratham_HW1.html
    └── Aggarwal_Pratham_HW1.pdf
```

## Analysis

The binary analysis uses `column_2C.dat`, which contains 310 observations
described by six biomechanical measurements: pelvic incidence, pelvic tilt,
lumbar lordosis angle, sacral slope, pelvic radius, and degree of
spondylolisthesis. The labels are `NO` (Normal) and `AB` (Abnormal). The
three-class `column_3C` files are included but are not used in this binary
analysis.

`Aggarwal_Pratham_HW1.ipynb` includes:

- Class-colored scatterplots for predictor pairs and boxplots for each
  predictor.
- The prescribed split: the first 70 Class 0 observations and first 140
  Class 1 observations are used for training; the rest are used for testing.
- Euclidean KNN, with train and test error for \(k=208,205,\ldots,4,1\), plus
  confusion matrix and classification metrics at the selected \(k\).
- A learning curve using training-set sizes from 10 through 210.
- Manhattan, Minkowski, Chebyshev, and Mahalanobis distances.
- Weighted KNN with Euclidean, Manhattan, and Chebyshev distances.

## Key Results

For Euclidean KNN, the selected value was \(k=4\), with test error 0.060. The
confusion matrix below uses the `[[TN, FP], [FN, TP]]` convention:

```text
[[25,  5],
 [ 1, 69]]
```

The corresponding true positive rate is 0.986, true negative rate is 0.833,
precision is 0.932, and F1-score is 0.958. At the full training size of 210,
the learning-curve experiment selected \(k=6\) and obtained test error 0.080;
its candidate \(k\) values do not include \(k=4\).

| Distance method | Best \(k\) | Test error |
|---|---:|---:|
| Euclidean | 4 | 0.06 |
| Manhattan | 6 | 0.11 |
| Minkowski (\(\log_{10}(p)=0.6\)) | 6 | 0.06 |
| Chebyshev | 16 | 0.08 |
| Mahalanobis | 1 | 0.17 |
| Weighted Euclidean | 6 | 0.10 |
| Weighted Manhattan | 26 | 0.10 |
| Weighted Chebyshev | 16 | 0.11 |

The classes are not completely separated by any single feature, supporting
the use of all six measurements together. The zero training errors observed
for some \(k=1\) or weighted models are not evidence of generalization: a
training observation can be its own zero-distance neighbor. Test error is
more informative for this comparison.

## Running the Notebook

Open `notebooks/Aggarwal_Pratham_HW1.ipynb` in Jupyter or VS Code, select a
Python kernel with the repository dependencies installed, and run cells from
top to bottom. Set the working directory to `assignment-01/notebooks/` so
`../data/column_2C.dat` resolves.

Install shared dependencies from the repository root using:

```bash
python -m pip install -r requirements.txt
```
