| template           | prompt-log                                                                                                                    |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| purpose            | Running log of meaningful AI prompts and outputs used in a project — supports reproducibility and AI-use disclosure           |
| audience           | student                                                                                                                       |
| fields_required    | | date | goal | prompt | tool | output_location | notes | | ---- | ---- | ------ | ---- | ---------------- | ----- |         |
| naming_convention  | prompt-log.md (one per project, lives in deliverables/)                                                                       |
| courses            | | BUS-313 | BUS-314 | BUS-620 | BUS-629 | FIN-321 | BUS-122B | | ------- | ------- | ------- | ------- | ------- | -------- | |


# Prompt Log

| Date | Goal | Exact Prompt | Tool (LLM/Sheet/Code) | Output Link/Location | Notes |
| ---- | ---- | ------------ | --------------------- | -------------------- | ----- |
| 2026-05-22 | Draft Stage 2 company selection memo for Zoom (ZM) filling all six required sections, 400-600 words, MD audience | "I'm drafting a Stage 2 company selection memo. Read the template at [repo memo-template URL], then draft a memo for Zoom Communications (ZM, NASDAQ) filling every section. Use the YAML frontmatter exactly as shown. Length 400-600 words. Audience: a managing director - concise, evidence-tight. Before drafting, ask me 3-5 clarifying questions about industry, why I chose it, my hypotheses, and data sources." | Claude (web) | docs/decisions/2026-05-22-cao-zoom-selection.md | I chose the company myself (Zoom, as the public benchmark for my employer Quickom). AI asked clarifying questions; I supplied career goal and rationale and asked it to propose hypotheses. |
| 2026-05-22 | Ground all figures in primary sources and lock sources for the project | "Verify the financial figures against Zoom's SEC 10-K filings rather than guessing; cite exactly what source you take, then stay consistent for the rest of the project." | Claude (web) + SEC EDGAR | docs/decisions/2026-05-22-cao-zoom-selection.md (References section) | Locked sources: Zoom 10-K FY2025 & FY2024 (SEC EDGAR, CIK 0001585521) and 8-K earnings releases. Flagged balance-sheet figures for my own re-check against the 10-K at Stage 3. |
| 2026-05-22 | Polish memo against the Stage 2 rubric criteria | "Review my memo against the Stage 2 rubric and tighten it: ensure all hypotheses are in 'I expect X because Y' form, use straight ASCII quotes, reconcile the audience/To line, and make the Executive Summary lead with the recommendation." | Claude (web) | docs/decisions/2026-05-22-cao-zoom-selection.md | Applied fixes: all hypotheses in "I expect X because Y" form, ASCII-only quotes, audience/To reconciled, Executive Summary closes on the recommendation. |
