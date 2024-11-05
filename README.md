## PROJECT OVERVIEW
The sales performance analysis of a retail shope aims to review key insights top selling products, regional performance and monthly sales trends.  The analysis on this project will identify the key issues or opportunities and provide recommendations to achieve specific outcome.

### BUSINESS PROBLEM/OPPURNITY
This analysis will review insights that will determine the top sold products 
that brought low or high sales should be indicated so as to determine their relevance in this business and
regions where more revenue were generated, should be given better opportunities in the business line.
### PROJECT OBJECTIVES
This is to determine the amount of revenue generated from January to December.
By the end of this analysis, products with low returns should be reconsidered while those with good return should be promoted.
This analysis will determine which of the business line is to be focused on and the area to improve on.

### DATA SOURCE
Sales databases
### DATA TOOLS USED (Excel)
- Pivot tables
- Charts
- VLOOKUP
- Data Validation
- Visualisation

### DATA CLEANING AND PREPARATION

This involves the following steps
- Handle Missing values.
- Data Cleaning (Remove duplicates )
- Transformation and Normalize Data
- Data Validation

### METHODOLOGY
DATA ANALYSIS:
The analysis was done using;
Applied statistical method SUM, SUMIF, AVERAGE, MINIMUM, MAXIMUM, COUNT
SQL Clauses such as; where, group by, order by and casewhen
Power BI Tools such as DAX Functions, measure, calculated and conditional columns

### ANALYSIS AND VISUALISATION FROM EXCEL	 
![image](https://github.com/user-attachments/assets/3cd49a51-b753-4316-940d-c9090e523243) 
![image](https://github.com/user-attachments/assets/d47afb17-b858-44dc-84e1-d3216d23efbe)

![image](https://github.com/user-attachments/assets/b08a2039-ba73-4b4d-8019-3d8f0ee401bc)	
![image](https://github.com/user-attachments/assets/44cf2dfc-8ff3-42d3-aa92-a5ed5145b16c)
![image](https://github.com/user-attachments/assets/0eb55930-88e2-487c-a571-5631623f0725)

### SALES PIVOT TABLES
![image](https://github.com/user-attachments/assets/75cdfa19-0153-413d-ae2b-c556f7133235)
![image](https://github.com/user-attachments/assets/d7865f5c-a9fb-46e1-97b8-6f23006888fb)
![image](https://github.com/user-attachments/assets/0368e9f6-3b9d-4f79-bd3c-4f7e946d1f2c)

### CHARTS
![image](https://github.com/user-attachments/assets/af8e73ff-8368-4186-81b6-cd9f03ac9c95)
![image](https://github.com/user-attachments/assets/2a75e3ce-239f-4a44-9105-13dcc475bdb3)

### REPORTS FROM POWERBI
![LITA WORKPBI 11_4_2024 6_53_02 PM](https://github.com/user-attachments/assets/ca5a18a3-0576-4439-9205-88eff48fa470)

### REPORT FROM SQL
 --------------------------------  TOTAL SALES PER PRODUCT------------------------------
 
  `Select` `product`, `sum` (sales) as Total_sales from [dbo].[LITA Capstone Dataset]
`group` `by` `product`

|PRODUCT|TOTAL SALES|
|-------|-----------|
|Shoes|3087500|
|Jacket|1050000|
|Hat|1587500|
|Socks|912500|
|Shirt|2450000|
|Gloves|1500000|

### NUMBER OF SALES TRANSACTION FOR EACH REGION------------------------------

`Select` REGION, `count`(Sales) as Sales_Count `from` [dbo].[LITA Capstone Dataset]
`group` `by` Region`

|REGION|SALES COUNT|
|------|-----------|
|North|12500|
|East|12500|
|South|12500|
|West|12500|

### HIGHEST SELLING PRODUCT BY TOTAL SALES VALUE-----------------------------------------

 `Select` `PRODUCT`, `sum` (Sales) as Totalsales `from` [dbo].[LITA Capstone Dataset]
 `group` `by` `product` 
 `order` `by` 2 `desc`

|PRODUCT|TOTAL SALES|
|-------|-----------|
|Shoes|3087500|
|Shirt|2450000|
|Hat|1587500|
|Gloves|1500000|
|Jacket|1050000|
|Socks|912500|

### TOTAL REVENUE(SALE) PER PRODUCTS----------------------------------

 `Select` `Product`, `sum` (Sales) as Total_Revenue `from` [dbo].[LITA Capstone Dataset]
 `group` `by` `product` 
 
|PRODUCT|TOTAL REVENUE|
|-------|-------------|
|Shoes|3087500|
|Jacket|1050000|
|Hat|1587500|
|Socks|912500|
|Shirt|2450000|
|Gloves|1500000|


### TOP 5 CUSTOMERS BY TOTAL PURCHASED AMOUNT------------------------

 `select` `top` 5 Customer_id, sum(Sales) as Total_Purchased_Amount
 `from`
 [dbo].[LITA Capstone Dataset]
 `group` `by` Customer_id
` Order ` ```by``` 2 ` desc `

|CUSTOMER ID|TOTAL PURCHASE AMOUNT|
|-----------|---------------------|
|Cus1488|29340|
|Cus1375|28925|
|Cus1023|28205|
|Cus1059|28005|
|Cus1367|27920|

### PERCENTAGE OF TOTAL SALES BY EACH REGION-------------------

``` SELECT``` 
 Region,
 `SUM`(sales) AS total_Sales,
 (`SUM`(sales)/(`SELECT` `SUM`(sales) `FROM`[dbo].[LITA Capstone Dataset]))*100 AS Sales_Percentage
 `FROM`
 [dbo].[LITA Capstone Dataset]
 `GROUP` `BY`
 region 
 `ORDER` `BY` 
 sales_percentage `DESC`;

|REGION|REGION TOTAL|PERCENTAGE SALES|
|------|------------|----------------|
|North|1950000|18.42|
|East|2450000|23.14|
|South|4675000|44.15|
|West|1512500|14.29|
