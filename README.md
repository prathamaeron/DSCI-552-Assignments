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
| **2 / 8** | Supervised learning | KNN, linear regression, nonlinear models |

## Assignment Progress

| # | Assignment | Topic | Status |
|:---:|---|---|:---:|
| 01 | [Vertebral Column](assignment-01/) | KNN classification | **Complete** |
| 02 | [Regression and ISLR](assignment-02/) | Power Plant regression and theory exercises | **Complete** |
| 03 | Assignment 3 | To be added | Not started |
| 04 | Assignment 4 | To be added | Not started |
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
</table>

## Repository Layout

```text
DSCI-552 Assignments/
├── assignment-01/   Vertebral Column KNN classification
├── assignment-02/   CCPP regression and ISLR exercises
├── LICENSE
└── README.md
```

Each assignment directory contains its own README, data, notebooks, and any
available submission artifacts.
