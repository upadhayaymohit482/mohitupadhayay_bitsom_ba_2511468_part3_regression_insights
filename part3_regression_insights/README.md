# Part 3: Regression-Based Business Insights & Model Interpretation

## Business Problem Summary

A retail chain leadership team wants to understand what factors drive monthly sales performance across stores. The objective is to identify which variables are most strongly associated with monthly sales and provide data-driven business recommendations on marketing spend, inventory, staffing, and store strategy.

---

## Dataset Description

**File:** `data/business_regression_data.xlsx`  
**Records:** 320 observations (80 stores × 4 months: Jan–Apr 2025)  
**Columns:** 14

| Column | Type | Description |
|---|---|---|
| store_id | Categorical (ID) | Unique store identifier |
| month | Date | Observation month |
| region | Categorical | Store region: East, North, South, West |
| store_type | Categorical | Store format: Residential, High Street, Airport, Mall |
| marketing_spend | Numerical | Monthly marketing expenditure ($) |
| footfall | Numerical | Monthly customer visitor count |
| avg_discount_pct | Numerical | Average discount percentage offered |
| staff_count | Numerical | Number of staff deployed |
| inventory_availability_pct | Numerical | % of SKUs available in inventory |
| competitor_distance_km | Numerical | Distance to nearest competitor (km) |
| holiday_flag | Binary (0/1) | Whether month contained a public holiday |
| customer_rating | Numerical | Average customer satisfaction rating |
| monthly_sales | Numerical | **Dependent variable** — monthly revenue ($) |
| monthly_profit | Numerical | Monthly profit ($) — excluded from regression |

---

## Dependent and Independent Variables

**Dependent Variable:**
- `monthly_sales` — the outcome we are trying to explain and predict

**Independent Variables Used in Regression:**
- `footfall` — primary driver (strongest correlation)
- `marketing_spend` — second strongest driver
- `staff_count` — moderate association
- `inventory_availability_pct` — moderate association
- `store_type` (dummy variables) — categorical predictor
- `region` (dummy variables) — categorical predictor

**Variables Excluded from Core Models:**
- `monthly_profit` — outcome variable, not a predictor of sales
- `store_id` — identifier only
- `month` — date column; not used as a numeric predictor in this analysis
- `avg_discount_pct` — very weak/negative correlation (−0.076)
- `competitor_distance_km` — weak correlation (−0.099); 6 missing values
- `customer_rating` — negligible correlation (−0.026); 8 missing values
- `holiday_flag` — weak positive correlation (0.190)

---

## Regression Approach

1. **Simple Regression Models:** Two models, each using one independent variable to predict `monthly_sales`
   - Model 1: `monthly_sales ~ footfall`
   - Model 2: `monthly_sales ~ marketing_spend`

2. **Multiple Regression Model:** One model using multiple predictors simultaneously
   - Model 3: `monthly_sales ~ footfall + marketing_spend + staff_count + inventory_availability_pct + store_type_dummies`

All models were estimated using Ordinary Least Squares (OLS).

---

## Dummy Variable Approach

**Categorical variable encoded:** `store_type`  
**Categories:** Residential, High Street, Airport, Mall  
**Reference category:** Residential (omitted to avoid multicollinearity)  
**Dummy variables created:**
- `store_type_HighStreet` (1 if High Street, else 0)
- `store_type_Airport` (1 if Airport, else 0)
- `store_type_Mall` (1 if Mall, else 0)

See `outputs/model_equations.md` for full explanation.

---

## Model Comparison Summary

| Model | R-Squared | Key Variables | Use |
|---|---|---|---|
| Model 1: Footfall | 0.7348 | footfall | Strong simple predictor |
| Model 2: Marketing Spend | 0.1574 | marketing_spend | Weak alone |
| Model 3: Multiple | 0.8171 | footfall, marketing_spend, inventory, store_type | Best overall |

---

## Final Model Selected

**Model 3 — Multiple Regression** is the final recommended model.

- R² = 0.8171 (explains ~82% of variance in monthly sales)
- All key variables are statistically significant (p < 0.05)
- Includes both numerical and categorical predictors
- Provides actionable levers for leadership

---

## Business Recommendation

Leadership should prioritize:
1. **Footfall** — strongest driver of sales; invest in location-level traffic generation
2. **Inventory Availability** — each 1% improvement adds ~$2,912 in monthly sales
3. **Marketing Spend** — positive ROI; each additional $1 in spend adds ~$1.16 in sales
4. **Store Type** — Airport and Mall formats outperform Residential stores significantly
5. **Staff Count** — meaningful but more modest effect

See `outputs/final_recommendation.md` for full details.

---

## Assumptions and Limitations

- Regression shows **association**, not causation
- Assumes linear relationship between predictors and sales
- Omitted variables (seasonality, economic conditions, local competition intensity) may affect results
- 14 records dropped due to missing values in `customer_rating` and `competitor_distance_km`
- Store-level fixed effects are not controlled for in this pooled OLS model

---

## Screenshots Included

| File | Content |
|---|---|
| `screenshots/simple_regression_output.png` | Simple regression — footfall model output |
| `screenshots/multiple_regression_output.png` | Multiple regression full output |
| `screenshots/residuals_preview.png` | Predicted vs actual values and residuals |
| `screenshots/model_comparison_preview.png` | Model comparison summary table |
