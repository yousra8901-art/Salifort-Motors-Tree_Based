# Salifort Motors — Employee Attrition Analysis

A data analytics project predicting employee attrition for a
fictional company, **Salifort Motors**, using HR data. This project
follows the **PACE** framework (Plan → Analyze → Construct → Execute) and
demonstrates an end-to-end analytics workflow: data cleaning, exploratory
data analysis, feature engineering, predictive modeling, and business
recommendations.


## 📌 Business Problem

Salifort Motors' HR department wants to understand **why employees leave**
and to identify employees who are currently at risk of leaving, so
leadership can intervene with targeted retention strategies before losing
valuable staff.

## 🗂️ Repository Structure

```
salifort-motors-portfolio/
├── data/
│   └── HR_capstone_dataset.csv        # Employee-level HR data
 └── salifort_motors_analysis.ipynb # Full EDA + modeling notebook
├── images/                            # Exported charts used in this README

└── README.md
```

## 📊 Dataset

| Column | Description |
|---|---|
| `satisfaction_level` | Employee-reported satisfaction (0–1) |
| `last_evaluation` | Score from most recent performance review (0–1) |
| `number_project` | Number of projects assigned |
| `average_montly_hours` | Average monthly hours worked |
| `time_spend_company` | Tenure in years |
| `Work_accident` | Whether the employee had a workplace accident (0/1) |
| `left` | **Target** — whether the employee left the company (0/1) |
| `promotion_last_5years` | Promoted in the last 5 years (0/1) |
| `Department` | Department/team |
| `salary` | Salary band: low / medium / high |



## 🔍 Key Findings

- **Overall attrition rate: ~23.8%**
- **Satisfaction level is the strongest predictor** of attrition — low
  satisfaction correlates strongly with leaving.
- **Two distinct at-risk groups emerge by workload:** employees with very
  few projects (disengagement risk) and employees with 6–7 projects and
  very high monthly hours (burnout risk).
- **Tenure of 4–6 years** shows elevated attrition compared to newer or
  longer-tenured employees.
- **Lower salary bands** show modestly higher attrition than high salary
  bands, though the effect is smaller than workload or satisfaction.

### Model comparison summary

| Model | Precision (Left) | Recall (Left) | F1 (Left) | ROC-AUC |
|---|---|---|---|---|
| Logistic Regression | 0.51 | 0.18 | 0.27 | 0.830 |
| Random Forest (tuned) | 0.95 | 0.92 | 0.94 | 0.978 |


The tuned Random Forest was selected as the final model: it trades some
precision for much higher recall on the "Left" class, which better suits
a retention use case where failing to flag a departing employee is more
costly than an occasional false alarm.



## 💡 Recommendations

1. Monitor workload extremes — both under- and over-allocated employees.
2. Use satisfaction pulse-surveys as an early-warning signal.
3. Target retention programs at the 4–6 year tenure band.
4. Review compensation for low-salary bands.
5. Operationalize the model to generate a monthly "attrition risk" list
   for HR business partners.

## 🛠️ Tools & Libraries

- Python (pandas, NumPy)
- scikit-learn (Logistic Regression, Random Forest, GridSearchCV)
- Matplotlib / Seaborn for visualization
- Jupyter Notebook


## Author
Yousra
