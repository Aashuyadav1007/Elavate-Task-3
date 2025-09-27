# Elavate-Task-3

E-commerce Sales Data Analysis & Visualization
This project encompasses the end-to-end process of data analysis, starting with raw sales data, transforming it using MySQL for key insights, and culminating in interactive dashboards built in Power BI.

1. Data Source and Schema
The foundation of this project is the ecommerce_sales.csv file, which is analyzed using a single MySQL table named ecommerce_sales.

Table: ecommerce_sales (Inferred Schema)
Column Name

Data Type

Key Analysis Role

order_id

VARCHAR(10)

Primary identifier for transactions.

customer_id

VARCHAR(10)

Used for customer segmentation and retention analysis.

category

VARCHAR(50)

Crucial for grouping revenue and profit performance.

price

DECIMAL(10, 2)

Unit price.

discount

DECIMAL(4, 2)

Impact of promotions.

quantity

INT

Volume of sales.

payment_method

VARCHAR(50)

Analysis of payment type popularity/efficiency.

total_amount

DECIMAL(10, 2)

Key metric for calculating revenue.

profit_margin

DECIMAL(10, 2)

Key metric for profitability analysis.

customer_age

INT

Used for demographic filtering.

2. SQL Analysis (ecommerce_analysis.sql)
The SQL script contains structured queries designed to extract specific business intelligence from the data.

Key Analysis Functions
SQL Technique

Query Goal

Business Insight

Aggregation (SUM, AVG)

Calculate Total Revenue and Average Profit per category (Query 1).

Identify top-performing product lines and overall profitability.

Filtering/Ordering

Identify the top 10 most profitable orders from younger customers (Query 2).

Target marketing efforts based on high-value youth segments.

Self-Join

Find customers who bought items from both 'Electronics' and 'Fashion' (Query 3).

Identify cross-category buying habits for bundle promotions.

Subquery

Flag orders where sales are above the local regional average (Query 5).

Isolate sales that are performing exceptionally well relative to their geography.

View Creation

Create a persistent view for 'High-Value, High-Profit' orders (Query 6).

Provide a simplified data source for executive-level dashboards.

Optimization
To ensure efficient query execution, indexes were created on frequently used columns:

CREATE INDEX idx_category ON ecommerce_sales(category);
CREATE INDEX idx_customer_id ON ecommerce_sales(customer_id);

3. Data Visualization (Project 2.pbix)
The Project 2.pbix file is a Microsoft Power BI report containing interactive dashboards built using the insights derived from the SQL queries.

Software Required: Microsoft Power BI Desktop.

Purpose: To transform the numerical results from the SQL analysis into visual, interactive reports that business stakeholders can easily consume.

Expected Content: The report likely includes visualizations for:

Time-series trends (sales over time).

Geographical sales distribution (using the region data).

Profitability comparisons by category and payment_method.

4. Getting Started
Database: Load the ecommerce_sales.csv data into a MySQL database and execute the ecommerce_analysis.sql script to set up the schema, indexes, and analytical views.

Visualization: Open the Project 2.pbix file in Power BI Desktop to explore the interactive dashboards. You may need to refresh the data connection if it's linked directly to your local database instance.
