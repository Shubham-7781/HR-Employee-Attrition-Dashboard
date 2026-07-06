# HR Employee Attrition Analysis Dashboard

An interactive Power BI dashboard that analyzes employee attrition patterns across departments, job roles, demographics, and job satisfaction — built to help HR teams identify *where* and *why* employees are leaving, not just *how many*.

## 📌 Project Overview

Employee attrition is expensive — replacing an employee can cost 6–9 months of their salary in hiring and training costs. This dashboard turns raw HR records into a decision-support tool that lets stakeholders slice attrition by department, role, age, education, and marital status in real time, instead of digging through spreadsheets.

## 🎯 Objective

- Identify the departments, job roles, and demographic segments with the highest attrition rates
- Distinguish between **attrition volume** (which departments lose the most people) and **attrition rate** (which roles are proportionally riskiest) — these tell very different stories
- Give HR/management a self-serve, filterable view instead of a static report

## 🗂️ Dataset

- **Source:** IBM HR Analytics Employee Attrition dataset (1,470 employee records, 24 attributes)
- **Fields include:** Department, Job Role, Education Field, Business Travel, Age, Gender, Marital Status, Job Satisfaction, Environment Satisfaction, Monthly Income, Years at Company, Years in Current Role, Years Since Last Promotion, Overtime, and more
- File: [`Company_Data.xlsx`](./Company_Data.xlsx)

## 🛠️ Tools & Techniques

| Area | Details |
|---|---|
| **Tool** | Microsoft Power BI Desktop |
| **Data Modeling** | Star-schema-style single fact table; derived columns (`Age Group` bucketing, `Sort_Age` for correct axis ordering) |
| **DAX Measures** | `Total Employees`, `Total Attrition`, `Attrition Rate = DIVIDE([Total Attrition],[Total Employees])`, `Active Employees` |
| **Visuals** | KPI cards, donut chart, clustered bar/column charts, area chart, funnel chart, pivot matrix, slicers with a "Clear All" reset button |
| **UX** | Single-page dashboard designed for at-a-glance scanning; consistent color theme; cross-filtering across all visuals |

## 📊 Key Insights

- Overall attrition rate is **16.12%** (237 of 1,470 employees), with **1,233 active employees**
- **Sales Representatives have the highest attrition rate at 39.76%** — more than double the next closest role (Laboratory Technician, 23.94%) — despite R&D having the largest *absolute* headcount and attrition count, since R&D is simply the biggest department
- Attrition is concentrated in employees under 35, peaking in the late-20s to early-30s age range
- Employees in the **Life Sciences** education field account for the largest share of attrition by education background
- Job satisfaction scores are fairly evenly spread across roles, suggesting attrition is driven more by role/compensation/travel factors than satisfaction alone — worth a deeper multivariate look

## 🖱️ Dashboard Features

- **Filter panel:** Gender, Marital Status, and Travel frequency slicers with one-click reset
- **KPI strip:** Total Employees, Total Attrition, Attrition Rate, Active Employees, Average Age
- **Cross-filtering:** clicking any chart filters every other visual on the page
- **Sorted visuals:** Attrition by Job Role sorted descending so the biggest risk areas surface immediately

## 🚀 How to Use

1. Download [`Dashboard.pbix`](./Dashboard.pbix)
2. Open in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
3. Use the left-hand slicers to filter by gender, marital status, or travel frequency
4. Click any chart to cross-filter the rest of the dashboard
5. Click **Clear all slicers** to reset

## 📁 Repository Structure

```
├── Dashboard.pbix          # Power BI project file
├── Company_Data.xlsx       # Source dataset
├── dashboard.png          # Dashboard preview image
└── README.md
```

## 🔮 Possible Next Steps

- Add a predictive attrition-risk score using a simple logistic regression / decision tree model
- Bring in compensation benchmarking to test if pay gaps correlate with the Sales Representative attrition spike
- Add a drill-through page per department for deeper root-cause analysis
