<div align="center">

# DSCI 552 Assignments

**Machine Learning for Data Science**  
University of Southern California

[Assignments](#assignment-overview) · [Setup](#setup) · [Repository Layout](#repository-layout)

</div>

Coursework for DSCI 552, taught by Professor Mohammad Reza Rajati. The
assignments cover exploratory analysis, regression, classification,
nearest-neighbor methods, time-series features, and statistical learning
theory.

## Assignment Overview

| # | Topic | Main work | Status |
|:---:|---|---|:---:|
| 01 | [Vertebral Column](assignment-01/) | Exploratory analysis and KNN classification | Complete |
| 02 | [Regression and ISLR](assignment-02/) | Power Plant regression and ISLR 2.4.1, 2.4.7 | Complete |
| 03 | [Time-Series Features and ISLR](assignment-03/) | AReM feature extraction and ISLR 3.7.4 | Complete |
| 04 | [Time-Series Classification and ISLR](assignment-04/) | AReM binary/multiclass models and ISLR 4.8.3, 4.8.7 | Complete |
| 05 | Assignment 5 | Not added yet | Not started |
| 06 | Assignment 6 | Not added yet | Not started |
| 07 | Assignment 7 | Not added yet | Not started |
| 08 | Assignment 8 | Not added yet | Not started |

## Completed Assignments

### 01 · Vertebral Column

[Assignment 1 details](assignment-01/)

KNN classification of Normal versus Abnormal patients using six biomechanical
measurements. The notebook explores the data, evaluates Euclidean KNN and
alternative distance metrics, and reports confusion matrices and classification
metrics.

### 02 · Regression and ISLR

[Assignment 2 details](assignment-02/)

Regression analysis of the Combined Cycle Power Plant data, including linear,
polynomial, interaction, and KNN regression. The companion ISLR notebook
answers exercises 2.4.1 and 2.4.7. The best reported regression model is
standardized KNN with \(k=4\), with test MSE 14.3057.

### 03 · Time-Series Features and ISLR

[Assignment 3 details](assignment-03/)

Extracts seven summary statistics from each of six AReM sensor series,
constructs bootstrap confidence intervals, and ranks features using training
data. The companion ISLR notebook answers exercise 3.7.4.

### 04 · Time-Series Classification and ISLR

[Assignment 4 details](assignment-04/)

Continues the AReM analysis with binary and multiclass logistic regression,
feature selection, class-imbalance handling, and Gaussian and Multinomial
Naive Bayes. The companion ISLR notebook answers exercises 4.8.3 and 4.8.7.

## Setup

From the repository root, create a Python environment and install the shared
dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Open notebooks in Jupyter or VS Code. Run each data-analysis notebook from
its own `notebooks/` directory so relative paths to that assignment's `data/`
directory resolve. ISLR exercise notebooks contain written solutions and do
not require execution.

## Repository Layout

```text
DSCI-552-Assignments/
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt
├── assignment-01/
│   ├── Homework1.pdf
│   ├── data/
│   ├── notebooks/
│   ├── submission/
│   └── README.md
├── assignment-02/
│   ├── Homework2.pdf
│   ├── data/
│   ├── notebooks/
│   └── README.md
├── assignment-03/
│   ├── Homework3.pdf
│   ├── data/
│   ├── notebooks/
│   └── README.md
├── assignment-04/
│   ├── Homework4.pdf
│   ├── data/
│   ├── notebooks/
│   └── README.md
```

Each assignment README describes its materials, analysis, results (where
applicable), and notebook-specific run instructions.
