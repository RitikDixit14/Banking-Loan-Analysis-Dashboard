# Banking Loan Analysis Dashboard

An interactive Power BI dashboard consolidating five independent loan and credit datasets into one connected, navigable report — covering personal loan marketing, credit risk, loan approval, legacy loan data, and loan default behavior.

**Author:** Ritik Dixit
**GitHub:** [github.com/RitikDixit14](https://github.com/RitikDixit14)

---

## Overview

This project brings together five structurally unrelated loan/credit datasets into a single Power BI report. Rather than analyzing each dataset in isolation, the report is built as one cohesive product:

- A landing **Overview** page summarizing findings across all five datasets
- Five dedicated pages, one per dataset, each explored in depth
- Clickable navigation buttons and interactive KPI card actions to jump between any page

Since the datasets share no common keys, no relationships were forced between them in the data model — each is kept as an independent fact table and compared visually through a shared summary table.

---

## Datasets

| Dataset | Records | Purpose |
|---|---|---|
| Personal Loan Marketing | 5,000 | Predict which bank customers take up personal loan offers |
| Credit Risk | 32,576 | Assess borrower default risk by credit grade and profile |
| Loan Approval | 2,000 | Model approval decisions from applicant financial profile |
| Loan Data (Legacy) | 381 | Classic loan approval demographics dataset |
| Loan Default | 255,347 | Identify default drivers across a large modern loan book |

**Total records analyzed:** 295,304

---

## Data Preparation

Each raw CSV was cleaned before being loaded into the Power BI model:

- **Personal Loan Marketing** — recoded numeric education levels into readable labels, labeled binary Yes/No flags
- **Credit Risk** — filled missing employment length with median, filled missing interest rate using the median per credit grade, removed implausible applicant ages
- **Loan Approval** — labeled approval outcome as Approved/Rejected
- **Loan Data (Legacy)** — filled missing Gender, Dependents, Self-Employed, Loan Term, and Credit History fields; labeled loan outcome
- **Loan Default** — labeled binary default outcome

---

## Dashboard Structure

| Page | Contents |
|---|---|
| **Overview** | 5 color-coded KPI cards, cross-dataset rate comparison chart, 3 headline insight tiles |
| **Personal Loan Marketing** | Take-up rate by education/income, spending vs. income view, account-type slicers |
| **Credit Risk** | Default rate by grade & intent, home-ownership comparison, prior-default slicer |
| **Loan Approval** | Credit score vs. income, approval rate by score band, top-cities table |
| **Loan Data (Legacy)** | Approval by property area & education, applicant demographic table |
| **Loan Default** | Default by loan purpose & employment type, credit score vs. interest rate |

Every page shares a consistent navigation bar, a matching accent color, and a text banner — with the KPI cards on the Overview page also directly clickable through to their matching dataset page.

---

## Key Findings

| Dataset | Headline Rate | Strongest Driver Observed |
|---|---|---|
| Personal Loan Marketing | 9.6% take-up | Advanced/Professional degree holders take up loans at ~3x the rate of undergraduates (13.7% vs. 4.4%) |
| Credit Risk | 21.8% default | Default climbs steadily with credit grade: 10.0% (Grade A) → 98.4% (Grade G) |
| Loan Approval | 44.0% approved | Average applicant credit score of 574 |
| Loan Data (Legacy) | 71.1% approved | Highest approval rate of all five datasets |
| Loan Default | 11.6% default | Business loans default most (12.3%); home loans least (10.2%) |

The widest risk spread in the project is within Credit Risk: Grade A borrowers default at ~10% vs. Grade G at over 98%, confirming the grading system is a strong, reliable predictor of repayment behavior.

---

## Tools & Methodology

- **Data cleaning:** Python (pandas) — null handling, categorical recoding, outlier removal
- **Dashboard:** Microsoft Power BI Desktop
- **Data model:** 5 independent fact tables + 1 manually entered summary table for cross-dataset comparison
- **Navigation:** custom button-based page navigation + clickable KPI card actions, replicated across all 6 pages
- **Visual design:** consistent per-dataset accent color, banner, canvas background, and KPI card styling

---

## Files in this Repository

- `Banking_Loan_Analysis_Dashboard.pbix` — the Power BI report
- `Banking_Loan_Dashboard_Report.pdf` — full project write-up with findings and methodology
- Cleaned datasets (`*_clean.csv`) — preprocessed versions of the 5 source files used in the report

---

## Contact

Ritik Dixit — [github.com/RitikDixit14](https://github.com/RitikDixit14)
