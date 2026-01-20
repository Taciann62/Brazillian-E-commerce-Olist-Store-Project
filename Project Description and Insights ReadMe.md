# Brazilian E-commerce Olist Store 

This project analyzes order lifecycle and delivery performance in the Brazilian Olist e-commerce platform, with a focus on customer location, order timelines, and delivery efficiency across states and cities.
The dataset integrates customer information, order status timestamps, delivery milestones, and geolocation data, enabling an in-depth examination of how geography and time influence order fulfillment.

## Project Overview
The Olist e-commerce dataset provides detailed information on customer regions, order events, delivery timelines, and geospatial coordinates. 
This project leverages these variables to evaluate operational efficiency, delivery reliability, and regional performance differences across Brazil.

### My Role
As the Business Data Analyst for this project, I was responsible for the data exploration and visualization of outcomes derived from the dataset, ensuring the reliability and accuracy of findings.

The analysis focuses on:
- Understanding and visualizing the business process model to provide insight into areas for optimization.
- Top-performing states with further analysis on product preference
- Order processing timelines (purchase → carrier dispatch → customer delivery)
- Actual vs estimated delivery performance
- Geographical patterns in order volume and delivery duration
- Temporal trends in purchasing and delivery activity
By examining these dimensions, the project aims to identify logistical bottlenecks, regional delivery disparities, and opportunities for process optimization, ultimately supporting improved customer experience and data-driven operational decisions.

### Tools 
- Google BigQuery (SQL) - Data Wrangling and Analysis
- Tableau - Data Visualisation
- LucidChart - Business Process Modelling
- Kaggle - Data Source

### Business Process Model
The dataset provided insight into the processes the stores takes from when the customers place thier orders to when they receive their parcel.

<img width="2150" height="1590" alt="Brazillian E-commerce Sales" src="https://github.com/user-attachments/assets/37ed4ed3-79ff-41b3-ae9a-a71a5ad551bf" />


The data analysis was broke diown into sections, based on the necessary focus. The first dataset merged was the Customers data and the Orders data to enable scalability and simplicity of analysis.
The merged data were a total of 99441 distinct data rows and 23 columns, following the formatting of the date section, year, month and the difference between the time of order approval and delivery to the receiver. 

Aggregate Analysis for the Years contained in the data.
```SQL
SELECT SUM(Day_till_delivery) AS SUM,
       AVG(Day_till_delivery) AS AVG,
       order_delivered_customer_year
FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customers_Orders` 

group by
      order_delivered_customer_year
```
Result: 
|  Year   |   Total    	|  Average     |
|---------|-------------|--------------|
|   2017  |  498894     | 	12.2       |
|   2018  |  701444     |   12.7       |
|   2016	|  5355   	  |   19.7       |






The status of the purchases was labelled Delivered, Cancelled, Created, and the counts through the years 2017 and 2016 were overall as 
|  No  | Order_Status	|  Count       |
|------|--------------|--------------|
|   1  | 	Delivered   | 	22418      |
|   2  |  Canceled	  |   2174       |
|   3	 |  Created	    |   39         |



TOP 5 States by Purchasing Frequency
| No   | Total	|customer_state|
|------|--------|--------------|
|   1  | 	6317  | 	RJ         |
|   2  |  5282	|   SP         |
|   3	 |  4096	|   MG         |
|   4	 |  1620  |	  RS         |
|   5  |  1344  |   BA         |

LEAST 5 States by Purchasing Frequency
| No  | Total	|customer_state|
|------|--------|--------------|
|  1   |  54    |	   AM        |
|  2	 |  34	  |    TO        |
|  3   | 	33	  |    AC        |
|  4   |  22	  |    AP        |
|  5   | 	9	    |    RR        |
