# Accounting-and-Finance-for-Technology-Managers

Northwestern University, M.S. in Data Science (Data Engineering specialization) · MSDS 474: Accounting and Finance for Technology Managers

**This repository is a course portfolio index only.** Excel models, presentations, and assignment workbooks are kept locally and are not published here.

## Overview

This course covers the finance a technology manager needs to defend a budget: accounting mechanics, financial statements, time value of money, capital budgeting, working capital, market risk, and ratios. The work was done as linked Excel models. The two pieces most relevant to a data engineering leader are a build-vs-buy comparison of cloud OpEx against an on-premises Hadoop cluster's CapEx, and DCF/NPV/IRR capital budgeting for technology projects. Both are the same argument a platform team has to make when it asks for money.

## Highlights / Results

The workbooks are not published, so this section describes what each model does rather than quoting figures.

| Work | Method | What the model produces |
|------|--------|-------------------------|
| Cloud vs. on-prem data platform (build vs. buy) | Per-project workload sizing; cumulative cloud OpEx over time compared with a fixed Hadoop cluster CapEx | The crossover point where owning the cluster becomes cheaper than paying for cloud capacity, given the projected project load |
| Capital budgeting for technology projects | DCF schedules with explicit year-end vs. year-start cash flow timing; NPV and IRR at stated discount rates; scenario and sensitivity analysis | Accept/reject and ranking of competing projects, and how sensitive that ranking is to the discount rate and cash flow assumptions |
| Venture business plan (Parallel LLC) | Operating assumptions linked to projected statements, cash needs, and NPV/IRR; structured on the Sequoia Capital business plan template | Projected statements, funding ask, runway, and return profile for a technology venture, plus an investor deck |
| Financial planning and working capital | Income statement build; operating, investing, and financing cash flows; AR, AP, and prepaid adjustments | Cash flow impact of accrual-basis results |
| Market risk | Return series; beta via `SLOPE`, covariance over variance, and regression; sector benchmarks including large-cap technology | Systematic risk estimates computed three ways for cross-checking |

## Engineering decisions and tradeoffs

- **Cumulative cost curves, not a single-year comparison.** The cloud vs. on-prem model accumulates cloud OpEx period by period against an upfront cluster CapEx. A single-period comparison hides the shape of the tradeoff; the cumulative view shows when, and whether, the fixed investment pays back.
- **Sizing per project.** Platform cost is driven from per-project workload sizing rather than a flat capacity guess, so the breakeven moves when the project pipeline changes.
- **Cash flow timing made explicit.** The DCF models separate year-end and year-start conventions. On multi-year infrastructure projects, timing alone moves NPV, so it is a stated assumption rather than a default.
- **Three ways to the same beta.** Beta is computed with `SLOPE`, with covariance divided by variance, and with regression output, as a consistency check on the spreadsheet formulas.
- **Statements linked to drivers.** Statement and cash flow tabs are formula-driven from operating assumptions, so scenario changes flow through instead of being retyped.

## Limitations and what I would do differently today

- The models live in Excel and are not published, so a reviewer cannot inspect the formulas. A sanitized version of the cloud vs. on-prem model would be the most useful thing to share.
- Spreadsheet logic is hard to test or diff. Today I would put the cost and DCF logic in a small Python module (or a dbt model fed by cloud billing exports) with tests on known NPV/IRR cases, and keep Excel as the presentation layer.
- The cloud vs. on-prem comparison is a cost model. A fuller version would add staffing, migration cost, utilization risk, and egress, and would treat the discount rate as part of the sensitivity analysis.
- Scenario analysis is deterministic. Monte Carlo over the key drivers (workload growth, unit prices) would give a range rather than a point estimate.

## Repository map

| Topic | Coverage |
|-------|----------|
| Managerial accounting for technology infrastructure | Per-project sizing; cumulative cloud OpEx vs. fixed Hadoop cluster CapEx; breakeven-style build vs. buy for data platform workloads |
| Time value of money and capital budgeting | DCF schedules; NPV and IRR; project comparison at stated discount rates; year-end vs. year-start conventions; scenario and sensitivity analysis |
| Venture business plan (investor-facing) | Investment narrative for Parallel LLC (problem, market, product, go-to-market); financial model tying assumptions to projected statements, cash needs, and returns; NPV/IRR on venture cash flows; business plan, investor deck, and supporting schedules on the Sequoia Capital template; connecting P&L, working capital, and infrastructure cost choices to funding ask and runway |
| Financial planning and working capital | Income statement build; operating, investing, and financing cash flows; AR, AP, and prepaid adjustments |
| Financial markets and capital | Return series analysis; beta via `SLOPE`, covariance/variance, and regression; sector benchmark comparison |
| Financial ratios | Liquidity, leverage, profitability, and efficiency metrics |
| Macro and FX exposure | Inflation, interest rate, and exchange rate sensitivity; foreign market integration risk |
| Principles of accounting | Double-entry journal mechanics; transaction-to-statement discipline |
| Financial statements | Balance sheet and income statement construction from operating activity |

Files in this repository:

```
Accounting-and-Finance-for-Technology-Managers/
├── README.md     # this index
└── .gitignore    # keeps local workbooks, decks, and exports out of the repo
```

## Reproducing

There is nothing to run here. The workbooks, decks, and plan documents are kept offline, and `.gitignore` blocks Office, PDF, CSV, and JSON files so they are not committed by accident. The models were built in Microsoft Excel.

## Stack

| Layer | Tools |
|-------|-------|
| Primary modeling | Microsoft Excel: linked models, DCF/NPV/IRR, scenario and sensitivity analysis, `SLOPE`/regression beta, statement and cash flow analytics |
| Deliverables | `.xlsx` workbooks, presentation decks, investor plan documents (local only) |
| Repository | Markdown documentation only (no published workbooks) |
| Analysis domain | Corporate finance, managerial accounting, capital markets, technology infrastructure economics |
