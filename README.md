## ☂️🌂🌞 Customer-Segmentation-Banking 🌞🌂☂️

## ☂️🌂🌞 Analytical Object🌞🌂☂️
 The goal of this analysis is to understand customer segmentation, create user personas, and identify business opportunities to increase engagement with Bank financial product.

1) CONVERT THE DATA TYPE
Check all data types to ensure they align with the data dictionary.

2) CHECKING UNIQUE VALUE AND HANDLE TYPO DATA
Review categorical values to detect and fix any inconsistencies or misspellings.

3) CHECKING MISSING VALUE AND DUPLICATE DATA
Identify and handle null values or repeated entries to maintain data quality.

4) REMOVE AGE LESS THAN 21
Exclude customers under 21 as they are not relevant to the target analysis scope.



## ☂️🌂🌞 Exploration Data Set 🌞🌂☂️
Online bank has provided several Dataset containing customer-level information, transaction history, and promotional activity, which will be used for Data Cleaning  :


<img width="397" height="139" alt="image" src="https://github.com/user-attachments/assets/71ee7999-09fd-43b3-a447-caa589dbf65d" />



## ☂️🌂🌞 Convert data type 🌞🌂☂️
 We checked whether any columns have incorrect data types and change them with df['col'] = df['col'].astype(type), as this can significantly impact the accuracy of the analysis. We updated the data types of account_id, MOB, and birth_date to ensure they align with their appropriate formats.

<img width="449" height="197" alt="image" src="https://github.com/user-attachments/assets/657c6621-7e3e-4dc4-bb7f-0323f78ed190" />


## ☂️🌂🌞 Checking unique value and handle typo data 🌞🌂☂️

We checked unique values in categorical columns. account_id has many unique entries, representing registered customers. account_activity_level and customer_value_level were validated against the data dictionary.

<img width="562" height="173" alt="image" src="https://github.com/user-attachments/assets/058dc775-1599-4371-9bc2-a3d58be64292" />


## ☂️🌂🌞 Checking missing value 🌞🌂☂️

We checked for missing values to identify any incomplete data within the dataset. We filled the missing values in avg_sales_36M with 0, as it indicates no transactions occurred, and this data will be needed for further analysis.

<img width="404" height="209" alt="image" src="https://github.com/user-attachments/assets/5a72976c-8d6c-4fee-b7fd-a822dff25d1b" />


## ☂️🌂🌞 Remove duplicate data 🌞🌂☂️
We checked for duplicates based on account_id and found duplicate entries. Therefore, duplicates need to be removed to ensure each account_id is unique. We need to remove 72 rows duplicate from 12,558 rows  to 12486 rows based on the `account_id` since 1 `account_id` in user should be only 1 per `account_id`.

<img width="271" height="162" alt="image" src="https://github.com/user-attachments/assets/7c9a7b3f-e9b8-4dfc-ba26-d33f56615f22" />



## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 Licences 🌞🌂☂️
Copyright by Diantya Pitaloka
