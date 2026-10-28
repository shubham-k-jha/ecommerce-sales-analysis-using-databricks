<div align="center">

# 🛒 E-Commerce Sales Analysis
### 📊 Databricks • PySpark • Data Quality • Business Insights

<p>
  <img src="https://img.shields.io/badge/Platform-Databricks-EF3E2F?style=for-the-badge&logo=databricks&logoColor=white" alt="Databricks"/>
  <img src="https://img.shields.io/badge/Language-Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Engine-PySpark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white" alt="PySpark"/>
  <img src="https://img.shields.io/badge/Focus-Data%20Analytics-7C3AED?style=for-the-badge" alt="Data Analytics"/>
</p>

<p>
  <b>From raw order data to clearer business decisions.</b><br/>
  An exploratory analytics project examining e-commerce sales, data quality, discount patterns, and category performance.
</p>

</div>

---

## 🧭 Project at a Glance

<table>
<tr>
<td align="center" width="25%">
<h3>🔍</h3>
<b>Inspect</b><br/>
<sub>Profile the source data</sub>
</td>
<td align="center" width="25%">
<h3>🧹</h3>
<b>Clean</b><br/>
<sub>Investigate quality issues</sub>
</td>
<td align="center" width="25%">
<h3>📈</h3>
<b>Analyze</b><br/>
<sub>Calculate and compare KPIs</sub>
</td>
<td align="center" width="25%">
<h3>💡</h3>
<b>Recommend</b><br/>
<sub>Translate evidence into action</sub>
</td>
</tr>
</table>

<p align="center">
  <code>RAW DATA</code> ➜ <code>QUALITY CHECKS</code> ➜ <code>CLEANING</code> ➜ <code>KPIs</code> ➜ <code>INSIGHTS</code>
</p>

> 🟡 **Project status: Exploratory — validation required.** The notebook has a useful end-to-end structure, but duplicate handling, missing-discount assumptions, and status-based sales definitions should be corrected and revalidated before its results are treated as final.

## 🎯 Business Problem

A sales manager wants to understand which product categories perform best, how discounts relate to order value, and whether order-status or data-quality issues distort reported performance.

### 🔎 Questions investigated

- 🧪 What data-quality issues exist in the order data?
- 🏆 Which product categories generate the most reported sales?
- 🧾 Which categories have the highest average order value (AOV)?
- 🏷️ How do discount rates relate to gross merchandise value (GMV) and quantity?
- 🌍 Which regions or products deserve further investigation?
- 💼 What additional evidence would support stronger business recommendations?

## 🧰 Tech Stack

<p>
  <img src="https://img.shields.io/badge/Databricks-Workspace-EF3E2F?style=flat-square&logo=databricks&logoColor=white" alt="Databricks"/>
  <img src="https://img.shields.io/badge/PySpark-Distributed%20Processing-E25A1C?style=flat-square&logo=apachespark&logoColor=white" alt="PySpark"/>
  <img src="https://img.shields.io/badge/Spark%20SQL-Data%20Transformations-FDEE21?style=flat-square&logo=apachespark&logoColor=black" alt="Spark SQL"/>
  <img src="https://img.shields.io/badge/EDA-Exploratory%20Analysis-0EA5E9?style=flat-square" alt="EDA"/>
  <img src="https://img.shields.io/badge/KPIs-Business%20Metrics-16A34A?style=flat-square" alt="KPIs"/>
</p>

| Area | Techniques |
|---|---|
| Data inspection | Schema, row counts, summary statistics, category distributions |
| Data quality | Missing values, duplicate IDs, exact duplicate rows, invalid quantities |
| Transformation | String normalization, validation, derived sales metrics |
| Business analysis | GMV, post-discount order value, AOV, cancellation and return rates |
| Segmentation | Category, region, product, order status, discount tier |
| Statistics | Pearson correlation and cautious interpretation |
| Communication | Findings, recommendations, limitations, follow-up questions |

## 🗂️ Dataset & Data Dictionary

The project uses `ecommerce_sales_analyst_task.csv`, a small practice dataset containing order and product attributes.

| Field | Description |
|---|---|
| `order_id` | Order identifier |
| `order_date` | Order date |
| `region` | Sales region |
| `category` | Product category |
| `product` | Product name |
| `quantity` | Quantity ordered |
| `unit_price_inr` | Unit price in Indian rupees (₹) |
| `discount_rate` | Discount expressed as a decimal; e.g. `0.10` = 10% |
| `status` | Order status, such as Delivered, Cancelled, or Returned |

📌 **Current notebook input:** `data_learn.default.ecommerce_sales_analyst_task`

To reproduce the project, upload the CSV to a location accessible from your Databricks workspace and either create the expected table or update the notebook's input reference.

## ⚙️ Analytical Workflow

<table>
<tr>
<td width="8%" align="center">🔍</td>
<td width="27%"><b>1. Inspect</b></td>
<td>Review schema, data types, distributions, missing values, and repeated records.</td>
</tr>
<tr>
<td align="center">🚦</td>
<td><b>2. Diagnose</b></td>
<td>Investigate conflicting order IDs, unexpected categories, invalid quantities, and missing fields.</td>
</tr>
<tr>
<td align="center">🧹</td>
<td><b>3. Clean & validate</b></td>
<td>Apply documented cleaning rules and preserve evidence of changed values.</td>
</tr>
<tr>
<td align="center">🧮</td>
<td><b>4. Calculate KPIs</b></td>
<td>Compute order counts, GMV, post-discount value, AOV, cancellation rate, and return rate.</td>
</tr>
<tr>
<td align="center">📊</td>
<td><b>5. Compare segments</b></td>
<td>Analyze category, region, product, status, and discount-tier patterns.</td>
</tr>
<tr>
<td align="center">💡</td>
<td><b>6. Recommend</b></td>
<td>Translate descriptive results into testable actions and identify limitations.</td>
</tr>
</table>

## 📊 Preliminary Findings

<details>
<summary><b>📌 Expand to view figures reported by the current notebook</b></summary>

> ⚠️ These are **saved notebook results**, not independently re-executed or fully validated figures. Reconcile them after correcting data-cleaning and KPI logic.

| Metric | Current notebook result | Interpretation |
|---|---:|---|
| Original rows | 41 | Initial dataset size |
| Rows after deduplication | 40 | Requires review of duplicate-resolution logic |
| Delivered orders | 36 | Reported order-status count |
| Cancelled orders | 2 | Reported order-status count |
| Returned orders | 2 | Reported order-status count |
| Electronics reported net sales | ₹28,140.95 | Current category calculation |
| Fashion reported net sales | ₹28,103.00 | Current category calculation |
| Home reported net sales | ₹19,302.40 | Current category calculation |
| Fashion reported AOV | ₹2,161.77 | Confirm order-level aggregation before publication |
| Electronics reported AOV | ₹2,010.07 | Confirm order-level aggregation before publication |
| Home reported AOV | ₹1,484.80 | Confirm order-level aggregation before publication |
| Discount rate vs. GMV Pearson correlation | 0.321 | Descriptive association; not causal evidence |
| Discount rate vs. quantity Pearson correlation | 0.028 | Descriptive association; not causal evidence |

</details>

### 💡 Recommendations to test

1. 🧪 **Evaluate discount effectiveness.** Test whether discounts improve conversion and net contribution. Larger order values alone do not demonstrate that a discount is effective.
2. 🧾 **Audit order processing and returns.** Investigate the returned record with zero quantity and review cancellation/return handling before interpreting regional differences.

## 🚧 Data Quality & Interpretation Caveats

These checks should be resolved before treating the analysis as complete:

- 🧩 **Duplicate records:** Do not automatically discard every repeated `order_id`. Distinguish exact duplicate rows from conflicting records sharing the same ID.
- 🏷️ **Status audit:** Preserve original values before normalization so that changed labels can actually be audited.
- ❓ **Missing discounts:** Do not assume a missing discount means zero unless a documented business rule supports it.
- 🔢 **Invalid quantities:** Investigate zero or negative quantities and document how each case should be handled.
- 📦 **Order vs. line grain:** Confirm whether each row represents a complete order or an order line. Aggregate by order ID before calculating order-level AOV if multiple lines can belong to one order.
- 🚚 **Status-aware sales:** Report delivered-order value separately from cancelled and returned orders. The dataset does not provide confirmed refund amounts, costs, or accounting recognition rules; do not describe these calculations as profit or confirmed accounting revenue.
- 📍 **Missing region:** Reconcile regional totals and explicitly account for orders with unknown regions.
- 📉 **Correlation:** Correlation is an association, not proof that discounts cause higher order values or change purchase quantity.
- 📏 **Sample size:** The dataset is small and covers a short period in September 2026. Findings are exploratory, not broadly generalizable.

## 🏃 How to Run

### Option A — Databricks

1. Import `notebooks/E-Commerce Sales Data Inspection.ipynb` into your Databricks workspace.
2. Upload the CSV to a location accessible to your notebook.
3. Create the expected source table or update the notebook's input reference.
4. Run all cells from top to bottom.
5. Review quality checks and reconcile KPI totals before relying on the conclusions.

### Option B — Local environment

The notebook currently uses Databricks-specific operations such as `spark.table()` and `display()`, so it will **not run unchanged in a pandas-only environment**.

To run locally, use a compatible PySpark setup and replace Databricks-specific table/display operations, or adapt the workflow to pandas. Record the required versions and dependencies in a `requirements.txt` file.

## 🗃️ Suggested Repository Structure

```text
ecommerce-sales-analysis/
├── README.md
├── notebooks/
│   └── E-Commerce Sales Data Inspection.ipynb
├── data/
│   └── ecommerce_sales_analyst_task.csv
└── outputs/
    └── charts/
```

Only commit datasets you are permitted to redistribute. Never commit credentials, access tokens, private business data, or unnecessary environment files.

## 🛣️ Roadmap

- [ ] Correct and test duplicate-resolution rules
- [ ] Preserve raw values and add a cleaning audit log
- [ ] Standardize KPI definitions and aggregate at the correct grain
- [ ] Add assertions and tests for sales calculations and edge cases
- [ ] Reconcile category, regional, and order-status totals
- [ ] Add clearly labeled visualizations and business context
- [ ] Evaluate discounts using a stronger comparison design
- [ ] Document a reproducible local execution path and dependencies

## 👤 Author

**Your Name**  
🔗 GitHub: `https://github.com/YOUR_USERNAME`  
🌐 Portfolio: `YOUR_PORTFOLIO_URL`

---

<div align="center">

### ⭐ Turning data into decisions — one question at a time.

<sub>Built as a practical analytics portfolio project. Results remain exploratory until the noted validation issues are resolved.</sub>

</div>
