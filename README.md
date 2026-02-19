# Country Risk Analyser 🌍

An LLM-powered pipeline that ingests real IMF World Economic Outlook data 
and generates structured country risk assessments using Groq's LLaMA 3.3 model.

## What it does

- Loads and cleans IMF World Economic Outlook 2024 data (190+ countries, 8 indicators)
- Formats economic indicators per country as structured analyst input
- Sends data to LLaMA 3.3 70B via Groq API with a prompt engineered for risk analysis
- Returns scored risk assessments across 4 categories: economic, financial, political, operational
- Flags data quality issues in source data
- Exports clean CSV output for downstream visualisation in Tableau or Power BI

## Output example

| Country | Overall Risk | Economic | Financial | Political | Operational | Action |
|---------|-------------|----------|-----------|-----------|-------------|--------|
| Argentina | High | 8/10 | 7/10 | 6/10 | 8/10 | Caution |
| Nigeria | High | 8/10 | 7/10 | 6/10 | 8/10 | Caution |
| Egypt | High | 8/10 | 7/10 | 6/10 | 5/10 | Caution |
| Brazil | Medium | 6/10 | 7/10 | 5/10 | 4/10 | Monitor |
| Indonesia | Medium | 6/10 | 5/10 | 4/10 | 5/10 | Monitor |
| United Kingdom | Medium | 6/10 | 5/10 | 4/10 | 5/10 | Monitor |

## Tech stack

- **Python** — data processing and pipeline orchestration
- **Groq API + LLaMA 3.3 70B** — LLM reasoning engine for risk classification
- **pandas** — data cleaning and CSV export
- **IMF World Economic Outlook April 2024** — source data

## How to run

1. Clone the repo
2. Install dependencies:
```bash
pip install groq pandas
```
3. Get a free API key at console.groq.com
4. Add your key to Cell 2 where it says `your-key-here`
5. Run all cells top to bottom

## Why I built this

Built to demonstrate practical LLM application to financial risk data workflows — 
specifically how large language models can be used to generate structured country 
risk insights from raw economic indicators, replacing manual analyst reasoning 
with a scalable, repeatable pipeline.

## Data source

IMF World Economic Outlook Database, April 2024  
https://imf.org/en/Publications/WEO
