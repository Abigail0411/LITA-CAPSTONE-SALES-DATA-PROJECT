# LITA-CAPSTONE-SALES-DATA-PROJECT

## Project Overview
This project collects data and analyses the sales performance of a retail store, Shade & Co. The goal is to uncover key insights such as, top-selling products, regional performance and monthly sales trend and come up with data-driven decisions to improve the business. The analysis also highlights key metrics such as Total Sales by each Product, Average Sales per Product and Total Sales by Region

## Data Source
The data used for this sales analysis was collected from the retail's store Point of Sales System(POS)
- Data Collected:
1. Order Id
2. Custormer Id
3. Product
4. Region
5. Order Date
6. Quantity
7. Unit Price
- Timeframe: Data from 31st of January 2023 to 1st of September 2024

## Project Objective
The goal is to uncover key insights such as, top-selling products, regional performance and monthly sales trend and come up with data-driven decisions to improve the business. 

## Data Cleaning and Exploratory Data Analysis (EDA)
- EDA alongside data cleaning was performed in this project to understand the dataset's structure, identify and handle missing values and address any data quality issues.
  * A missing colunm was added, which was the Revenue column which was found by multipling the Quantity by the Unit Price in order to know the Total Sales generated.
  * The data was checked for duplicates by highlighting the whole data in an excel sheet and clicking on the 'Remove Duplicates' in the Data tab interface.
- EDA also invovles he exploring of Data to answer the some questions about the Data, which are to determine;
  * Total sales generated by each product
  * Total sales generated by each region
  * Total sales generated each month
  * Average sales per product
  * The number of Sales transactions in each region
  * The Highest-selling product by the total sales
  * The Top 5 Customers by their purchase amount
  * Number of sales transactions in each region
  *  The percentage of total sales contributed by each region
  * The products with no sales in the last quarter
    
## Data Tools and Methods Used
1. Microsoft Excel 
- For Data Cleaning
- For Analysis utilizing Pivot Tables to summarize and analyze the dataset making it easier to identify insights
- For Visualization - Bar charts were used to visually represent key insights
2. Structured Query Language(SQL) for Quering of Data
3. Power BI used for converting data from different data sources to interactive dashbords and BI reports.

## Data Analysis
Some formulars, functions, queries were used during the analysis, which are as follows;
### Excel formulars used
- Total Sales = Quantity * Unit price
- AVERAGEIF(range,criteria,[average_range]): Used to calculate the Average sales per Product
![Screenshot (154)1](https://github.com/user-attachments/assets/a7b4f5ea-a396-4b37-b64a-44b442d0da9b)

- SUMIF(range,criteria,[sum_range]):  Used to calculate the Total Revenue by region
![Screenshot (155)](https://github.com/user-attachments/assets/983b2631-0f64-47a1-9d87-7368d051149a)


### SQL queries executed

```SQL
Select [Product], sum(Revenue) as TotalSales 
From Sales_Data 
Group by [Product]
order by 2 Desc
```

```SQL
Select Region, sum(Revenue) as TotalSales 
From Sales_Data 
Group by Region
order by 2 Desc
```

```SQL
Select Region, Count(OrderID) as SalesTransaction
From Sales_Data
Group by Region
order by 2 Desc
```

```SQL
Select top 1 [Product], Sum(Quantity*UnitPrice) as Total_Sales 
From Sales_Data
Group by [Product]
```

```SQL
Select [Product], sum(Quantity*UnitPrice) as TotalRevenue 
From Sales_Data
Group by [Product]
Order by 2 Desc
```

```SQL
Select Month(OrderDate) as Sales_Month, Sum(Revenue) as Monthly_Sales
From Sales_Data
Where Year(OrderDate) = Year(Getdate())
Group by Month(OrderDate)
Order by 2 Desc
```

```SQL
Select Top 5 Customer_id, Sum(Revenue) as TotaL_Purchase_Amount
From Sales_Data
Group by Customer_id
Order by 2 Desc
```

```SQL
Select Region, TotalSales,
Format (TotalSales *100 / Sum(TotalSales)Over (),'0.00') + '%' As Percentage_Of_TotalSales 
From SalesData
```

```SQL
Select Distinct [Product]
From Sales_Data
Where[Product] NOT IN(
Select [Product]
From Sales_Data
Where OrderDate >=
DATEADD(quarter, 4, GETDATE()) 
And Orderdate < GETDATE())
```

### DAX Functions used

## Data Visualization Analysis and Inferences
## 1. Total Sales by Product - Microsoft Excel
## Pivot Table
![Screenshot (134)](https://github.com/user-attachments/assets/11f233e6-d21e-4ac4-85f7-78d3b067a0af)

## Filtered Column Chart for Year 2023
![Screenshot (50)](https://github.com/user-attachments/assets/13b63d89-82bc-4b46-9117-74f304b69013)
## Filtered Column Chart for Year 2024
![Screenshot (52)](https://github.com/user-attachments/assets/9a0c50ad-df6a-4b7c-83bb-8fad4a5db282)
## Total Sales by Product - SQL
![Screenshot (74)](https://github.com/user-attachments/assets/e8168173-c5a7-40f7-94ed-b21a1a78a4a6)

## i. Inferences:
- ### Overall Total Sales Trends;
  * There was a decrease of $109,570 in total sales from 2023 to 2024. This indicates a negative trend in revenue generation which was caused by ineffective pricing strategies. 
- ### Analyzing Product Performance;
 * Shirt: Had the hightest sales in the year 2023 and had a decrease in sales in 2024 due to high in price as compared to the competitors.
- Shoes: Increased in sales in 2024 due to the store introducing new shoe styles and collections which attracted both new and returning customers.
- Socks: The column chart for the year 2024 shows a decline in sales due to bulk purchase patterns, customers often buy socks in bulk and replace them infrequently, which reduces repeat purchase.
- Gloves: Remains relatively stable, indicating that it continues to be a strong market, although it doesn't show significant growth.
- Hats: Shows a huge incerease in sales in 2024, suggesting improved performance or market conditions.
- Jacket: Shows a huge decrease in sales in 2024, with a difference of $120,950 due to the increase in price of the product.
### Conclusion
The Total Sales data from 2023 to 2024 shows an unstable growth performance and instability in sales. The store should take closer examination of market conditions and customer behavior as well as re-evaluating their pricing strategies.

## 2. Total Sales by Region - Microsoft Excel
## Pivot Table
![Screenshot (135)](https://github.com/user-attachments/assets/c9b90668-c770-46ac-984a-ea1804b05a89)

## Filtered Column Chart for Year 2023
![Screenshot (63)](https://github.com/user-attachments/assets/f403f6e4-42ad-46c8-85f0-8f32f27689be)
## Filtered Column Chart for Year 2024
![Screenshot (64)](https://github.com/user-attachments/assets/713aafe5-48c0-4011-b5e8-38dc685dcf02)
## Total Sales by Region - SQL
![Screenshot (75)](https://github.com/user-attachments/assets/a0ff07cc-a6d3-404b-ada5-39e701c0b577)

## Inferences:
### 1. Overall Overview on Regional Sales Performance;
The total sales in the South and East region have decreased this year compared to last year while the sales of the North and West region increaded in sales in 2024 as compared to 2023.
### 2. Sales Performance by each region in each year;
- South: The South region had the highest revenue in both 2023 and 2024 but shows a slight drop in sales in 2024. The drop in sales may be due to increased competition in the market.
- East: Had the 2nd hightes revenue in 2023 but Shows a huge decrease in revenue in 2024. The decline in sales may indicate a rising competitor in the market andthe prices of the products were seen to be high.
- North and West: Both regions show high revenue figures which indicates improved and effective implemented price strategies. 
### 3. Sales Distribution by Region;
The Column bar charts illustrate a clear drop in revenue for 2024 compared to 2023. This might indicate that overall market conditions may be affecting all the regions.
### 4. Strategic Intervention

## 4. The number of Sales transactions in each region - SQL
![Screenshot (76)](https://github.com/user-attachments/assets/c5b69b50-759b-4ab7-a670-2e6ec6ae708f)
### i. Inferences
- #### The number of sales orders in all regions appears to be in the same range but with East region leading with 2,483 number of orders indicating that Shade & Co. has a strong market prence than in the other regions. It may also indicate that the customers in the East region have greater spending capacity.
### ii. Strategic Recomendations
- To boost sales transactions in all the regions, Shade & Co can consider implementing the following strategies;
  * They can design promotions such as discounts on products based on the purchasing power of each region's customers.
  * They canalso offer preffered payment methods basede on regional preferences, e.g a customer paying for the product bought in installments.
  * 

## 5. The percentage of total sales contributed by each region-SQL
![Screenshot (81)](https://github.com/user-attachments/assets/42d5ed87-da78-41e9-bd7f-31853dad25d0)
### Inferences:
### 1. Overall Regional performance;
- South shows the highest percentage of total sales with 44.16% which might indicate strong market penetration or rffective sale strtedies in the region.
- West region Contributed the least total sales with 14.29%. This suggests potential challenges and may be due to low brand awareness or ineffective marketing.
### 2. Strategic Intervention;
- Cloudy Wears should continue investing in the South region with 44.16% sales rate to increase advertising and improve customer loyalty program to retain and grow the customers.
- For low-performing regions, Cloudy Wears should conduct market research on the needs and preferences of the customers and increase brand awareness by allocating more resourses towards advertising and promotions,
### Conclusion
By strenthening marketing and operational strategies in the region, the company can aim to boost overall revenue and expand market share.

## 6. Monthly Sales - Microsoft Excel
## Pivot Table
![Screenshot (54)](https://github.com/user-attachments/assets/9563ae3f-4685-478a-b883-d3c6b5ce10c3)
## Filtered Column Chart for Year 2023
![Screenshot (62)](https://github.com/user-attachments/assets/d903e2ac-4931-4add-886c-655f0202ab5d)
## Filtered Column Chart for Year 2024
![Screenshot (61)](https://github.com/user-attachments/assets/281b0d10-a083-4399-93fc-03d94953574a)
## Monthly Sales for Year 2024 - SQL
![Screenshot (79)](https://github.com/user-attachments/assets/8769ad09-83df-4849-92d5-e3040854c603)
### Inferences:
### 1. Oveview of the Monthly Sales Performance;
The sales fluctuate monthly in both year, which indicates unstable growth performance in the store.
### 2. Sales Performance in each month in each year;
- January: Sales increased in 2024 as compared to last year. This may indicate Cloud Wears effective implemented pricing strtegies.
- February: February appears to have the highest sales in both years as shown on the column bar charts. This suggest that the store normally launch promotions to boost sales after the quiet less eventful January and also looking at the fact that valentines day is in this month which drives customers to buy gifts to celebrate their loved ones.
- March: The sales in this month in both years are low and the sales decreased in 2024 as compared to last year. This may indicate lower inveswtment in marketing or fewer promotions in March.
- April: The sales in April slightly increased which may be due to improved marketing strategies as well as well timed promotions timing around holiday season (Easter).
- May: Sales were low in both years and it decreased further in 2024.
- June: Sales were low in both years and it decreased further in 2024.
- July: High sales in July 2023 might have been due to a one-time event , such as a mojor promotion or special sale that was repeated this year.
- August: Increase in sales in 2024 might have been due to improved marketing strategies.
- September: Salesin this month in 2023 was more than the sales in Aug 2023 was was still in the low range.
- October, November and December: There was a drastic decreases in sales in these months which might have been caused by increase in competition and discounting in other stores.


## 7. The Highest-selling product by the total sales - SQL
![Screenshot (77)](https://github.com/user-attachments/assets/e62943f5-2b77-420f-aebb-f8f5d07b7318)
### Inferences:
### 1. Performance of the Product;
- As seen by the return of the SQL query, shoes generated the highest sales among all the products. This may indicate that there is a strong demand for foot wear.
### 2. Intervention Strategies;
- Cloudy wears should ensure that they keep popular shoe styles, sizes and colors in stock by closely monitoring inventory levels and reordering based on sales forecasts.
- They should also leverage pricing strategies that alignwith seasonal trends and offering discounts during high purchase periods.
### Conclusion
Shoes represent a high-demand category with growth potential. To amplify sales, a mix of targeted marketing and inventory management should be implemented . By doing so Cloudy Wears can maximize profitability from its top-selling product line.

## 8. The Top 5 Customers by their purchase amount - SQL
![Screenshot (80)](https://github.com/user-attachments/assets/d1590985-69fe-40ae-abf3-86846da7484c)
### Inferences:
### 1. Overall Custormers Performance;
These 5 Customers appear to be frequent customers which may reflect brand loyalty.
### 2.Strategy Intervention;
Cloudy wears should create exclusive rewards for each of the top customers e.g offering early access to new products, special discounts and also engage the customers through personalised emails or messages highlighting new arrivals.
### Conclusion
Understanding the top 5 customers by purchase amount is crucial for building loyalty and monitoring thrir life time value. By implementing targeted rewards and dedicated communication,these customers can be developed into brand ambassadors, contributing to both revenue and long-term btand loyalty.


## 9. The products with no sales in the last quarter
![Screenshot (83)](https://github.com/user-attachments/assets/b35dca5d-f15d-4a12-af17-21307d026cff)

![Screenshot (115)](https://github.com/user-attachments/assets/e72c3b41-6114-4c76-a17a-e26af17944eb)
![Screenshot (117)](https://github.com/user-attachments/assets/12b94ffb-1084-415e-b228-fb4990b8f275)
![Screenshot (118)](https://github.com/user-attachments/assets/0679a43a-c6e9-48e4-aeb9-5943c44aa918)
![Screenshot (119)](https://github.com/user-attachments/assets/c55927c8-a211-4168-8421-2f12b8ad2bf7)
![Screenshot (120)](https://github.com/user-attachments/assets/0d54225f-9f20-4854-b665-882514e0ddf8)
![Screenshot (121)](https://github.com/user-attachments/assets/8a945350-6773-4913-ac29-76a3dbcd49da)
![Screenshot (123)](https://github.com/user-attachments/assets/8d3d837d-e785-48ab-9646-16cd0e9406b2)







