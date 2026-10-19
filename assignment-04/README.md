# DSCI 552 Homework 4

Homework 4 continues the AReM activity-recognition analysis with binary and
multiclass classification and includes written solutions to ISLR exercises
4.8.3 and 4.8.7.

## Contents

```text
assignment-04/
├── README.md
├── Homework4.pdf
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
    ├── Aggarwal_Pratham_HW4_AReM.ipynb
    └── Aggarwal_Pratham_HW4_ISLR.ipynb
```

## Part 1: AReM Time-Series Classification

`Aggarwal_Pratham_HW4_AReM.ipynb` carries forward the HW3 data loading,
feature extraction, and prescribed train/test split. The 88 instances are
split into 69 training and 19 test examples. Datasets 1 and 2 in `bending1`
and `bending2`, and datasets 1, 2, and 3 in the other activity folders, are
held out for testing.

The notebook first examines the extracted minimum, mean, and maximum features
for sensor series 1, 2, and 6, including plots for full series and for two
contiguous halves. It then covers:

- **Binary logistic regression:** Identifies bending versus other activities;
  searches segment counts 1 through 20 and RFE feature counts with five-fold
  stratified cross-validation. Scaling and feature selection are fitted
  inside each training fold.
- **Evaluation and imbalance:** Reports training/test confusion matrices and
  ROC/AUC, checks for separation, and fits a case-control model with an
  intercept correction for the original class prevalence.
- **L1 binary logistic regression:** Cross-validates the segment count and
  penalty strength and compares the results with the RFE model.
- **Multiclass classification:** Fits L1 multinomial logistic regression and
  compares it with Gaussian and Multinomial Naive Bayes. Test confusion
  matrices, one-versus-rest ROC curves, and AUC are reported.

The binary task combines the two bending folders into one positive class.
The multiclass training set has only four `bending2` instances, so
four-fold stratified cross-validation is used to tune the multiclass penalty;
this allows every validation fold to contain an example from each activity.
Binary model selection uses the assignment's five-fold stratified
cross-validation.

## Part 2: ISLR Exercises

`Aggarwal_Pratham_HW4_ISLR.ipynb` contains written solutions to:

- **4.8.3:** Derives the one-dimensional QDA discriminant and shows that its
  general decision boundary is quadratic.
- **4.8.7:** Applies Bayes' theorem to estimate the probability of a dividend
  given a company's prior-year percent profit.

## Running the Notebooks

Open the AReM notebook in Jupyter or VS Code and run it with the working
directory set to `assignment-04/notebooks/`, so its relative `../data` path
resolves. The ISLR notebook is markdown-based and does not require execution.

Install shared dependencies from the repository root using:

```bash
python -m pip install -r requirements.txt
```
