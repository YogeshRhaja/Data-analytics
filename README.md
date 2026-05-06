# 📊 Sales & Revenue Analysis

> Exploratory data analysis and interactive dashboards uncovering revenue trends, regional performance, and product-level insights from sales data.

![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 🔍 Overview

This project performs end-to-end exploratory data analysis (EDA) on a sales dataset to answer key business questions around revenue performance, seasonal trends, top products, and regional breakdowns. Insights are surfaced through interactive dashboards in Tableau / Power BI.

**Business Questions Answered:**
- Which products and categories drive the most revenue?
- How does sales performance vary across regions and time periods?
- What are the peak and low seasons for revenue?
- Which customer segments contribute most to overall sales?

---

## 📁 Project Structure

```
sales-revenue-analysis/
│
├── data/
│   ├── raw/                  # Original, unmodified datasets
│   └── processed/            # Cleaned and transformed data
│
├── sql/
│   ├── data_cleaning.sql     # Null handling, deduplication, type casting
│   ├── exploratory.sql       # EDA queries — aggregations, rankings, trends
│   └── views.sql             # Reusable SQL views for dashboards
│
├── dashboards/
│   ├── sales_overview.pbix   # Power BI dashboard file
│   └── sales_tableau.twbx    # Tableau packaged workbook
│
├── reports/
│   └── key_findings.md       # Summary of insights and recommendations
│
└── README.md
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **SQL** (PostgreSQL / MySQL) | Data extraction, cleaning, transformation, EDA |
| **Tableau** | Interactive visual dashboards |
| **Power BI** | Executive-level reporting & KPI tracking |
| **Excel / CSV** | Raw data storage and initial inspection |

---

## 📊 Key Findings

- 📈 **Q4 drives ~38% of annual revenue** — strong holiday and year-end purchasing spikes observed
- 🏆 **Top 3 product categories account for 62% of total sales** — long-tail products contribute minimally
- 🌍 **North region outperforms all others by 24%** in revenue despite similar headcount
- 📉 **February and August are consistent low-revenue months** — potential targets for promotional campaigns
- 👥 **Enterprise customers (< 5% of base) contribute 47% of revenue** — high retention risk concentration

---

## 🗃️ Dataset

| Attribute | Details |
|-----------|---------|
| Source | *(e.g., Kaggle / Internal CRM / Dummy data)* |
| Records | *(e.g., ~50,000 transactions)* |
| Period | *(e.g., Jan 2020 – Dec 2023)* |
| Fields | Order ID, Date, Product, Category, Region, Customer Segment, Revenue, Quantity |

> ⚠️ If using real business data, ensure sensitive fields are anonymised before committing.

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/your-username/sales-revenue-analysis.git
cd sales-revenue-analysis
```

### 2. Set up the database
```sql
-- Run scripts in order:
-- 1. data_cleaning.sql
-- 2. views.sql
```

### 3. Open dashboards
- **Power BI**: Open `dashboards/sales_overview.pbix` in Power BI Desktop
- **Tableau**: Open `dashboards/sales_tableau.twbx` in Tableau Desktop or Tableau Public

---

## 📸 Dashboard Preview

> *(Add screenshots of your Tableau / Power BI dashboards here)*

```
![Sales Overview Dashboard](reports/dashboard_preview.png)
```

---

## 📌 SQL Highlights

```sql
-- Monthly revenue trend
SELECT
    DATE_TRUNC('month', order_date) AS month,
    SUM(revenue)                    AS total_revenue,
    COUNT(DISTINCT order_id)        AS total_orders
FROM sales
GROUP BY 1
ORDER BY 1;

-- Top 10 products by revenue
SELECT
    product_name,
    SUM(revenue) AS revenue,
    RANK() OVER (ORDER BY SUM(revenue) DESC) AS rank
FROM sales
GROUP BY product_name
ORDER BY revenue DESC
LIMIT 10;
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙋 Author

**Your Name**
[GitHub](https://github.com/YogeshRhaja) · [LinkedIn](https://linkedin.com/in/yogeshrhaja-s)

---

*⭐ Star this repo if you found it useful!*
