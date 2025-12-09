# Coffee_Shop_Sales_Analysis
## Table of Content
  - [Project Overview](#project-overview)
  - [Objectives](#objectives)
  - [Dataset Description](#dataset-description)
  - [Data Cleaning and Preparation](#data-cleaning-and-preparation)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Visualization](#visualization)
  - [Insights and Recommendations](#insights-and-recommendations)
    
## Project Overview
This project explores and analyzes coffee sales data to uncover insights about sales performance, customer behavior, and profitability trends.
## Objectives
- Analyze overall coffee sales performance across time periods.
- Identify top-selling products.
- Understand seasonal trends and customer purchase behavior.
- Build an interactive dashboard for management reporting.
- Provide actionable recommendations to improve sales and profitability.
## Dataset Description
- Source (Kaggle)
- 12 columns and 3000+ rows
- Key fields (Coffee Name, Payment Mode, Time Of Day, etc)
## Data Cleaning and Preparation
- Standardized data formats, renamed columns, filtered rows.
- Created a date table for time intelligence DAX functions.
- Defined relationship between tables.
## Exploratory Data Analysis
- Used Power Query, Power BI Data Modelling and DAX functions
- Calculated measures (e.g. YTD Sales, MTD Sales, Previous Day Sales, e.t.c)
  -  Total Sales = SUM('Coffee Sales'[Revenue])
  -  Total Transactions = COUNTROWS('Coffee Sales')
  -  Unique Customers = DISTINCTCOUNT('Coffee Sales'[Card Number])
  -  YTD Sales = TOTALYTD([Total Sales], 'Date'[Date])
  -  MTD Sales = TOTALMTD([Total Sales], 'Date'[Date])
  -  Previous Month Sales = CALCULATE([Total Sales], PARALLELPERIOD('Date'[Date], -1, MONTH))
  -  Previous Day Sales = CALCULATE([Total Sales], PREVIOUSDAY('Date'[date]))
  -  Customer Purchase Frequency = CALCULATE(COUNTROWS('Coffee Sales'), ALLEXCEPT('Coffee Sales','Coffee Sales'[Card Number]))

## Visualization

![Coffee Sales Dashboard](https://github.com/user-attachments/assets/8aa8e460-4326-4932-8652-a1347ba507ce)

![Coffee Sales Dashboard(Details)](https://github.com/user-attachments/assets/9d5923d6-7a91-4e9f-a3a1-2a6108c714d9)
 
## Insights and Recommendations
  ### Insights
  - Americano with Milk & Latte are best-sellers. These two make up a large portion of total transactions.
  - The peak period for sales is in the morning and late in the afternoon while Mondays, Tuesdays and Fridays are peak days for sales.
  - 97% of transactions are by card which is great for loyalty programs.
  - 1,316 unique customers which suggests good customer base.
  - There was a significant decrease in sales from 2024 to 2025.
    
### Recommendations
  - Increase staffing during peak hours and days.
  - Track loyal customers (using card IDs) and reward frequent buyers.
  - Offer discounts for customers in slower hours to drive sales.
  - Stock up more on high-demand products/raw materials.
  - For less popular items, consider seasonal promotions or removing underperforming ones.


