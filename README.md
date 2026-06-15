# PossiblePage Labs — Revenue Quality Case

Synthetic AI + business strategy case on **revenue quality** in a B2B no-code SaaS.

## Executive question

Not: **How much revenue did Sales close?**

But: **How much of that revenue is still healthy after 90/180 days?**

The case simulates a realistic management problem: some revenue looks good at deal close, but becomes fragile when low-fit customers or misaligned beta-feature promises create support overload, poor customer health, lower NPS/CSAT and churn.

## Dataset

All data is synthetic. No real customer, company or personal data is included.

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
- Revenue Quality Risk Index.
- Segmentation into Healthy / Watchlist / Risky / Toxic.
- HTML dashboard ready for GitHub Pages.
- LinkedIn carousel assets showing the business argument.

## Key findings from this generated version

- Closed MRR: **€2,989,287**.
- Surviving MRR after 180 days: **€2,786,514**.
- MRR churned within 180 days: **€202,773**.
- 180-day account churn rate: **6.8%**.
- Risky + Toxic revenue share: **7.1%**.
- Toxic accounts generate **2.5×** the first-90-day ticket volume of Healthy accounts.
- Beta-promised accounts churn at **15.1%** within 180 days vs **4.0%** for non-beta-promised accounts.

## Strategic recommendation

Sales incentives should not be based only on closed revenue. A revenue-quality component should be added to the commercial KPI framework, reducing variable compensation when early churn, support overload or post-sale health deterioration exceed defined thresholds.

This is not about penalizing Sales. It is about aligning Sales, Customer Success, Support and Product around revenue that survives.

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
│   └── key_metrics.json
├── docs/
│   ├── DATA_DICTIONARY.md
│   └── LINKEDIN_POST.md
└── assets/
    └── linkedin-carousel/
```

## How to view the dashboard locally

Open `index.html` in a browser.

## Suggested GitHub Pages setup

1. Create a public GitHub repository, for example `possiblepage-labs-revenue-quality`.
2. Upload all files in this folder.
3. In GitHub: **Settings → Pages**.
4. Select deployment from branch, then choose `main` and `/root`.
5. GitHub will generate the public dashboard URL.

## Notes

`closed_mrr_eur` is booked MRR at deal close, not current active MRR. This is deliberate: it enables the case to compare revenue closed vs revenue that survives after 90/180 days.
