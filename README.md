# Customer-Shopping-Behavior


**Overview**

This project simulates an end-to-end, corporate-grade data analytics workflow to transform raw transactional data into strategic business intelligence. Using a dataset of 3,900 purchase records across multiple product categories, the work encompassed data preparation and validation in Python, analytical querying and business-logic simulation in PostgreSQL, interactive visualization with Power BI, and a concise set of business recommendations. The objective is to demonstrate technical proficiency (data engineering, analytical SQL, and visualization) while producing actionable insights that support subscription growth, margin management, and targeted marketing.


**Project Objectives**

- Produce a clean, structured dataset suitable for analytical and reporting workloads.
- Explore customer behavior to identify high-value segments, purchase drivers, and conversion patterns.
- Use SQL-based business-transaction simulations to quantify revenue drivers and segment performance.
- Build an interactive Power BI dashboard to communicate findings to stakeholders.
- Formulate evidence-based business recommendations to increase retention, optimize discounts, and improve product positioning.



**Deliverables**

- Cleaned and documented dataset (PostgreSQL-ready).
- Python scripts/notebooks for data preparation and EDA.
- A set of SQL queries implementing business questions and KPIs.
- Power BI dashboard with interactive visuals and filters.
- Project report and short stakeholder presentation summarizing insights and recommendations.


**Methodology**
1. Data Preparation (Python)

- Ingestion & Profiling: Loaded raw data with pandas. Used df.info() and df.describe() to capture schema, datatypes, and distributional summaries.
- Cleaning: Normalized column names to snake_case for reproducibility and code readability. Removed redundant columns after a consistency check (e.g., promo_code_used removed when redundant with discount_applied). Handled nulls in review_rating by imputing the median rating within product categories to preserve within-category comparability.
- Date & Frequency Engineering: Extracted purchase timestamps and derived purchase_frequency_days to represent recency/frequency for each customer.
- Categorical Binning: Created age_group buckets to support cohort-level revenue analysis.
- Data Validation: Performed sanity checks (revenue totals, negative amounts, duplicate records) before loading into PostgreSQL.

2. Feature Engineering & Enrichment

- Customer Segments: Classified customers into new, returning, and loyal based on thresholds for previous_purchases.
- Discount Sensitivity Flag: Derived a boolean discount_dependent if the share of purchases with discounts for a product exceeded a threshold.
- Subscription Indicator: Standardized subscription status and computed per-customer lifetime value proxies (average spend, total revenue, purchase frequency).

3. Analytical Modeling (SQL in PostgreSQL)

- Implemented production-like SQL queries to answer business questions including:
- Revenue split by gender and by age_group.
- Identification of high-spending customers who still use discounts (segmentation for margin analysis).
- Top-rated products and top-selling SKUs by category.
- Shipping-type comparisons (Standard vs Express) on average order value and frequency.
- Subscriber vs Non-subscriber behavioral comparisons (average order value, retention proxies).
- Discount-dependent products and percentage of discounted transactions by SKU.
- Repeat buyers analysis: correlation between purchase count (>5) and subscription propensity.

4. Visualization & Dashboarding (Power BI)

Designed an interactive dashboard focused on stakeholder-readiness, including: KPI cards (Total Revenue, AOV, Subscriber Revenue Share), time-series revenue trends, cohort funnel for New → Returning → Loyal customers, SKU-level heatmaps for discount-share and average rating, and drill-through capability to view customer-level transactions.
