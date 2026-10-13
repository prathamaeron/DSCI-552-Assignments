# DSCI 552 Homework 3

Homework 3 covers time-domain feature extraction for activity recognition and
an ISLR exercise comparing linear and cubic regression.

## Repository Structure

```text
assignment-03/
├── README.md
├── Homework3.pdf
├── data/
│   ├── bending1/
│   ├── bending2/
│   ├── cycling/
│   ├── lying/
│   ├── sitting/
│   ├── standing/
│   └── walking/
└── notebooks/
    ├── Aggarwal_Pratham_HW3_AReM.ipynb
    └── Aggarwal_Pratham_HW3_ISLR.ipynb
```

## Part 1: AReM Time-Series Features

`Aggarwal_Pratham_HW3_AReM.ipynb` processes the AReM activity-recognition
dataset. Each instance contains six sensor series with 480 observations per
series. The notebook assigns datasets 1 and 2 in `bending1` and `bending2` to
the test set, and datasets 1, 2, and 3 in the other activity folders to the
test set. This yields 69 training instances and 19 test instances.

For each sensor series, the notebook calculates the minimum, maximum, mean,
median, sample standard deviation, first quartile, and third quartile, yielding
42 features per instance. It also reports bootstrap 90% confidence intervals
for each feature's standard deviation and ranks nonconstant features using
ANOVA F-statistics computed from the training data.

## Part 2: ISLR 3.7.4

`Aggarwal_Pratham_HW3_ISLR.ipynb` contains written answers comparing linear
and cubic regression. It explains why the cubic model's training RSS cannot
exceed the linear model's, why a linear model is expected to generalize better
when the true relationship is linear, and why the test-RSS comparison is
undetermined when the true relationship is nonlinear but unspecified.

## Running the Notebooks

Open the notebooks in Jupyter or VS Code. The AReM notebook expects the
assignment's `data/` directory and should be run with its working directory
set to `notebooks/`. The ISLR notebook contains only markdown and does not
require code execution.

## Dependencies

- Python 3
- NumPy
- pandas
- scikit-learn
