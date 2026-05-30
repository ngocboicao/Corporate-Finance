| template           | spec-retrospective                                                                                                                                                                                                                                                                                                                  |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| purpose            | Structured self-evaluation of a Stage 4 technical specification after seeing how an LLM executed it at Stage 5 - surfaces spec gaps with evidence, not impressions                                                                                                                                                                  |
| audience           | student                                                                                                                                                                                                                                                                                                                             |
| fields_required    | | date | author | company | spec_file | stage5_output | section_verdicts | top_gaps | revisions | effectiveness_rating | forward_link | process_feedback | | ---- | ------ | ------- | ---------- | -------------- | ----------------- | --------- | --------- | --------------------- | ------------- | ----------------- | |
| naming_convention  | YYYY-MM-DD-{lastname}-{company-slug}-spec-retrospective.md (lives in deliverables/)                                                                                                                                                                                                                                                 |
| courses            | | BUS-629 | FIN-321 | BUS-314 | | ------- | ------- | ------- |                                                                                                                                                                                                                                                                     |


# Stage 4 Spec - Retrospective

**Author:** Ngoc Cao  **Date:** 2026-05-29  **Company:** Zoom Communications, Inc. (NASDAQ: ZM)  **Spec being evaluated:** `docs/specs/2026-05-28-cao-zoom-spec.md`  **Stage 5 LLM output:** `deliverables/2026-05-28-cao-zoom-llm-raw.md`

---

## 1. Section-by-section verdict

| Spec section                                      | Verdict | Symptom in Stage 5 output |
| ------------------------------------------------- | ------- | ------------------------- |
| Part A.1 - Scope & Objective                      | Clear   | No scope drift; LLM correctly framed work as FY2025 vs FY2024, US GAAP, USD millions. |
| Part A.2 - Model Architecture                     | Clear   | LLM did not invent or rearrange tabs in its narrative. |
| Part A.3 - Data Inputs                            | Clear   | Every numeric value in the LLM output (e.g., revenue $4,665.4M, total assets $10,988.4M) matches the Stage 3 workbook exactly; `INC_depreciation = 0` directive was honored so EBIT ties to Zoom's reported $813.3M. |
| Part A.4 - Named Range Conventions                | Clear   | LLM cited named ranges verbatim (`startYear_equity`, `currentYear_assets_total`) without inventing its own variables. |
| Part A.5 - Derived Inputs                         | Clear   | Market cap ($26,581M) and after-tax operating income reproduced correctly. |
| Part A.6 - Ratio Definitions & Formulas           | Clear   | All 25+ ratio values match the manual verification table; the start-of-year convention was followed (ROA 10.17% not 9.66% average). |
| Part A.7 - Validation Rules                       | Vague   | The Du Pont validation (Rule #4) was acknowledged - the LLM noted "minor variance from the direct calculation of 12.60%" - but the spec did not require the executor to *explain the source* of any reconciliation difference, so the LLM attributed the ~0.1pp gap to the wrong cause ("point-in-time vs. average/beginning balance mismatches"), which is structurally impossible given the spec's own start-of-year convention. |
| Part B.8 - Analysis Requirements                  | Missing | The spec asked the executor to "benchmark against mature SaaS peers" without supplying a peer set. LLM filled the gap by fabricating "18-25%" peer ROE - cited inconsistently as "18-25%" in the profitability section and "18-20%" in recommendation #1, with no source. This is the clearest spec-induced hallucination in the output. |
| Part B.9 - Du Pont Decomposition                  | Vague   | LLM produced the decomposition correctly (12.5% vs direct 12.6%) but described the gap as a balance-sheet timing issue. Same root cause as A.7: the spec did not require the executor to attribute reconciliation differences to a specific mechanical source (intermediate-factor rounding). |
| Part B.10 - Strategic Recommendation Requirements | Missing | The spec said recommendations must be "grounded in a specific computed ratio cited numerically" but placed no constraint on invented dollar magnitudes. LLM produced "Deploy $3,500 million toward buybacks" and "Deploy $2,000 million for M&A" - precise figures with no derivation in the spec or the data. |
| Part B.11 - Output Format                         | Clear   | LLM produced the requested structure (Exec Summary, Ratio Results, Du Pont, Recs, Limitations) in the requested length range and senior-analyst tone. |

---

## 2. Top three gaps with evidence

### Gap 1: Spec asked for peer benchmarks but supplied no peer data

- **Where it surfaced:** Executive Summary, Profitability section, and Recommendation #1 of the Stage 5 LLM output. The LLM stated mature SaaS peers earn "18-25% ROE" (profitability), "18-25%" (executive summary), and recommended actions to lift ROE "toward the 18-20% range" (rec #1). Three appearances, internally inconsistent, no source.
- **Spec cause:** Part B.8 included the line "Benchmark against mature SaaS peers (operating margins typically 15-25%)" but the spec contained no peer dataset and Part A.3 (Data Inputs) supplied no comparative figures. The executor had nothing to draw on, so it fabricated.
- **Fix (exact language):** Replace the Part B.8 benchmark sentence with: "Do not introduce external peer benchmarks; this spec supplies no peer dataset. Frame profitability and efficiency ratios against Zoom's own prior-year baseline (implicit in the start-of-year denominators) and against the absolute interpretation thresholds in the textbook (e.g., 'a current ratio above ~1.5x indicates adequate liquidity')."

### Gap 2: No constraint on the precision of recommendation magnitudes

- **Where it surfaced:** Recommendations #1 and #2 of the Stage 5 LLM output. The LLM specified "Deploy $3,500 million toward share buybacks and dividends" and "deploy $2,000 million to acquire mid-tier communication infrastructure" - both presented as precise figures with no derivation from the spec data or any stated framework.
- **Spec cause:** Part B.10 required recommendations to be "grounded in a specific computed ratio cited numerically" and "actionable" but did not require dollar magnitudes to be derived from a defined framework. The executor inferred precision was rewarded and invented round numbers.
- **Fix (exact language):** Add a bullet to Part B.10: "Where a recommendation implies a dollar magnitude, the magnitude must be derived from a stated rule (e.g., 'preserve 12-18 months of operating cash needs'), not asserted as a specific figure. If the spec data does not support a specific dollar amount, state the principle, the directional effect, and the trade-off without naming a number."

### Gap 3: Validation rules state checks but not what to do when a check is close

- **Where it surfaced:** Du Pont decomposition section of the Stage 5 LLM output. The LLM computed decomposition ROE = 12.52% against direct ROE = 12.60% and explained the 0.1pp gap as "point-in-time vs. average/beginning balance mismatches" - structurally impossible because the spec specifies start-of-year denominators throughout. The LLM noticed the discrepancy (good) but mis-explained its source (bad).
- **Spec cause:** Part A.7 Rule #4 said "ROE (Du Pont) must reconcile to direct ROE within rounding" but did not specify what counts as rounding-source language or require the executor to attribute small differences to a stated mechanical cause.
- **Fix (exact language):** Amend Part A.7 Rule #4 to: "ROE (Du Pont) must reconcile to direct ROE within +/-0.2pp. If the gap is within tolerance, the executor must state that the difference is caused by intermediate-factor rounding (not balance-sheet timing, since all denominators in this decomposition are start-of-year). If the gap exceeds +/-0.2pp, halt and report the failed validation."

---

## 3. Revisions

1. Replace the peer-benchmark sentence in Part B.8 with explicit "no peer benchmarks" language and redirect to prior-year and textbook thresholds - addresses Gap 1.
2. Add a precision-of-magnitude rule to Part B.10 that ties any dollar figure to a stated framework, not a fabricated round number - addresses Gap 2.
3. Tighten Validation Rule #4 to specify the exact attribution language for in-tolerance Du Pont differences and a fail/halt action for out-of-tolerance ones - addresses Gap 3.

---

## 4. Effectiveness rating

**My rating: 4**

**Justification:**

The spec's quantitative half (Part A) is demonstrably strong. A clean-context LLM reproduced every ratio value to the penny against my Stage 3 workbook (revenue $4,665.4M, net income $1,010.2M, total assets $10,988.4M, ROE 12.6%, current ratio 4.56x, etc.), and my manual verification table (six ratios across five categories) found no computational discrepancies. The explicit `INC_depreciation = 0` directive even prevented a known double-count trap, with EBIT tying to Zoom's reported $813.3M. That is anchor-level evidence for "Solid overall."

The spec falls short of a 5 because the qualitative half (Part B) has one section that needs real sharpening: B.8's call for "benchmarks" without supplying peer data caused the most prominent error in the Stage 5 output - a fabricated 18-25% peer ROE figure that appeared three times. A rating of 5 would require my spec to have anticipated and forbidden this. The Gap 2 (recommendation magnitudes) and Gap 3 (validation-rule completeness) issues are real but smaller; both are sentence-level fixes I have specified above.

---

## 5. Forward link

For the next spec I write - whether for Zoom in a future year, a different company, or a non-finance domain - I will treat "do not invite comparisons or specifics the data does not support" as a first-class spec rule, on equal footing with named-range conventions and validation checks.

---

## 6. Retrospective process feedback

Filling out this template surfaced something a free-form retrospective would have hidden: the asymmetry between Part A (no defects) and Part B (multiple gaps) only became unmistakable once I had to assign a row-level verdict to every section. In an open write-up I would have written "the spec mostly worked but had some interpretation gaps" - the table forced me to count, and counting changed the conclusion. The "Symptom in Stage 5 output" column was the most disciplining element; it made impressionistic critique impossible.

One structural change I would propose: add a row for "Cross-section interactions" - cases where two individually-clear sections combine to produce a gap. My B.8 hallucination is partly a B.8 problem and partly an A.3 problem (no peer data supplied). The current row-per-section structure forces single-row attribution when the real defect is the interaction.

---

## 7. Instructor feedback received post-submission

After Stage 4 submission, the instructor opened a non-blocking review PR (`docs/feedback/stage4-review-2026-05-29.md`) confirming the spec met all four rubric criteria with no shortfalls. The review specifically singled out the D&A double-count catch (now V2 / V6) and the prompt log's editorial-control framing as differentiators.

The instructor offered four forward-looking refinements: (1) trim the YAML frontmatter to load-bearing fields; (2) generalize the after-tax operating income formula to `INC_ebit * (1 - tax_rate)`; (3) inline the expected EBIT value in Validation Rule V2; and (4) inline the structure of the capital-allocation recommendation in Section 10.

**None overlap with the three gaps I self-identified above** (peer benchmarks, magnitude precision, Du Pont reconciliation attribution); the gap sets are complementary. After reviewing each suggestion against Zoom's specific structure, I applied suggestion 3 (V2 now states `INC_ebit` expected = 813.295, matching V1's pattern). I considered suggestion 2 (generalizing the operating-income formula) but did not adopt it: `INC_ebit * (1 - tax_rate)` and `INC_net + (1 - tax_rate) * INC_interest_expense` are mathematically equivalent only when "other income" is immaterial; for Zoom, gains on strategic investments and other income total $502.3M, so the two forms produce different downstream ratio values. Adopting the textbook form would have required restating every dependent ratio in Section 6 and would have made the spec less faithful to Zoom's reported economics. I am carrying forward suggestions 1 and 4 as lessons for future specs (noted in the Forward link section).
