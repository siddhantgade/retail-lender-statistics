# Credit Risk Triage – Applied Statistics

## Objective
Build a small, fast analysis that highlights which basic applicant attributes separate Good and Bad credit outcomes. The goal is to support an underwriting triage step, not to build a full scoring model.

## Dataset
Public European consumer-credit dataset with 1,000 records.  
I worked only with operational fields that a real lender relies on: loan duration, loan amount, age, purpose, savings level, employment duration, housing status, and the final credit outcome.

## Approach
- Loaded and restricted the dataset to the fields relevant for early-stage triage.
- Produced two distribution checks (box plots) comparing Good vs Bad outcomes for loan amount and loan duration.
- Tested three categorical attributes (purpose, savings, employment duration) using chi-square to check whether risk distribution differs across groups.
- Encoded the data and fitted a compact logistic regression to quantify directional impact.
- Reviewed classification metrics and ROC AUC.
- Exported two box plots and a ROC curve for reporting.

## Insights
- Both loan amount and loan duration show clear separation between Good and Bad outcomes.
- Purpose, savings level, and employment duration show statistically meaningful shifts in risk.
- Logistic regression returns an ROC AUC of ~0.70, which is sufficient for steering manual reviews in an early-stage underwriting flow.

## Files
- Notebook: `notebooks/01_lending_statistics.ipynb`
- Visuals: `box_amount.png`, `box_duration.png`, `roc_curve.png`
- Environment: `requirements.txt`

## Outcome
A compact triage view that surfaces straightforward risk signals.  
Useful for routing applications into low-touch or manual-review buckets before more advanced modelling or policy rules are applied.
