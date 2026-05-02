# Fashion Sales Data Cleaning Project

## Project Overview
This project focuses on the end-to-end data cleaning and validation process of a raw "Fashion Sales" dataset. The primary goal was to transform a messy, inconsistent dataset into a reliable source for analysis, ensuring data integrity and logical accuracy.

## Dataset Description
The dataset contains transaction records for fashion items, including columns such as:
- **Product Information:** Category and Name.
- **Sales Data:** Units Sold, Unit Price, Discount Percentage, and Sales Amount.
- **Geography & Date:** City and Order Date.
- **Performance Metrics:** Segment and Profit.

## Challenges & Issues Identified
During the Initial Data Inspection (Exploratory Data Analysis), several critical issues were identified:
1. **Missing Values:** Significant gaps were found in `Units_Sold`, `Unit_Price`, and `Order_Date` columns.
2. **Calculation Errors:** The `Sales_Amount` column was either zero or empty in many rows despite having price and quantity data.
3. **Major Business Logic Flaw:** A critical inconsistency was discovered where the `Profit` was significantly higher than the `Sales_Amount` for several entries. In a real-world scenario, profit cannot exceed total sales revenue.
4. **Formatting Issues:** Dates were inconsistent, and some cells were locked/un-editable (Read-only mode).

## Data Cleaning Steps Taken
To ensure the dataset is ready for analysis, the following steps were performed:

### 1. Handling Missing Data
- Used Excel's **Go To Special (Blanks)** to identify empty cells.
- Removed rows that lacked critical information (e.g., records with no product name and no price).
- For missing `Sales_Amount`, I applied the following business formula:
  `Sales_Amount = (Units_Sold * Unit_Price) * (1 - Discount_%)`

### 2. Business Logic Validation (The "Profit" Dilemma)
- **Problem:** Found entries where `Profit > Sales_Amount`.
- **Action:** Created a validation column using an `IF` logic to flag these rows as "Invalid Logic." 
- **Resolution:** As a professional analyst, I decided to exclude these rows from the final analysis to maintain **Data Integrity**, as the source data was fundamentally flawed in these specific instances.

### 3. Standardization
- Standardized the `Order_Date` format across the entire sheet.
- Fixed spelling errors in product names and categories.
- Removed duplicate transaction IDs to ensure unique records.

## Tools Used
- **Microsoft Excel:** Advanced Formulas, Data Validation, Filtering, and Conditional Formatting.

## Key Learning Outcomes
Through this project, I demonstrated the ability to:
- Identify and troubleshoot data quality issues.
- Apply business logic to validate financial data.
- Document the cleaning process for transparency and reproducibility.
- Make informed decisions on whether to impute, flag, or delete inconsistent data.

---
**Status:** Data is now cleaned and ready for Visualization/Dashboarding.
