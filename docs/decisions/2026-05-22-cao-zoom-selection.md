---
template: memo
purpose: "Executive memo for stage 1 / 2 deliverables - problem framing, analysis summary, and recommendation"
audience: Managing Director
fields_required: [title, to, from, date, re, executive_summary, background, method, findings, implications, limitations, references]
naming_convention: "YYYY-MM-DD-{slug}.md"
courses: [BUS-313, BUS-314, BUS-620, BUS-629, FIN-321, BUS-122B]
---

# Company Selection Memo

## BUS 629: International Corporate Finance -- Stage 2

**To:** Professor Adam Stauffer (acting as MD)
**From:** Ngoc Cao
**Date:** 2026-05-22
**Re:** Company Selection - Zoom Communications, Inc. (NASDAQ: ZM)

---

## Executive Summary

I propose **Zoom Communications, Inc. (NASDAQ: ZM)** for the BUS 629 ratio analysis project. Zoom is the largest public pure-play in real-time communication - the exact layer at the core of my company, Quickom, where I am working to build a global communication infrastructure and scale toward unicorn status. Studying Zoom is therefore direct competitive intelligence, not an academic exercise. Zoom also offers an unusually clean analytical case: a single-segment SaaS model showing flat revenue growth (~3%) alongside sharply expanding margins, a ~$7.8B cash position against ~$4.7B revenue, and an active buyback program. With this analytical structure and complete FY2024-FY2025 data confirmed available, I recommend Zoom as the project subject and propose moving directly to the Stage 3 build.

---

## 1. Company Overview

| Field | Detail |
| --- | --- |
| **Company** | Zoom Communications, Inc. |
| **Ticker / Exchange** | ZM / NASDAQ Global Select Market |
| **Industry** | Communications Software / SaaS (Technology) |
| **Business** | AI-first unified communications platform: video meetings, phone, team chat, contact center, and events, sold by subscription to enterprises and individuals worldwide |
| **Market Capitalization** | ~USD 20-25 billion (FY2025) |
| **Fiscal Year End** | January 31 |
| **Reporting Currency** | U.S. Dollar (USD) |
| **Reporting Standards** | U.S. GAAP |

---

## 2. Selection Rationale

Zoom is the closest public pure-play benchmark for the real-time communication layer at the core of my company, Quickom, where I am working to build a global communication infrastructure and scale toward unicorn status. Analyzing how a mature, public version of that core business converts revenue into cash and profit is direct competitive intelligence, not an academic exercise. Zoom is also a compelling ratio-analysis subject in its own right: it sits at a strategic inflection where revenue growth has stalled near 3% while profitability has expanded sharply, it holds an unusually large cash balance relative to its revenue base, and it is pivoting hard toward an AI-first model. That tension between a flat top line and a strengthening bottom line should surface clearly in the profitability, liquidity, and return ratios.

---

## 3. Data Availability & Sources

| Source | Contents |
| --- | --- |
| **SEC EDGAR** (edgar.sec.gov) | 10-K filings for FY2025 and FY2024 - Income Statement, Balance Sheet, Cash Flow Statement, and Notes (CIK 0001585521) |
| **Zoom Investor Relations** (investors.zoom.us) | Quarterly earnings releases (Form 8-K, Exhibit 99.1), supplemental data, historical filings |
| **Yahoo Finance** | Fiscal year-end (Jan 31) closing share price and diluted shares for market-based ratios |

All statements are in English under U.S. GAAP, reported in USD millions; two full fiscal years (FY2025 + FY2024) are confirmed available. Fiscal year ends January 31, so no currency conversion is required.

---

## 4. Preliminary Observations

1. **I expect Zoom's operating and net margins to improve materially from FY2024 to FY2025, because management prioritized efficiency and reduced stock-based compensation even as revenue growth stalled near 3%.** GAAP income from operations rose from $525.3M (FY2024) to $813.3M (FY2025) on near-flat revenue ($4,527.2M to $4,665.4M), lifting GAAP operating margin from ~11.6% to 17.4%.

2. **I expect Zoom's current ratio to exceed 4x in FY2025, because the company holds roughly $7.8B in cash and marketable securities against a ~$4.7B revenue base, signaling possible over-capitalization.** This raises a capital-allocation question central to any growth-stage communication business, including my own.

3. **I expect Zoom's return on equity to remain in the low double digits in FY2025 despite strong margins, because the large cash balance and equity accumulated through buybacks inflate the equity denominator.** FY2025 net income of ~$1.01B against total equity near $8.96B implies strong profits diluted by a heavy balance sheet - directly testable in Stage 3.

---

## 5. Ratio Categories Preview

| Category | Relevance |
| --- | --- |
| **Profitability** | Most analytically interesting - tests whether efficiency gains lifted margins despite flat revenue |
| **Liquidity** | High relevance - the oversized cash balance produces unusually strong current and quick ratios |
| **Leverage / Solvency** | Moderate - Zoom carries minimal debt, so the story is about an equity-heavy, cash-rich structure |
| **Efficiency / Activity** | Asset turnover is depressed by the large cash pile; useful for the capital-allocation question |
| **Return (ROE / ROA / ROIC)** | Core to hypothesis 3 - strong margins versus a heavy balance sheet |
| **Market / Valuation** | Useful for framing how the market prices a no-growth, high-margin SaaS name |

---

## 6. Data Collection Plan

- **Statements:** Income Statement, Balance Sheet, Cash Flow Statement - FY2025 (current) and FY2024 (prior), from the 10-K filings on SEC EDGAR
- **Market data:** January 31 closing share price and diluted shares for market-based ratios
- **Currency:** USD millions throughout; no conversion required
- **GAAP considerations:** Zoom's GAAP and non-GAAP figures diverge materially due to stock-based compensation; the model will use GAAP statements throughout for consistency
- **Build target:** `models/builds/2026-05-22-cao-zoom-financials.xlsx`
