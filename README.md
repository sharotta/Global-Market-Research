# Global-Market-Research
Comprehensive Excel dashboard analyzing sales performance, customer behavior, and marketing impact. Features include dynamic charts, pivot tables, funnel analysis, and sentiment tracking to uncover actionable insights.

## Overview
This project delivers an **interactive Excel dashboard** for a global marketing team to evaluate **regional performance, brand competitiveness, customer behavior, and market potential**. 

The dashboard answers key business questions and supports **strategic decisions for market entry and resource allocation**.

## Objectives
- Analyze **market share by product category and region**.
- Correlate **customer sentiment with revenue performance**.
- Track **sales funnel and acquisition patterns**.
- Identify **growth opportunities across markets**.

## Business Questions
1. Which regions generate the highest revenue and market share?
2. Does positive customer sentiment correlate with higher revenue?
3. Where do customers drop off in the acquisition journey?
4. Which regions and product categories have the greatest growth potential despite competition?
5. Which customer segments contribute most to sales?

## Dataset Overview
This dataset captures global sales and marketing data across multiple product categories and regions. It includes KPIs like revenue, acquisition sources, engagement funnel metrics, sentiment scores, and repeat purchase behavior. Data was cleaned and analyzed in Excel to uncover performance trends and customer journey insights.

## Data Cleaning & Preparation
1. Sales_Data
- Removed blank rows and verified data types
- Date column was changed to a proper dd/mm/yyyy format
- Standardized Product Category entries using PROPER() and TRIM() functions
- Created reference table for countries and region and misclassified country and region is fixed with a mapping table XLOOKUP
- Missing Revenue was replaced with average revenue for that product category using AVERAGEIFS
- Missing Brand was replaced with mode using helper table and INDEX-MATCH
- Standardized "Usa" to "USA" using UPPER function
- Created reference table for countries and region and misclassified country and region is fixed with a mapping table XLOOKUP
- Check for Duplicate Order IDs using =COUNTIF(A:A, A2) → Filter for results > 1

2. Feedback_Data
- Cleaned rating values and ensured all are numeric.
- Mapped Product Category from Product Dimension using INDEX-MATCH on Product ID.
- Trimmed and formatted textual data fields like Review Text Created a sentiment score.

3. Customer Dimension Table
- Cleaned Segment, Age Group, and Gender fields
- Removed duplicate Customer IDs
- Verified uniqueness of Customer ID for relationship creation
- Added to Power Pivot and linked to Sales_Data and Feedback_Data

4. Product Dimension Table
- Cleaned Product Category names Standardize categorical values (e.g., strip white spaces in "Product Category")
- Verified Product ID as unique (primary key)
- Used as a lookup table to enrich Feedback_Data
- Product Category mismatch- Cleaned with TRIM, PROPER, I also removed Duplicates.

## Data Modeling in Excel (Power Pivot) 
The following relationships were successfully created: 

- Feedback_Data ↔ Product_Dim → via Product ID 
- Feedback_Data ↔ Customer_Dim → via Customer ID 
- Sales_Data ↔ Customer_Dim → via Customer ID
