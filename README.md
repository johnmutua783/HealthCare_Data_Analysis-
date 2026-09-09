# Hospital Operations & Patient Insights

## Project Overview

This project analyzes hospital patient records to identify patterns in **treatment costs, hospital resource utilization, readmissions, patient satisfaction, and patient segments**.

The goal is to move beyond descriptive statistics and provide management-oriented insights that can support areas such as cost monitoring, resource planning, readmission review, and patient experience improvement.

---

## Business Problem

Hospital management needs a clearer view of how patient characteristics and medical conditions relate to:

- Treatment costs
- Hospital length of stay
- Readmission
- Patient satisfaction
- High-cost patient segments

The analysis therefore focuses on identifying the conditions and patient groups that may deserve closer operational attention.

---

## Objectives

The analysis aims to:

1. Measure overall hospital performance using key KPIs.
2. Identify the medical conditions driving treatment costs.
3. Compare hospital resource utilization across conditions.
4. Examine readmission patterns.
5. Compare patient experience between readmitted and non-readmitted patients.
6. Understand how cost, readmission, length of stay, and satisfaction vary across age groups.
7. Identify patients with both high treatment costs and low satisfaction.
8. Translate the findings into practical management recommendations.

---

## Dataset

The dataset contains **984 patient records** and includes:

- Patient demographics
- Medical condition
- Medication/treatment
- Admission and discharge dates
- Patient state
- Length of stay
- Readmission status
- Patient outcome
- Satisfaction score
- Insurance claim status
- Treatment cost

The original dataset contained **15 columns**.

After cleaning and feature engineering, the analytical dataset contains **19 columns**.

---

## Tools & Technologies

- **Python**
- **Pandas** — data cleaning, transformation, aggregation, and analysis
- **Power BI** — interactive dashboard and KPI reporting
- **Jupyter Notebook** — analysis workflow

---

## Data Cleaning & Preparation

The raw data was prepared using Pandas.

Key steps included:

- Checked dataset dimensions and column names.
- Checked for missing values.
- Checked for duplicate records and duplicate patient IDs.
- Reviewed data types and categorical values.
- Removed leading/trailing whitespace from column names and text fields.
- Converted admission and discharge dates from strings to datetime.
- Validated that discharge dates were not earlier than admission dates.
- Recalculated length of stay from admission and discharge dates and compared it with the recorded value.
- Verified age and satisfaction ranges.
- Verified that the recorded admission year matched the admission date.
- Created age groups for demographic analysis.
- Created treatment cost bands.
- Created numeric readmission and insurance-claim flags.

The cleaned dataset was exported as:

`healthcare_clean.csv`

---

## Key Performance Indicators

| KPI | Result |
|---|---:|
| Total Patients | 984 |
| Total Treatment Cost | 8,233,600 |
| Average Treatment Cost | 8,367.48 |
| Average Length of Stay | 37.66 days |
| Readmission Rate | 26.83% |
| Average Satisfaction | 3.60 / 5 |

---

## Key Analysis & Findings

### 1. Treatment Cost Drivers

Cancer was the largest observed treatment-cost contributor, generating **1.65M**, equivalent to **20.04% of total treatment costs**.

The next largest contributors were:

- Prostate Cancer — **1.30M**
- Heart Attack — **1.206M**
- Heart Disease — **975K**
- Childbirth — **780K**

This indicates that a relatively small group of high-cost conditions accounts for a substantial portion of the dataset's overall treatment expenditure.

**Management implication:** High-cost conditions should be prioritized when reviewing treatment-cost drivers, resource requirements, and budget allocation.

---

### 2. Hospital Resource Utilization

Cancer recorded the highest average length of stay at approximately **42.65 days**, followed by:

- Prostate Cancer — **41.58 days**
- Heart Attack — **41.00 days**
- Stroke — **40.33 days**
- Fractured Leg — **39.00 days**

Cancer also accounted for **2,815 hospital days**, representing **7.60%** of total hospital days.

**Management implication:** Conditions with both high treatment cost and extended stays deserve particular attention during capacity and resource planning.

---

### 3. Readmission

Overall readmission was **26.83%**.

The dataset shows particularly high readmission rates for:

- Heart Attack — **100%**
- Heart Disease — **98.46%**
- Appendicitis — **50%**
- Cancer — **50%**
- Stroke — **50%**
- Fractured Arm — **50%**

These patterns are unusually structured, so they should not be interpreted as real-world clinical benchmarks.

**Management implication:** The conditions with the highest observed readmission rates can be used as starting points for reviewing discharge planning, follow-up processes, and patient-care pathways within the dataset context.

---

### 4. Readmission & Patient Experience

Readmitted patients showed:

- Average satisfaction: **3.11 / 5**
- Average treatment cost: **13,649.62**
- Average length of stay: **39.17 days**

Patients who were not readmitted showed:

- Average satisfaction: **3.78 / 5**
- Average treatment cost: **6,430.69**
- Average length of stay: **37.11 days**

The dataset therefore shows an association between readmission and both higher average cost and lower average satisfaction.

**Management implication:** Readmission should be monitored alongside patient experience and cost rather than treated as an isolated operational metric.

---

### 5. Age Group Analysis

The **75+** group showed the strongest risk indicators within the dataset:

- Average treatment cost — **15,280**
- Average length of stay — **40.87 days**
- Readmission rate — **67%**
- Average satisfaction — **2.00 / 5**

By comparison, patients aged 25–34 had:

- Average treatment cost — **3,175**
- Average length of stay — **34.50 days**
- Readmission rate — **0%**
- Average satisfaction — **4.75 / 5**

**Management implication:** Older patient segments may warrant closer monitoring of cost, length of stay, readmission, and patient experience.

---

### 6. High-Cost & Low-Satisfaction Segment

The analysis identified **165 patients**, representing **16.77% of all patients**, who had both:

- High or very-high treatment costs
- Satisfaction scores of 3 or below

The largest condition groups within this segment were:

| Condition | Patients |
|---|---:|
| Heart Attack | 67 |
| Prostate Cancer | 65 |
| Heart Disease | 33 |

**Management implication:** This segment provides a focused population for investigating whether expensive care episodes are also associated with weaker patient experience.

---

## Power BI Dashboard

The Power BI dashboard brings the analysis together into an executive view covering:

- Hospital KPIs
- Treatment cost by condition
- Cost versus hospital utilization
- Readmission by condition
- Age-group performance
- High-cost / low-satisfaction patients

### Dashboard Title

**Hospital Operations & Patient Insights**

*Cost, Resource Utilization, Readmissions & Patient Experience*

### Dashboard Preview

Add the final dashboard screenshot here:

`images/executive_page.png`

---

## Recommendations

Based on the patterns observed in the dataset:

1. **Prioritize high-cost conditions for cost monitoring**  
   Focus analysis on conditions such as Cancer, Prostate Cancer, Heart Attack, and Heart Disease.

2. **Monitor high-utilization conditions**  
   Conditions with longer stays should be considered when planning hospital capacity and resource allocation.

3. **Investigate high-readmission conditions**  
   The conditions with the highest observed readmission rates should receive further review of discharge and follow-up processes.

4. **Monitor patient experience alongside cost**  
   The high-cost/low-satisfaction segment provides a useful target for service-quality review.

5. **Pay closer attention to older patient segments**  
   The 75+ group shows the highest observed cost and readmission rate and the lowest satisfaction in this dataset.

6. **Use segmentation rather than relying only on hospital-wide averages**  
   Segmenting patients by condition, age, cost band, and readmission status provides more actionable insight than overall KPIs alone.

