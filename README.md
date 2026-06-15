# PossiblePage Labs — Revenue Quality & Churn Risk Case

Synthetic AI + business strategy case on **revenue quality** in a B2B no-code SaaS.

> **All data is synthetic. No real customer, company or personal data is included.**  
> **Copyright © 2026 Flavia Occhini. All rights reserved.**  
> This repository is published for portfolio and demonstration purposes only. No permission is granted to copy, reuse, modify, redistribute or use this work commercially without explicit written consent.

## Executive recommendation

Sales incentives should not be based only on closed revenue. A **Revenue Quality KPI** should be added to the commercial framework, linked to early churn, support overload, onboarding completion and customer health within the first 90/180 days.

This is not about penalizing Sales. It is about aligning Sales, Customer Success, Support and Product around revenue that survives.

## Executive question

Not: **How much revenue did Sales close?**

But: **How much of that revenue is still healthy after 90/180 days?**

The case simulates a realistic management problem: some revenue looks good at deal close, but becomes fragile when low-fit customers or misaligned beta-feature promises create support overload, poor customer health, lower NPS/CSAT and churn.

## What kind of business is PossiblePage Labs?

Based on the simulated numbers, PossiblePage Labs reads as a **mid-market / scaling B2B SaaS** selling mainly to SMB and mid-market customers.

Evidence:

- **1,500** paying accounts in the clean table.
- **€35.9M** simulated annual contract value / ARR proxy.
- **€24k** average ACV and **€14k** median ACV.
- Plan mix is mostly Starter / Growth / Scale, with Enterprise at **6.5%**.
- Customer employee bands are mostly 11-50 and 51-200 employees.

It is not a tiny small business, because the simulated ARR and customer base are too large. It is also not a pure enterprise SaaS, because the plan mix and customer-size bands skew toward SMB and mid-market.

## Dataset

| Source | Grain | Rows |
|---|---:|---:|
| `sales_deals_raw.csv` | Deal | 1,565 raw rows → 1,500 accounts |
| `onboarding_product_usage_raw.csv` | Account | 1,380 rows, 8% intentionally absent |
| `support_tickets_raw.csv` | Ticket | 4,713 tickets across 1,316 accounts |
| `customer_health_monthly_raw.csv` | Account-month | 18,000 rows = 1,500 × 12 months |
| `clean_account_table.csv` | Account | 1,500 accounts × 38 columns |

## What I built

- Raw synthetic data with intentional data-quality issues.
- End-to-end reconciliation into a clean account table.
- Corrected economic logic for `discount_pct`, recalculated from source value fields.
- Anonymized synthetic Sales Rep labels: `Sales Rep #1`, `Sales Rep #2`, etc.
- Revenue Quality Risk Index.
- Segmentation into Healthy / Watchlist / Risky / Toxic.
- Public HTML dashboard ready for GitHub Pages.
- Business recommendations based on commercial quality, churn risk and support load.

## Key findings

- Closed MRR: **€3.0M**.
- Simulated ARR / annual contract value: **€35.9M**.
- Surviving MRR after 180 days: **€2.8M**.
- MRR churned within 180 days: **€203k**.
- 180-day account churn rate: **6.8%**.
- Risky + Toxic revenue share: **7.1%**.
- Toxic accounts generate **2.5×** the first-90-day ticket volume of Healthy accounts.
- Beta-promised accounts churn at **15.1%** within 180 days vs **4.0%** for non-beta-promised accounts.

## Support-load spillover hypothesis

The dataset includes a directional proxy: high-ticket-volume months show lower average NPS and CSAT than lower-load months. This supports the business hypothesis that low-quality revenue can create operational strain that affects the broader customer experience.

This is a proxy, not a causal proof: the dataset does not directly measure internal team sentiment or workload capacity. The management implication is that fragile revenue can create cross-functional friction between Sales, Customer Success, Support and Product when incentives are not aligned.

## Repo structure

```text
.
├── index.html
├── data/
│   ├── raw/
│   └── processed/
├── analysis/
│   ├── discount_pct_reconciliation.csv
│   ├── qa_checks_summary.csv
│   ├── key_metrics.json
│   ├── revenue_quality_segment_summary.csv
│   ├── sales_rep_quality_summary.csv
│   ├── cohort_quality_comparison.csv
│   ├── support_load_proxy_monthly.csv
│   ├── support_load_spillover_proxy.json
│   └── business_sizing_summary.json
├── docs/
│   └── DATA_DICTIONARY.md
└── assets/
    └── dashboard-screens/
```

## How to view the dashboard locally

Open `index.html` in a browser.

## Suggested GitHub Pages setup

1. Create or open the public GitHub repository.
2. Upload the files and folders in this repository to the root.
3. Go to **Settings → Pages**.
4. Select **Deploy from a branch**.
5. Choose branch `main` and folder `/ (root)`.
6. Save and wait for GitHub Pages to publish the dashboard.
