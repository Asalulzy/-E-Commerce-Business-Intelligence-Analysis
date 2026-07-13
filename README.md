# 📊 Brazilian E-Commerce Business Intelligence Analysis

An end-to-end **Business Intelligence** case study using the **Olist Brazilian E-Commerce Public Dataset (2016–2018)**. This project simulates the role of a **Data Analyst / Business Intelligence Analyst**, transforming raw transactional data into actionable business insights through data cleaning, feature engineering, exploratory data analysis, customer analytics, statistical hypothesis testing, and star schema modeling for downstream BI dashboards.

---

## 📖 Project Overview

The Olist marketplace connects thousands of small and medium-sized sellers across Brazil to major online marketplaces. As the business grows, management needs a comprehensive understanding of sales performance, customer behavior, logistics efficiency, and seller contribution to support strategic decision-making.

This project follows a complete Business Intelligence workflow—from business understanding to generating analysis-ready datasets and strategic recommendations backed by statistical evidence.

---

## 📈 Executive KPI

| KPI                           |                Value |
| ----------------------------- | -------------------: |
| Gross Merchandise Value (GMV) | **R$ 13.59 Million** |
| Total Orders                  |           **98,666** |
| Unique Customers              |           **95,420** |
| Average Order Value           |        **R$ 137.75** |
| Average Review Score          |      **4.03 / 5.00** |
| On-Time Delivery Rate         |            **93.4%** |
| Average Delivery Time         |  **12.0 days (median 10)** |
| Repeat Customer Rate          |             **3.1%** |

---

## 🎯 Business Questions

The analysis investigates five major business domains:

* 📈 Sales & Revenue Performance
* 🛍️ Product & Seller Performance
* 🚚 Logistics & Delivery Efficiency
* 👥 Customer Behavior & Retention
* 📊 Customer Satisfaction & Statistical Validation

The notebook contains **10 detailed business questions**, each accompanied by analytical findings, visualizations, statistical validation (where applicable), business insights, and strategic recommendations.

---

## 🔍 Key Business Insights

* Revenue experienced rapid growth throughout **2017**, peaking during **Black Friday (November 2017)** with a **52.1% month-over-month increase** to **R$1.01 million**, before plateauing at R$950K–1M/month throughout early-to-mid 2018.
* **Health & Beauty**, **Watches & Gifts**, and **Bed, Bath & Table** generated the highest revenue. **Office Furniture** stood out as a red flag: despite solid volume (**R$273,960** revenue, **1,273 orders**), it scored only **3.49/5.0** in customer reviews — making it the **#1 priority for quality/vendor audit**. A meaningful share of revenue (**R$185,050**) also came from products with an unlabeled `unknown` category, pointing to a data quality gap at the source that limits category-level visibility.
* **São Paulo (SP)** contributed **38.3%** of total revenue while maintaining the fastest average delivery time (**8.26 days**). Conversely, **Rio de Janeiro (RJ)** — the #2 revenue contributor — averaged **14.69 days**, nearly double SP's despite its geographic proximity, pointing to localized logistics inefficiency rather than distance alone.
* Delivery delays had a **statistically significant negative impact** on customer satisfaction (review score **4.21 on-time vs. 2.26 late**, **Mann–Whitney U Test, p < 0.000001**), confirming that logistics performance directly influences review scores. This was cross-validated with an independent t-test, ANOVA (across product categories), and a Chi-Square test (delay vs. repeat-customer status).
* RFM segmentation of 95,420 customers identified **Potential Loyalists (34.4%)** as the largest segment, followed by Loyal Customers (33.3%) and Champions (16.0%) — highlighting where retention campaigns would have the most realistic impact.
* Cohort analysis revealed month-one retention near 0% across almost every cohort, consistent with the overall **3.1% repeat customer rate** — the marketplace relies heavily on continuous new customer acquisition rather than repeat purchases.
* The top **20% of sellers generated 82.7% of total revenue** (a strong Pareto pattern), revealing real business concentration risk — alongside a subset of active sellers with review scores as low as 1.26 and late rates up to 50%, posing reputational risk.

Detailed strategic recommendations are provided in the final section of the notebook.

---

## 🗂️ Dataset

The project uses the **Brazilian E-Commerce Public Dataset by Olist**, containing more than **100,000 orders** distributed across eight relational tables:

* Customers
* Orders
* Order Items
* Products
* Sellers
* Payments
* Reviews
* Product Category Translation

The raw tables are integrated into a centralized analytical dataset (`fact_ecommerce_sales`) before further analysis.

---

## 🛠️ Technologies Used

**Programming & Analysis**

* Python
* Pandas
* NumPy

**Visualization**

* Matplotlib
* Seaborn

**Statistics**

* SciPy
* Mann–Whitney U Test
* Independent t-test
* ANOVA
* Chi-Square Test

**Machine Learning**

* Scikit-learn
* StandardScaler
* K-Means Clustering (Elbow Method for optimal *k*)

**Development**

* Jupyter Notebook

---

## 💼 Skills Demonstrated

* Business Intelligence
* Data Cleaning & Wrangling
* Data Integration
* Feature Engineering
* Exploratory Data Analysis (EDA)
* KPI Development
* Customer Segmentation (RFM)
* K-Means Clustering
* Cohort & Retention Analysis
* Seller Performance & Pareto Analysis
* Statistical Hypothesis Testing
* Business Insight Generation
* Strategic Recommendation
* Star Schema Modeling for BI Tools

---

## 📁 Repository Structure

```text
.
├── E_Commerce_Business_Intelligence.ipynb   # Main notebook (end-to-end analysis)
├── data_e-commerse/                         # Raw dataset (download from Kaggle)
│   ├── olist_customers_dataset.csv
│   ├── olist_orders_dataset.csv
│   ├── olist_order_items_dataset.csv
│   ├── olist_products_dataset.csv
│   ├── olist_order_payments_dataset.csv
│   ├── olist_order_reviews_dataset.csv
│   ├── olist_sellers_dataset.csv
│   └── product_category_name_translation.csv
├── data/
│   └── processed/                           # Auto-generated analysis outputs
│       ├── fact_ecommerce_sales.csv
│       ├── monthly_revenue_trend.csv
│       ├── category_performance.csv
│       ├── geo_performance.csv
│       ├── seller_performance.csv
│       ├── customer_rfm_segments.csv
│       ├── cohort_retention_matrix.csv
│       ├── monthly_new_vs_returning.csv
│       ├── seller_quadrant_matrix.csv
│       ├── dim_date.csv
│       ├── dim_customer.csv
│       ├── dim_product.csv
│       ├── dim_seller.csv
│       └── fact_sales.csv                   # Star schema fact table (BI-ready)
└── README.md
```

---

## ▶️ Getting Started

1. Clone this repository.
2. Download the **Olist Brazilian E-Commerce Public Dataset** from Kaggle.
3. Place the raw CSV files inside the `data_e-commerse/` directory, or point the notebook to a custom location via an environment variable:
   ```bash
   export OLIST_DATA_PATH=/path/to/dataset
   ```
4. Install the required Python libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter
   ```
5. Run the notebook using Jupyter Notebook or Visual Studio Code:
   ```bash
   jupyter notebook E_Commerce_Business_Intelligence.ipynb
   ```

The notebook automatically exports processed datasets, aggregated tables, and star schema tables into `data/processed/`, making them ready for visualization using Power BI, Tableau, or Looker Studio.

---

## 📌 Limitations

* The dataset covers **2016–2018** (with partial data in the earliest months), so findings may not represent current marketplace conditions.
* Geographic information is available only at the **state** level, limiting the precision of logistics recommendations.
* Customer reviews are analyzed using numerical scores only; the `review_comment_message` text field (58.7% filled) is not yet leveraged for sentiment analysis.
* RFM segmentation and clustering are based on a historical snapshot rather than a real-time, continuously refreshed pipeline.
* The unusually low 3.1% repeat customer rate could be partly influenced by limitations in how `customer_unique_id` is matched in this public dataset — worth confirming with the data source team if replicated in a production environment.

---

## 🚀 Future Improvements

* Portuguese review sentiment analysis using NLP on `review_comment_message`.
* Machine learning models for customer churn prediction and delivery delay prediction.
* Monthly revenue forecasting (Prophet/ARIMA) leveraging the identified November seasonal spike.
* Interactive BI dashboard (Power BI, Tableau, or Streamlit) auto-refreshed from `fact_ecommerce_sales.csv` and the star schema tables, with filters by state, category, and RFM segment.

---

## 📄 License

This repository is intended for educational purposes and portfolio demonstration. The original dataset is publicly available through Kaggle under the Olist Brazilian E-Commerce Public Dataset.

---

> **This project was developed as a portfolio case study to demonstrate an end-to-end Business Intelligence workflow, emphasizing reproducible data analysis, transparent preprocessing decisions, statistical validation, and actionable business recommendations.**
