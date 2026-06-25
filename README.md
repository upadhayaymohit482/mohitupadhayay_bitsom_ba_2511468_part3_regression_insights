# mohitupadhayay_bitsom_ba_2511468_part2_kpi_experiment

**Student:** Mohit Upadhayay | **Program:** BITSOM Business Analytics | **ID:** 2511468

> This repository contains the full solution for **Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation**.

---

## Quick Summary

| Item | Detail |
|---|---|
| Business Scenario | Subscription-based SaaS — evaluating a new onboarding & activation campaign |
| Experiment | A/B test: Control (n=693) vs Treatment (n=715) |
| North Star Metric | Paid Conversion Rate |
| Key Result | Treatment: **6.99%** vs Control: **3.17%** — Z=3.25, p=0.00057 ✅ |
| Recommendation | **Conditional Launch** — address support ticket spike before full rollout |

---

## Repository Structure

```
part2_kpi_experiment/
├── data/
│   └── campaign_experiment_data.xlsx       # Raw experiment dataset (1,408 users)
├── analysis/
│   ├── experiment_analysis.xlsx            # Cleaned data + QA checks
│   └── hypothesis_test_notes.md            # H0/H1, Z-test setup & interpretation
├── outputs/
│   ├── kpi_tree.png                        # KPI tree visual
│   ├── experiment_summary.xlsx             # Metrics summary + 4 segment breakdowns
│   └── recommendation_memo.md             # Full executive recommendation memo
├── screenshots/
│   ├── summary_metrics.png                 # Control vs Treatment comparison table
│   ├── hypothesis_test_output.png          # Z-test output with distribution plot
│   └── kpi_tree_preview.png               # KPI tree screenshot
└── README.md                               # Full project documentation
```

---

## Full Documentation

All detailed documentation — business problem statement, KPI tree explanation, data cleaning steps, hypothesis test results, guardrail analysis, segment insights, and final recommendation — is inside the project folder:

**[View Full README →](./part2_kpi_experiment/README.md)**

