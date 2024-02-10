SELECT <br/>
 **name 
 **city
FROM
 'personal project name.customer_data.customer_address'

## when the new customer is added 

INSERT INTO personal project name.customer_data.customer_address'
 (customer_id, name, address, city, state, zipcode, country)
VALUES
 (2645, 'Rachel DaSandos', '333 SQL Road', 'Jackson'. 'MI', '9202','US')

## when we are making updates on the customer information */

UPDATE  'personal project name.customer_data.customer_address'
SET address = '123 New Address'
WHERE customer_id = 2645 

## if only using total number of customers then csv file format is not needed 
## week track weekiend promotion of stores, data as csv to visualize as spreadsheet
## if we want to pull trend on a regular basis regular refresh query when written SQL is ideal 
## Create table if not exists

## when there are tables for housekeeping 

Drop table if exists
## cleaning data including DISTINCT in your SELECT statement removes duplications 
## For example, we want to get customer Ids of customers who live in Ohio 

SELECT
  DISTINCT customer_id
FROM
  'customer_data.customer_addresss'

## DISTINCT function unique customer id
## text strings a group of characters within a cell, need to be cleaned before you can analyze 
## LENGTH function to double check string variables are consistent same as LEN 

SELECT 
  LENGTH(country) /*column we want to check*/ AS letters_in_country
FROM
  'customer_data.customer_address'

## query for checking data consistence which are incorrectly listed

SELECT
  country
FROM
  'customer_data.customer_address'
WHERE
  Length(country)

SELECT 
 DISTINCT customer_id /*to remove duplicates*/
FROM
  'customer_data.customer_address'
WHERE
  SUBSTR(country, 1,2) = 'US' /*first letter of each country to pull 2 letters to US only

SELECT 
  state
FROM
  'customer_data.customer_address'
WHERE 
  LENGTH(state) > 2 /*states that have more than 2 letter to see incorrect list */ 

## TRIM function removes any spaces

SELECT
  DISTINCT customer_id
FROM
  'customer_data.customer_address'
WHERE
  TRIM(state)='OH

## Inspect length of the column if there is a maximum of 70 

SELECT  
  DISTINCT fuel_type
FROM `sql-workspace-413616.cars.car_info` LIMIT 1000
SELECT
  MIN(length) AS min_length,
  MAX(length) AS max_length
FROM
  you project name.cars.car_info
WHERE
 compression_ratio <> 70;

## if you were to dete those that did not return correct 70 value to count how many 

SELECT
 COUNT(*) AS num_of_rows_to_delete
FROM
 your project name.cars.car_info
WHERE
 compression_ratio = 70

## to delete the know with wrong value 

DELETE your project name.cars.car_info
WHERE compression_ratio = 70;

## check your data for null or missing values 

SELECT  
*
FROM `sql-workspace-413616.cars.car_info` 
WHERE
  num_of_doors IS NULL;

## To fill in missing values 

UPDATE
  your project name.cars.car_info
SET
  num_of_doors = "four"
WHERE
  make = "dodge"
  AND fuel_type = "gas"
  AND body_style = "sedan";

## Identify potential errors 

SELECT
  DISTINCT num_of_cylinders
FROM
  your project name.cars.car_info;

## to correct the misspelling for all rows 

UPDATE
  your project name.cars.car_info
SET
  num_of_cylinders = "two"
WHERE
  num_of_cylinders = "tow";

## duplicate values

SELECT
  DISTINCT drive_wheels,
  LENGTH(drive_wheels) AS string_length
FROM
  your project name.cars.car_info;
UPDATE
  your project name.cars.car_info
SET
  drive_wheels = TRIM(drive_wheels)
WHERE TRUE;

## CAST function for cleaning and sorting data 

SELECT
 date
 purchase_price
FROM
   your project name.cars.car_info;
WHERE
   date BETWEEN '2020-12-01' AND '2020-12-31'
 ## date to the date time 
 SELECT
 CAST (date AS date) AS date_only,
 purchase_price
FROM
   your project name.cars.car_info;
WHERE
   date BETWEEN '2020-12-01' AND '2020-12-31'

## CONCAT () adds strings together to create new text strings that can be used as unique keys 
## to see if customers like certain colors over the others => concat function
SELECT
 CONCAT(product_code, product_color) AS new_product_code
FROM
 'your project name. customer_data.customer_purchase'
WHERE
 product = 'couch'

 ## COALESCE() returns non-null values
product name columns to understand what products are sold  product_code instead. 
SELECT
 COALESCE(product, product-code) AS product_info
FROM
 'your project name. customer_data.customer_purchase'
