# 📊 HR Analytics Dashboard — Power BI Project

A complete HR Analytics project built in Power BI using a synthetic dataset of **10,000 employees** modelled on Indian workforce data.

---

## 🗂️ Project Structure

```
hr-analytics-powerbi/
├── HR_Dataset_10000.xlsx     ← Source data (10,000 employee records)
├── HR_Analysis.pbix          ← Power BI report file
└── README.md
```

---

## 📁 Dataset Overview

The dataset (`HR_Dataset_10000.xlsx`) contains **10,000 rows** and **24 columns** covering:

| Column | Description |
|---|---|
| Employee_ID | Unique identifier (EMP10001–EMP20000) |
| Employee_Name | Full name |
| Gender | Male / Female / Non-Binary |
| Age & Date_of_Birth | Demographic data |
| Education | Highest qualification |
| Department | 10 departments (Engineering, Sales, HR…) |
| Job_Title | Role within department |
| Employment_Type | Full-Time / Part-Time / Contract |
| Location | 10 Indian cities |
| Join_Date & Years_of_Experience | Tenure information |
| Annual_Salary_INR | Annual CTC in Indian Rupees |
| Bonus_Percent & Bonus_Amount_INR | Incentive data |
| Performance_Rating | Excellent / Good / Average / Below Average / Poor |
| Employment_Status | Active / Resigned / Terminated / On Leave |
| Attrition | Yes / No |
| Leaves_Taken & Leaves_Available | Leave balance |
| Training_Hours | Annual training hours (0–120) |
| Job_Satisfaction_Score | Score from 1–10 |
| Overtime | Yes / No |

---

## 📊 Dashboard Pages

### 1. Overview
- Total employee count (KPI Card)
- Active vs Resigned vs Terminated vs On Leave (Donut Chart)
- Overall Attrition Rate (KPI Card)
- Employees by Department (Bar Chart)
- Employees by Location (Bar Chart)
- Gender Distribution (Donut Chart)

### 2. Attrition Analysis
- Attrition Rate by Department
- Attrition Rate by Location
- Attrition Rate by Employment Type
- Attrition Rate by Gender

### 3. Salary Analysis
- Average Salary by Department (Horizontal Bar)
- Average Salary by Location (Horizontal Bar)
- Salary Distribution by Range (Histogram)

### 4. Performance & Engagement
- Performance Rating Breakdown (Bar Chart)
- Average Training Hours by Department
- Average Job Satisfaction Score by Department
- Overtime Distribution

---

## 🧮 Key DAX Measures

```dax
-- Total Employees
Total Employees = COUNTROWS(HR_Data)

-- Active Employees
Active Employees =
COUNTROWS(FILTER(HR_Data, HR_Data[Employment Status] = "Active"))

-- Attrition Rate
Attrition Rate =
DIVIDE(
    COUNTROWS(FILTER(HR_Data, HR_Data[Attrition] = "Yes")),
    COUNTROWS(HR_Data)
) * 100

-- Average Salary
Avg Salary = AVERAGE(HR_Data[Annual Salary INR])

-- Average Satisfaction Score
Avg Satisfaction = AVERAGE(HR_Data[Job Satisfaction Score])

-- Average Training Hours
Avg Training Hours = AVERAGE(HR_Data[Training Hours])
```

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Python (pandas, openpyxl) | Dataset generation |
| Microsoft Power BI Desktop | Dashboard & visualisation |
| DAX | Custom measures & calculations |
| GitHub | Version control |

---

## 🚀 How to Use

1. Clone or download this repository
2. Open `HR_Analysis.pbix` in **Power BI Desktop**
3. If prompted, re-link the data source to `HR_Dataset_10000.xlsx`
4. Explore the 4 dashboard pages using slicers and filters

---

## 📌 Key Insights from the Data

- Overall attrition rate is approximately **18.2%**
- **Customer Support** has the highest attrition rate (~25%)
- **R&D** employees have the highest average salary (~₹13.8L)
- **Contract employees** have significantly higher attrition (31%) vs Full-Time (16%)
- **Bangalore** is the highest-paying location on average (~₹11.5L)
- Average job satisfaction score is **6.8 / 10**

---

## 👤 Author

**Alhaj**
Student — Silver Oak University
Learning: Data Analytics | Power BI | Python | SQL

---

## 📄 License

This project uses a synthetically generated dataset for educational purposes only.
