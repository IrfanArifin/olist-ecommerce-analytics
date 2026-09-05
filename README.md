# 📊 Olist E-Commerce Analytics: End-to-End Business & Logistics Performance

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-CC292B?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Business Questions Addressed](#-business-questions-addressed)
- [Tools & Technologies](#-tools--technologies)
- [Dataset Architecture](#-dataset-architecture)
- [Data Analytics Workflow](#-data-analytics-workflow)
- [Data Modeling (Star Schema)](#-data-modeling-star-schema)
- [Interactive Power BI Dashboard](#-interactive-power-bi-dashboard)
- [Key Business Insights](#-key-business-insights)
- [Strategic Business Recommendations](#-strategic-business-recommendations)
- [Repository Structure](#-repository-structure)
- [How to Reproduce](#-how-to-reproduce)

---

## 🛠️ Project Overview

This project analyzes the **Olist Brazilian E-Commerce Dataset** to evaluate commercial performance, customer purchasing behavior, product category dynamics, logistics efficiency, customer satisfaction, and seller ecosystem health.

The project demonstrates a complete, production-grade **Data Analytics Workflow**—transitioning from data quality validation and analytical querying in **PostgreSQL** to data modeling and interactive business intelligence dashboard development in **Power BI**.

The primary objective is to translate ~100,000 raw transactional records into actionable, data-backed strategic recommendations for key business stakeholders.

---

## ❓ Business Questions Addressed

The analysis addresses **26 core business questions (Q1–Q26)** categorized into 5 critical operational domains:

<details>
<summary><b>1. Sales & Revenue Performance</b></summary>

* How much total revenue was generated across the platform?
* How does revenue fluctuate over time (monthly/quarterly trends)?
* How many orders were placed, and what is the platform's Average Order Value (AOV)?
* Which Brazilian states generate the highest revenue?
</details>

<details>
<summary><b>2. Customer Behavior & Retention</b></summary>

* How many unique customers are registered on the platform?
* What is the customer repeat purchase rate?
* What is the average revenue generated per customer?
* Who are the highest-value customers?
* Which states hold the highest concentration of customers?
</details>

<details>
<summary><b>3. Product Category Dynamics</b></summary>

* Which product categories generate the highest revenue?
* Which product categories drive the highest sales volume?
* What are the top-performing individual products by revenue and volume?
* Which categories appear most frequently in order baskets?
</details>

<details>
<summary><b>4. Delivery & Customer Satisfaction</b></summary>

* What is the average order delivery lead time across Brazil?
* What percentage of orders suffer from late delivery?
* Which Brazilian states experience the highest late-delivery rates?
* How severely does late delivery impact customer review scores?
* What is the overall distribution of review scores across product categories?
</details>

<details>
<summary><b>5. Seller Ecosystem & Supply Health</b></summary>

* How many total and active sellers operate on Olist?
* What is the average revenue generated per active seller?
* How has active seller growth evolved relative to order growth over time?
* Who are the top-performing sellers on the platform?
* How are sellers geographically distributed, and how do their rating tiers perform?
</details>

---

## 🧰 Tools & Technologies

* **PostgreSQL & pgAdmin 4**: Relational database storage, data quality checks, data cleaning, complex aggregation queries (CTE, Window Functions, Joins), and analytical view creation.
* **Power BI Desktop**: Data transformation (Power Query), Star Schema data modeling, DAX measure creation, and interactive visual dashboard development.
* **DAX (Data Analysis Expressions)**: Custom time-intelligence metrics, KPI cards, dynamic filters, and performance aggregations.
* **Git & GitHub**: Project documentation, query version control, and portfolio presentation.

---

## 📁 Dataset Architecture

The analysis utilizes the **Olist Brazilian E-Commerce Public Dataset** sourced from Kaggle. It contains real commercial data of ~100,000 orders placed between 2016 and 2018 across marketplaces in Brazil.

The raw database consists of **9 relational tables**:
1. `olist_customers_dataset`
2. `olist_geolocation_dataset`
3. `olist_order_items_dataset`
4. `olist_order_payments_dataset`
5. `olist_order_reviews_dataset`
6. `olist_orders_dataset`
7. `olist_products_dataset`
8. `olist_sellers_dataset`
9. `product_category_name_translation`

> **Note:** Raw CSV datasets are excluded from this repository due to file size constraints. You can access the official dataset here: [Olist Brazilian E-Commerce Dataset on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

---

## 🔄 Data Analytics Workflow

```text
Raw E-Commerce Dataset (Kaggle)
             │
             ▼
Data Quality & Integrity Check (PostgreSQL)
             │
             ▼
PostgreSQL Database Storage
             │
             ▼
SQL Business Analysis (26 Analytical Queries)
             │
             ▼
Query Validation & Logic Deduplication
             │
             ▼
Analytical Views Creation (SQL Views)
             │
             ▼
Star Schema Data Modeling (Power BI)
             │
             ▼
Interactive Dashboard & DAX Development
             │
             ▼
Business Insights & Strategic Recommendations

## 📐 Data Modeling (Star Schema)

Rather than directly importing 9 unoptimized relational tables into Power BI, an **analytical Star Schema** was designed. Data was pre-aggregated and structured using dedicated SQL views (`08_create_star_schema_views.sql`) to optimize reporting performance and measure calculations.

<img width="731" height="578" alt="image" src="https://github.com/user-attachments/assets/a8096fea-e832-460a-a554-573c7f7ea993" />

* **`Fact_Sales`**: Central transactional fact table containing order items, item prices, freight costs, payment values, delivery performance metrics, and review scores.
* **`Dim_Customers`**: Customer attributes, unique IDs, and geographic locations (city, state).
* **`Dim_Products`**: Product IDs, translated product categories, and physical measurements.
* **`Dim_Sellers`**: Seller IDs, locations, and historical performance tiers.
* **`Dim_Date`**: Comprehensive calendar table enabling seamless time-intelligence DAX calculations.

## 💻 Interactive Power BI Dashboard

The dashboard consists of 4 specialized analytical pages:

### Page 1 — Executive Overview
High-level executive summary tracking platform health and top-line commercial metrics.
* **Key Focus**: Total Revenue, Total Orders, Total Unique Customers, Average Order Value (AOV), Average Review Score, Revenue Trends over Time, and Revenue Breakdown by State.
* **Preview**: `screenshots/executive-overview.png`

<img width="1432" height="805" alt="image" src="https://github.com/user-attachments/assets/3d0fdb14-90e6-4616-a34f-cd093662c4eb" />


---

### Page 2 — Customer & Product
Deep dive into customer demographics, retention characteristics, and product category drivers.
* **Key Focus**: Customer Geographic Distribution, Repeat Purchase Rate, Customer Spend Segments, Top Categories by Revenue vs. Volume, and Basket Analysis.
* **Preview**: `screenshots/customer-product.png`

<img width="1431" height="805" alt="image" src="https://github.com/user-attachments/assets/c9369da5-8fc7-4c23-b3d1-187c3625cd61" />


---

### Page 3 — Seller Ecosystem Health
Analysis of marketplace seller supply, productivity, and regional density.
* **Key Focus**: Total Sellers, Active Seller Growth, Revenue per Active Seller, Top Performing Sellers, Seller Geographical Density, and Seller Rating Tier Breakdown.
* **Preview**: `screenshots/seller-analysis.png`

<img width="1431" height="802" alt="image" src="https://github.com/user-attachments/assets/bc19d4ca-e7aa-4174-9222-b046a6be8e53" />

---

### Page 4 — Delivery & Customer Satisfaction Performance
Operational analysis evaluating supply chain efficiency and its direct impact on customer feedback.
* **Key Focus**: Average Lead Time (Days), Late Delivery Rate (%), Regional Delivery Bottlenecks, Review Score Comparison (On-Time vs. Late Deliveries), and Category Satisfaction Distribution.
* **Preview**: `screenshots/delivery-satisfaction.png`

<img width="1432" height="798" alt="image" src="https://github.com/user-attachments/assets/063e6638-46b3-42c5-b303-f9a957866edf" />


---



## 💡 Key Business Insights

### 1. Severe Revenue Concentration in Primary States
* **São Paulo (SP)** alone accounts for approximately **38%** of total platform revenue.
* The top 3 states (**São Paulo, Rio de Janeiro, and Minas Gerais**) collectively generate roughly **63%** of overall revenue.
* **Business Implication**: Olist's revenue streams are heavily reliant on Southeastern Brazil, leaving the platform vulnerable to regional market shifts or localized supply chain bottlenecks.

### 2. Critically Low Customer Retention
* The overall customer repeat purchase rate is approximately **3%**.
* Over **97%** of customers complete only a single transaction on the platform.
* **Business Implication**: Platform growth is overwhelmingly driven by continuous acquisition of new users rather than customer retention, indicating an opportunity to increase Customer Lifetime Value (CLV).

### 3. Direct Link Between Delivery Delays and Customer Satisfaction
* **On-Time Deliveries**: Average Review Score = **4.29 / 5.00**
* **Late Deliveries**: Average Review Score = **2.57 / 5.00**
* **Insight**: Delays cause a sharp drop of **1.72 rating points**, making delivery punctuality one of the single largest drivers of customer review scores.

### 4. Seller Supply Growth Outpaces Order Volume
* The count of active sellers grew significantly throughout 2018, but total order volume did not scale at a matching rate.
* **Insight**: Average **orders per active seller declined**, pointing to heightened intra-marketplace competition and potential seller revenue dilution.

### 5. Extreme Seller Geographic Bottleneck
* Approximately **60% of all registered sellers** operate from the state of **São Paulo (SP)**.
* **Business Implication**: This heavy seller concentration increases long-distance shipping lead times and freight costs when fulfilling orders to Northern and Northeastern regions.

---

## 🎯 Strategic Business Recommendations

1. **Improve Delivery Performance & Logistics Optimization**
   * Prioritize logistical infrastructure and regional carrier partnerships in states with high late-delivery rates (e.g., Alagoas, Maranhão).
   * Establish late-delivery rate as a primary operational KPI for supply chain teams.

2. **Increase Customer Retention & Lifetime Value**
   * Launch automated post-purchase marketing campaigns and loyalty incentives to encourage repeat purchases within 30–60 days.
   * Introduce purchase subscriptions or automated re-order reminders for high-frequency consumable categories.

3. **Expand Regional Seller Coverage Outside Major Hubs**
   * Actively recruit and onboard sellers in Northern, Northeastern, and Southern states to shorten regional fulfillment distances.
   * Target regions displaying high customer demand but low local seller representation.

4. **Monitor and Maintain Seller Productivity**
   * Track "Orders per Active Seller" as a standard marketplace health metric.
   * Balance seller recruitment with demand generation to protect average seller profitability and reduce seller churn.

5. **Reduce Geographic Concentration Risk**
   * Run targeted marketing campaigns to increase customer penetration beyond SP, RJ, and MG.
   * Offer regional freight subsidies to incentivize cross-state purchasing.

## 📂 Repository Structure

```text
olist-ecommerce-analytics/
│
├── README.md                              # Main portfolio documentation
│
├── data/
│   └── README.md                          # Dataset details and download source link
│
├── sql/
│   ├── 01_data_quality.sql                # Data cleaning and integrity checks
│   ├── 02_sales_performance.sql           # Revenue, orders, and AOV queries
│   ├── 03_customer_analysis.sql           # Customer demographics and retention queries
│   ├── 04_product_analysis.sql            # Category and product performance queries
│   ├── 05_delivery_analysis.sql           # Logistics and late delivery analysis
│   ├── 06_review_analysis.sql             # Satisfaction and review score queries
│   ├── 07_seller_analysis.sql             # Seller productivity and supply queries
│   └── 08_create_star_schema_views.sql    # SQL views for Power BI Star Schema
│
├── powerbi/
│   └── Olist_Ecommerce_Analytics.pbix     # Interactive Power BI dashboard file
│
├── screenshots/
│   ├── executive-overview.png             # Page 1 preview image
│   ├── customer-product.png               # Page 2 preview image
│   ├── delivery-satisfaction.png          # Page 3 preview image
│   └── seller-analysis.png                # Page 4 preview image
│
└── documentation/
    └── data-model.png                     # Star Schema architecture diagram

    ## 🚀 How to Reproduce

1. **Database Setup**:
   * Download the dataset from [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).
   * Create a local database named `olist_db` in **PostgreSQL**.
   * Import all CSV files into their corresponding PostgreSQL tables.

2. **Execute SQL Queries**:
   * Run scripts `01_data_quality.sql` through `07_seller_analysis.sql` in pgAdmin to explore business metrics.
   * Run `08_create_star_schema_views.sql` to generate the analytical database views.

3. **Power BI Setup**:
   * Open `powerbi/Olist_Ecommerce_Analytics.pbix` using **Power BI Desktop**.
   * Update the PostgreSQL data source settings to connect to your local database credentials.
   * Refresh the data model to populate all dashboard pages and DAX metrics.
