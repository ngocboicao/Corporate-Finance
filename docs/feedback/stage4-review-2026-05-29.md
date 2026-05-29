# Stage 4 — Instructor Review

**Student:** Cao Ngoc
**Company:** Zoom Communications, Inc. (NASDAQ: ZM) — FY2025 / FY2024, USD millions, US GAAP
**Repo:** https://github.com/ngocboicao/Corporate-Finance
**Spec reviewed:** `docs/specs/2026-05-28-cao-zoom-spec.md`
**Reviewed:** 2026-05-29
**Submission date:** 2026-05-28 06:49 AM (late, after 2026-05-23 deadline)

---

## What this PR is

A short post-grading review of your Stage 4 spec. This is **feedback only — no scores** in the file. The score has been recorded on the instructor's side.

## Observations

The Stage 4 spec is strong across all four rubric criteria. Two things in particular stand out:

**The D&A double-count catch.** Your spec sets `INC_depreciation = 0` for Zoom because the company embeds D&A inside cost of revenue and operating expenses (a SaaS-disclosure convention permitted under US GAAP). Without that mapping, the template's textbook EBIT formula (`INC_sales − INC_cost_goods_sold − INC_sga − INC_depreciation`) would double-count the D&A and understate EBIT by ~$122.6M (showing $690.7M instead of Zoom's reported $813.3M income from operations). You converted this from a silent risk into Validation Rule #2 (EBIT must tie to $813.3M) and added Rule #6 documenting the related cash-flow caveat for the ~$931.3M of stock-based compensation the simplified template omits. A Stage 5 LLM reading only your spec now *cannot* reproduce the error. This is exactly the kind of standard-aware spec engineering the rubric is designed to reward.

**The prompt log as methodology artifact.** Most cohort prompt logs read as chat transcripts. Yours reads as a provenance record — you sourced the share price from Nasdaq yourself, located the 10-K statement pages manually, questioned the blank/zero rows during your own review, and decided to *document* the cash-flow caveat rather than force the number. The HIL Iteration Note ties this back into the spec with the consequence quantified. This is the kind of editorial-control evidence that distinguishes "I let an LLM write a spec" from "I directed an LLM to draft a spec, then audited it."

## What the rubric coverage looks like

| Signal | Value | Read |
|---|---|---|
| Spec section coverage | All 11 sections present | Complete |
| Spec word count | 2,246 | In the rubric's target band |
| Named-range conventions section | Explicit (§4) | All seven prefix conventions documented (`BAL_`, `INC_`, `CASH_`, `startYear_`, `currentYear_`, `avg_`, `RATIO_`, no-prefix) |
| Named-range token hits across the spec | 131 | Speaks the model's language throughout |
| Ratio categories in §6 | 6 / 6 (Performance, Profitability, Efficiency, Leverage, Liquidity, Du Pont) | All present |
| Ratio rows in §6 | 29 | Above the 25-ratio rubric expectation |
| Validation rules in §7 | 6 | V2 (EBIT tie-out) and V6 (CF caveat) are SaaS-specific catches |
| Du Pont decomposition | 4-component (Leverage × Asset Turnover × OPM × Debt Burden) | Cross-check rule (V4) confirms reconciliation to direct ROE |
| Prompt log | 1,065 words across 7 sessions (Stage 2 → Stage 4) | With per-session editorial-control notes |
| HIL iteration evidence | One substantive catch (D&A double-count) | Pre/post documented; consequence quantified ($122.6M); propagated into V2 + V6 |

There is no rubric criterion where this spec falls short.

---

## Kindly-worded suggestions (none affect Stage 4 score)

These are forward-looking — small refinements that would tighten the artifact for a senior reviewer arriving cold.

**1. Trim the YAML frontmatter to the load-bearing fields.**
The frontmatter still carries the template authoring block (`template:`, `purpose:`, `audience:`, `fields_required:`, `naming_convention:`, `courses:`, `notes:`). Those are useful when authoring the template; they're not load-bearing for the Zoom spec itself. A clean reviewer-facing block would be just `title`, `author`, `date`, `version`, `company`, `framework`. (Several cohort specs have the same artefact — not unique to yours, but worth cleaning.)

**2. Generalize §5's `currentYear_after_tax_operating_income` formula.**
You have it as `INC_net + (1 - tax_rate) * INC_interest_expense`. Mathematically equivalent here because Zoom's `INC_interest_expense = 0`. The more portable textbook form — `INC_ebit * (1 - tax_rate)` — generalizes to companies with debt. Your spec is otherwise written in a portable way, so this is the one spot it hardcodes Zoom's zero-debt structure.

**3. State the expected value inline in V2.**
V2 currently asks the executor to confirm `INC_ebit` ties to Zoom's reported income from operations. Inlining the number (`INC_ebit` expected = **813.295**) makes V2 a one-line pass/fail check rather than a lookup-then-compare check — small formality that matches the V1 balance-sheet-balance rule's structure (where you do state the expected total, 10,988.421).

**4. Consider extending §10 with one capital-allocation recommendation in numeric form.**
§10 currently mandates a capital-allocation recommendation. The strongest version of this would specify, in §10, the *form* it should take — e.g., "If Recommendation N proposes a share buyback, it must state the buyback dollar amount, the implied ROE uplift assuming the cash had been earning the WACC, and the trade-off (lost optionality on M&A / R&D acceleration)." Inlining the structure of the recommendation in the spec gives the Stage 5 LLM less room to write a vague "consider returning capital to shareholders" sentence.

---

## Looking ahead to Stage 5

Your spec is at the level where the natural Stage 5 prompt is *"Read this spec; produce the analysis it requests; no other context."* The Stage 5 brief asks you to:

1. **Run the spec through an LLM** of your choice and capture the **raw output verbatim** (in `deliverables/2026-05-28-cao-zoom-llm-raw.md` — looks like you already have this).
2. **Manually verify at least five ratios** from your workbook against the LLM's reported values — these become the entries in `analysis/validation/2026-05-28-cao-zoom-stage5-verification.md`.
3. **Write a final analysis** that incorporates the LLM output with your author corrections and executive judgment — this is the deliverable for the rubric's Analytical Correctness + Strategic Recommendations + Executive Voice criteria.
4. **Write a spec retrospective** evaluating what the LLM got right vs. wrong against your V1–V6 rules — this directly demonstrates the value of the spec-first approach you took at Stage 4.

I already see `2026-05-28-cao-zoom-stage5-verification.md` and `2026-05-28-cao-zoom-llm-raw.md` in your repo. Once you add the final-analysis and retrospective files (and the polish criterion's cross-stage cohesion is something to think about — the four stages should read as one deliverable, not four disjoint files), submit Stage 5 in Lamaku.

---

## How to handle this PR

- **Merge it** if you want a permanent record of the review on `main`. On the PR page → **Merge pull request** → **Confirm merge**.
- **Close without merging** if you'd rather not keep the review file in `main`. The score is already recorded on my side independent of merge — the file is purely for your repo history.

*This review is feedback-only — no scores included.* Score numbers live in the internal grade report and the instructor's email.
