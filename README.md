<div align="center">

# DSCI 552 Assignments

**Machine Learning for Data Science**  
University of Southern California

[Progress](#assignment-progress) · [Completed Work](#completed-work) · [Repository Layout](#repository-layout)

</div>

This repository contains my coursework for DSCI 552, taught by Professor
Mohammad Reza Rajati. The work focuses on exploratory data analysis,
regression, classification, and nearest-neighbor methods.

## At A Glance

| Completed | Current focus | Main methods |
|:---:|---|---|
| **4 / 8** | Time-series classification | Regression, KNN, logistic regression, Naive Bayes, time-domain features |

## Assignment Progress

| # | Assignment | Topic | Status |
|:---:|---|---|:---:|
| 01 | [Vertebral Column](assignment-01/) | KNN classification | **Complete** |
| 02 | [Regression and ISLR](assignment-02/) | Power Plant regression and theory exercises | **Complete** |
| 03 | [Time Series Classification and ISLR](assignment-03/) | AReM feature extraction and regression theory | **Complete** |
| 04 | [Time Series Classification Part 2 and ISLR](assignment-04/) | AReM binary/multiclass classification and ISLR theory | **Complete** |
| 05 | Assignment 5 | To be added | Not started |
| 06 | Assignment 6 | To be added | Not started |
| 07 | Assignment 7 | To be added | Not started |
| 08 | Assignment 8 | To be added | Not started |

## Completed Work

<table>
<tr>
<td width="50%" valign="top">

### 01 · Vertebral Column

[Open Assignment 1](assignment-01/)

Classifies patients as Normal or Abnormal using six biomechanical
measurements from the UCI Vertebral Column Data Set.

**Covers**

- Exploratory scatterplots and boxplots
- A specified training/test split
- Euclidean KNN and selection of $k$
- Error rates, confusion matrix, and classification metrics
- Learning curves and alternative distance metrics
- Weighted KNN classification

</td>
<td width="50%" valign="top">

### 02 · Regression and ISLR

[Open Assignment 2](assignment-02/)

Combines a Combined Cycle Power Plant regression study with written ISLR
exercises on model flexibility and KNN.

**CCPP analysis**

- Simple, multiple, cubic, and interaction regression
- Studentized-residual outlier checks
- Train/test evaluation using MSE
- KNN regression with raw and standardized features
- Best reported model: standardized KNN, $k = 4$, test MSE **14.3057**

**ISLR exercises**

- Bias-variance reasoning for flexible methods
- Euclidean distance and KNN classification

</td>
</tr>
<tr>
<td colspan="2" valign="top">

### 03 · Time Series Classification and ISLR

[Open Assignment 3](assignment-03/)

Extracts time-domain features from the AReM activity-recognition data and
answers ISLR 3.7.4 on linear versus cubic regression.

**Covers**

- The specified 69/19 training/test split across 88 activity instances
- Seven summary statistics for each of six sensor series
- Bootstrap 90% confidence intervals for feature standard deviations
- Training-only ANOVA ranking of the three most discriminative features
- Training and test RSS comparisons for linear and cubic regression

</td>
</tr>
<tr>
<td colspan="2" valign="top">

### 04 · Time Series Classification Part 2 and ISLR

[Open Assignment 4](assignment-04/)

Continues the AReM activity-recognition analysis with binary and multiclass
classification, and answers ISLR exercises 4.8.3 and 4.8.7.

**AReM classification**

- Reuses the HW3 feature extraction and the prescribed 69/19 train/test split
- Compares full-series and two-half time-domain feature plots
- Tunes unpenalized logistic regression with five-fold stratified CV and RFE
- Evaluates L1-penalized logistic regression and handles binary class imbalance
- Compares L1 multinomial logistic regression with Gaussian and Multinomial
  Naive Bayes; reports confusion matrices, ROC curves, and AUC

**ISLR exercises**

- Derives the quadratic Bayes decision boundary for QDA
- Computes a posterior dividend probability using Bayes' theorem

</td>
</tr>
</table>

## Setup

Create and activate a virtual environment, then install the dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Run each notebook from its assignment's `notebooks/` directory so relative
data paths resolve correctly.

## Repository Layout

```text
DSCI-552 Assignments/
├── .gitignore
├── assignment-01/   Vertebral Column KNN classification
├── assignment-02/   CCPP regression and ISLR exercises
├── assignment-03/   AReM time-series features and ISLR regression exercise
├── assignment-04/   AReM classification and ISLR exercises
├── LICENSE
├── README.md
└── requirements.txt
```

Each assignment directory contains its own README, data, notebooks, and any
available submission artifacts.
