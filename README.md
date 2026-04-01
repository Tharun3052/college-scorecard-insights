# 🎓 College Scorecard Insights — Helping Students Make Smarter Decisions

<div align="center">

![BigQuery](https://img.shields.io/badge/BigQuery-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![OpenRefine](https://img.shields.io/badge/OpenRefine-3F7DC0?style=for-the-badge)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-2ECC71?style=for-the-badge)
![Course](https://img.shields.io/badge/Course-ADTA%205240-blueviolet?style=for-the-badge)

**An end-to-end data pipeline analyzing 6,000+ U.S. colleges to surface the best-value institutions — comparing tuition, student debt, and 10-year post-graduation earnings.**

[📌 Problem](#-problem-statement) • [🔧 Pipeline](#-data-pipeline) • [📈 Findings](#-key-findings) • [🚀 Getting Started](#-getting-started)

</div>

---

## 📌 Problem Statement

Choosing the right college is one of the most important and expensive decisions a student will ever make — yet most students lack clear, accessible data to guide that choice. Many take on significant debt without understanding whether their college or program will deliver a worthwhile return on investment.

This project uses publicly available U.S. Department of Education data to **identify colleges that offer the best financial value** — ranked by comparing cost of attendance and student debt against median earnings 10 years after graduation.

---

## 🔍 Key Questions Answered

1. Which colleges offer the best ROI — high earnings relative to cost and debt?
2. How do public vs. private institutions compare on value?
3. Do higher-cost colleges always lead to better post-graduation earnings?
4. Which institutions carry the lowest median student debt burden?
5. How does Pell Grant eligibility correlate with college value?

---

## 📦 Dataset

| Property | Detail |
|---|---|
| **Source** | [U.S. Department of Education — College Scorecard](https://collegescorecard.ed.gov/data) |
| **File** | `Most-Recent-Cohorts-Institution_05192025.csv` |
| **Scale** | 6,000+ U.S. colleges and universities |
| **Coverage** | 2022–2025 most recent cohort window |

### Key Variables

| Variable | Description |
|---|---|
| `INSTNM` | Institution name |
| `COSTT4_A` | Average annual cost of attendance |
| `MD_EARN_WNE_P10` | Median earnings 10 years post-entry |
| `GRAD_DEBT_MDN_SUPP` | Median student debt at graduation |
| `PCTPELL` | % of Pell Grant recipients |
| `CONTROL` | Public / Private Non-Profit / Private For-Profit |

---

## 🔧 Data Pipeline

```
Raw CSV (College Scorecard)
        ↓
   OpenRefine
   ├── Remove null & "PrivacySuppressed" values
   ├── Convert columns to numeric formats
   └── Standardize column naming
        ↓
Google Cloud Storage
   └── Upload cleaned CSV
        ↓
BigQuery
   ├── SQL-based analysis & aggregations
   └── Value scoring: earnings / (cost + debt)
        ↓
   Visualization & Insights
```

---

## 🛠 Tech Stack

| Tool | Purpose |
|---|---|
| **OpenRefine** | Data cleaning & normalization |
| **Google Cloud Storage** | Cloud dataset storage |
| **BigQuery** | SQL querying & large-scale analysis |
| **Python / Pandas** | Supplementary EDA |
| **Matplotlib / Seaborn** | Visualization |

---

## 📈 Key Findings

- **Public universities** outperform private for-profits on ROI in most states
- Colleges with **median debt below $15K** still produce graduates earning $45K+ after 10 years
- **Pell Grant access** is a strong proxy for institutional value for low-income students
- Cost of attendance alone is a **poor predictor** of post-graduation earnings
- Several mid-sized public universities in Texas ranked among the **top-value institutions** nationally

---

## 📂 Project Structure

```
📁 college-scorecard-insights/
│
├── 📊 presentation.pptx          ← Final project slides
├── 📄 README.md
├── 📄 requirements.txt
├── 📄 .gitignore
├── 📁 sql/
│   └── analysis_queries.sql      ← BigQuery SQL queries
└── 📁 data/
    └── listings_cleaned.csv      ← Cleaned dataset (add manually)
```

---

## 🚀 Getting Started

```bash
git clone https://github.com/Tharun3052/college-scorecard-insights.git
cd college-scorecard-insights
pip install -r requirements.txt
```
---

## 👥 Team

| Member | Role |
|---|---|
| Tharun Reddy Marreddy | Data pipeline, BigQuery analysis |
| Monica Valli Kandulapati | Data preprocessing & cleaning |
| Srinija Chowdary Garapati | Visualization & insights |
| Venkata Satya Abhi Madhav Nallamalli | Reporting |
| Vihal Thatipamula | Presentation |

**Course:** ADTA 5240 — Harvesting, Storing and Retrieving Data | University of North Texas  
**Instructor:** Tony Fantasia

---

<div align="center">
Made with ❤️ | <a href="https://github.com/Tharun3052">Tharun Reddy</a>
</div>
