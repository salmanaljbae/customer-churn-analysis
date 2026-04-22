# Customer Churn Analysis — Databel

> A business-focused Power BI project analyzing customer churn drivers, behavioral risk patterns, and retention opportunities.

---

## Project Status

`Completed` &nbsp;|&nbsp; **Tool:** Power BI &nbsp;|&nbsp; **Data Source:** DataCamp Dataset

---

## Table of Contents

- [Business Problem](#business-problem)
- [Challenges](#challenges)
- [Tools Used](#tools-used)
- [How to Use](#how-to-use)
- [Analytical Story](#analytical-story)
- [Dashboard Overview](#dashboard-overview)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)
- [Deliverables](#deliverables)
- [Author](#author)

---

## Business Problem

Databel is facing a high customer churn rate, leading to significant revenue loss and a decline in customer lifetime value.

**Monthly Revenue Leakage: $66,094**, compared with a target of $46,266, representing **42.86% above the acceptable threshold**.

If left unaddressed, this trend will continue to affect both short-term revenue and long-term business value.

---

## Challenges

The raw dataset presented several analytical challenges:

- **Single flat table** with 29 columns, requiring restructuring for analysis
- **Noisy fields** that were not relevant to churn analysis and required careful filtering
- **Multiple interrelated variables** across customers, services, and contracts that needed thoughtful segmentation and modeling

---

## Tools Used

| Tool | Purpose |
|---|---|
| **Power BI** | Dashboard design and data visualization |
| **Power Query** | Data cleaning, transformation, and preparation |
| **DAX** | Calculated measures, KPIs, and conditional logic |

---

## How to Use

### Option 1 — Power BI Desktop (Interactive)
1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) if it is not already installed.
2. Open the `.pbix` file included in this repository.
3. Explore the dashboard pages interactively.

### Option 2 — PDF Preview (Read-only)
1. Go to the `/docs` folder in this repository.
2. Open the `.pdf` file for a static view of the dashboard pages.

---

## Analytical Story

### Framework

This analysis follows a **top-down investigative approach**, moving from the overall problem to the underlying drivers:

```text
What is driving churn? → Who is churning? → Under what conditions? → Where is churn concentrated?
```

### Step 1 — Defining KPIs and Churn Scope

Established the overall churn rate at **26.86%** and identified the main churn categories as the starting point for deeper investigation.

### Step 2 — Data Cleaning and Preparation

| Table | Action |
|---|---|
| `Fact_Subscriptions` | Set international charges to $0 when `International Plan = No` |
| `Dim_Customer` | Grouped `Prefer not to say` under `Other` for cleaner segmentation |
| All dimension tables | Applied `Table.Distinct` on Customer ID to remove duplicates |

### Step 3 — Data Modeling

The flat table was restructured into a **star schema** to improve clarity, performance, and analytical flexibility:

```text
Fact_Subscriptions      →  Transactional and numerical data
Dim_Customer            →  Demographics such as state, gender, and age groups
Dim_Contract_Service    →  Plans, contracts, and payment methods
Dim_Churn               →  Churn categories, labels, and reasons
```
![Data Model](images/data%20set%20diagram.png)

### Step 4 — Measure Design

Created measures and KPIs in DAX to support churn tracking, segmentation, and comparison across customer groups.

---

## Dashboard Overview

The dashboard contains four connected pages.

### 1. Churn Drivers

![Churn Drivers](images/Churn%20Drivers.png)

This page identifies the main reasons customers leave.

**Key findings:**
- Competition is the dominant churn driver.
- The most common reasons were better offers and better devices from competitors.
- Pricing dissatisfaction and service attitude were also important factors.

### 2. Customer Behavior

![Customer Behavior](images/Customer%20Behavior.png)

This page examines behavioral patterns associated with churn risk.

**Key findings:**
- Customers with **2 or more service calls** show a churn rate of **66%**, compared with **9%** for customers with no calls.
- Customers with **tenure under 1 year** are at much higher risk.
- Customers without an assigned plan group form a concentrated high-risk segment.

**High-risk profile:** No assigned group + tenure under 1 year + more than 2 service calls

### 3. Plan and Contract Analysis

![Plan & Contract Analysis](images/Plan%20%26%20Contract%20Analysis.png)


This page explores how pricing and contract structure affect churn.

**Key findings:**
- Month-to-month contracts show a churn rate of **46.29%**, compared with **2.78%** for two-year contracts.
- Customers with unlimited data plans churn at **32.11%**, compared with **16.10%** for those without.
- Paper check payment is associated with the highest churn rate.

**High-risk profile:** Month-to-month + unlimited data plan + age above 60

### 4. Geographic Distribution

![Geographic Distribution](images/Geographic%20Distribution.png)

This page maps churn concentration across U.S. states.

**Key findings:**
- California ranks highest in churn rate by a clear margin.
- Most states remain relatively stable, suggesting the issue is concentrated in a few outlier regions.
- The pattern points to possible regional competition or service-quality differences.

---

## Key Insights

1. Competition is the primary churn driver, with customers leaving for better value.
2. The business is losing **$66,094 per month** in revenue, which is well above the acceptable target.
3. High service call volume is a strong leading indicator of churn.
4. Short-tenure customers are disproportionately at risk.
5. Month-to-month contracts carry far higher churn risk than long-term contracts.
6. Unlimited data plan pricing appears misaligned with perceived value.
7. California requires immediate, focused retention attention.
8. Customers often try to resolve issues before leaving, which makes service quality a key retention lever.

---

## Recommendations

| Priority | Action |
|---|---|
| **High** | Monitor and respond to competitor offers in real time |
| **High** | Redesign pricing for unlimited data plans to better align value and cost |
| **High** | Improve first-contact resolution to reduce repeat service calls |
| **Medium** | Offer targeted retention campaigns for month-to-month customers |
| **Medium** | Launch a California-specific retention initiative |
| **Low** | Assign plan groups to all ungrouped customers for better tracking and targeting |

---

## Deliverables

- Power BI dashboard file (`.pbix`)
- PDF version of the report
- README documentation

---

## Author

**Salman Al-Jabai**  
Data Analysis | MIS Student

[![Email](https://img.shields.io/badge/Email-salmansss113%40gmail.com-blue?style=flat&logo=gmail)](mailto:salmansss113@gmail.com)

---

<div align="center">

*From identifying the problem to uncovering root causes, this project demonstrates a structured and business-driven approach to churn analysis.*

</div>