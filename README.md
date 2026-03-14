# Country Risk Analyser 🌍
**AI-powered country risk assessment pipeline for financial services workflows**

---

## The Business Problem

Country risk assessment is a critical function in asset management and investment banking. Traditionally, analysts manually review macroeconomic indicators across dozens of countries - a process that is time-consuming, inconsistent across teams, and difficult to scale.

This project demonstrates how a structured LLM pipeline can automate the generation of country risk assessments from raw economic data, producing analyst-ready outputs in seconds rather than hours.

---

## About

Built to demonstrate practical LLM application to financial risk data workflows - specifically how large language models can augment analyst workflows by generating structured, auditable country risk insights from raw macroeconomic indicators. Demonstrated across 12 representative economies spanning high, medium, and low risk profiles, with architecture designed to scale to full IMF WEO coverage of 190+ countries.

---

## What This Solves

| Without This Pipeline | With This Pipeline |
|---|---|
| Analyst manually reviews IMF data per country | Pipeline demonstrated across 12 economies - architecture designed to scale to full IMF WEO coverage of 190+ countries |
| Inconsistent scoring across different analysts | Standardised risk framework applied uniformly |
| Hours spent writing risk summaries | Executive summaries generated in seconds |
| No audit trail on data quality | Built-in data quality flagging per country |
| Outputs locked in analyst notebooks | Clean CSV output ready for Power BI / Tableau |

---

## How It Works
```
IMF WEO Data (190+ countries available)
        ↓
Data Cleaning & Indicator Selection (Python / pandas)
        ↓
Structured Prompt Engineering (LLaMA 3.3 via Groq API)
        ↓
Risk Scoring Across 4 Categories + Executive Summary
        ↓
CSV Export → Power BI / Tableau Dashboard
```

**Risk categories assessed:**
- **Economic** - GDP growth, inflation, trade balance
- **Financial** - Government borrowing, fiscal deficit, current account
- **Political** - Policy risk inferred from macroeconomic instability signals
- **Operational** - Business environment risk based on import/export dynamics

**Output per country includes:**
- Overall risk level (Low / Medium / High / Critical)
- Scores (1–10) across all 4 categories
- 3 key signals per category
- Executive summary narrative (senior stakeholder ready)
- Recommended action (Monitor / Caution / Restrict / Avoid)
- Data quality flag (highlights missing or unreliable indicators)

---

## Sample Output

| Country | Overall Risk | Economic | Financial | Political | Operational | Action |
|---------|-------------|----------|-----------|-----------|-------------|--------|
| Argentina | High | 8/10 | 7/10 | 6/10 | 8/10 | Caution |
| Nigeria | High | 8/10 | 7/10 | 6/10 | 8/10 | Caution |
| United Kingdom | Medium | 6/10 | 5/10 | 4/10 | 5/10 | Monitor |
| Brazil | Medium | 6/10 | 7/10 | 5/10 | 4/10 | Monitor |
| Switzerland | Low | 3/10 | 3/10 | 2/10 | 3/10 | Monitor |
| Singapore | Low | 2/10 | 2/10 | 2/10 | 2/10 | Monitor |

---

## Responsible AI & Governance

This pipeline is designed with responsible AI principles in mind:

- **Data quality flagging** - every output includes a `data_quality_flag` field that surfaces missing, extreme, or potentially unreliable indicators before scores are used
- **Human-in-the-loop** - outputs are framed as decision-support, not decision-making. Recommended actions are inputs to analyst judgment, not replacements for it
- **Auditability** - all prompt logic is version-controlled and transparent; scoring rationale is included in every output
- **Source transparency** - data sourced exclusively from IMF World Economic Outlook (April 2024), a credible and publicly documented source
- **Limitations acknowledged** - political risk is inferred from economic signals only; geopolitical events and qualitative factors are outside scope

---

## Tech Stack

- **Python** - pipeline orchestration and data processing
- **pandas** - data cleaning, indicator selection, CSV export
- **Groq API + LLaMA 3.3 70B** - LLM reasoning engine for risk classification
- **Power BI / Tableau** - downstream visualisation and dashboard
- **IMF World Economic Outlook April 2024** — source data (190+ countries available, 8 macroeconomic indicators - pipeline demonstrated across 12 representative economies)

---

## How to Run

1. Clone the repo
2. Install dependencies:
```bash
pip install groq pandas
```
3. Get a free API key at [console.groq.com](https://console.groq.com)
4. Add your key to Cell 2 where it says `your-key-here`
5. Run all cells top to bottom

---

## Data Source

IMF World Economic Outlook Database, April 2024
https://www.imf.org/en/publications/weo/weo-database/2025/april

