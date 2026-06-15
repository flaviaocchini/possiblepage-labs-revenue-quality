# Data dictionary — PossiblePage Labs

All files are synthetic and generated for a public business analytics case. Currency is EUR.

Sales rep names are intentionally anonymized as `Sales Rep #1`, `Sales Rep #2`, etc.

## Clean account table columns

- `account_id` — Canonical account key after raw-source reconciliation.
- `account_name` — Synthetic account name.
- `industry` — Simulated customer industry.
- `employee_band` — Company size band of the customer, not of PossiblePage Labs.
- `plan` — Commercial plan sold.
- `sales_rep` — Anonymized synthetic sales representative label: Sales Rep #1, Sales Rep #2, etc.
- `acquisition_channel` — Sales / marketing acquisition channel.
- `close_date` — Deal close date.
- `contract_start_date` — Contract start date.
- `gross_contract_value_eur` — Annual gross contract value before discounts.
- `contract_value_eur` — Clean annual contract value. Impossible rows are capped to gross value and flagged.
- `discount_pct` — Clean discount percentage, recalculated as 1 - contract_value / gross_contract_value.
- `discount_anomaly_flag` — TRUE when the raw discount was inconsistent or source economic values were impossible.
- `closed_mrr_eur` — Monthly recurring revenue booked at deal close. This is not active current MRR.
- `sales_fit_score` — Synthetic sales/customer-fit score, 0-100.
- `low_fit_flag` — TRUE when sales_fit_score < 55.
- `beta_feature_promised` — TRUE if a beta feature was part of the commercial promise.
- `beta_feature_category` — Promised beta feature category; five missing values are intentionally retained.
- `product_record_present` — TRUE if the account appears in Product usage raw data.
- `onboarding_completed` — TRUE if onboarding was completed.
- `activation_days` — Days from start to first meaningful activation.
- `feature_adoption_rate` — Share of key features adopted, 0-1.
- `weekly_active_users` — Synthetic weekly active users.
- `pages_published` — Number of pages published through the platform.
- `ecommerce_enabled` — TRUE if mini e-commerce was enabled.
- `support_ticket_count_90d` — Number of support tickets opened in first 90 days.
- `support_ticket_count_180d` — Number of support tickets opened in first 180 days.
- `avg_first_response_hours` — Average support first-response time; raw contains five intentionally missing values.
- `avg_support_csat` — Average support CSAT after removing out-of-range raw values.
- `latest_health_score` — Latest valid customer health score in the 12-month window.
- `avg_nps_6m` — Average valid NPS in the last six months of observation.
- `avg_csat_6m` — Average valid CSAT in the last six months of observation.
- `churned_90d` — TRUE if the account churned within 90 days.
- `churned_180d` — TRUE if the account churned within 180 days.
- `churned_12m` — TRUE if the account churned within 12 months.
- `churn_reason` — Reason for observed churn, plus five post-window reasons intentionally retained.
- `revenue_quality_risk_index` — Composite risk index from fit, support load, product adoption, beta promises, health and churn signals.
- `revenue_quality_segment` — Healthy / Watchlist / Risky / Toxic segment based on risk index.

## Raw files included

- `data/raw/sales_deals_raw.csv` — raw CRM/deal data with duplicate correction rows and intentionally inconsistent discount fields. Sales reps are anonymized.
- `data/raw/onboarding_product_usage_raw.csv` — raw onboarding/product usage; 8% of accounts absent by design.
- `data/raw/support_tickets_raw.csv` — raw support tickets with intentional missing/out-of-range fields.
- `data/raw/customer_health_monthly_raw.csv` — account-month health, NPS, CSAT and churn signals.

## Additional analysis files

- `analysis/revenue_quality_segment_summary.csv` — segment-level performance and risk summary.
- `analysis/sales_rep_quality_summary.csv` — anonymized sales rep quality metrics.
- `analysis/cohort_quality_comparison.csv` — beta, low-fit, healthy and risky/toxic cohort comparison.
- `analysis/support_load_proxy_monthly.csv` — monthly support-load and customer-health proxy.
- `analysis/support_load_spillover_proxy.json` — high/low support-load comparison.
- `analysis/business_sizing_summary.json` — interpretation of the fictional company profile.
