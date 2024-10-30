# LITA-CAPSTONE-SALES-DATA-PROJECT

## Project Overview
This project collects data and analyses the sales performance of a retail store. The goal is to uncover key insights such as, top-selling products, regional performance and monthly sales trend. The analysis also highlights key metrics such as Total Sales by each Product, Average Sales per Product and Total Sales by Region

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
The objectives of this project was to determine and analyze the following;
- Total sales generated by each product
- Total sales generated by each region
- Total sales generated each month
- Average sales per product
- The number of Sales transactions in each region
- The Highest-selling product by the total sales
- The Top 5 Customers by their purchase amount
- Number of sales transactions in each region
- The percentage of total sales contributed by each region
- The products with no sales in the last quarter

## Data Cleaning and Exploratory Data Analysis (EDA)
- EDA alongside data cleaning was performed in this project to understand the dataset's structure, identify and handle missing values and address any data quality issues.
  - A missing colunm was added, which was the Revenue column which was found by multipling the Quantity by the Unit Price in order to know the Total Sales generated.
  - The data was checked for duplicates by highlighting the whole data in an excel sheet and clicking on the 'Remove Duplicates' in the Data tab interface.

## Data Tools and Methods Used
1. Microsoft Excel 
- For Data Cleaning
- For Analysis utilizing Pivot Tables to summarize and analyze the dataset making it easier to identify insights
- For Visualization - Bar charts were used to visually represent key insights
2. Structured Query Language(SQL) for Quering of Data
3. Power BI used for converting data from different data sources to interactive dashbords and BI reports.

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

## Inferences:
### 1. Overall Total Sales Trends;
There was a decrease of $109,570 in total sales from 2023 to 2024. This indicates a negative trend in revenue generation which was caused by ineffective pricing strategies. 
### 2. Analyzing Product Performance;
- Shirt: Had the hightest sales in the year 2023 and had a decrease in sales in 2024 due to high in price as compared to the competitors.
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
Total Sales across all regions have decreased this year compared to last year, wwith the exception of West region, which recorded total sales of $213,740.
### 2. Sales Performance by each region in each year;
- South: The South region had the highest revenue in both 2023 and 2024 but shows a drop in sales in 2024. The drop in sales may be due to increased competition in the market.
- East: Had the 2nd hightes revenue in 2023 but Shows a huge decrease in revenue in 2024. The decline in sales may indicate a rising competitor in the market andthe prices of the products were seen to be high.
- North: 
- West
North East: The North East region had the highest revenue in 2014 but shows a significant drop in 2015. This decline may indicate market saturation or increased competition.
South West: This region also shows a decrease in revenue, although it remains one of the higher-performing areas.
South South: The revenue for this region appears to have decreased slightly, indicating a potential area of concern.
South East: Similar to the South South, this region also shows a decline in revenue, which could suggest challenges in maintaining sales.
North West and North Central: Both regions show lower revenue figures, with North Central consistently trailing behind other regions.
### 3. Sales Distribution by Region;
The bar charts illustrate a clear drop in revenue for 2015 compared to 2014, indicating that while the North East led in 2014, the gap between regions has narrowed, suggesting that overall market conditions may be affecting all regions similarly.
## 3. Monthly Sales - Microsoft Excel
## Pivot Table
![Screenshot (54)](https://github.com/user-attachments/assets/9563ae3f-4685-478a-b883-d3c6b5ce10c3)
## Filtered Column Chart for Year 2023
![Screenshot (62)](https://github.com/user-attachments/assets/d903e2ac-4931-4add-886c-655f0202ab5d)
## Filtered Column Chart for Year 2024
![Screenshot (61)](https://github.com/user-attachments/assets/281b0d10-a083-4399-93fc-03d94953574a)
## Monthly Sales for Year 2024 - SQL
![Screenshot (79)](https://github.com/user-attachments/assets/8769ad09-83df-4849-92d5-e3040854c603)

## 4. The number of Sales transactions in each region - SQL
![Screenshot (76)](https://github.com/user-attachments/assets/c5b69b50-759b-4ab7-a670-2e6ec6ae708f)

## 5. The Highest-selling product by the total sales - SQL
![Screenshot (77)](https://github.com/user-attachments/assets/e62943f5-2b77-420f-aebb-f8f5d07b7318)

## 6. The Top 5 Customers by their purchase amount - SQL
![Screenshot (80)](https://github.com/user-attachments/assets/d1590985-69fe-40ae-abf3-86846da7484c)

## 7. The percentage of total sales contributed by each region-SQL
![Screenshot (81)](https://github.com/user-attachments/assets/42d5ed87-da78-41e9-bd7f-31853dad25d0)


## 9. The products with no sales in the last quarter
![Screenshot (83)](https://github.com/user-attachments/assets/b35dca5d-f15d-4a12-af17-21307d026cff)


