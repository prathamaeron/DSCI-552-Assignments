# DSCI 552 Homework 4

Homework 4 continues the AReM activity-recognition work from Homework 3 and
adds binary and multiclass classification. It also includes written solutions
to ISLR exercises 4.8.3 and 4.8.7.

## Repository Structure

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

## AReM Time-Series Classification

`Aggarwal_Pratham_HW4_AReM.ipynb` carries forward the HW3 data loading,
feature extraction, and prescribed train/test split. It then addresses
Homework 4 Question 2:

- Plots minimum, mean, and maximum features for sensor series 1, 2, and 6,
  comparing bending with other activities.
- Splits each training series into two contiguous halves and compares the
  resulting feature plots.
- Searches segment counts from 1 to 20 and RFE feature counts using
  five-fold stratified cross-validation for unpenalized binary logistic
  regression. Scaling and feature selection are fitted within each fold.
- Evaluates the binary model on the held-out test set, reports confusion
  matrices and ROC/AUC, and checks for separation and class imbalance.
- Fits a case-control logistic model with an intercept adjustment for the
  original class prevalence.
- Tunes the segment count and L1 penalty for binary logistic regression and
  compares it with RFE.
- Tunes an L1 multinomial logistic model and compares its multiclass
  performance with Gaussian and Multinomial Naive Bayes. Confusion matrices,
  one-versus-rest ROC curves, and AUC are reported.

The prescribed split has 69 training and 19 test instances. Datasets 1 and 2
from `bending1` and `bending2`, and datasets 1, 2, and 3 from each other
activity, are held out for testing. Since the `bending2` training class has
only four instances, multiclass penalty selection uses four-fold stratified
cross-validation so each validation fold contains that activity. Binary
model selection uses the assignment's five-fold stratified cross-validation.

## ISLR Exercises

`Aggarwal_Pratham_HW4_ISLR.ipynb` contains markdown solutions:

- **4.8.3:** Derives the one-dimensional QDA discriminant and explains why
  its general decision boundary is quadratic.
- **4.8.7:** Applies Bayes' theorem to estimate the probability of a dividend
  given a company's prior-year percent profit.

## Running the Notebooks

Install the repository dependencies from the repository root:

```bash
pip install -r requirements.txt
```

Open the notebooks in Jupyter or VS Code. Run the AReM notebook with its
working directory set to `assignment-04/notebooks/`, so its relative
`../data` path resolves. The ISLR notebook contains only markdown and does
not require code execution.