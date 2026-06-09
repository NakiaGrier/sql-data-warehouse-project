## Overview 

This folder contains SQL scripts focused on deeper analysis of the gold layer in a sales data warehouse. The goal is to move beyond basic exploration and use advanced SQL techniques to analyze trends, cumulative performance, product behavior, customer segments, and category contributions.

These scripts help show how data can be transformed into insights that support business performance tracking and decision-making.

---

## Scripts Description 

### `01_change_over_time_analysis.sql`

* **Purpose**: Tracks how key metrics change across time periods.
* **Queries**:

  * Analyzes monthly sales, customer count, and quantity sold.
  * Uses date functions such as `YEAR()`, `MONTH()`, `DATETRUNC()`, and `FORMAT()`.
  * Helps identify trends, seasonality, and changes in performance over time.

### `02_cumulative_analysis.sql`

* **Purpose**: Calculates running totals and moving averages over time.
* **Queries**:

  * Aggregates sales and average price by year.
  * Calculates running total sales using `SUM() OVER()`.
  * Calculates moving average price using `AVG() OVER()`.

### `03_performance_analysis.sql`

* **Purpose**: Compares product performance across different years.
* **Queries**:

  * Calculates yearly sales by product.
  * Compares each product’s sales against its average sales.
  * Uses `LAG()` to compare current sales to the previous year.

### `04_data_segmentation_analysis.sql`

* **Purpose**: Groups products and customers into meaningful segments.
* **Queries**:

  * Segments products by cost range.
  * Segments customers as VIP, Regular, or New based on lifespan and spending.
  * Uses `CASE` logic to create custom business categories.

### `05_part_to_whole_analysis.sql`

* **Purpose**: Shows how each category contributes to total sales.
* **Queries**:

  * Calculates total sales by product category.
  * Calculates overall sales using `SUM() OVER()`.
  * Finds each category’s percentage contribution to total sales.

---

## Key SQL Concepts Used 

* **Date Functions**: `YEAR()`, `MONTH()`, `DATETRUNC()`, `FORMAT()`
* **Aggregate Functions**: `SUM()`, `COUNT()`, `AVG()`
* **Window Functions**: `SUM() OVER()`, `AVG() OVER()`, `LAG()`
* **Conditional Logic**: `CASE`
* **Grouping and Sorting**: `GROUP BY`, `ORDER BY`
* **Joins**: `LEFT JOIN`
* **Common Table Expressions**: `WITH`
* **Percentage Calculations**: `CAST()`, `ROUND()`
