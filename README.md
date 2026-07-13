# 🇧🇭 Bahrain Imports: Direct Import Feasibility for Local Businesses

## 📌 Project Overview
This project presents an **Exploratory Data Analysis (EDA)** on the Kingdom of Bahrain's international trade activities across five consecutive years (**2021–2025**). 

Local businesses in Bahrain frequently face inflated operational costs and compressed profit margins due to a heavy reliance on third-party distributors and middlemen. This technical report and analytical pipeline evaluate transaction-level import records to establish a data-backed roadmap for a **direct-import strategy**, allowing local enterprises to bypass intermediary fees, optimize supply chains, and structurally cut costs.

---

## 📑 Table of Contents
1. [Problem Statement](#-problem-statement)
2. [The Dataset](#-the-dataset)
3. [Data Cleaning & Methodology](#-data-cleaning--methodology)
4. [Key Insights & Findings](#-key-insights--findings)
5. [Strategic Recommendations](#-strategic-recommendations)
6. [Repository Structure](#-repository-structure)

---

## 🎯 Problem Statement
> **How can local businesses in Bahrain transition from costly third-party distribution networks to a highly efficient direct-import model?**

A local business currently relies on third-party distributors to source commodities, inflating procurement expenses. By analyzing five years of historical customs import data, this project identifies aggregate volume trends, micro-level fluctuations, and the most cost-effective countries of origin. The goal is to formulate a data-backed blueprint that identifies optimal global sourcing partners to scale profitability.

---

## 📊 The Dataset
* **Source:** Sourced originally from the Bahrain Open Data Portal and verified via Bahrain Customs Affairs.
* **Scope:** Approximately 1.6 million comprehensive import records spanning from **2021 to 2025**.
* **Key Features Monitored:** `Country Name`, `Commodity`, `Import Value (BD)`, `Import Weight (KG)`, `Import Quantity`, and `Year`.

---

## 🛠️ Data Cleaning & Methodology
To guarantee a production-ready, clean dataset for statistical visualization, a rigorous data-cleaning pipeline was executed:

* **Drop Arabic Columns:** Removed redundant columns (`الدولة` and `السلعة`) to enforce strict English column naming conventions (`Country Name` and `Commodity`).
* **Remove Unused Columns:** Eliminated the system-generated index column `N` which contained uninformative null sequence values.
* **Fix Missing Values:** Imputed missing values within the `Commodity`, `UN code`, and `UM` categorical attributes with the fallback string standard **'Unknown'**.
* **Correct Data Types:** Cast the `Import Quantity` column from a decimal format (`float64`) into a clean, whole-number integer format (`int64`).
* **Remove Negative Records:** Cleaned anomalous data entry errors by locating and dropping rows where `Import Value (BD) < 0`.

---

## 📈 Key Insights & Findings

### 🇨🇳 1. Top Trading Partners
Our analytical charts clearly identify **China** as Bahrain's **#1 import partner** by absolute transaction value, with **Brazil** securing the **second-place** position. These two global hubs represent the highest impact starting points for local businesses seeking to strike direct corporate trade deals.

### 📉 2. Import Value Trends
The trade trajectory reflects consistent commercial scaling. Total import values **grew steadily from 2021 to 2025**, marking 2021 as the historical baseline low and 2025 as the peak transaction year. A single temporary **micro-dip** was identified and isolated during the **2023** fiscal year.

---

## 🚀 Strategic Recommendations

1. **Establish Direct Procurement Contracts:** Prioritize manufacturing plants and primary suppliers located in **China and Brazil** to completely eliminate unnecessary distributor margins.
2. **Implement System Entry Guardrails:** Integrate structural database validation checks at the application level to stop negative financial entry anomalies from corrupting live data stores.
3. **Logistics & Warehousing Expansion:** Leverage the steady upward import trajectory to forecast warehouse capacity demands and contract logistics space well ahead of time.
4. **Next Analytical Steps:** Run deep-dive micro-analysis to identify the specific product categories driving this multi-year growth and investigate the macroeconomic catalysts behind the 2023 market dip.

---

## 📁 Repository Structure
```filesystem
├── data/                             # Raw and cleaned data directories
├── notebooks/                        # Jupyter notebooks containing the core EDA & data cleaning
│   └── Bahrain_Imports_EDA.ipynb     # Main analytical notebook
├── presentation/                     # Final presentation materials
│   └── Bahrain_Imports_Slides.pdf    # Executive slideshow for non-technical audiences
├── README.md                         # Project executive summary (This file)
└── requirements.txt                  # Python library dependencies