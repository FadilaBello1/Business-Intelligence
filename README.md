# Business Intelligence and Dynamic Executive Insights
## Project Overview
This project was completed as part of my data analytics training at IFEXA Academy.
The project uses retail business data to develop an interactive Power BI dashboard that enables management to monitor sales, profitability, customers, products, regions, and overall business performance.
The project was further extended into a Dynamic Insights & Storytelling analysis, where Power BI was used to transform key performance metrics into automatically generated executive insights.
The objective was not only to present numbers, but to make the data easier for management to understand and use for decision-making
## Business Problem
The dashboard was designed to answer question such as:
1. How the business is performing ?
2. What is driving revenue and profitability ?
3. Which products and categories perform strongly ?
4. Which regions and salespeople contribute most to performance.Where profitability may require attention ?
5. How revenue changes from month to month ?
6. How business performance can be communicated through dynamic insights rather than raw numbers alone ?
## Project Objectives
The project aimed to:
1. Analyze overall sales and profitability.
2. Monitor revenue trends over time.
3. Identify high- and low-performing products.
4. Compare category and regional performance.
5. Analyze customer and salesperson performance.
6. Calculate key business performance indicators.
7. Analyze month-over-month revenue growth.
8. Develop dynamic performance insights using DAX.
9. Create executive-friendly visualizations.
10. Provide actionable recommendations based on the analysis.
## Tools & Techniques
### Tools
1. Microsoft Excel
2. Power Query
3. Power BI	Data
4. DAX
5. GitHub
   
### Techniques
1. Data cleaning
2. Data transformation
3. Data modelling
4. Star schema
5. Relationship management
6. KPI development
7. DAX calculations
8. Dynamic storytelling
9. Interactive dashboard design
### Dataset
The dataset was provided by IFEXA Academy for the project.
It contains information relating to:
- Sales transactions
-  Customers
-   Products
-   Employees
-   Inventory
-   Expenses
-   Targets
-   Dates
## Data Preparation
Before analysis, the dataset was reviewed and prepared for Power BI.
The preparation process included:
1. Checking data types.
2. Reviewing missing values.
3. Checking for duplicates.
4. Reviewing inconsistent categories.
5. Ensuring date fields were correctly formatted.
6. Reviewing ID fields.
7. Preparing the date table.
8. Organising fact and dimension tables.
9. Establishing appropriate relationships between tables.
## Data Model
A star-schema structure was used to organize the data.
The dimension tables provide descriptive information, while the fact tables contain transactional/business records.
The objective was to ensure that the dataset was structured correctly before building the dashboard.
## DAX Measures
The analysis used DAX to create key business performance metrics.
### Total Sales
Total Sales =
SUM(Fact_Sales[Net_Sales])
### Total Quantity
Total Quantity =
SUM(Fact_Sales[Quantity])
### Total Cost
Total Cost =
SUMX(
    Fact_Sales,
    Fact_Sales[Quantity] *
    RELATED(Dim_Products[Unit_Cost]))
### Total Profit
Total Profit =
[Total Sales] - [Total Cost]
### Profit Margin %
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales],0 )
### Previous Month Sales
Previous Month Sales =
CALCULATE(
    [Total Sales],
    DATEADD(Dim_Date[Date], -1, MONTH)
)
### Sales Growth %
Sales Growth % =
DIVIDE( [Total Sales] - [Previous Month Sales], [Previous Month Sales], 0 )
### Previous Year Sales
Previous Year Sales =
CALCULATE(
    [Total Sales],
    DATEADD(Dim_Date[Date], -1, YEAR)
)
### YoY Growth %
YoY Growth % =
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales],
    0
)
### Average Quantity per Order
Average Quantity per Order =
DIVIDE(
    [Total Quantity],
    [Total Orders],
0 )
## Dynamic Insights & Storytelling
### Dynamic Executive Insights
The project was extended to create dynamic management insights using DAX.
The analysis included:
- Total Revenue
- Previous Month Revenue
- MoM Growth %
- Performance Insight
- Top State
- Top Category
- Executive Insight
- Management Alert
Instead of requiring management to interpret every KPI manually,
 the dashboard was designed to communicate changes in business performance using automatically generated text.
## Conclusion
This project demonstrated how raw business data can be transformed into an interactive business intelligence solution using Power BI.
By combining data preparation, data modeling, DAX calculations, visualization, and dynamic storytelling, the project provides management with a clearer view of business performance and areas requiring attention.
