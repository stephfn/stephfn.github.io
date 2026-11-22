# Beyond Accuracy: Credit Card Default Risk Analysis

**The random forest was 81.62% accurate and still missed 870 of 1,327 defaults.** This project examines how model rankings, predicted probabilities, and decision thresholds shape a credit risk analysis when the two types of classification errors have different consequences.

## Project overview

I compared logistic regression and random forest for predicting next-month credit card default. The analysis asks three questions.

1. How well does each model rank customers by default risk?
2. How closely do predicted probabilities align with observed default rates?
3. How does the decision threshold change when a missed default carries a higher penalty than a false alert?

## Data and workflow

The analysis uses the [UCI Default of Credit Card Clients dataset](https://doi.org/10.24432/C55S3H), which contains 30,000 customer records from Taiwan in 2005. About 22% of customers defaulted. The 23 predictors include repayment history, bill amounts, payments, credit limits, and recorded demographics.

- Audited missing values, repeated predictor patterns, and incompletely documented category codes. Retained and documented ambiguous values.
- Excluded the record identifier and fitted preprocessing on the training data. Standardized numeric features and one-hot encoded categorical features.
- Used a stratified 60/20/20 train, validation, and test split with random seed 42.
- Selected the model using validation average precision and selected thresholds on the validation set. Reserved the test set for final evaluation.

## Held-out test results

| Metric | Logistic regression | Random forest |
| --- | ---: | ---: |
| ROC-AUC | 0.7591 | **0.7704** |
| Average precision | 0.5258 | **0.5511** |
| Brier score ↓ | 0.1388 | **0.1361** |
| Accuracy at 0.50 | **81.77%** | 81.62% |
| Default recall at 0.50 | **35.19%** | 34.44% |

Random forest ranked default risk better and had slightly lower probability prediction error. Logistic regression had slightly higher accuracy and default recall at the 0.50 cutoff. Calibration plots showed imperfect alignment between predicted and observed default rates for both models.

## Decision thresholds and error costs

I held the hypothetical false-positive penalty at $100 and varied the penalty for a missed default. Each threshold was selected on the validation set and then applied to the held-out test set.

| Missed-default penalty | Selected threshold | Missed defaults | False alerts |
| ---: | ---: | ---: | ---: |
| $100 | 0.45 | 812 | 293 |
| $300 | 0.29 | 585 | 681 |
| $500 | 0.17 | 356 | 1,685 |

As the assumed cost of a missed default increased, the selected threshold fell. Across the three scenarios, the model caught more defaults while flagging more customers who did not default. The penalties are illustrative. The dataset did not include realized losses, recoveries, or intervention costs.

## Limitations

The data describe one historical credit card population, and the random split measures performance within that dataset. Eleven distinct predictor patterns appeared in both training and test data, which could inflate performance if those records are dependent. The analysis also compares error rates across recorded sex groups as an initial fairness check. A lending application would require current representative data, temporal and external validation, measured costs, and a more thorough fairness and calibration assessment.

## Run the analysis

Open [credit_risk_analysis.ipynb](credit_risk_analysis.ipynb) to see the full workflow, including the ROC and precision–recall curves, calibration plots, confusion matrix, and threshold analysis.

```bash
python -m pip install jupyter ucimlrepo pandas numpy scikit-learn matplotlib
jupyter notebook credit_risk_analysis.ipynb
```

Run the notebook from top to bottom. The data retrieval cell requires internet access to fetch UCI dataset 350.

*Stephanie Nord · DSC680 Applied Data Science · Bellevue University*
