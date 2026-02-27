# 🏥 Diabetic Patient Readmission Analysis  
### Clinical Data Engineering, Risk Stratification & VCI Score Development

---

## 📌 Project Overview

This end-to-end healthcare analytics project analyzes hospital readmission patterns among diabetic patients using Python.

The project simulates a real-world clinical analytics pipeline including:

- Clinical data cleaning & sanitation  
- Ethical web scraping for ICD-9 enrichment  
- Exploratory Data Analysis (EDA)  
- Operational metric evaluation  
- Feature engineering  
- Development and validation of a custom risk scoring model  
- Final structured dataset export  

The ultimate goal is to identify high-risk patients likely to be readmitted within 30 days and provide data-driven hospital strategy insights.

---

# 🧭 Project Phases

---

# 🔹 Phase 01 — Data Ingestion & Clinical Sanitation

### 🎯 Objective
Transform raw, inconsistent hospital data into a clean, analysis-ready dataset.

### ✔ Key Steps

- Loaded dataset using `pandas`
- Audited schema using:
  - `df.info()`
  - `df.describe()`
  - `df.head()`
- Converted ID columns to categorical types
- Standardized missing values (`? → NaN`)
- Dropped `weight` column (>90% missing)
- Removed deceased patients using mapping file
- Removed exact duplicate rows

### 🏥 Clinical Importance

- Excluding deceased patients ensures readmission prediction validity.
- Data cleaning ensures model reliability and statistical accuracy.

---

# 🔹 Phase 02 — Data Enrichment via Web Scraping

### 🎯 Objective
Convert ICD-9 diagnosis codes into human-readable clinical descriptions.

### ✔ Key Steps

- Identified Top 20 most frequent `diag_1` codes
- Built ethical web scraper using:
  - `requests`
  - `BeautifulSoup`
- Implemented session handling
- Added delay for ethical scraping
- Mapped descriptions back into dataset
- Labeled remaining diagnoses as `"Not in Top 20"`

### 🧠 Clinical Value

Transforms numeric codes into interpretable medical categories for decision-makers.

---

# 🔹 Phase 03 — Exploratory Data Analysis (EDA)

### 🎯 Objective
Discover patterns affecting 30-day readmission.

All visualizations are saved in `Project_Charts/`.

---

## 📊 1. Readmission Distribution

- Strong class imbalance observed
- <30 day readmissions significantly lower than NO category
- Predictive modeling challenge identified

---

## 📊 2. Demographic Profiling

### Age Distribution
- Majority between 50–90 years
- Peak: 70–80 age group

### Race & Gender Readmission
- Asian (Male) and Hispanic (Male) show higher risk
- Gender disparities observed in certain races

---

## 💊 3. Medication Analysis

### Insulin vs Other Medications
- Insulin users show ~2% higher readmission risk
- Indicates disease severity impact

### Medication Change Impact
- Dosage change correlates with higher readmission
- Reflects clinical instability

---

## 🏥 4. Operational Metrics

### Hospital Stay vs Lab Tests
- Moderate positive relationship
- High lab density clusters identified

### Correlation Heatmap
- No severe multicollinearity
- Strong indicators:
  - Time in hospital
  - Number of medications
  - Lab procedures

### Stay Duration vs Readmission
- Readmitted patients had longer median stay
- Length of stay is strong complexity indicator

---

# 🔹 Phase 04 — Feature Engineering  
## 🧮 Vitality Complexity Index (VCI)

### 🎯 Objective
Develop a clinical risk scoring model inspired by LACE index.

---

## 🧩 VCI Components

| Component | Description | Logic |
|------------|-------------|--------|
| L | Length of Stay | Higher stay = higher score |
| A | Admission Acuity | Emergency / Trauma |
| C | Comorbidity | Number of diagnoses |
| E | Emergency History | Prior emergency visits |

### Formula:

```
VCI Score = L + A + C + E
```

---

## 🎯 Risk Stratification

| Score Range | Risk Level |
|-------------|------------|
| < 7 | Low Risk |
| 7 – 10 | Medium Risk |
| > 10 | High Risk |

---

## 📊 Validation Results

| Risk Level | Actual 30-Day Readmission |
|------------|---------------------------|
| Low Risk | ~8% |
| Medium Risk | ~11% |
| High Risk | ~15% |

### ✅ Model Successfully Stratifies Risk

Higher predicted risk → Higher actual readmission rate.

---

# 📁 Project Structure

```
Project/
│
├── Project_Charts/
│   ├── 1_readmission_distribution.png
│   ├── 2_age_distribution.png
│   ├── 3_readmission_race_gender.png
│   ├── 4_insulin_vs_others.png
│   ├── 5_medication_change_impact.png
│   ├── 6_stay_vs_lab_scatter.png
│   ├── 7_operational_heatmap.png
│   ├── 8_stay_duration_by_readmit_boxplot.png
│   └── 9_vci_validation_bar.png
│
├── diabetic_data.csv
├── IDs_mapping.csv
├── health.ipynb
├── final_processed_diabetic_data.csv
└── README.md
```

---

# 🛠 Technologies Used

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Requests
- BeautifulSoup
- Jupyter Notebook

---

# 🚀 How to Run This Project

## 1️⃣ Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn requests beautifulsoup4
```

## 2️⃣ Open Notebook

```bash
jupyter notebook
```

## 3️⃣ Run `health.ipynb`

Charts will automatically save to:

```
Project_Charts/
```

Final processed dataset:

```
final_processed_diabetic_data.csv
```

---

# 📈 Business & Clinical Impact

- Enables targeted discharge planning
- Identifies high-risk patients early
- Supports cost optimization
- Reduces preventable readmissions
- Provides explainable scoring model for clinicians

---

# 🧠 Key Learning Outcomes

✔ Real-world healthcare data cleaning  
✔ Ethical web scraping implementation  
✔ Feature engineering for risk modeling  
✔ Handling class imbalance  
✔ Correlation & multicollinearity analysis  
✔ Risk stratification validation  

---

# 📌 Final Output

The final enriched dataset with VCI scoring is saved as:

```
final_processed_diabetic_data.csv
```

---

# 👩‍💻 Author

Academic Healthcare Data Analytics Project  
Focus Area: Clinical Risk Modeling & Hospital Operations Optimization  

---

⭐ If you found this project valuable, feel free to fork or star the repository!
