# Stock Sales Performance and Strategic Insights
A Retail Stock Sales Data Analysis that uncover trends in revenue, product performance, regional sales, and profitability | From Raw Data to Business Insights

## Table of Contents

* [Project Overview](#project-overview)
* [Tools & Technologies](#tools--technologies)
* [Dataset Overview](#dataset-overview)
* [Data Cleaning Process](#data-cleaning-process)
* [Exploratory Analysis](#exploratory-analysis)
* [Power BI Dashboard](#power-bi-dashboard)
* [Key Insights](#key-insights)
* [Recommendations](#recommendations)


### Project Overview
This project analyzes retail stock sales data to uncover trends in revenue, product performance, regional sales, and profitability.
Using SQL for data exploration, Excel for transformation, and Power BI for visualization, the project turns raw transaction records into actionable business insights.

### Tools & Technologies
1. SQL 
2. Excel
3. Power BI

### Dataset Overview
The dataset consists of authenticated customer transactions tracking core operational and commercial metrics.The scope of the audited dataset includes 12 primary structural metrics across all records. 


Sample Preview
<img width="2000" height="1000" alt="dashboard" src="https://github.com/adediperhema/Stock-Sales-Performance-Strategic-Insights/blob/main/sales%20anaysis%20table%20sample%20data.png" />


### Data Cleaning Process
• Converted OrderDate to proper date format
• Remove duplicate records.
• Identify and handle blank cells.
• Standardize text fields (e.g., proper case for names).
• Created new calculated field:  Total Sales = Quantity * UnitPrice

### Exploratory Analysis 
1. Total Revenue(TotalSalesAmount)
```sql
SELECT SUM(SalesAmount) AS TotalSalesAmount FROM SalesData;
```

2. Top 5 Products by Total Sales
```sql
SELECT TOP 5 OrderID,OrderDate, CustomerName,Product, Category, Performance, SalesAmount FROM SalesData ORDER BY SalesAmount DESC;
```

3. Total Sales by Region
```sql
SELECT City, 
      COUNT(OrderID) AS TotalTransactions, 
      SUM(Quantity) AS TotalUnitsSold, 
      SUM(SalesAmount) AS TotalSalesAmount 
FROM SalesData 
GROUP BY City;
```

4. Total Sales by Category
```sql
SELECT Category,
       COUNT(OrderID) AS TotalTransactions,
       SUM(Quantity) AS TotalUnitsSold,
       SUM(SalesAmount) AS TotalSalesAmount
FROM SalesData
GROUP BY Category;
```

5. Total Sales by Product
```sql

SELECT Product,
       COUNT(OrderID) AS TotalTransactions, 
       SUM(Quantity) AS TotalUnitsSold, 
       SUM(SalesAmount) AS TotalSalesAmount 
FROM SalesData 
GROUP BY Product 
ORDER BY TotalSalesAmount DESC;

```


### Power BI Dashboard
The dashboards built with Power BI and Excel include the following visuals:
- Revenue over time
- Regional sales performance
- Best and worst-performing products
- Monthly and quarterly growth trends
- Sales by category
- Interactive filters for product and region comparison
  
<img width="262" height="192" alt="dashboard" src="" />
<img width="262" height="192" alt="dashboard" src="" />

### Key Insights
A. Product and Category Concentration: The Electronics vertical serves as the primary core engine of the firm, accounting for 181,250, or 90.60% of total enterprise revenue. Within Electronics, Laptops yielded the highest revenue of 157,200 (78.57% of total sales). Conversely, Notebooks represented the lowest revenue-generating line at only 340 (0.17%).

B. Geographic and Demographics Footprint: The capital city of Accra (Ghana) represents the flagship territorial market with 58,795 (29.39%), followed by Kumasi at 47,855 and Abuja at 38,055. Female consumers were the drivers of the top-line transactional volume, generating 110,105 (55.03%), compared to Male consumers at 79,590 (39.78%). 

C. Revenue peaked profoundly in Q2 at 80,595 before dropping to 55,405 in Q3. In Q4 (October–December), revenue collapsed to 38,705 which was a severe 30.14% contraction relative to Q3. This drop was caused by a complete halt in Laptop sales within Accra during Q4 due to localized stock depletion. While Printer demand spiked in Q4, its low unit price (250) failed to compensate for lost hardware margins.

### Recommendations
1. Establish Supply Chain & Safety Stock Minimums: Re-engineer supply chain mechanisms to avoid inventory stockouts. Since the Q4 revenue contraction was directly triggered by a supply freeze of Laptops in Accra, automated safety-stock thresholds must be established in primary hubs (Accra and Kumasi) to trigger reorders when local warehouse stock drops below 5 units.
 
2. Implement Cross-Category Product Bundling: Capitalize on high-frequency, low-margin products to increase the Average Order Value (AOV). Low-ticket Stationery items like Notebooks (340 total revenue) should be dynamically bundled as complimentary accessories with premium Laptop purchases, optimizing corporate warehouse margins. 

3. Targeted Marketing and Demographics Reallocation: Realign digital acquisition budgets to target the highest performing segment. Because Female consumers generated 55.03% of total gross sales, corporate advertising campaigns should focus heavily on professional hardware tailored for female enterprise users across West African urban centers. 

4. Pricing & Promo Adjustments for Underperforming Markets: Establish regional penetration campaigns within Lagos (Nigeria), which generated only 12.56% of total revenue. Introduce flexible pricing tiers or volume discounts on corporate Furniture (Desks and Chairs) to capture market share from regional competitors.

Dataset Source

[Download Here](https://github.com)





