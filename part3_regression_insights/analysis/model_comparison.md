# Model Comparison

## Overview

This document compares the two simple regression models and one multiple regression model built to explain monthly sales performance across retail stores.

---

## Model 1: Simple Regression — Footfall

| Item | Detail |
|---|---|
| **Model Name** | Model 1 — Simple Regression (Footfall) |
| **Dependent Variable** | monthly_sales |
| **Independent Variable** | footfall |
| **R-Squared** | 0.7348 |
| **Coefficient** | 35.64 (each additional visitor adds ~$35.64 in monthly sales) |
| **Intercept** | $447,699 |
| **P-value (footfall)** | < 0.0001 (highly significant) |
| **Significant Variables** | footfall |
| **Business Usefulness** | Very high. Footfall alone explains 73.5% of monthly sales variation. This tells leadership that driving store traffic is the single most important lever for revenue. |
| **Limitations** | Ignores marketing spend, inventory, store format, and other drivers. Cannot distinguish what *causes* footfall to be high. May overestimate the impact of footfall for stores where other variables suppress sales. |

---

## Model 2: Simple Regression — Marketing Spend

| Item | Detail |
|---|---|
| **Model Name** | Model 2 — Simple Regression (Marketing Spend) |
| **Dependent Variable** | monthly_sales |
| **Independent Variable** | marketing_spend |
| **R-Squared** | 0.1574 |
| **Coefficient** | 2.05 (each additional $1 in marketing adds ~$2.05 in monthly sales) |
| **Intercept** | $567,464 |
| **P-value (marketing_spend)** | < 0.0001 (significant) |
| **Significant Variables** | marketing_spend |
| **Business Usefulness** | Moderate. Marketing spend alone explains only 15.7% of sales variance. While statistically significant, its explanatory power is weak on its own. It becomes more useful in combination with other predictors. |
| **Limitations** | Marketing spend may be correlated with store size and type. Very low R² means most sales variation is left unexplained. A positive coefficient doesn't confirm causation — larger stores tend to spend more on marketing and also have higher sales. |

---

## Model 3: Multiple Regression — Full Model

| Item | Detail |
|---|---|
| **Model Name** | Model 3 — Multiple Regression |
| **Dependent Variable** | monthly_sales |
| **Independent Variables** | footfall, marketing_spend, staff_count, inventory_availability_pct, store_type_HighStreet, store_type_Airport, store_type_Mall |
| **R-Squared** | 0.8171 |
| **Adjusted R-Squared** | 0.8128 |
| **N (observations)** | 306 |
| **Significant Variables** | footfall (p<0.0001), marketing_spend (p<0.0001), inventory_availability_pct (p<0.0001), store_type_Airport (p<0.0001), store_type_Mall (p=0.0001), store_type_HighStreet (p=0.015), staff_count (p=0.049) |
| **Business Usefulness** | High. The model explains ~82% of the variation in monthly sales. It identifies multiple actionable levers and quantifies the incremental value of each. Leadership can use this model to simulate the expected impact of changes in marketing spend, inventory, or store format decisions. |
| **Limitations** | Does not account for store-specific fixed effects (e.g., location quality, lease terms). Does not capture seasonality beyond a 4-month window. Assumes linear additive relationships. Cannot prove causation. Omits competitor pricing, economic conditions, and online channel effects. |

---

## Comparative Summary Table

| Metric | Model 1 (Footfall) | Model 2 (Marketing) | Model 3 (Multiple) |
|---|---|---|---|
| R-Squared | 0.7348 | 0.1574 | **0.8171** |
| Adjusted R² | — | — | **0.8128** |
| # of Predictors | 1 | 1 | 7 |
| Significant Variables | 1 | 1 | 7 |
| Explains Residual Variation | No | No | Substantially |
| Business Applicability | Moderate | Low | **High** |
| Recommended | No | No | **Yes** |

---

## Conclusion

**Model 3 (Multiple Regression)** is the best model. It combines the strong predictive power of footfall with additional meaningful variables — marketing spend, inventory availability, staff count, and store type — to explain over 82% of the variation in monthly sales. Each coefficient in the model is statistically significant, and the model provides leadership with multiple actionable levers for business improvement.

Model 1 is a useful diagnostic tool to understand the importance of footfall, but it should not be used in isolation for business planning. Model 2 has limited standalone value due to its low R².
