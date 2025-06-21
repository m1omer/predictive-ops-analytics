# Predictive Operations Analytics

Unplanned machine failures in manufacturing can lead to costly downtime and inefficiencies. This project uses machine learning to predict failures before they happen — enabling proactive maintenance decisions that save time, reduce costs, and improve operational reliability.

Built on real-world equipment sensor data, the pipeline walks through EDA, model training, evaluation, and key insights, with a supporting Power BI dashboard for business-facing storytelling.

---

## Dataset

- **Name**: AI4I 2020 Predictive Maintenance Dataset  
- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset)  
- **Size**: 10,000 rows × 14 columns  
- **Target**: `machine_failure` (binary: 1 = failure, 0 = no failure)  
- **Features**: Sensor readings (torque, temperature, rotational speed, tool wear), machine type, and process variables

---

## 🚀 Project Workflow

- EDA and preprocessing
- Addressing class imbalance (1 = failure is only ~0.7%)
- Training 2 models:  
  - Logistic Regression  
  - Random Forest  
- Evaluating performance using:
  - Classification Report
  - ROC AUC Score
- Extracting feature importance
- Visualizing insights via Power BI

---

## Results

| Model              | AUC Score | Precision (Failure) | Recall (Failure) | F1-Score (Failure) |
|-------------------|-----------|----------------------|------------------|--------------------|
| Logistic Regression | 0.9069   | 0.14                 | 0.82             | 0.25               |
| Random Forest       | 0.9631   | 0.94                 | 0.47             | 0.63               |

**Random Forest** offered the best trade-off between interpretability and predictive power, achieving a strong AUC and high precision on failure cases.

---

## Key Insights

- `torque_nm` and `tool_wear_min` are top predictors of failure
- Class imbalance required special handling (used `class_weight='balanced'`)
- Predictive models enable **real-time risk monitoring** and **automated inspection triggers**

---

## Dashboard

A Power BI dashboard (included in the repo) allows stakeholders to:

- Explore failure trends
- Filter by machine type and component conditions
- See top predictors and model outputs in a business-friendly format

---

## 📁 Project Structure

```markdown
predictive-ops-analytics/
├── data/
│   └── ai4i2020.csv
├── notebooks/
│   └── predictive_maintenance.ipynb
├── dashboard/
│   └── predictive-maintenance.pbix
├── output/
│   ├── predictive_maintenance_output.csv
│   └── feature_importance.csv
├── report/
│   └── strategy-summary.md
└── README.md

