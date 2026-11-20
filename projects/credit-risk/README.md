# Beyond Accuracy: Credit Card Default Risk

Stephanie Nord compared logistic regression and random forest on 30,000 historical Taiwanese credit card records. The study evaluated next-month default predictions using ranking metrics, probability calibration, and the estimated costs of two types of classification errors.

[Open the executed Jupyter notebook](credit_risk_analysis.ipynb)

## What the analysis found

Random forest ranked defaults slightly better on the held-out test split (ROC-AUC 0.7704 versus 0.7591). Logistic regression had slightly higher accuracy at the 0.50 threshold (81.77% versus 81.62%).

| Assumed missed-default cost relative to a false alarm | Validation-selected threshold | False alarms on test | Missed defaults on test |
| --- | ---: | ---: | ---: |
| 1:1 | 0.45 | 293 | 812 |
| 3:1 | 0.29 | 681 | 585 |
| 5:1 | 0.17 | 1,685 | 356 |

The cost scenarios are hypothetical. Subgroup error rates were examined at the 0.50 threshold, and repeated predictor patterns were documented across splits. Results reflect the 2005 dataset and a random holdout.

## Reproduce the analysis

Use Python 3.12. From this project directory, run:

```bash
python -m pip install -r requirements.txt
jupyter lab credit_risk_analysis.ipynb
```

Select the Python 3 kernel and run all cells. The notebook downloads the [UCI Default of Credit Card Clients dataset](https://doi.org/10.24432/C55S3H) and regenerates the figures, summary tables, and data dictionary. An internet connection is needed to fetch the dataset.
