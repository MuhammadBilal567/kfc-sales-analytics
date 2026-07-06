# -kfc-sales-analytics
End-to-end sales analytics: Python data cleaning pipeline + Power BI dashboard on 100K+ transaction records.
# 🍗 KFC Sales Analytics — Python & Power BI

End-to-end sales analytics project: cleaning 100K+ messy transaction records with a documented Python pipeline, exploring the data, and delivering an interactive Power BI dashboard with a written business report.

![Dashboard](<img width="1678" height="730" alt="Screenshot 2026-07-05 211625" src="https://github.com/user-attachments/assets/a70dd3aa-f75a-4af9-b236-a7850223a02f" />
)

## 📌 Project Overview

This project simulates a real client engagement for a KFC-style restaurant chain with **8 stores across Pakistan, UAE, and the UK** (2023–2025). Starting from a deliberately messy raw dataset of **~104,500 rows**, the project covers the complete analytics workflow:

**Raw data → Python cleaning pipeline → EDA → Power BI dashboard → Business report**

## 🧹 Data Cleaning (Python / Pandas)

The raw data contained realistic quality problems: missing values across 7 columns, ~6,500 duplicate records, inconsistent text ("LAHORE" / "Lahor" / "lahore"), mixed date formats, impossible values (ages of 999, negative sales, ratings outside 1–5), and totals that didn't match quantity × price.

The cleaning pipeline follows a principled order:

1. **Standardize text first** — canonical city/product/payment names, so lookups work
2. **Relationship-based recovery** — missing cities recovered from `store_id`, categories from `product` (100% recovery, zero guessing)
3. **Fix impossible values before imputation** — so outliers don't poison the median
4. **Honest imputation** — "Unknown" for unrecoverable categories, median for age, ratings deliberately left null (missing-not-at-random)
5. **Deduplicate, validate business rules, parse dates**

Result: **104,500 → 98,886 clean rows (5.4% removed)**, every decision documented.

## 📊 Key Findings

| Metric | Value |
|---|---|
| Total Revenue | PKR 194.5M |
| Total Orders | 98,886 |
| Avg Order Value | PKR 1,967 |
| Avg Rating | 3.0 / 5 (92% response) |

- **Buckets dominate**: 35.7% of revenue from just 2 products (Chicken Bucket PKR 36.6M, Boneless Bucket PKR 32.9M)
- **Geography**: Pakistan ~63% of revenue, UK ~25%, UAE ~12% — driven by store count, not per-store performance
- **Satisfaction gap**: 3.0/5 average rating vs a 4.0 target, visualized as a KPI gauge

## 📈 Power BI Dashboard

One-page interactive overview: KPI cards, monthly revenue trend, Top-10 products, category share, revenue by city/country map, order-type mix, satisfaction gauge — all cross-filtered by **Year / City / Category slicers**. Built on a dedicated date table with explicit DAX measures.

## 🗂️ Repository Contents

| File | Description |
|---|---|
| `kfc_analysis.ipynb` | Cleaning pipeline + exploratory analysis (Colab notebook) |
| `kfc_sales_raw.csv` | Raw synthetic dataset (with quality problems) |
| `dashboard.png` | Final dashboard screenshot |
| `KFC_Sales_Analytics_Report.pdf` | Full written business report |

## 🛠️ Tools

**Python** (Pandas, NumPy, Matplotlib) · **Power BI** (DAX, data modeling) · Google Colab

## ⚠️ Note

The dataset is **synthetic**, generated to mirror the structure and quality problems of real point-of-sale data. The value of this project is the pipeline and methodology, which are production-ready for real client data.

---

**Muhammad Bilal** — Final-year BS Data Science, PAF-IAST
📧 bilalamjadtitnec@gmail.com · [LinkedIn](www.linkedin.com/in/muhammad-bilal-33861b402)
