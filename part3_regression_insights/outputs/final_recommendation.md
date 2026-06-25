# Final Business Recommendation

**Prepared for:** Retail Chain Leadership Team  
**Based on:** OLS Regression Analysis — 320 store-month observations, Jan–Apr 2025  
**Final Model:** Multiple Regression (R² = 0.8171)

---

## 1. Which Factors Are Most Strongly Associated with Monthly Sales?

Based on the regression analysis, the following factors show the strongest association with monthly sales:

| Rank | Factor | Evidence |
|---|---|---|
| 1 | **Footfall (store visitor traffic)** | Correlation: 0.857; Coefficient: $28.97/visitor; p < 0.0001 |
| 2 | **Store Type (Airport > Mall > High Street > Residential)** | Airport premium: +$37,673; Mall: +$26,649; High Street: +$15,299 |
| 3 | **Inventory Availability** | Each 1% improvement → +$2,912/month; p < 0.0001 |
| 4 | **Marketing Spend** | Each $1 → +$1.16 in sales; p < 0.0001 |
| 5 | **Staff Count** | Each additional staff → +$2,587/month; p = 0.049 (borderline) |

---

## 2. Which Variables Should Leadership Focus On?

### Priority Actions — High Confidence

**a) Invest in Footfall Generation**
- Footfall is the single largest driver of sales.
- Actions: improve store signage and visibility, partner with local events, enhance online-to-offline traffic (Google Maps, social media, local advertising).
- A 1,000-visitor increase per month drives ~$28,970 additional sales.

**b) Optimize Inventory Availability**
- Inventory stockouts directly cost sales.
- A 10 percentage point improvement in availability (e.g., from 80% to 90%) adds ~$29,115 in monthly sales.
- Actions: strengthen supply chain, improve demand forecasting, reduce overstock on slow-moving SKUs.

**c) Leverage Store Format Advantages**
- Airport stores outperform Residential stores by ~$37,673/month in comparable conditions.
- When evaluating new store openings, prioritize Airport, Mall, and High Street locations over pure Residential formats.

**d) Treat Marketing Spend as a Supporting Lever**
- Marketing contributes positively, but the standalone ROI is modest (≈$1.16 per $1 spent).
- Marketing is most valuable when it drives footfall — the real revenue driver.
- Avoid increasing marketing spend in low-footfall locations without addressing underlying traffic barriers.

**e) Staff Count — Monitor but Don't Overweight**
- Each additional staff member is associated with ~$2,587 more in monthly sales.
- This is borderline significant (p = 0.049); the effect may partly reflect store size or busy trading periods.
- Focus staffing decisions on maintaining service quality, particularly during peak footfall periods.

---

## 3. Which Variables Should Not Be Over-Interpreted?

| Variable | Reason for Caution |
|---|---|
| `avg_discount_pct` | Weakly negative correlation; no significant regression effect. Discounting does not appear to drive meaningful sales improvement. Over-reliance on discounts may erode margin without boosting revenue. |
| `competitor_distance_km` | Weak negative correlation; not statistically significant in multivariate analysis. Distance from competitors alone does not predict performance well. |
| `customer_rating` | Near-zero correlation with sales. While important for brand reputation, current data does not show customer rating significantly predicting monthly sales volumes. |
| `holiday_flag` | Positive correlation (0.19) but not included as a key model predictor. Effect may be partially captured by footfall. |
| `marketing_spend` (standalone) | R² of only 0.16 in simple regression. Do not use marketing spend as a primary strategic lever without also improving footfall and inventory. |

---

## 4. Business Action Recommendations

### Immediate Actions (0–3 months)

1. **Audit inventory availability** at bottom-quartile stores; target raising availability above 90% across all stores.
2. **Identify high-footfall levers** for Residential stores: walk-in promotions, local partnerships, improved local SEO/Google presence.
3. **Review staffing levels** at high-footfall stores to ensure service quality supports conversion.

### Medium-Term Actions (3–12 months)

4. **Redirect marketing budget** from low-footfall stores to traffic-building activities; focus on channels that drive physical visits.
5. **New store location strategy:** Prioritise Airport and Mall formats for future openings based on the format premium identified.
6. **Deep-dive the West region:** Multiple West-region stores show large negative residuals — meaning they underperform even accounting for their inputs. Conduct operational review of West-region stores.

### Longer-Term Strategy

7. **Investigate the top-performing outlier stores** (STR-1030, STR-1073, STR-1032) to identify best practices that can be scaled.
8. **Expand the dataset** to include seasonality (full year), online channel interaction, and neighbourhood income data to improve model accuracy.

---

## 5. Risks and Limitations Leadership Should Keep in Mind

| Risk | Explanation |
|---|---|
| **Omitted variables** | Factors not in the dataset — neighbourhood demographics, local economy, competing brands' promotions, rent/lease quality — are not captured. Results may overstate some effects. |
| **Short time window** | Only 4 months of data (Jan–Apr 2025). Seasonal patterns, year-end peaks, and broader economic cycles are not captured. |
| **Pooled data** | Each store appears 4 times. Store-specific fixed effects (e.g., inherent location quality) are not controlled. This can introduce store-level bias in coefficients. |
| **Multicollinearity** | Footfall and staff_count may be correlated. In stores that get more traffic, more staff are typically deployed. This makes it harder to isolate the independent effect of each. |
| **No causal guarantee** | All findings reflect statistical associations. Leadership should not assume that increasing marketing spend by $X will mechanically produce $1.16X in sales without further testing. |

---

## 6. Why Regression Shows Association, Not Causation

Regression analysis finds the best-fit linear relationship between predictors and outcomes. **It does not prove that one variable causes another.**

Key reasons causation cannot be assumed:

- **Reverse causality:** High-sales stores may invest *more* in marketing because they can afford it — not the other way around. The causal arrow is unclear.
- **Confounding variables:** A store's footfall may be high because it is in a premium shopping district, not because of any store-level action. The district quality drives both footfall and sales.
- **Selection effects:** Airport and Mall stores may attract a different customer demographic than Residential stores, making the comparison imperfect.
- **Omitted variable bias:** If an important driver of sales is not included in the model, its effect gets partially absorbed by the variables that are included, inflating their coefficients.

**To confirm causal relationships, leadership would need controlled experiments** — for example, randomising marketing budget increases across comparable stores and measuring the effect. Regression is a powerful tool for identifying *where to look*, but not a substitute for experimental evidence when making major capital or strategy decisions.

---

## Summary

The regression analysis provides clear evidence that **footfall, inventory availability, marketing spend, and store format** are the most important levers for monthly sales performance. The multiple regression model (R² = 0.8171) offers a reliable, interpretable framework for business planning. Leadership should prioritise actions that drive physical store traffic and ensure products are reliably in stock, while treating marketing spend as a supporting rather than primary tool.
