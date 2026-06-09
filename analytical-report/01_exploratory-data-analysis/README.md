## Overview 

This folder contains SQL scripts used to explore and analyze the gold layer of a sales data warehouse. The goal is to understand the database structure, review key dimensions, calculate business metrics, and identify sales trends across customers, products, and time.

---

## Scripts Description 

### `01_database_exploration.sql`

* **Purpose**: Explores the structure of the database.
* **Queries**:

  * Lists all tables, schemas, and table types using `INFORMATION_SCHEMA.TABLES`.
  * Inspects column names, data types, nullability, and field lengths using `INFORMATION_SCHEMA.COLUMNS`.
  * Helps identify what data is available before deeper analysis.

### `02_dimensions_exploration.sql`

* **Purpose**: Explores unique values in dimension tables.
* **Queries**:

  * Retrieves a distinct list of customer countries.
  * Reviews product categories, subcategories, and product names.
  * Identifies descriptive fields that can be used for grouping and filtering.

### `03_date_range_exploration.sql`

* **Purpose**: Identifies the time span of the dataset.
* **Queries**:

  * Finds the earliest and latest order dates.
  * Calculates the total order history in months.
  * Finds the youngest and oldest customers based on birthdate.

### `04_measures_exploration.sql`

* **Purpose**: Calculates key business metrics.
* **Queries**:

  * Calculates total sales, total quantity sold, and average selling price.
  * Counts total orders, products, customers, and customers who placed orders.
  * Combines major KPIs into one summary report using `UNION ALL`.

### `05_magnitude_analysis.sql`

* **Purpose**: Measures how data is distributed across different categories.
* **Queries**:

  * Groups customers by country and gender to understand customer distribution.
  * Groups products by category and calculates average cost by category.
  * Joins fact and dimension tables to calculate revenue by category, customer, and country.

### `06_ranking_analysis.sql`

* **Purpose**: Ranks products and customers based on performance.
* **Queries**:

  * Identifies the top and bottom products by revenue.
  * Uses `RANK()` to create flexible product rankings.
  * Finds the top customers by revenue and customers with the fewest orders.

---

## Key SQL Concepts Used 

* **Database Metadata**: `INFORMATION_SCHEMA.TABLES`, `INFORMATION_SCHEMA.COLUMNS`
* **Aggregate Functions**: `SUM()`, `COUNT()`, `AVG()`, `MIN()`, `MAX()`
* **Date Functions**: `DATEDIFF()`, `GETDATE()`
* **Grouping and Sorting**: `GROUP BY`, `ORDER BY`
* **Joins**: `LEFT JOIN`
* **Ranking**: `TOP`, `RANK()`
* **Set Operators**: `UNION ALL`
