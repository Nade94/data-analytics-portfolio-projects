# NHANES 2017–2018: Predicting Diabetes Risk from Clinical Risk Factors

Logistic regression model that predicts diabetes diagnosis in ~5,600 U.S. adults using clinical and demographic risk factors — deliberately excluding direct lab markers (HbA1c, fasting glucose) to reflect what's available in a routine clinical assessment.

**Data source:** [NHANES 2017–2018](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?BeginYear=2017) (CDC)
**Tools:** Python, pandas, matplotlib, scikit-learn

## Approach

1. Merged demographics, examination, laboratory, and questionnaire files on participant ID (`SEQN`)
2. Filtered to adults (18+) with a valid diabetes response, leaving 5,678 records
3. Imputed missing values (median for continuous, mode for categorical) using training-set statistics only
4. Standardized features and fit an L2-regularized logistic regression
5. Re-fit with `class_weight='balanced'` to address the 84.5% / 15.5% class imbalance

## Results

| Model | Accuracy | Recall | Precision | AUC-ROC |
|---|---|---|---|---|
| Baseline | 84.2% | 14.8% | 47.3% | 0.800 |
| Balanced | — | 74.4% | 31.0% | 0.798 |

The baseline model looks accurate but is clinically useless — it barely beats predicting "no diabetes" for everyone. Reweighting classes raised recall from 14.8% to 74.4% (catching 131 of 176 diabetic patients instead of 26) with almost no loss in AUC, a reasonable tradeoff for a screening tool where missing a diabetic patient is costlier than a false positive.

**Strongest predictors (odds ratios):** age (2.84), waist circumference (1.51) — a better predictor than BMI (1.19), pointing to abdominal fat as more informative than overall body mass.

## Files

- `portfolio_project_3_nhanes.ipynb` — full analysis notebook
