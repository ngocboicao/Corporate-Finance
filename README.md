# Ngoc Cao

I'm Ngoc Cao, **Chief Design Officer at QUICKOM** — an event infrastructure-as-a-service platform integrating registration, ticketing, livestreaming, AI-assisted engagement, and analytics into one system, supporting events of up to **100,000 concurrent online attendees** and hundreds of thousands of users across thousands of events in Vietnam and surrounding markets. I'm currently leading the design of **QUICKOM for Education**, a new vertical positioning the platform as an operating system for the digital university — hybrid classrooms, LMS integration, AI learning assistance, and institutional dashboards — already adopted by leading Vietnamese universities across business, technology, and international-education programs.

**Focus areas:** design leadership and brand strategy, UX/UI for enterprise SaaS, and the design-to-development handoff for products serving enterprise, government, and academic clients.

**Background:** BA in Graphic Design, University of Architecture Ho Chi Minh City (2019). Six-plus years leading design at QUICKOM and Beowulf Blockchain, building multidisciplinary teams and aligning creative direction with executive growth strategy.

**Goals:** complete my MBA at VEMBA (University of Hawaiʻi) and pursue a DBA, with the long-term aim of leading as a CEO or teaching the next generation of creative leaders at the intersection of design, strategy, and education technology.

---

📄 [View full resume](./RESUME.md) · 📖 [Read long-form bio](./BIO.md)

📫 ngocboicao@gmail.com
---

## About this repository

This is my BUS-629 International Corporate Finance portfolio repo — the home of a single semester-long project analyzing **Zoom Communications, Inc. (NASDAQ: ZM)** using FY2024 and FY2025 audited financial statements. The repo is structured so a manager, recruiter, or future collaborator can land here cold and follow the work from raw filings to executive recommendation.

## What you'll find here

- **`docs/`** — written reasoning: the Stage 2 selection memo, the Stage 4 technical specification, the instructor's review PR, and project plans.
- **`models/`** — the Excel ratio model. `templates/` holds the unmodified Stage 1 starting point; `builds/` holds the populated Stage 3 build.
- **`data/`** — placeholder for source financial data (this project sourced directly from SEC EDGAR; the 10-K reference is in the specs and verification files).
- **`analysis/validation/`** — Stage 5 manual ratio verification table.
- **`deliverables/`** — the polished outputs: Stage 5 raw LLM output, evaluated final analysis, spec retrospective, and the running `prompt-log.md`.

## Project status

| Stage | Status | Key artifact |
|---|---|---|
| 0 — Repo setup, resume, bio | ✅ Complete | `README.md`, `RESUME.md`, `BIO.md` |
| 1 — Template architecture | ✅ Complete | `models/templates/performance-ratios-template.xlsx` |
| 2 — Company selection memo | ✅ Complete | `docs/decisions/2026-05-22-cao-zoom-selection.md` |
| 3 — Model population | ✅ Complete | `models/builds/2026-05-22-cao-zoom-financials.xlsx` |
| 4 — Technical specification | ✅ Complete | `docs/specs/2026-05-28-cao-zoom-spec.md` |
| 5 — LLM analysis & evaluation | ✅ Complete | `deliverables/2026-05-29-cao-zoom-final-analysis.md` |

## Source data

All financial figures trace to **Zoom Communications, Inc. Form 10-K for the fiscal year ended January 31, 2025** (SEC EDGAR, CIK 0001585521). Reporting standard: U.S. GAAP. All workbook values are in USD millions; the 10-K reports in thousands (converted by dividing by 1,000). Market assumptions (fiscal year-end share price, shares outstanding) are sourced from Nasdaq historical data on January 31, 2025.