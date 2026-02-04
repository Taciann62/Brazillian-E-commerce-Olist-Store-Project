CREATE TABLE `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.data_set` AS
SELECT
  order_id AS order_id,
  customer_id AS customer_id,
  order_status AS order_status,
  DATETIME(order_purchase_timestamp) AS order_purchase_timestamp,
  DATETIME(order_approved_at) AS order_approved_at,
  DATETIME(order_delivered_carrier_date) AS order_delivered_carrier_date,
  DATETIME(order_delivered_customer_date) AS order_delivered_customer_date,
  DATETIME(order_estimated_delivery_date) AS order_estimated_delivery_date


FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Orders_dataset`;

SELECT *,
       CAST(order_approved_date AS DATE)           AS order_approved_date,
       CAST(order_approved_time AS TIME)           AS order_approved_time,
       CAST(order_purchase_date AS DATE)           AS order_purchased_date,
       CAST(order_purchase_time AS time)           AS order_purchase_time,
       CAST(order_delivered_carrier_date AS DATE)  AS order_delivered_carrier_date,
       CAST(order_delivered_carrier_time AS TIME)  AS order_delivered_carrier_time,
       CAST(order_delivered_customer_date AS DATE) AS order_delivered_customer_date,
       CAST(order_delivered_customer_time AS TIME) AS order_delivered_customer_time,
       CAST(order_estimated_delivery_date AS DATE) AS order_estimated_delivery_date,
       CAST(order_estimated_delivery_time AS TIME) AS order_estimated_delivery_time


 FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Orders`


To join the datasets:
SELECT  C.customer_id,
        C.customer_city,
        C.customer_state,
        C.customer_unique_id,
        C.customer_zip_code_prefix,
        O.order_id,
        O.order_status,
        O.order_approved_at,
        O.order_delivered_carrier_date,
        O.order_delivered_customer_date,
        O.order_estimated_delivery_date,
        O.order_purchase_timestamp
       


 FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customers_Dataset` C




LEFT JOIN `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Order_data` O ON C.customer_id = O.customer_id




SELECT *,
        TIMESTAMP_DIFF(order_delivered_customer_date, order_purchase_timestamp, DAY) AS Day_till_delivery,
        TIMESTAMP_DIFF(order_delivered_customer_date, order_purchase_timestamp, MINUTE) AS Time_till_delivery
       
FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customer_Orders_Bind`


WHERE order_purchase_timestamp IS NOT NULL AND
      order_delivered_customer_date IS NOT NULL




with Customers_Orders AS
(SELECT customer_id,
        customer_city,
        customer_state,
        customer_unique_id,
        customer_zip_code_prefix,
        order_id,
        order_status,
        order_approved_at,
        order_delivered_carrier_date,
        order_delivered_customer_date,
        order_estimated_delivery_date,
        order_purchase_timestamp,
        TIMESTAMP_DIFF(order_delivered_customer_date, order_purchase_timestamp, DAY) AS Day_till_delivery,
        TIMESTAMP_DIFF(order_delivered_customer_date, order_purchase_timestamp, MINUTE) AS Time_till_delivery
        
FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customer_Orders_Bind`)

SELECT *,
     EXTRACT(YEAR FROM order_purchase_timestamp)           AS order_purchased_year,
     EXTRACT(YEAR FROM order_approved_at)                  AS order_approved_year,
     EXTRACT(YEAR FROM order_delivered_carrier_date)       AS order_delivered_carrier_year,
     EXTRACT(YEAR FROM order_delivered_customer_date)     AS order_delivered_customer_year,
     EXTRACT(YEAR FROM order_estimated_delivery_date )     AS order_estimated_delivery_year,
     
     CASE 
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 1 THEN 'January'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 2 THEN 'February'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 3 THEN 'March'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 4 THEN 'April'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 5 THEN 'May'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 6 THEN 'June'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 7 THEN 'July'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 8 THEN 'August'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 9 THEN 'September'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 10 THEN 'October'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 11 THEN 'November'
        WHEN EXTRACT(MONTH FROM order_purchase_timestamp) = 12 THEN 'December'
    END AS order_purchased_month,

    CASE 
        WHEN EXTRACT(MONTH FROM order_approved_at) = 1 THEN 'January'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 2 THEN 'February'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 3 THEN 'March'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 4 THEN 'April'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 5 THEN 'May'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 6 THEN 'June'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 7 THEN 'July'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 8 THEN 'August'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 9 THEN 'September'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 10 THEN 'October'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 11 THEN 'November'
        WHEN EXTRACT(MONTH FROM order_approved_at) = 12 THEN 'December'
    END AS order_approved_month,

 CASE 
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 1 THEN 'January'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 2 THEN 'February'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 3 THEN 'March'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 4 THEN 'April'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 5 THEN 'May'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 6 THEN 'June'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 7 THEN 'July'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 8 THEN 'August'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 9 THEN 'September'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 10 THEN 'October'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 11 THEN 'November'
        WHEN EXTRACT(MONTH FROM order_delivered_carrier_date) = 12 THEN 'December'
    END AS order_delivered_carrier_month,


    CASE 
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 1 THEN 'January'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 2 THEN 'February'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 3 THEN 'March'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 4 THEN 'April'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 5 THEN 'May'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 6 THEN 'June'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 7 THEN 'July'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 8 THEN 'August'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 9 THEN 'September'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 10 THEN 'October'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 11 THEN 'November'
        WHEN EXTRACT(MONTH FROM order_delivered_customer_date) = 12 THEN 'December'
    END AS order_delivered_customer_month,

 CASE 
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 1 THEN 'January'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 2 THEN 'February'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 3 THEN 'March'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 4 THEN 'April'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 5 THEN 'May'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 6 THEN 'June'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 7 THEN 'July'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 8 THEN 'August'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 9 THEN 'September'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 10 THEN 'October'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 11 THEN 'November'
        WHEN EXTRACT(MONTH FROM order_estimated_delivery_date) = 12 THEN 'December'
    END AS order_estimated_delivery_month,


FROM Customers_Orders
ORDER BY Customers_Orders.Day_till_delivery DESC


## Insights into the sales by customer state, year, deriving SUM, AVG, SDV and FREQUENCY
                       
SELECT order_delivered_customer_year,
       customer_state,
       COUNT(customer_state) AS Frequency,
       SUM (Day_till_delivery) AS Sum_Day_till_delivery,
       AVG(Day_till_delivery) AS AVG_Day_till_delivery,
       STDDEV_SAMP(Day_till_delivery) AS SDV_Day_till_delivery

FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customers_Orders` 

WHERE order_delivered_customer_year IS NOT NULL

GROUP BY order_delivered_customer_year,
                       customer_state
ORDER BY Frequency DESC




## Insights into the sales by customer statederiving SUM, AVG, SDV and FREQUENCY

SELECT customer_state,
       COUNT(customer_state) AS Frequency,
       SUM (Day_till_delivery) AS Sum_Day_till_delivery,
       AVG(Day_till_delivery) AS AVG_Day_till_delivery,
       STDDEV_SAMP(Day_till_delivery) AS SDV_Day_till_delivery

FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customers_Orders` 

GROUP BY               customer_state
ORDER BY Frequency DESC


SELECT customer_state,
       SUM(TIMESTAMP_DIFF(order_approved_at, order_purchase_timestamp,MINUTE)) AS Difftime_approved_purchased,
       SUM(TIMESTAMP_DIFF(order_approved_at, order_purchase_timestamp, DAY))   AS Diffday_approved_purchased
FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customers_Orders` 

GROUP BY customer_state


## ORDER APPROVAL AND PURCHASE
SELECT customer_state,
       order_approved_year,
       order_approved_month,
       SUM(TIMESTAMP_DIFF(order_approved_at, order_purchase_timestamp, DAY))   AS Diffday_approved_purchased,
       AVG(TIMESTAMP_DIFF(order_approved_at, order_purchase_timestamp, DAY))   AS Average,
       COUNT(customer_state)                                                   AS Frequency
FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customers_Orders`

WHERE order_approved_at IS NOT NULL

GROUP BY customer_state,
         order_approved_year,
         order_approved_month


## ORDER STATUS
SELECT customer_state,
       order_status,
       order_approved_year,
       order_approved_month,
       SUM(TIMESTAMP_DIFF(order_approved_at, order_purchase_timestamp, DAY))   AS Diffday_approved_purchased,
       AVG(TIMESTAMP_DIFF(order_approved_at, order_purchase_timestamp, DAY))   AS Average,
       COUNT(customer_state)                                                   AS Frequency
FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customers_Orders`

WHERE order_approved_at IS NOT NULL

GROUP BY customer_state,
         order_approved_year,
         order_approved_month,
         order_status


## BIND ORDER ITEMS AND PURCHASE CATEGORY
SELECT  P.product_id,
        P.product_category_name,
        P.product_description_lenght,
        P.product_height_cm,
        P.product_length_cm,
        P.product_name_lenght,
        P.product_photos_qty,
        P.product_weight_g,
        P.product_width_cm,
        O.order_id,
        O.order_item_id,
        O.seller_id,
        O.shipping_limit_date,
        O.price,
        O.freight_value


FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Products_Dataset` P

LEFT JOIN `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Order_items` O ON P.product_id = O.product_id


WHERE product_category_name IS NOT NULL


SELECT  
        C.customer_id,
        C.customer_city,
        C.customer_state,
        C.customer_unique_id,
        C.order_id,
        C.order_purchase_timestamp,
        C.order_purchased_month,
        C.order_purchased_year,
        C.order_status,
        C.order_approved_at,
        C.order_approved_month,
        C.order_approved_year,
        C.order_delivered_carrier_date,
        C.order_delivered_carrier_month,
        C.order_delivered_carrier_year,
        C.order_delivered_customer_date,
        C.order_delivered_customer_month,
        C.order_delivered_customer_year,
        C.order_estimated_delivery_date,
        C.order_estimated_delivery_month,
        C.order_estimated_delivery_year,
        C.Day_till_delivery,
        G.geolocation_city,
        G.geolocation_lat,
        G.geolocation_lng,
        G.geolocation_state
        

FROM `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Customers_Orders` C

LEFT JOIN `rugged-sunbeam-415914.Brazillian_Ecommerce_Olist_Stores.Olist_Geolocation` G ON C.customer_zip_code_prefix = G.geolocation_zip_code_prefix







