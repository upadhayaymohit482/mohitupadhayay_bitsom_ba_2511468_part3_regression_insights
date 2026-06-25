# Residual Analysis

## Overview

This document presents the residual analysis for Model 3 (Multiple Regression). Residuals are calculated as:

**Residual = Actual Monthly Sales − Predicted Monthly Sales**

A positive residual means the model **under-predicted** actual sales (the store performed better than expected).  
A negative residual means the model **over-predicted** actual sales (the store performed worse than expected).

---

## Records with Largest Positive Residuals (Under-Predicted)

These stores sold significantly more than the model expected given their characteristics.

| # | Store ID | Store Type | Region | Actual Sales ($) | Predicted Sales ($) | Residual ($) |
|---|---|---|---|---|---|---|
| 1 | STR-1030 | Residential | West | 820,519 | 715,779 | **+104,740** |
| 2 | STR-1073 | Residential | East | 813,317 | 713,727 | **+99,589** |
| 3 | STR-1028 | Mall | East | 713,611 | 614,470 | **+99,141** |
| 4 | STR-1032 | High Street | South | 914,544 | 819,946 | **+94,598** |
| 5 | STR-1026 | Mall | East | 625,514 | 531,107 | **+94,407** |

### Business Interpretation — Positive Residuals

These stores are **outperforming** what their observable characteristics would predict. Possible reasons include:

- **Loyal customer base or community reputation** not captured in the data
- **Superior store management quality** — execution, staff motivation, or local leadership
- **Micro-location advantages** — e.g., high footfall street corner, near transit hub, or in a high-income neighbourhood
- **Local events or partnerships** that temporarily boosted sales in those months
- **Product mix advantages** — stocking premium or locally popular products

**Recommendation:** Leadership should investigate what these stores do differently and consider replicating their practices at underperforming locations.

---

## Records with Largest Negative Residuals (Over-Predicted)

These stores sold significantly less than the model expected given their characteristics.

| # | Store ID | Store Type | Region | Actual Sales ($) | Predicted Sales ($) | Residual ($) |
|---|---|---|---|---|---|---|
| 1 | STR-1017 | High Street | West | 685,379 | 837,196 | **−151,816** |
| 2 | STR-1012 | Residential | West | 595,468 | 721,997 | **−126,530** |
| 3 | STR-1023 | Mall | South | 627,172 | 742,725 | **−115,553** |
| 4 | STR-1007 | Mall | West | 800,452 | 904,335 | **−103,883** |
| 5 | STR-1001 | Residential | East | 658,920 | 762,578 | **−103,658** |

### Business Interpretation — Negative Residuals

These stores are **underperforming** relative to what their inputs would predict. Possible reasons include:

- **Operational challenges** — poor staff management, high turnover, or execution gaps
- **Local competition pressure** not fully reflected in the competitor distance metric
- **Product assortment mismatch** — stocking items that don't match local demand
- **Lease or physical store limitations** — poor store layout, limited parking, or unattractive presentation
- **Local economic conditions** — lower income area or recent local economic downturn
- **West region effect** — multiple large negative residuals are in the West region, suggesting a possible regional factor not captured in the model

---

## Under-Prediction vs Over-Prediction Pattern

| Pattern | Store Count in Top/Bottom 5 | Possible Systemic Issue |
|---|---|---|
| West region stores over-predicted (negative residuals) | 3 of bottom 5 | West region may face challenges not reflected in inputs |
| Residential stores appear in both top and bottom | Mixed | High variability in Residential store performance |
| Mall stores under-perform in South | 1 notable case | South region Mall stores may face unique local pressure |

---

## Model Accuracy Assessment

- The model explains **81.7%** of sales variance, leaving ~18.3% unexplained
- Largest residuals are up to ±$150,000 on sales ranging from ~$400K to ~$950K
- Most residuals are within ±$50,000, indicating reasonable model fit
- The residual pattern does not appear to be systematically biased upward or downward overall, but there is a **West region cluster of over-prediction**

---

## Conclusion

The residual analysis reveals that while the model is a strong predictor overall, certain stores — particularly in the West region — are consistently outperformed or underperformed relative to model expectations. This suggests that **unmeasured local factors** (management quality, neighbourhood dynamics, or regional economic conditions) play a meaningful role. Leadership should conduct store-level qualitative investigations for the top outlier stores identified above.
