# DSCI 552 Assignments

This repository contains my coursework for DSCI 552 at the University of
Southern California, taught by Professor Mohammad Reza Rajati.

## Progress

| Assignment | Topic | Status |
|---|---|---|
| [Assignment 1](assignment-01/) | Vertebral Column classification with KNN | Completed |
| [Assignment 2](assignment-02/) | Power Plant regression and ISLR exercises | Completed |
| Assignment 3 | TBD | Not started |
| Assignment 4 | TBD | Not started |
| Assignment 5 | TBD | Not started |
| Assignment 6 | TBD | Not started |
| Assignment 7 | TBD | Not started |
| Assignment 8 | TBD | Not started |

## Assignment 1: Vertebral Column

[Assignment 1](assignment-01/) uses the UCI Vertebral Column Data Set to
classify patients as Normal or Abnormal from six biomechanical measurements.
The notebook covers:

- Exploratory scatterplots and boxplots
- A specified training/test split
- Euclidean KNN classification and selection of $k$
- Error rates, a confusion matrix, and classification metrics
- Learning-curve analysis
- Alternative and weighted distance metrics

## Assignment 2: Regression and ISLR

[Assignment 2](assignment-02/) contains two notebook-based components:

- **Combined Cycle Power Plant:** Predicts net hourly electrical energy output
	from ambient temperature, pressure, relative humidity, and exhaust vacuum.
	The analysis compares linear, nonlinear, interaction, and KNN regression
	models using train/test MSE. Standardized KNN with $k = 4$ achieved the best
	reported test MSE of 14.3057.
- **ISLR exercises:** Provides written solutions to ISLR 2.4.1, which applies
	bias-variance reasoning to flexible methods, and ISLR 2.4.7, which applies
	Euclidean distance and KNN classification.
