# DSCI 552 Homework 3

Homework 3 studies time-domain feature extraction for activity recognition
using the AReM dataset and answers an ISLR exercise on linear and cubic
regression.

## Contents

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
│   ├── walking/
│   ├── bendingType.pdf
│   └── sensorsPlacement.pdf
└── notebooks/
    ├── Aggarwal_Pratham_HW3_AReM.ipynb
    └── Aggarwal_Pratham_HW3_ISLR.ipynb
```

## Part 1: AReM Time-Series Features

`Aggarwal_Pratham_HW3_AReM.ipynb` processes instances from seven activity
folders. Each instance contains six sensor series. The prescribed split holds
out datasets 1 and 2 in `bending1` and `bending2`, and datasets 1, 2, and 3
in each of the other activity folders. This yields 69 training instances and
19 test instances.

For each sensor series, the notebook calculates the minimum, maximum, mean,
median, sample standard deviation, first quartile, and third quartile,
producing 42 features per instance. It reports bootstrap 90% confidence
intervals for the feature standard deviations and ranks nonconstant features
by ANOVA F-statistics computed using the training data.

## Part 2: ISLR 3.7.4

`Aggarwal_Pratham_HW3_ISLR.ipynb` contains written answers comparing linear
and cubic regression. It explains why the nested cubic model cannot have
higher training RSS, why a linear model is generally expected to perform
better when the true relationship is linear, and why test RSS is
undetermined when the true relationship is nonlinear but unspecified.

## Running the Notebooks

Open the AReM notebook in Jupyter or VS Code and run it with the working
directory set to `assignment-03/notebooks/`, so its relative `../data` path
resolves. The ISLR notebook is markdown-based and does not require execution.

Install shared dependencies from the repository root using:

```bash
python -m pip install -r requirements.txt
```
