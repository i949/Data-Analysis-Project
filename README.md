# Heart Disease Data Analysis Project

Exploratory data analysis of a clinical heart disease dataset (1,025 patient records), answering a set of core diagnostic questions through descriptive statistics, cross-tabulations, and an interactive dashboard.

## 📌 Project Overview

This project explores the relationship between clinical/demographic features (age, sex, blood pressure, cholesterol, chest pain type, exercise test results, etc.) and the presence of heart disease. The analysis is built entirely in Excel using PivotTables, and summarized in a written report and a slide presentation for discussion.

**Key questions answered:**
- What percentage of patients have heart disease?
- Does age affect the risk of heart disease?
- Are males more likely to have heart disease than females?
- What is the relationship between blood pressure and heart disease?
- Does cholesterol level affect heart disease?
- Does fasting blood sugar increase the risk?
- Which features are the strongest predictors of heart disease?
- What is the correlation between all medical features?
- How is heart disease distributed across different age groups?
- What insights can be obtained from the dataset?

## 📂 Repository Structure

```
heart-disease-analysis/
│
├── README.md                                  # Project overview (this file)
├── data/
│   └── project_data_done_pivot_tables.xlsx     # Cleaned dataset + PivotTables + dashboard
├── report/
│   └── Heart_Disease_Data_Discussion_Report.docx
├── presentation/
│   └── Heart_Disease_Analysis.pptx
```

> Adjust folder names above to match what you actually upload — the key idea is separating raw/processed data, the written report, and the slides into their own folders so the repo stays organized as it grows.

## 🗂️ Dataset

- **Records:** 1,025 patients
- **Columns:** 20 (raw clinical fields + binned/grouped versions created during cleaning: age group, blood pressure category, cholesterol category)
- **Target:** `target` / `heart_disease_flag` — 1/Yes = has heart disease, 0/No = does not
- **No missing values** after cleaning

| Column | Type | Description |
|---|---|---|
| Patient_ID | ID | Unique record identifier |
| age / Group_age | Numeric / Category | Patient age, and binned age group |
| sex | Category | Male / Female |
| chest_pain_type | Category | Typical Angina, Atypical Angina, Non-Anginal Pain, Asymptomatic |
| resting_blood_pressure / Group_blood_pressure | Numeric / Category | Resting BP (mm Hg) and clinical BP category |
| cholestrol / cholestrol_group | Numeric / Category | Serum cholesterol (mg/dl) and category |
| fasting_blood_sugar | Category | Above or below 120 mg/dl |
| rest_ecg | Category | Resting ECG result |
| Max_heart_rate | Numeric | Maximum heart rate achieved |
| exercise_induced_angina | Category | Yes / No |
| oldpeak | Numeric | ST depression induced by exercise |
| slope | Category | Slope of the peak exercise ST segment |
| vessels_colored_by_flourosopy / Num_vessels_colored | Category / Numeric | Number of major vessels (0–4) colored by fluoroscopy |
| thalassemia | Category | Normal, Fixed Defect, Reversable Defect, Unknown |
| target / heart_disease_flag | Binary / Category | 1 = has heart disease, 0 = does not |

## 🔑 Key Findings

- The dataset is nearly balanced: **51.3% have heart disease, 48.7% do not**.
- Traditional "textbook" risk factors — **age, blood pressure, cholesterol** — show weak or *reversed* relationships with the diagnosis label in this sample (e.g., the highest blood-pressure group has the *lowest* disease rate).
- **Exercise-test-based features** are much stronger separators of the two classes: `Max_heart_rate` (+0.42 correlation), `oldpeak` (−0.44), `Num_vessels_colored` (−0.38), exercise-induced angina, and chest pain type.
- **Women in this sample have a notably higher disease rate than men** (72.4% vs. 42.1%) — a known characteristic of this particular (Cleveland-derived) dataset, likely tied to referral/selection bias rather than a general population finding.
- These patterns are most likely explained by **selection/referral bias**: this is a clinical testing sample (patients referred for testing), not a random sample of the general population — younger/at-risk patients are often only tested when symptomatic, and patients with severe readings may already be under treatment by the time they're measured.

## 🛠️ Tools Used

- **Microsoft Excel** — data cleaning, PivotTables, dashboard
- **Word** — written discussion report
- **PowerPoint** — presentation deck

## 🚀 How to Use

1. Download `project_data_done_pivot_tables.xlsx` from the `data/` folder.
2. Open the `PivotTabels` sheet to explore each cross-tabulation, or the dashboard sheet for the visual summary.
3. Read `report/Heart_Disease_Data_Discussion_Report.docx` for the full write-up of each question, the numbers behind it, and discussion caveats.
4. See `presentation/` for the summarized slide deck.

## ⚠️ Limitations

- This is a clinical testing sample, not a general-population sample — disease rates by age/sex/BP/cholesterol should not be generalized as population risk factors.
- Some relationships (BP, cholesterol vs. target) are likely confounded by pre-measurement treatment effects.
- The direction of the `target` coding should be double-checked, since clinically-expected-to-be-positive features (oldpeak, vessel count) correlate negatively with it here.


