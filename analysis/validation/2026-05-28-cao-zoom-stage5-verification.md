# Stage 5 — Manual Ratio Verification

**Author:** Ngoc Cao
**Date:** 2026-05-28
**Company:** Zoom Communications, Inc. (NASDAQ: ZM)
**Purpose:** Recompute selected ratios by hand from the Stage 3 financial-statement data and compare to the LLM's stated values in the raw output.

---

## Sources compared

- **Manual value:** recomputed by hand from the Stage 3 statement inputs in `models/builds/2026-05-22-cao-zoom-financials.xlsx` (Income Statement and Balance Sheet tabs). Not transcribed from the Ratios tab — recomputed from the raw line items.
- **LLM's value:** as stated in `deliverables/2026-05-28-cao-zoom-llm-raw.md`, produced by executing the Stage 4 spec with no other context.

All figures in USD millions unless noted. Return ratios use start-of-year (FY2024) denominators per the Stage 4 spec.

## Statement inputs used (from Stage 3 workbook)

| Input | Value | Source tab |
|-------|-------|-----------|
| Net income (`INC_net`) | 1,010.238 | Income Statement |
| Revenue (`INC_sales`) | 4,665.433 | Income Statement |
| After-tax operating income | 1,010.238 | = net income (interest expense = 0) |
| Total assets FY2025 | 10,988.421 | Balance Sheet |
| Total assets FY2024 (start-of-year) | 9,929.793 | Balance Sheet |
| Total equity FY2025 | 8,935.084 | Balance Sheet |
| Total equity FY2024 (start-of-year) | 8,019.406 | Balance Sheet |
| Current assets FY2025 | 8,675.974 | Balance Sheet |
| Current liabilities FY2025 | 1,903.294 | Balance Sheet |
| Total liabilities FY2025 | 2,053.337 | Balance Sheet |
| Receivables FY2024 (start-of-year) | 536.078 | Balance Sheet |

---

## Verification table

| Ratio | Formula (named-range notation) | Manual value (show arithmetic) | LLM's value | Match? | One-line note |
|---|---|---|---|---|---|
| ROE | `INC_net / startYear_equity` | 1,010.238 / 8,019.406 = 0.1260 = **12.6%** | 12.60% | ✓ | LLM correctly used start-of-year (FY2024) equity per the spec, not FY2025 equity (which would give 11.3%). |
| ROA | `currentYear_after_tax_operating_income / startYear_total_assets` | 1,010.238 / 9,929.793 = 0.1017 = **10.2%** | 10.17% | ✓ | LLM also reported an "average assets" ROA of 9.66%; the spec specifies start-of-year, so 10.17% governs. Good catch that it offered both. |
| Asset turnover | `INC_sales / startYear_total_assets` | 4,665.433 / 9,929.793 = **0.47x** | 0.47x | ✓ | Ties exactly; both use start-of-year assets. |
| Current ratio | `currentYear_assets_current / currentYear_liabilities_current` | 8,675.974 / 1,903.294 = **4.56x** | 4.56x | ✓ | — |
| Total debt ratio | `currentYear_liabilities_total / currentYear_assets_total` | 2,053.337 / 10,988.421 = 0.1869 = **18.7%** | 18.68% | ✓ | Liabilities are predominantly deferred revenue, not interest-bearing debt. |
| Average collection period | `startYear_receivables / currentYear_daily_sales_average` | 536.078 / (4,665.433 / 365) = 536.078 / 12.782 = **41.9 days** | 41.94 days | ✓ | LLM used start-of-year receivables and a 365-day year, matching the spec convention. |
| Du Pont ROE | `RATIO_leverage * RATIO_asset_turnover * RATIO_operating_profit_margin * RATIO_debt_burden` | 1.23 x 0.470 x 0.2165 x 1.00 = **12.5%** | 12.52% | ✗ (≈) | Decomposition (12.5%) differs from direct ROE (12.6%). Cause is rounding in the intermediate factors — NOT the "point-in-time vs. average balance" reason the LLM gave. The LLM noticed the gap but mis-explained it. |

---

## Summary

Six of seven recomputed ratios tie to the LLM's stated values, confirming the LLM executed the Stage 4 spec's data inputs and formulas faithfully. The one flagged item (Du Pont ROE) is a ~0.1 percentage-point reconciliation gap that the LLM acknowledged but explained incorrectly; the true cause is intermediate-factor rounding. The ROA row is also informative: the LLM correctly distinguished start-of-year (10.17%) from average (9.66%) denominators, which the spec resolved by specifying start-of-year. No hallucinated or unit-error ratio values were found in the computed figures (the LLM's fabrications appear in its narrative benchmarks and recommendation dollar amounts, addressed in the final-analysis evaluation, not in the ratio arithmetic).
