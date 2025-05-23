# GameZone Sales Analysis
## Objective
Explore Gamezones data, cleaning data so that it can be usable for analysis. Once data is clean I will use any dimensions available to determine any trends in the data set and establish key metrics for the companies performance

## Dataset
Total Rows in Dataset : 21864
Fixed types of USER_ID, PRODUCT_ID to text
- USER_ID : User Identifier (Text)
- ORDER_ID : Order Identifier (Text)
- PURCHASE_TS : Date of purchase YYYY/MM/DD (Date)
- SHIP_TS : Shipping Date YYYY/MM/DD (DATE)
- PRODUCT_NAME : Name of Product (Text)
- PRODUCT_ID : Product Identifier (Text)
- USD_PRICE : Sell Price in US (Number)
- PURCHASE_PLATFORM : Sale Channel (Text)
- MARKETING_CHANNEL : Marketing Source (Text)
- ACCOUNT_CREATION : Account Creation Method (Text)
- COUNTRY_CODE : Country of Sale (Text)
- REGION: Joined on COUNTRY_CODE
  

## Cleaning Data
Addressing errors/outlier in dataset
-  Region had many errors, created new Region cleaned column based on Region applying rules to impute region values where appropriate
-  Changing Null values to 0 to be addressed later by data engineering or removed for analysis purposes (39 Rows 0.1% of Dataset)
  
![image](https://github.com/user-attachments/assets/0219b606-2da0-4f62-8d98-4b56966efc3b)
-  USD_PRICE has null and 0 values, these should be removed for analysis and data engineering should be contacted to address 0/null values (34 Rows 0.1% of Dataset)
-  Also resolved formatting differences when making _CLEAN version of column
  
![image](https://github.com/user-attachments/assets/b4e70d73-f415-493c-a575-11cc652ce944)
![image](https://github.com/user-attachments/assets/66c6c8aa-60de-4c87-90d4-f3e283ecf79d)

-  Account Creation Method has 743 Unknown Values, Cannot impute value
-  Marketing Channel Null/Unknown in 130 Rows, Change null values to Unknown
-  Product Name has two different names for 27in 4K Gaming monitor 61 rows appear to be named incorrectly, will change the values for the purpose analysis as they are similar if not the same item
-  Null values in date, choosing to omit rows without a date sold since the value cannot be imputed
-  Adding Days to Ship metric, could be useful for operations
-  Filtering out any rows null PURCHASE_TS USD_PRICE or COUNTRY_CODE as data is nonsensical

-  Replace and rename any columns which needed to be cleaned as described above
-  Data is ready for Dashboard
