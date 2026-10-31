# 🛒 E-commerce & Retail Analytics

### Brazilian E-Commerce Public Dataset by Olist \| End-to-End Data Analytics Project

![Python](https://img.shields.io/badge/Python-Pandas-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Analysis-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
![Power
BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=flat&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-Data%20Analysis-217346?style=flat&logo=microsoftexcel&logoColor=white)

> An end-to-end analysis of e-commerce revenue, product categories,
> seller activity, delivery performance, freight costs, and customer
> review scores using Olist's original Brazilian E-Commerce Public
> Dataset.

------------------------------------------------------------------------

## 📌 Project Overview

This project examines the commercial and operational performance of
Olist, a Brazilian e-commerce marketplace. It combines order,
order-item, product, seller, payment, customer, delivery, and review
data to identify revenue drivers and operational issues that may affect
customer experience.

The analysis focuses on five business areas:

-   Revenue performance by product category, seller, and customer state
-   Delivery performance against estimated delivery dates
-   Relationship between delivery delays and customer review scores
-   Freight costs across orders and product categories
-   Business priorities supported by measurable findings

### Dataset at a Glance

The original Olist dataset contains approximately 100,000 orders placed
between 2016 and 2018. The source files are relational: one order can
contain multiple items, sellers, payment records, and review records.

  Dataset                             Records
  ------------------------------- -----------
  Orders                               99,441
  Customers                            99,441
  Order items                         112,650
  Payments                            103,886
  Reviews                              99,224
  Products                             32,951
  Sellers                               3,095
  Geolocation records               1,000,163
  Product category translations            71

### Dataset-Level Business Snapshot

  Metric                                 Observed result
  ------------------------- ----------------------------
  Product sales value                        \~R\$13.59M
  Freight value                               \~R\$2.25M
  Product + freight value                    \~R\$15.84M
  Delivered orders                                96,478
  Total orders                                    99,441
  Highest-revenue month       November 2017 (\~R\$1.18M)

*Financial values are in Brazilian reais (BRL). Revenue figures refer to
item price and freight values in the source data; they should not be
interpreted as accounting profit.*

------------------------------------------------------------------------

## 🎯 Business Problem

An e-commerce business needs to grow sales while maintaining reliable
delivery, manageable freight costs, and positive customer experiences.
Overall revenue alone cannot show which categories and sellers drive
performance or where fulfillment problems may be damaging customer
feedback.

This project investigates the following business questions:

1.  Which product categories generate the highest sales?
2.  Which sellers and customer states contribute most to sales?
3.  How frequently do delivered orders arrive after the estimated
    delivery date?
4.  How do customer review scores differ between on-time and late
    deliveries?
5.  How significant are freight costs in relation to product sales, and
    which segments warrant further review?

The analysis distinguishes order-level measures from item-level measures
to avoid inflating order counts or duplicating values when tables are
joined.

------------------------------------------------------------------------

## 💡 Recommendations

The following actions are based on patterns reported from the original
Olist dataset. They are investigation priorities, not proof of
causation.

### 1. Treat delivery reliability as a customer-experience priority

An independent analysis of the original dataset reports an average
review score of approximately **4.29** for on-time deliveries and
**2.57** for late deliveries.

**Recommended action:** - Monitor on-time delivery performance by seller
state, customer state, and product category. - Investigate the
seller--region combinations associated with recurring delays. - Review
dispatch timing, carrier hand-offs, and estimated delivery promises for
affected segments. - Track review scores alongside delivery performance
after operational changes.

### 2. Protect performance in the highest-revenue categories

The leading product categories by sales include **Health & Beauty,
Watches & Gifts, Bed & Bath Table, Sports & Leisure, and Computers &
Accessories**.

**Recommended action:** - Monitor sales, order volume, freight value,
and review scores for these categories together. - Prioritize stock
availability and fulfillment monitoring for categories with high sales
volume. - Investigate whether high freight costs or delivery delays are
concentrated in particular categories.

### 3. Investigate freight costs as a separate operational measure

The dataset contains approximately **R\$2.25M** in freight value against
approximately **R\$13.59M** in product sales value.

**Recommended action:** - Track freight value and
freight-to-product-price ratio by category, seller, and destination
state. - Identify segments where freight represents a relatively high
share of the item price. - Review package dimensions, shipment
consolidation opportunities, and carrier pricing before changing
shipping policies.

### 4. Use regional concentration to guide seller and logistics reviews

Customer and seller activity is strongly concentrated in **São Paulo
(SP)** in the dataset.

**Recommended action:** - Monitor São Paulo separately while retaining a
state-by-state comparison. - Compare sales concentration with delivery
performance and review scores. - Investigate whether other states have
lower sales because of demand, seller coverage, or fulfillment
constraints; do not assume the cause from sales totals alone.

### 5. Use November 2017 as a historical peak-period reference

November 2017 is the highest-revenue month in the dataset, at
approximately **R\$1.18M**.

**Recommended action:** - Review order volume, category mix, freight
value, and delivery performance around this period. - Use the peak as a
historical planning reference, not as a forecast of current demand. -
Assess whether promotional or seasonal demand coincided with changes in
fulfillment performance.

------------------------------------------------------------------------

## 🔎 Key Findings

### Revenue and category performance

-   Product sales value is approximately **R\$13.59M**.
-   The leading sales categories include Health & Beauty, Watches &
    Gifts, Bed & Bath Table, Sports & Leisure, and Computers &
    Accessories.
-   November 2017 is the strongest month by reported revenue, at
    approximately **R\$1.18M**.

### Delivery and customer experience

-   The source contains **99,441 orders**, of which **96,478** are
    recorded as delivered.
-   Reported average review scores are approximately **4.29** for
    on-time deliveries and **2.57** for late deliveries.
-   This difference is an association in historical data; it does not
    establish that delivery delay alone caused lower review scores.

### Freight

-   Freight value totals approximately **R\$2.25M** compared with
    approximately **R\$13.59M** in product sales value.
-   Freight should therefore be monitored alongside sales rather than
    treated as an incidental field.

### Geographic performance

-   Customer and seller activity is concentrated in São Paulo (SP).
-   State-level comparisons should consider sales volume, delivery
    performance, and customer feedback together.

------------------------------------------------------------------------

## 🔄 Project Workflow

``` text
Business Problem Definition
          ↓
Dataset Understanding
          ↓
Data Quality Assessment
          ↓
Data Cleaning & Preparation
          ↓
Exploratory Data Analysis (EDA)
          ↓
SQL Business Analysis
          ↓
Delivery & Customer Experience Investigation
          ↓
Power BI Dashboard
          ↓
Evidence-Based Recommendations
```

### 1. Dataset Understanding

-   Inspect the nine original CSV files, their columns, data types, and
    row counts.
-   Identify the grain of each table: order, order item, payment,
    review, product, seller, or customer.
-   Map table relationships using their keys.

### 2. Data Quality Assessment

-   Check missing values, duplicate keys, and invalid timestamps.
-   Review order statuses and delivery-date completeness.
-   Validate relationships before combining tables.
-   Translate Portuguese product category names using the supplied
    translation table.

### 3. Data Cleaning & Preparation

-   Convert date/time fields to datetime and financial fields to numeric
    types.
-   Derive delivery duration and a late-delivery flag by comparing
    actual delivery date with estimated delivery date.
-   Keep order-level and item-level datasets at their correct grains.
-   Aggregate payment and review data to the required order-level grain
    before joining to item-level data when necessary.

### 4. Exploratory Data Analysis

-   Analyze monthly sales and category performance.
-   Compare sales by seller and customer state.
-   Examine delivery status, delivery duration, and freight value.
-   Compare review-score distributions across delivery groups.

### 5. SQL Business Analysis

Use SQL to calculate revenue, order counts, average order value,
delivery measures, freight metrics, and category/seller/region
comparisons.

### 6. Root Cause Investigation

Drill into categories, sellers, and destination states with weaker
delivery or review performance. Treat these as areas for investigation
rather than confirmed causes.

### 7. Power BI Dashboard

Present executive KPIs and interactive breakdowns for revenue, product
categories, seller and state performance, delivery reliability, freight,
and customer reviews.

### 8. Recommendations

Convert validated patterns into prioritized actions for sales
monitoring, fulfillment review, freight-cost investigation, and
customer-experience improvement.

------------------------------------------------------------------------

## 🧰 Tools & Technologies

  -----------------------------------------------------------------------
  Tool                                Purpose
  ----------------------------------- -----------------------------------
  **Python**                          Data preparation and analysis

  **Pandas**                          Data cleaning, transformation,
                                      joins, and aggregation

  **SQL Server**                      Relational queries, KPI
                                      calculations, and business analysis

  **Excel**                           Data inspection and supplementary
                                      analysis

  **Power BI**                        Interactive dashboards and business
                                      reporting

  **Jupyter Notebook**                Exploratory analysis and
                                      documentation
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 📊 Power BI Dashboard

The dashboard is organized around business decisions rather than
standalone charts.

### Executive Overview

-   Total orders
-   Product sales value
-   Freight value
-   Average order value
-   Delivered-order percentage

### Sales Performance

-   Monthly sales trend
-   Sales by product category
-   Sales by seller
-   Sales by customer state

### Delivery Performance

-   Late-delivery percentage
-   Actual versus estimated delivery time
-   Delivery performance by seller and destination state
-   Order status distribution

### Customer Experience

-   Average review score
-   Review-score distribution
-   Review scores by delivery status
-   Review performance by category and region

### Freight Analysis

-   Total freight value
-   Freight-to-product-price ratio
-   Freight by category, seller, and destination state

------------------------------------------------------------------------

## 🗂️ Project Structure

``` text
ecommerce-retail-analytics/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── ecommerce_retail_analysis.ipynb
│
├── sql/
│   └── ecommerce_retail_analysis.sql
│
├── powerbi/
│   └── ecommerce_retail_dashboard.pbix
│
├── images/
│   └── dashboard-screenshot.png
│
└── README.md
```

------------------------------------------------------------------------

## 📁 Dataset Source

**Brazilian E-Commerce Public Dataset by Olist**

-   [Original dataset on
    Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
-   Coverage: orders placed from 2016 to 2018
-   Provider: Olist
-   License: **CC BY-NC-SA 4.0**

The dataset is anonymized. Store and partner names in review text were
replaced by fictional names. Refer to the original Kaggle dataset page
for the complete data description and license terms.

------------------------------------------------------------------------

## ⚠️ Data & Methodology Notes

-   The source tables have different grains. `order_items` contains
    multiple rows per order; summing order counts after joining it
    directly to orders can overcount orders.
-   Payment and review tables can also contain multiple records per
    order. Aggregate them to the intended grain before joining to avoid
    multiplying sales or freight values.
-   Product sales are based on item `price`; freight is recorded
    separately in `freight_value`. Neither should be described as net
    profit.
-   Delivery performance should be calculated only for orders with valid
    actual and estimated delivery timestamps. Canceled, unavailable, and
    undelivered orders should not be silently classified as late or on
    time.
-   Review scores are customer-submitted ratings and may not exist for
    every order. State the review coverage used in any review-score KPI.
-   The dataset is historical and anonymized. Its results should not be
    presented as current Olist operating performance.
-   Reported category and delivery-score comparisons are descriptive.
    They do not establish causality.

------------------------------------------------------------------------

## 👤 Author

**Habibur Rahaman**\
Aspiring Data Analyst \| SQL • Python • Pandas • Excel • Power BI

-   [LinkedIn](https://www.linkedin.com/in/habiburrahamankolkata)
-   [GitHub
    Portfolio](https://github.com/habibur-rahaman-data-analytics)

------------------------------------------------------------------------

*This project demonstrates an end-to-end analytics workflow: translating
business questions into data preparation, SQL analysis, exploratory
investigation, dashboard reporting, and practical recommendations.*
