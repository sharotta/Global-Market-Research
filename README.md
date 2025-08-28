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

## Tools Used
- **Microsoft Excel** (Power Query, Power Pivot, Pivot Table, Pivot Charts, Slicers)
- **Data Cleaning**: PROPER, TRIM, XLOOKUP, INDEX-MATCH

## Data Cleaning & Preparation
1. Sales Data
- Removed blank rows and verified data types
- Date column was changed to a proper dd/mm/yyyy format
- Standardized Product Category entries using PROPER() and TRIM() functions
- Created reference table for countries and region and misclassified country and region is fixed with a mapping table XLOOKUP
- Missing Revenue was replaced with average revenue for that product category using AVERAGEIFS
- Missing Brand was replaced with mode using helper table and INDEX-MATCH
- Standardized "Usa" to "USA" using UPPER function
- Created reference table for countries and region and misclassified country and region is fixed with a mapping table XLOOKUP
- Check for Duplicate Order IDs using =COUNTIF(A:A, A2) → Filter for results > 1

2. Feedback Data
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

## Data Analysis & Visualization 
This project culminates in a two-page interactive Dashboard built in Excel, designed to translate raw data into actionable business intelligence for different stakeholder groups.

### **Dashboard Structure:**

**Page 1: Executive Performance Overview**
-  **Audience:** C-Suite, VPs, General Managers, Stakeholders
-  **Purpose:** To provide a high-level snapshot of business health, highlighting top-level KPIs, key drivers of revenue, and the most significant opportunities and risks.

<img width="1077" height="488" alt="Dashboard 1" src="https://github.com/user-attachments/assets/607a837b-85cb-420e-b866-c25757695bd4" />

### Key Insights
1. Regional Performance: North America is the undisputed revenue leader, generating $90,020—commanding the largest market share. In stark contrast, Europe is the lowest-performing region, contributing only $11,100.
2. Product Category Analysis: Electronics is the top-performing category ($34,735), followed by Home Appliances ($33,096). However, a critical issue exists: the Clothing category has both the lowest revenue ($27,995) and the lowest customer satisfaction rating (2.71)
3. Monthly Trends: Revenue peaked in August at $17,547 after a climb from a February low of $13,734. However, this was followed by a significant downturn throughout Q3, falling through October.
4. Customer Segmentation: The Adult demographic is your core customer base, dominating both revenue ($57,629) and quantity purchased (592 units).

### Recommendations
1. Double down on successful strategies in North America. Analyze the marketing, product mix, and customer engagement tactics that drive success here and document them as best practices.
2. Launch a focused review of European operations. Investigate potential causes for low sales: logistics, marketing relevance, local competition, or product-market fit. Consider a targeted campaign or local partnership to stimulate growth.
3. Leverage winning categories. Feature Electronics and Home Appliances more prominently in marketing campaigns and ensure optimal stock levels.
4. Initiate an urgent turnaround project for Clothing. This dual threat of low sales and low satisfaction signals a failing product line or poor customer experience. Immediately gather customer feedback, review quality, sizing, and marketing, and consider a strategic reboot or discontinuation.
5. Analyze the Q3 drop. Investigate external factors (e.g., back-to-school shifts, competitor activity) and internal factors (e.g., inventory stockouts, reduced ad spend) that caused the post-peak decline.
6. Plan for next year’s cycle. Use this trend to forecast more accurately. Budget for increased marketing spend in Q2 to fuel the summer peak and develop strategies to maintain momentum through Q3.
7. Allocate the majority of marketing resources toward acquiring and retaining Adult customers. Develop loyalty programs, personalized marketing, and new product offerings tailored to this segment's preferences.
8. Conduct research to understand why Seniors and Youth underperform. There may be untapped potential with tailored messaging or product adjustments.

## **Page 2: Marketing & Customer Insights**
- **Audience:** Marketing Directors, Growth Teams
- **Purpose:** To dive into the operational metrics behind customer acquisition and retention, analyzing marketing channel efficiency and the customer journey funnel.

<img width="912" height="419" alt="Dashboard 2" src="https://github.com/user-attachments/assets/02055ed4-48bc-4ced-a336-cc9deff9de49" />

### Key Insights
1. Social Media and Organic channels generate the highest revenue, indicating strong ROI. Paid Ads significantly underperform in comparison, suggesting inefficient budget allocation or poor ad targeting.
2. The Beauty category has a critically high level of negative customer sentiment. This indicates widespread product dissatisfaction, which directly threatens customer retention and future revenue from this segment.
3. The Clothing category is a low sales performer. Unlike Beauty, its issue is not primarily negative sentiment, but likely poor discoverability, ineffective marketing, or uncompetitive pricing.
4.The business suffers a massive 77.3% drop-off between customer engagement and conversion. Furthermore, repeat purchases are extremely low (8.89%), indicating a failure to retain customers.
5. Social Media is the primary driver for acquiring new users, while Organic Search is key for customer retention and building loyalty.

### Recommendations
1. Immediately pause the current Paid Ads campaign. Conduct a thorough audit of target audiences, ad creative, and landing page relevance. Reallocate the budget to top-performing Social Media and Organic growth initiatives.
2. Launch a urgent product quality review for the Beauty line. Analyze customer returns and negative reviews to identify specific failure points (e.g., ingredients, packaging, false advertising). Halt promotional spending until issues are diagnosed.
3. Investigate Clothing's market fit. Review pricing strategies, product positioning, and marketing campaigns. Focus on improving product visibility and appeal to drive acquisition.
4. Audit the sales funnel. Fix website UX, checkout process, and loading speeds. Implement email nurturing sequences and post-purchase engagement strategies to improve retention.
5. Double down on successful channels. Increase budget for targeted Social Media campaigns to acquire new users. Invest in SEO and content marketing to strengthen Organic Search and improve customer retention rates.

## Conclusion
The business is on solid ground with clear strengths, a dominant region (North America), wining product categories (Electronics, Home Appliances), and a valuable core customer segments (Adults). The path to accelerated growth involves defending these strengths while aggressively addressing weaknesses, particularly the failing Clothing category and the volatile Q3 sales dip. By focusing resources on the highest-impact opportunities revealed by the data, the company can unlock significant new revenue and build a more resilient business model.
