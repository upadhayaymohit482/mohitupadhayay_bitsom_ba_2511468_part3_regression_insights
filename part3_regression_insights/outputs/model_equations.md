# Model Equations

## 1. Dummy Variable Approach

### Why Dummy Variables Are Needed

The variable `store_type` is categorical with four categories: **Residential, High Street, Airport, Mall**. Regression models require numerical inputs. Dummy variables convert each category into a binary (0/1) numeric column.

### Categories and Dummies Created

| Category | Dummy Variable | Value |
|---|---|---|
| Residential | *(Reference — omitted)* | 0 in all dummies |
| High Street | `store_type_HighStreet` | 1 if High Street, else 0 |
| Airport | `store_type_Airport` | 1 if Airport, else 0 |
| Mall | `store_type_Mall` | 1 if Mall, else 0 |

### Reference Category

**Reference Category = Residential**

This means all store-type dummy coefficients are interpreted **relative to Residential stores**. A positive coefficient on `store_type_Airport` means Airport stores generate more monthly sales than Residential stores, holding all other factors constant.

**Why Residential was chosen:** It is the most common store format in the dataset, making it a natural baseline for comparison.

**Why we use K−1 dummies (not K):** Using all 4 categories would create perfect multicollinearity (the "dummy variable trap"). One category must always be dropped as the reference.

---

## 2. Simple Regression Equation — Model 1

### Model 1: Monthly Sales ~ Footfall

```
monthly_sales = 447,699.03 + 35.64 × footfall
```

| Term | Value | Meaning |
|---|---|---|
| Intercept | $447,699 | Baseline predicted sales if footfall = 0 |
| footfall coefficient | $35.64 | Each additional store visitor adds ~$35.64 in monthly sales |
| R-Squared | 0.7348 | Footfall explains 73.5% of monthly sales variation |
| P-value | < 0.0001 | Highly statistically significant |

**Business meaning:** Stores with higher foot traffic generate substantially higher sales. For every 1,000 additional monthly visitors, expected sales increase by approximately $35,640.

---

## 3. Simple Regression Equation — Model 2

### Model 2: Monthly Sales ~ Marketing Spend

```
monthly_sales = 567,463.56 + 2.05 × marketing_spend
```

| Term | Value | Meaning |
|---|---|---|
| Intercept | $567,464 | Baseline predicted sales if marketing spend = $0 |
| marketing_spend coefficient | $2.05 | Each $1 increase in marketing spend adds ~$2.05 in monthly sales |
| R-Squared | 0.1574 | Marketing spend explains 15.7% of monthly sales variation |
| P-value | < 0.0001 | Statistically significant |

**Business meaning:** Marketing spend has a positive association with sales but explains only a small proportion of total variation. Marketing ROI (revenue per dollar spent) is approximately 2.05× when considered in isolation.

---

## 4. Multiple Regression Equation — Model 3 (Final Model)

```
monthly_sales = 110,752
              + 28.97 × footfall
              +  1.16 × marketing_spend
              +  2,587.09 × staff_count
              +  2,911.55 × inventory_availability_pct
              + 15,298.74 × store_type_HighStreet
              + 37,673.40 × store_type_Airport
              + 26,648.99 × store_type_Mall
```

---

## 5. Coefficient Explanations (Multiple Regression)

| Variable | Coefficient | Interpretation |
|---|---|---|
| **Intercept** | $110,752 | Baseline monthly sales for a Residential store, with all numerical predictors at zero. Not practically meaningful in isolation. |
| **footfall** | $28.97 | Each additional monthly visitor adds ~$28.97 in sales, holding other variables constant. A 1,000-person increase in footfall drives ~$28,970 more in monthly sales. |
| **marketing_spend** | $1.16 | Each additional $1 in marketing spend adds ~$1.16 in monthly sales. Note: ROI drops from $2.05 (simple model) to $1.16 when other factors are controlled. |
| **staff_count** | $2,587 | Each additional staff member is associated with ~$2,587 more in monthly sales. Borderline significant (p=0.049). |
| **inventory_availability_pct** | $2,912 | Each 1 percentage point improvement in inventory availability adds ~$2,912 in monthly sales. A store improving from 80% to 90% availability could gain ~$29,115 in monthly sales. |
| **store_type_HighStreet** | $15,299 | High Street stores generate ~$15,299 more per month than equivalent Residential stores. |
| **store_type_Airport** | $37,673 | Airport stores generate ~$37,673 more per month than equivalent Residential stores — the largest store-type premium. |
| **store_type_Mall** | $26,649 | Mall stores generate ~$26,649 more per month than equivalent Residential stores. |

---

## 6. Final Model Selected

**Model 3 — Multiple Regression** is the final model.

**Equation:**
```
monthly_sales = 110,752 + 28.97×footfall + 1.16×marketing_spend
              + 2,587×staff_count + 2,912×inventory_availability_pct
              + 15,299×HighStreet + 37,673×Airport + 26,649×Mall
```

---

## 7. Reason for Selecting Model 3

| Criterion | Justification |
|---|---|
| **Highest R²** | R² = 0.8171 vs. 0.7348 (Model 1) and 0.1574 (Model 2) |
| **All coefficients significant** | Every predictor has p < 0.05 |
| **Business completeness** | Captures multiple actionable levers: traffic, marketing, inventory, staffing, and store format |
| **Reduced omitted variable bias** | Controlling for store type prevents confounding between format and other predictors |
| **Adjusted R²** | 0.8128 confirms the added predictors genuinely improve the model (not just overfitting) |

Model 3 is not only statistically superior but also more useful for business decision-making, as it enables leadership to simulate the impact of changing any one of the key inputs.
