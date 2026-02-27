# 🏥 Diabetic Patient Readmission Analysis

## 📌 Project Overview
This project analyzes hospital readmission patterns among diabetic patients using Python-based data analysis and visualization techniques.  
The main objective is to identify demographic, clinical, and operational factors that influence 30-day hospital readmission probability.

---

## 🎯 Objectives

- Analyze demographic disparities (Race, Gender, Age)
- Evaluate medication impact (Insulin vs Other Medications)
- Examine the effect of medication changes
- Identify operational relationships (Hospital Stay vs Lab Procedures)
- Detect correlations among clinical metrics
- Provide strategic insights for hospital decision-making

---

## 📊 Key Analyses Performed

### 1️⃣ Demographic Analysis
- Age distribution of diabetic patients
- Readmission probability by race and gender

### 2️⃣ Medication Impact Analysis
- Insulin users vs other medication users
- Effect of medication change on readmission

### 3️⃣ Operational Analysis
- Scatter Plot: Hospital Stay vs Number of Lab Procedures
- Correlation Heatmap of Operational Metrics
- Box Plot: Initial Stay Duration by Readmission Status

---

## 📁 Project Structure

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
│   └── 8_stay_duration_by_readmit_boxplot.png
│
├── diabetic_data.csv
├── final_processed_diabetic_data.csv
├── health.ipynb
└── README.md
```

---

## 🛠 Technologies Used

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## 🚀 How to Run the Project

### 1️⃣ Install Required Libraries
```bash
pip install pandas numpy matplotlib seaborn
```

### 2️⃣ Open Jupyter Notebook
```bash
jupyter notebook
```

### 3️⃣ Run the Notebook
Open `health.ipynb` and run all cells.

All charts will be automatically saved inside the `Project_Charts` folder.

---

## 📈 Key Insights

- Male patients show slightly higher readmission probability in certain racial groups.
- Insulin usage patterns influence readmission outcomes.
- Medication changes may impact patient stability.
- Longer initial hospital stays are associated with higher readmission likelihood.
- Certain operational variables show moderate correlations.

---

## 📌 Conclusion

This project demonstrates how healthcare data analytics can support evidence-based hospital strategies to reduce 30-day readmissions and improve patient care outcomes.

---

👩‍💻 Academic Data Analysis Project  
📊 Focus: Healthcare Analytics & Operational Insights
