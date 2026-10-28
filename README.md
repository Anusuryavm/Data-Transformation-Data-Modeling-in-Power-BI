Data-Transformation-Data-Modeling-in-Power-BI
Data import, Transformation, cleansing, aggregation, and relationship modelling

📊 Power BI Sales & Performance Analysis

📌 Project Overview

This project is an end-to-end data analytics solution built using **Power BI** and **Power Query**. It demonstrates core data analyst skills including data ingestion, cleaning, transformation, feature engineering, and relational data modeling. The objective is to analyze sales performance, profitability, profit margins, and track them against established sales targets.

📂 Dataset Sources
The project utilizes three primary raw data files:

1. **List of Orders.csv**: Contains order-level metadata including Order ID, Order Date, Customer Name, State, and City
2. **Order Details.csv**: Contains line-item transaction details such as Amount, Profit, Quantity, Category, and Sub-Category.
3. **Sales target.csv**: Contains monthly sales targets categorized by product lines.
   

🛠️ Data Transformation & Power Query Logic:

Before loading the data into the reporting layer, extensive data cleaning and feature engineering were performed in **Power Query**:

* **Data Type Standardization**: 
  * Converted `Order Date` into proper Date format using locale settings (`English - India`).
  * Changed financial metrics (`Amount`, `Target`) into fixed decimal/currency data types.
* **Text Cleaning & Formatting**: 
  * Trimmed excess whitespace and corrected spelling errors (e.g., standardizing `"Hankerchief"` to `"Hand kerchief"`)
  * Formatted `Customer Name` to proper case.
* **Feature Engineering (Custom & Conditional Columns)**:
  * **`Location`**: Merged `City` and `State` columns into a single unified location attribute.
  * **`Profit Margin`**: Created a custom calculated column (`[Profit] / [Amount]`) formatted as a percentage.
  * **`Profit Status`**: Added a conditional column categorizing orders into `Loss` ($\text{Profit} < 0$), `Break-Even` ($\text{Profit} = 0$), or profit levels.
* **Table Merging & Aggregation**:
  * Merged tables using keys like `Order ID` to construct comprehensive analytical tables (e.g., `Orders Data`)
  * Applied `Group By` operations to compute aggregated metrics, such as **Average Profit by Category**, **Total Amount by Sub-Category**, and **Total Target by Month**.


🧱 Data Modeling & Relationships
Once transformed, the tables were structured into a relational schema to enable cross-filtering and accurate measure calculations:

* **List of Orders ↔ Order Details**: Connected via `Order ID` (1-to-Many relationship) to link customer metadata with item specifics.
* **Order Details ↔ Order Data**: Linked via `Order ID` to support consolidated analysis.
* **Order Details ↔ Sales Target**: Linked via the `Category` field to evaluate actual performance against targets.
* *All relationships were verified and managed to ensure active filtering paths.


🚀 Key Skills Demonstrated
* Data Ingestion & Extraction from CSV sources
* Advanced Power Query Transformations & M-Code logic
* Data Cleaning, Handling Nulls, and Typo Corrections
* Conditional Logic & Custom Column Creation
* Relational Data Modeling & Star Schema Principles

