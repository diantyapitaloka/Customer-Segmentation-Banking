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



## ☂️🌂🌞 Remove age less than 21 🌞🌂☂️
We will remove customers who are under 21 years old to align with the analysis requirements.

The code as below :

```
# Determine the cutoff date
cutoff_date = datetime(2023, 5, 31)

# Calculate age using vectorization
df_sales_dc['age'] = (cutoff_date - df_sales_dc['birth_date']).dt.days // 365

# Filter data (remove ages below 21)
df_sales_dc = df_sales_dc[df_sales_dc['age'] >= 21]

# Show the result
df_sales_dc

```


## ☂️🌂🌞 Total Sales in the past 3 Years 🌞🌂☂️

Total sales in the last 3 years is €405,580,520. That figure can be compared against business targets (if available) or with the previous period (if such data exists).

<img width="430" height="116" alt="image" src="https://github.com/user-attachments/assets/0546cfe4-87a0-4e8d-9a11-18c56188fc15" />


## ☂️🌂🌞 Clients with no sales 🌞🌂☂️

Over the past 36 months, 93.91% of the activity resulted in sales — a strong indicator of market demand and effective conversion.

Only 6.09% showed no sales, suggesting minimal friction in the sales funnel.

<img width="255" height="191" alt="image" src="https://github.com/user-attachments/assets/6bb33c8e-6248-4f6d-aab6-d18cc3eec2b1" />


## ☂️🌂🌞 Level X is the most transacting 🌞🌂☂️

Despite similar recency in transactions across all activity levels (18-19 months), there’s a clear difference in engagement: Level X clients are the most active, averaging 3.28 transactions, while Level Z clients are the least active, with just 1.22 transactions. 
This suggests that activity level is driven more by transaction frequency over time than by recent transactions.

<img width="233" height="313" alt="image" src="https://github.com/user-attachments/assets/a1947aee-a118-46fa-912c-79ec4b685041" />



## ☂️🌂🌞 Comparing profits of gender 🌞🌂☂️

Male and female customers generate almost the same median profit, but female customers show a slightly higher upper range and maximum value — reaching up to 5,865.6 vs. 5,400 for males.

While both genders perform similarly on average, female customers have more high-profit outliers — a potential segment for upselling or premium targeting.


## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 A 🌞🌂☂️

## ☂️🌂🌞 Licences 🌞🌂☂️
Copyright by Diantya Pitaloka
