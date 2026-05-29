# Zoom Communications, Inc. (NASDAQ: ZM) - Final Accounting-Ratio Analysis

**To:** Managing Director / Senior Finance Executive
**From:** Ngoc Cao
**Date:** 2026-05-29
**Subject:** Evaluated final analysis (Stage 5) - corrections of the LLM draft and executive judgment

> **About this document.** This is my evaluated final version of an analysis produced by an LLM executing my Stage 4 specification (`deliverables/2026-05-28-cao-zoom-llm-raw.md`). The LLM's underlying ratio computations were correct; my role here was to correct its narrative errors, flag where it invented unsupported figures, and deliver the executive judgment in my own voice. Detailed spec-quality reflection lives in the companion file `deliverables/2026-05-29-cao-zoom-spec-retrospective.md`.

---

## 1. Company & Data Summary

**Subject:** Zoom Communications, Inc. (NASDAQ: ZM) - the global pure-play video communications platform.
**Fiscal period:** FY2025 (year ended January 31, 2025), with FY2024 (ended January 31, 2024) as the prior-year baseline.
**Reporting standard:** U.S. GAAP. **Currency / units:** USD, in millions (10-K reports in thousands; converted by 1,000).
**Source filings:** Form 10-K for FY2025 (SEC EDGAR, CIK 0001585521).
**Market assumptions used:** share price $86.94 (Nasdaq close, January 31, 2025); 305.741M shares outstanding (Class A + B, per the statement of stockholders' equity); effective tax rate 23.2% (provision $305.3M / pretax $1,315.6M); cost of capital 9.0% (analyst assumption).

**Modeling conventions worth flagging:** (i) `INC_depreciation` is set to 0 in the model because Zoom's D&A is already embedded inside cost of revenue and operating expenses on the 10-K - making the depreciation row a separate line would double-count and understate EBIT by ~$122.6M. With this convention, modeled EBIT ties exactly to Zoom's reported income from operations of $813.3M. (ii) The simplified cash-flow tab omits ~$931.3M of stock-based compensation and other non-cash add-backs; no ratio in this report uses the cash-flow tab. (iii) No peer benchmark dataset was used - the Stage 4 spec did not supply one, and I deliberately reject the LLM's invented benchmarks in the LLM Evaluation section below.

---

## 2. Ratio Results & Interpretation

All ratios were independently recomputed by hand from the Stage 3 statement data (see `analysis/validation/2026-05-28-cao-zoom-stage5-verification.md`). Return ratios use start-of-year denominators per the Stage 4 spec.

### 2.1 Performance
| Ratio | Value | Note |
|---|---|---|
| Market value added (MVA) | $17,646M | Market premium over book equity |
| Market-to-book | 2.97x | Verified |
| Economic Value Added (EVA) | $288M | Positive - operations earn above the 9% cost of capital |

**Interpretation.** Positive EVA confirms operations earn above the 9% estimated cost of capital, and the market reflects that with a 2.97x market-to-book ratio. Value is being created within the business. The open question - the one the recommendations below address - is whether shareholders would be better off if the excess cash were redeployed or returned, rather than held at low yield.

### 2.2 Profitability
| Ratio | Value | Note |
|---|---|---|
| ROE | 12.6% | Verified |
| ROA | 10.2% | Spec specifies start-of-year; "average assets" version would be 9.7% |
| ROC | 12.6% | = ROE because Zoom carries no long-term debt |
| Profit margin | 21.7% | Verified |
| Operating profit margin | 21.7% | = profit margin because interest expense is zero |

**Interpretation.** Evaluated against its own baseline, Zoom's earnings power is strong: a 21.7% net margin reflects high pricing power and tight cost discipline. The diagnostic point is the gap between asset-level profitability (10.2%) and equity returns (12.6%) - the ROE is suppressed by the balance sheet, not by anything weak in the underlying margins.

### 2.3 Efficiency
| Ratio | Value | Note |
|---|---|---|
| Asset turnover | 0.47x | Verified - low due to cash, not operations |
| Receivables turnover | 8.70x | Verified |
| Average collection period | 41.9 days | Verified |
| Inventory turnover | n/a | No inventory (SaaS) |

**Interpretation.** The 0.47x asset turnover implies each dollar of assets generates 47 cents of revenue, which would be alarming for an operating business but is misleading here. Stripping cash and marketable securities from the start-of-year asset base ($9,929.8M - $6,962.5M = $2,967.3M) puts operational asset turnover at roughly **1.57x** ($4,665.4M / $2,967.3M). Core operations are productive; the headline number is dragged down by capital that has not been deployed.

### 2.4 Leverage
| Ratio | Value | Note |
|---|---|---|
| Total debt ratio | 18.7% | Almost entirely deferred revenue - customer-funded, non-interest-bearing |
| Long-term debt-to-equity | 0.00x | Zero interest-bearing debt |
| Leverage ratio | 1.23x | Equity-funded structure |
| Debt burden | 1.00x | = 1 because interest expense is zero |
| Times interest earned | n/a | No interest expense |

**Interpretation.** The 18.7% total debt ratio needs reframing. Zoom carries zero interest-bearing debt - the entire 18.7% is operational liabilities, and most of it is deferred revenue: customers who have prepaid for service. That is not a leverage indicator in the conventional sense; it is a sign of a business funded at zero cost by its own customers. Reading it as "debt" overstates risk and understates the quality of the revenue model.

### 2.5 Liquidity
| Ratio | Value | Note |
|---|---|---|
| Current ratio | 4.56x | Roughly 3x the conventional adequacy threshold |
| Quick ratio | 4.35x | Verified |
| Cash ratio | 4.09x | Zoom could retire all current liabilities ~4 times in cash |
| NWC to assets | 61.6% | Working capital dominates the asset base |

**Interpretation.** Zoom's liquidity is materially in excess of any operating need. Against $1.9B of current liabilities, the company holds $7.8B in cash and marketable securities - a 4.09x cash ratio and 4.56x current ratio. With revenue growth at ~3%, roughly $6B of that balance is uninvested capital earning near-Treasury yields. The risk is not insolvency (there is none); the risk is structural value dilution from holding low-yielding assets at scale.

### 2.6 Cross-category synthesis
The six categories tell one coherent story: a profitable, debt-free, hyper-liquid SaaS business whose equity returns are limited by its own conservative capital structure, not by anything in the underlying operations. Cash generated by customer prepayments is accumulating on the balance sheet rather than being returned or redeployed, and that accumulation is what drives down asset turnover and ROE. The strategic question for Zoom is one of capital allocation, not operating performance.

---

## 3. Du Pont Analysis

Direct ROE = **12.6%**. Decomposition = 1.23 x 0.470 x 0.2165 x 1.00 = **12.5%**.

**Drivers.**
- **Strength:** operating margin (21.7%) - the strongest line in the decomposition; high pricing power and cost discipline.
- **Drag:** asset turnover (0.47x) - driven by the cash balance, not by sales execution.
- **Choice:** leverage (1.23x) and debt burden (1.00x) - Zoom has deliberately not used financial leverage to amplify returns.

**On the LLM's Du Pont interpretation.** The LLM attributed the ~0.1 percentage-point gap between decomposition (12.5%) and direct ROE (12.6%) to "point-in-time vs. average/beginning balance mismatches." That explanation is wrong: all denominators in this decomposition are start-of-year per the spec, so no balance-sheet timing mismatch exists. The real cause is rounding in the intermediate factors (using 0.470 rather than 0.46983, 1.230 rather than the unrounded leverage). The LLM noticed the discrepancy - good - but mis-explained its source.

**Sustainability.** The 12.6% ROE rests on real operating margins, not on financial engineering, which makes it durable. But it is also capped by capital structure: incremental software revenue alone will not move ROE meaningfully. The lever that matters is what Zoom does with its cash.

---

## 4. Strategic Recommendations

### 4.1 Return excess capital through a structured repurchase program
- **Grounded in:** cash ratio 4.09x, current ratio 4.56x, and a $7,791.7M cash and securities balance.
- **Action:** establish a multi-year share repurchase framework sized to reduce the cash balance to a level that preserves roughly 12-18 months of operating cash needs. Avoid committing to a specific dollar figure today; calibrate against actual operating cash flow each quarter.
- **Expected effect and trade-off:** shrinking the equity base will lift ROE by removing the cash drag on asset turnover, without changing anything about the underlying business. The trade-off is reduced absolute liquidity; the remaining balance still comfortably exceeds any reasonable operating contingency.
- **Did the LLM get this right?** Direction yes, specifics no. The LLM proposed "Deploy $3,500 million... ROE will lift toward 18-20%." The $3.5B figure was not derived from any framework in my spec - it was invented for precision. The "18-20% ROE target" rests on the LLM's fabricated peer benchmark (see Section 5). I retain the direction and replace the invented specifics with a defensible operating-cash framework.

### 4.2 Deploy a portion of excess cash into adjacent enterprise infrastructure
- **Grounded in:** flat top-line growth (~3% YoY) and asset turnover of 0.47x.
- **Action:** allocate capital toward expanding into adjacent enterprise communication and learning-infrastructure verticals (LMS, hybrid classroom tools, contact-center extensions) where Zoom already has distribution. Treat this as growth investment, not financial engineering.
- **Expected effect and trade-off:** redirects low-yielding marketable securities into revenue-generating assets, addressing the growth constraint directly and improving operational asset turnover. The risk is execution: integration friction and the possibility that adjacent markets do not scale as projected.
- **Did the LLM get this right?** Direction yes, specifics no. The LLM proposed "$2,000 million for M&A targeting communication infrastructure and AI integration." The $2B figure had no derivation. From a Quickom operator's lens I also question whether traditional M&A is the right vehicle for a no-growth mature SaaS - it may be, but the bar is high. I keep the directional point (deploy, don't hoard) and drop the precise figure.

### 4.3 Institute an explicit capital-hurdle framework
- **Grounded in:** positive EVA of $288M against a 9% cost of capital, and NWC/assets of 61.6%.
- **Action:** establish a treasury policy that imposes an explicit return hurdle on any uninvested cash above the operating buffer: deploy it productively, return it, or document why holding it is the better option.
- **Expected effect and trade-off:** stops the compounding of low-yield reserves and forces an active capital-allocation posture. The trade-off is governance overhead - leadership must defend cash retention each cycle rather than treating accumulation as a default.
- **Did the LLM get this right?** No. The LLM's original third recommendation proposed customer pricing discounts to "expand the leverage ratio multiplier organically" via deferred revenue. That conflates an operational lever (longer contracts) with financial engineering (leverage decomposition), and it sits oddly next to the LLM's own praise of Zoom's conservative structure. I replaced it entirely with a capital-hurdle framework, which is closer to the actual diagnostic (capital allocation, not pricing).

---

## 5. LLM Evaluation & Annotations

This section consolidates what the LLM did well, where it deviated, and which deviations trace to gaps in my Stage 4 spec versus to LLM limitations. Detailed section-by-section verdicts on the spec itself are in the companion retrospective.

**What the LLM executed correctly.**
- Every ratio value the LLM stated matched my Stage 3 workbook to the cent: revenue $4,665.4M, net income $1,010.2M, total assets $10,988.4M, ROE 12.6%, ROA 10.2%, current ratio 4.56x, cash ratio 4.09x, market-to-book 2.97x, EVA $288M. Six of seven ratios in the manual verification table matched exactly.
- The named-range conventions and formulas were used verbatim - the executor did not invent its own variables.
- The simplified cash-flow caveat was respected: the LLM correctly noted SBC omission in its Limitations section.

**Where the LLM deviated or hallucinated.**

| Error | Where it appeared in the raw output | Cause |
|---|---|---|
| Hallucinated "18-25% peer ROE" benchmark | Executive summary, profitability section, and recommendation #1 (inconsistently cited as "18-25%" and "18-20%") | Spec gap. Part B.8 asked the executor to "benchmark against mature SaaS peers" but supplied no peer data. The LLM filled the empty slot by fabricating a figure. |
| Invented "$3,500M" buyback and "$2,000M" M&A magnitudes | Recommendations #1 and #2 | Spec gap. Part B.10 required recommendations to be "grounded in a specific computed ratio" but placed no constraint on the precision of dollar magnitudes. |
| Mis-explained Du Pont reconciliation gap | Du Pont section | Both. Spec did not require the executor to attribute small reconciliation differences to a specific mechanical cause, AND the LLM compounded that by attributing a rounding artifact to a structurally impossible cause (timing mismatch where none exists). |
| Questionable deferred-revenue-as-leverage logic in original rec #3 | Strategic recommendations | LLM limitation. The spec did not invite this framing; the LLM reached for a Du Pont link that does not hold. I rejected the recommendation. |

**Spec-caused vs LLM-caused, summary.** Two of the four major errors trace cleanly to spec gaps (the missing peer dataset and the unconstrained magnitude precision); one is a mixed cause; one is genuine LLM judgment error. The structural-attribution work matters because the fix for each class is different: spec gaps are sentence-level edits, LLM judgment errors require human review of every recommendation. See `deliverables/2026-05-29-cao-zoom-spec-retrospective.md` for the spec-side fixes.

---

## 6. Executive Justification

**Thesis.** Zoom is a high-quality operating business trapped inside a low-yield balance sheet. The recommendation is to fix the balance sheet, not the business: return a meaningful portion of the $7.8B cash and marketable securities balance through structured repurchases, deploy a portion into adjacent growth, and institute a capital-hurdle policy so this pattern does not silently re-form. The operating thesis (21.7% margins, positive EVA, customer-funded liabilities, zero debt) is strong enough to justify a market premium - shareholders are getting that. What they are not getting is the additional several percentage points of ROE that disciplined capital allocation would deliver, and which the 4.09x cash ratio makes plainly available.

**What this means for me as the reader.** I chose Zoom precisely because it is the closest public benchmark for the real-time communication layer at the core of Quickom, the platform I am building toward unicorn scale. The diagnostic that matters most for an operator in this space is not the headline margin - it is the discipline about what to do with the cash those margins produce. Zoom's profile shows that even a debt-free, profitable, market-leading communications business can leave significant shareholder value on the table by defaulting to balance-sheet accumulation. For Quickom, the lesson is to install capital-allocation discipline early - explicit hurdle rates, a willingness to return capital, a clear posture on whether customer prepayments fund growth or sit idle - before excess liquidity becomes a structural feature. That is materially cheaper to do at our stage than to retrofit at Zoom's.

---

## 7. Limitations

- **Backward-looking.** Ratios reflect performance through the fiscal year ended January 31, 2025, and do not capture intra-quarter changes or events after the reporting date.
- **Simplified cash-flow modeling.** Per the Stage 4 spec, the model omits large non-cash add-backs - chiefly stock-based compensation of ~$931.3M for FY2025. Zoom's operating cash conversion is materially stronger than the simplified model implies; no ratio in this report depends on the cash-flow tab.
- **No non-financial SaaS metrics.** Standard accounting ratios cannot capture net revenue retention, customer acquisition cost payback, or engagement metrics that are central to evaluating a SaaS franchise.
- **No peer benchmarks.** The Stage 4 spec deliberately did not supply peer data, so this analysis is framed against Zoom's own baseline rather than against a sector cohort.

---

## 8. Sources

- Underlying data: Zoom Communications, Inc. Form 10-K, fiscal year ended January 31, 2025 (SEC EDGAR, CIK 0001585521).
- LLM draft analyzed: `deliverables/2026-05-28-cao-zoom-llm-raw.md`.
- Spec executed: `docs/specs/2026-05-28-cao-zoom-spec.md`.
- Manual ratio verification: `analysis/validation/2026-05-28-cao-zoom-stage5-verification.md`.
- Spec retrospective (companion document): `deliverables/2026-05-29-cao-zoom-spec-retrospective.md`.
- All ratio values verified by hand against the Stage 3 model (`models/builds/2026-05-22-cao-zoom-financials.xlsx`).
