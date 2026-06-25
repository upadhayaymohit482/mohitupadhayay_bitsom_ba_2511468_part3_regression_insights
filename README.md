# Part 3: Regression-Based Business Insights & Model Interpretation

| | |
|---|---|
| **Name** | Mohit Upadhayay |
| **Student ID** | 2511468 |
| **Program** | Business Analytics — BITS School of Management (BITSOM) |
| **Assignment** | BA Project — Part 3 |

---

## 📌 Project Overview

This project applies **Simple and Multiple Linear Regression** to analyse monthly sales performance across 80 retail stores (320 observations) and deliver data-driven business recommendations to store leadership.

The analysis identifies which factors — such as store footfall, marketing spend, inventory availability, and store format — are most strongly associated with monthly sales, and quantifies the contribution of each.

---

## 🗂️ Repository Structure

```
mohitupadhayay_bitsom_ba_2511468_part3_regression_insights/
│
├── README.md                          ← You are here (root overview)
│
└── part3_regression_insights/         ← Main project folder
    ├── README.md                      ← Detailed project documentation
    ├── data/
    │   └── business_regression_data.xlsx
    ├── analysis/
    │   ├── regression_workbook.xlsx
    │   ├── model_comparison.md
    │   └── residual_analysis.md
    ├── outputs/
    │   ├── regression_summary.xlsx
    │   ├── final_recommendation.md
    │   └── model_equations.md
    └── screenshots/
        ├── simple_regression_output.png
        ├── multiple_regression_output.png
        ├── residuals_preview.png
        └── model_comparison_preview.png
```

---

## 🔍 Key Findings at a Glance

| Model | Variables | R-Squared |
|---|---|---|
| Model 1 — Simple Regression | Footfall | 0.7348 |
| Model 2 — Simple Regression | Marketing Spend | 0.1574 |
| **Model 3 — Multiple Regression** | Footfall + Marketing + Inventory + Staff + Store Type | **0.8171** |

**Top business drivers of monthly sales:**
- 🏃 **Footfall** — strongest single predictor; each 1,000 additional visitors → +$28,970 in sales
- 📦 **Inventory Availability** — each 1% improvement → +$2,912 in monthly sales
- 📢 **Marketing Spend** — each $1 invested → +$1.16 in sales
- 🏪 **Store Type** — Airport stores outperform Residential stores by ~$37,673/month

---

## 📄 Full Documentation

👉 **[View the detailed project README here](./part3_regression_insights/README.md)**

---

## 🛠️ Tools & Methods

- **Method:** Ordinary Least Squares (OLS) Regression
- **Dataset:** 320 store-month observations (80 stores × 4 months, Jan–Apr 2025)
- **Tools:** Python (pandas, numpy, scipy, matplotlib, openpyxl)
- **Dummy Variables:** store_type encoded with Residential as reference category
- **Files:** Excel workbooks, Markdown reports, PNG screenshots
