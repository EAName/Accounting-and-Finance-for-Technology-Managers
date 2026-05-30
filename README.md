# Accounting-and-Finance-for-Technology-Managers

Graduate coursework in corporate finance and managerial accounting for technology leaders: capital budgeting, financial statement analysis, market risk metrics, and infrastructure cost tradeoffs, captured as structured spreadsheet exports.

---

## 1. Title and Summary

**Accounting and Finance for Technology Managers**  
Northwestern University M.S. in Data Science (Data Engineering specialization): financial decision support for technology projects through Excel-oriented modeling of project returns, income/cash-flow statements, capital-market betas, and cloud vs. on-premise cost comparisons.

---

## 2. Concepts and Methods

- **Capital budgeting / project returns:** discounted cash flow schedules; NPV at year-end vs. year-start cashflows; IRR; side-by-side comparison of Project A vs. Project B at stated discount rates; Excel formula validation columns (`Calculating_Project_Returns.json`)
- **Managerial accounting (technology infrastructure):** per-project sizing; cumulative cloud computing cost vs. fixed Hadoop cluster capital; breakeven-style comparison of elastic cloud spend against upfront cluster investment across a project portfolio (`Managerial_Accounting.json`)
- **Financial statements and working capital:** income statement build (Sales, COGS, gross profit, SG&A, depreciation, operating/pretax/net income); statement of cash flows with operating (net income, depreciation, AR/AP/prepaid adjustments), investing, and financing sections; net change in cash (`Financial_Planning_and_Working_Capital_Management.json`)
- **Financial markets and risk:** monthly S&P 500 vs. Home Depot (HD) return series; beta estimation methods documented inline (Excel `SLOPE`, covariance/variance ratio, regression); summary statistics for standard deviation, variance, covariance, and correlation (`Financial Markets and Capital.json`)

**Course syllabus topics not represented in committed artifacts:** Sequoia Capital-style business plan deliverable; standalone financial ratio workbook; dedicated time-value-of-money module; inflation, interest-rate, and foreign-exchange exercises

**Artifact format:** four JSON files appear to be spreadsheet/tabular exports (wide columns, embedded Excel instruction text), not executable Python/R notebooks

**Out of scope for this repo:** Python programming foundations (see **Programming-with-Python**); inferential statistics (see **Statistics**); prescriptive optimization (see **Decision-Analytics**); production analytics engineering (see **Analytics-Applications-Engineering**).

---

## 3. Stack

| Layer | Tools |
|-------|-------|
| Primary modeling | Microsoft Excel (formulas referenced: NPV, IRR, SLOPE, regression beta) |
| Repository format | JSON tabular exports |
| Analysis domain | Corporate finance, managerial accounting, capital markets |

---

## 4. Structure

```
Accounting-and-Finance-for-Technology-Managers/
├── Calculating_Project_Returns.json
├── Managerial_Accounting.json
├── Financial_Planning_and_Working_Capital_Management.json
├── Financial Markets and Capital.json
└── README.md
```

- **Organization:** one JSON export per major course module; no code packages or notebooks
- **Reusable modules:** none
- **Engineering practice:** ROI/NPV/IRR justification for technology investments; translate P&L into cash-flow impacts; quantify systematic risk (beta) against a market benchmark; compare OpEx cloud path vs. CapEx cluster path for data platform workloads

---

**Course context:** Northwestern University, M.S. in Data Science, Data Engineering specialization  
**Repository:** https://github.com/EAName/Accounting-and-Finance-for-Technology-Managers
