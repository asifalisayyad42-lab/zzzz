# 🛒 Zepto E-Commerce Data Analysis | SQL Project

---

# 📊 Project Overview
This project is an **end-to-end SQL Data Analytics project** built using **Microsoft SQL Server** to analyze quick-commerce product, inventory, and pricing data for **Zepto**.  
The goal of this project is to clean raw catalog data, extract **business insights**, handle **data type anomalies**, and optimize operational parameters like inventory weight distribution and category revenues.

This project simulates a **real-world data analyst workflow**:
- **Raw data exploration & validation**
- **Data cleaning & unit conversion** (paise to rupees)
- **Resolving arithmetic & precision bugs** (data type casting)
- **Business-focused SQL query development**

---

# 🛠️ Tools & Technologies Used
- **Database Engine:** Microsoft SQL Server (T-SQL / SSMS)
- **Data Source:** CSV / Excel
- **Version Control:** Git & GitHub

---

# 📂 Dataset Information
- **Source:** Zepto Product & Inventory Dataset (CSV)
- **Primary Table:** `dbo.zepto`
- **Key Columns:**
  - `sku_id` *(Primary Key)*
  - `name`
  - `category`
  - `mrp`
  - `discountedSellingPrice`
  - `discountPercent`
  - `weightInGms`
  - `availableQuantity`
  - `outOfStock`

---

# 📈 Key Business KPIs
The following key performance metrics were calculated using SQL:

1. **Total Estimated Inventory Revenue Potential**
2. **Category-Wise Total Inventory Weight**
3. **Average Discount Percentage per Category**
4. **Unit Economics (Price Per Gram)**
5. **High-Value Out-of-Stock Item Count**

---

# 📊 Analytical Insights

## 🔹 Pricing & Discounts Analysis
- Top 10 products with the **highest discount percentage**
- Average discount comparison across product categories

## 🔹 Inventory & Supply Chain Analysis
- Total estimated revenue per category
- Total inventory weight per category using weight aggregations
- Out-of-stock analysis on high-MRP items ($\ge$ ₹300)

## 🔹 Product Categorization & Logistics
- Unit economics evaluation (**price per gram** for items $\ge$ 100g)
- Weight classification into **Low, Medium, and Bulk** ranges

---

# 🧠 SQL Analysis
All SQL queries used in this project are available in the repository.

### Key operations performed:
- **Data Cleaning:** `DELETE`, `UPDATE`, `/ 100.0` conversion
- **Precision & Type Safety:** `CAST AS BIGINT`, `DECIMAL` management
- **Aggregations:** `SUM`, `AVG`, `COUNT`, `ROUND`
- **Categorical Logic:** `CASE WHEN`
- **Grouping, Sorting & Filtering:** `GROUP BY`, `HAVING`, `DISTINCT`, `TOP N`

📁 **SQL File:** `zepto_queries.sql`

---

# 🧹 Data Cleaning Highlights

## 🔹 Anomaly Removal
- Identified and deleted records where `mrp = 0` to preserve data integrity for pricing calculations.

## 🔹 Unit Conversion
- Transformed prices from **paise to rupees** using decimal division (`/ 100.0`) to avoid integer truncation.

## 🔹 Data Type & Overflow Resolution
- Handled `smallint` limits by explicitly casting `weightInGms` to `BIGINT` during inventory weight calculations.

---

# 🧠 Key Insights

## 🔹 Revenue & Inventory Dynamics
- Higher-priced categories contribute significantly to total potential revenue when weighted against available quantities.
- Certain high-demand products ($\ge$ ₹300) are currently out of stock, indicating restock priorities.

## 🔹 Unit Economics & Packaging
- Calculating price per gram highlights strong price-to-weight value for bulk-sized items over smaller package options.

## 🔹 Operational Optimization
- Categorizing items into **Low, Medium, and Bulk** weight buckets provides immediate data support for delivery logistics planning.
