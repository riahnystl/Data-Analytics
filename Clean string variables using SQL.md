SELECT <br/>
 **name <br/>
 **city <br/>
FROM <br/>
 'personal project name.customer_data.customer_address' <br/>

## when the new customer is added 

INSERT INTO personal project name.customer_data.customer_address' <br/>
 (customer_id, name, address, city, state, zipcode, country)<br/>
VALUES<br/>
 (2645, 'Rachel DaSandos', '333 SQL Road', 'Jackson'. 'MI', '9202','US')<br/>

## when we are making updates on the customer information */

UPDATE  'personal project name.customer_data.customer_address'<br/>
SET address = '123 New Address'<br/>
WHERE customer_id = 2645 <br/>

## if only using total number of customers then csv file format is not needed 
## week track weekiend promotion of stores, data as csv to visualize as spreadsheet
## if we want to pull trend on a regular basis regular refresh query when written SQL is ideal 
## Create table if not exists

## when there are tables for housekeeping 

Drop table if exists
## cleaning data including DISTINCT in your SELECT statement removes duplications 
## For example, we want to get customer Ids of customers who live in Ohio 

SELECT<br/>
  DISTINCT customer_id<br/>
FROM<br/>
  'customer_data.customer_addresss'<br/>

## DISTINCT function unique customer id
## text strings a group of characters within a cell, need to be cleaned before you can analyze 
## LENGTH function to double check string variables are consistent same as LEN 

SELECT <br/>
  LENGTH(country) /*column we want to check*/ AS letters_in_country<br/>
FROM<br/>
  'customer_data.customer_address'<br/>

## query for checking data consistence which are incorrectly listed

SELECT<br/>
  country<br/>
FROM<br/>
  'customer_data.customer_address'<br/>
WHERE<br/>
  Length(country)<br/>

SELECT<br/> 
 DISTINCT customer_id /*to remove duplicates*/<br/>
FROM<br/>
  'customer_data.customer_address'<br/>
WHERE<br/>
  SUBSTR(country, 1,2) = 'US' /*first letter of each country to pull 2 letters to US only<br/>

SELECT <br/>
  state<br/>
FROM<br/>
  'customer_data.customer_address'<br/>
WHERE <br/>
  LENGTH(state) > 2 /*states that have more than 2 letter to see incorrect list */<br/> 

## TRIM function removes any spaces

SELECT<br/>
  DISTINCT customer_id<br/>
FROM<br/>
  'customer_data.customer_address'<br/>
WHERE<br/>
  TRIM(state)='OH<br/>

## Inspect length of the column if there is a maximum of 70 

SELECT  <br/>
  DISTINCT fuel_type<br/>
FROM `sql-workspace-413616.cars.car_info` LIMIT 1000<br/>
SELECT<br/>
  MIN(length) AS min_length,<br/>
  MAX(length) AS max_length<br/>
FROM<br/>
  you project name.cars.car_info<br/>
WHERE<br/>
 compression_ratio <> 70;<br/>

## if you were to dete those that did not return correct 70 value to count how many 

SELECT<br/>
 COUNT(*) AS num_of_rows_to_delete<br/>
FROM<br/>
 your project name.cars.car_info<br/>
WHERE<br/>
 compression_ratio = 70<br/>

## to delete the know with wrong value 

DELETE your project name.cars.car_info<br/>
WHERE compression_ratio = 70;<br/>

## check your data for null or missing values 

SELECT  <br/>
*<br/>
FROM `sql-workspace-413616.cars.car_info` <br/>
WHERE<br/>
  num_of_doors IS NULL;<br/>

## To fill in missing values 

UPDATE<br/>
  your project name.cars.car_info<br/>
SET<br/>
  num_of_doors = "four"<br/>
WHERE<br/>
  make = "dodge"<br/>
  AND fuel_type = "gas"<br/>
  AND body_style = "sedan";<br/>

## Identify potential errors 

SELECT<br/>
  DISTINCT num_of_cylinders<br/>
FROM<br/>
  your project name.cars.car_info;<br/>

## to correct the misspelling for all rows 

UPDATE<br/>
  your project name.cars.car_info<br/>
SET<br/>
  num_of_cylinders = "two"<br/>
WHERE<br/>
  num_of_cylinders = "tow";<br/>

## duplicate values

SELECT<br/>
  DISTINCT drive_wheels,<br/>
  LENGTH(drive_wheels) AS string_length<br/>
FROM<br/>
  your project name.cars.car_info;<br/>
UPDATE<br/>
  your project name.cars.car_info<br/>
SET<br/>
  drive_wheels = TRIM(drive_wheels)<br/>
WHERE TRUE;<br/>

## CAST function for cleaning and sorting data 

SELECT<br/>
 date<br/>
 purchase_price<br/>
FROM<br/>
   your project name.cars.car_info;<br/>
WHERE<br/>
   date BETWEEN '2020-12-01' AND '2020-12-31'<br/>
 ## date to the date time 
 SELECT<br/>
 CAST (date AS date) AS date_only,<br/>
 purchase_price<br/>
FROM<br/>
   your project name.cars.car_info;<br/>
WHERE<br/>
   date BETWEEN '2020-12-01' AND '2020-12-31'<br/>

## CONCAT () adds strings together to create new text strings that can be used as unique keys 
## to see if customers like certain colors over the others => concat function
SELECT<br/>
 CONCAT(product_code, product_color) AS new_product_code<br/>
FROM<br/>
 'your project name. customer_data.customer_purchase'<br/>
WHERE<br/>
 product = 'couch'<br/>

 ## COALESCE() returns non-null values
product name columns to understand what products are sold  product_code instead. <br/>
SELECT<br/>
 COALESCE(product, product-code) AS product_info<br/>
FROM<br/>
 'your project name. customer_data.customer_purchase'<br/>
