## ☂️🌂🌞 Market Segmentation Banking 🌞🌂☂️ 

- The primary objective of this analysis is to thoroughly examine customer segmentation to better understand the characteristics, behaviors, and purchasing patterns of DaintyBank’s customer base. By summarizing sales performance across different customer groups, this study aims to identify which segments contribute the most to revenue and which require further attention.
- Additionally, the analysis seeks to develop comprehensive customer personas that represent key target audiences, enabling more personalized and effective marketing strategies.

- Furthermore, the insights gained from this research will be used to uncover new business opportunities that can strengthen customer engagement and encourage greater adoption of DaintyBank’s financial products. Ultimately, this analysis supports data-driven decision-making, optimizes product offerings, and enhances long-term customer relationships.

- AI and Machine Learning (ML) move segmentation beyond basic demographics (like age or income) to highly detailed behavioral, psychographic, and transactional segments.

- Long-Term Purpose: The ultimate goal is to offer hyper-personalized products, services, and communication at the right time through the right channel. AI analyzes massive datasets—including real-time transaction history, channel usage (mobile vs. branch), sentiment analysis from call center logs, and web navigation—to predict individual customer needs and their propensity to purchase specific products (e.g., a mortgage, an investment product, or a personal loan).

- Benefit: This level of personalization significantly increases the Customer Lifetime Value (CLV) and leads to higher conversion rates for marketing campaigns, as customers receive offers that are genuinely relevant to their current financial situation and life stage.

- Market Segmentation in Banking is the process of partitioning the broad banking market into distinct subsets of customers who are expected to respond similarly to a particular marketing strategy. The segments created are identifiable, substantial (large and profitable enough to serve), accessible (reachable through marketing efforts), and responsive (different from other segments in their reaction to a marketing mix).

- The core principle is to move from mass marketing to targeted marketing. Instead of offering a generic checking account to everyone, a bank might create a "Student Success Account" for one segment and a "Premier Wealth Account" for another, recognizing their vastly different life stages, incomes, and financial goals.
- Market segmentation in banking is the process of dividing a bank's entire customer base or potential market into smaller, distinct groups, or segments, that share similar characteristics, needs, or behaviors.
- Instead of treating all customers as one homogenous group, banks use segmentation to recognize the diversity in their market and tailor their products, services, marketing messages, and service delivery to meet the specific requirements of each segment. This allows the bank to operate more efficiently, enhance customer satisfaction, and improve profitability.
- Market segmentation in banking is the process of dividing a bank's entire customer base or potential market into smaller, distinct groups, or segments, that share similar characteristics, needs, or behaviors.

- Instead of treating all customers as one homogenous group, banks use segmentation to recognize the diversity in their market and tailor their products, services, marketing messages, and service delivery to meet the specific requirements of each segment. This allows the bank to operate more efficiently, enhance customer satisfaction, and improve profitability.
- -Bases for Market Segmentation. Banks typically use a combination of different bases to create their segments. The main categories include: Demographic Segmentation: Dividing the market based on measurable population characteristics.

### Dataset :
Please find dataset below:

1. DaintyBank : https://drive.google.com/file/d/1dXE7wrsL37LhWl962gqluv6ZOuEnn_zG/view?usp=drive_link
2. Dictionary : https://docs.google.com/spreadsheets/d/1YO7D80qVsSC73J1ERl-GqxYYLLDqdjE5/edit?usp=sharing&ouid=108812084155815508815&rtpof=true&sd=true

### Outline  :
Please find outline below:

1. Data Extraction
2. Data Cleaning
3. Exploratory Data Analysis
4. Customer Segmentation
5. Insights and Business Recommendation

### Objective :

1. Identify customer segmentation to increase engagement financial product
2. Optimize which insights can attract the increase engagement financial product



## ☂️🌂🌞 Analytical Object🌞🌂☂️
The goal of this analysis project is to understand customer segmentation, create user personas, and identify business opportunities to increase engagement with Bank financial product. Here is the objectives below:

1) CONVERT THE DATA TYPE
Check all data types to ensure they align with the data dictionary.

2) CHECKING UNIQUE VALUE AND HANDLE TYPO DATA
Review categorical values to detect and fix any inconsistencies or misspellings.

3) CHECKING MISSING VALUE AND DUPLICATE DATA
Identify and handle null values or repeated entries to maintain data quality.

4) REMOVE AGE LESS THAN 21
Exclude customers under 21 as they are not relevant to the target analysis scope.



## ☂️🌂🌞 Exploration Data Set 🌞🌂☂️
Online bank has provided several Dataset containing customer-level information, transaction history, and promotional activity, which will be used for Data Cleaning.
Here is the exploration dataset:


<img width="397" height="139" alt="image" src="https://github.com/user-attachments/assets/71ee7999-09fd-43b3-a447-caa589dbf65d" />



## ☂️🌂🌞 Convert Data Type 🌞🌂☂️
Checked whether any columns have incorrect data types and change them with df['col'] = df['col'].astype(type), as this can significantly impact the accuracy of the analysis. We updated the data types of account_id, MOB, and birth_date to ensure they align with their appropriate formats. Here is the objectives below:

<img width="449" height="197" alt="image" src="https://github.com/user-attachments/assets/657c6621-7e3e-4dc4-bb7f-0323f78ed190" />


## ☂️🌂🌞 Checking Unique Value and Handle Typo Data 🌞🌂☂️

Checked unique values in categorical columns. account_id has many unique entries, representing registered customers. account_activity_level and customer_value_level were validated against the data dictionary. As below :

<img width="562" height="173" alt="image" src="https://github.com/user-attachments/assets/058dc775-1599-4371-9bc2-a3d58be64292" />


## ☂️🌂🌞 Checking missing value 🌞🌂☂️

We checked for missing values to identify any incomplete data within the dataset. We filled the missing values in avg_sales_36M with 0, as it indicates no transactions occurred, and this data will be needed for further analysis. Here is the objectives below:

<img width="404" height="209" alt="image" src="https://github.com/user-attachments/assets/5a72976c-8d6c-4fee-b7fd-a822dff25d1b" />


## ☂️🌂🌞 Remove Duplicate Data 🌞🌂☂️
We checked for duplicates based on account_id and found duplicate entries. Therefore, duplicates need to be removed to ensure each account_id is unique. We need to remove 72 rows duplicate from 12,558 rows  to 12486 rows based on the `account_id` since 1 `account_id` in user should be only 1 per `account_id`. Here is the objectives below:

<img width="271" height="162" alt="image" src="https://github.com/user-attachments/assets/7c9a7b3f-e9b8-4dfc-ba26-d33f56615f22" />



## ☂️🌂🌞 Remove Age Less Than 21 🌞🌂☂️
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


## ☂️🌂🌞 Total Sales in The Past 3 Years 🌞🌂☂️

Total sales in the last 3 years is €405,580,520. That figure can be compared against business targets (if available) or with the previous period (if such data exists). Here is the objectives below:


<img width="430" height="116" alt="image" src="https://github.com/user-attachments/assets/0546cfe4-87a0-4e8d-9a11-18c56188fc15" />


## ☂️🌂🌞 Clients with No Sales 🌞🌂☂️

Over the past 36 months, 93.91% of the activity resulted in sales — a strong indicator of market demand and effective conversion.

Only 6.09% showed no sales, suggesting minimal friction in the sales funnel. Here is the objectives below:

<img width="255" height="191" alt="image" src="https://github.com/user-attachments/assets/6bb33c8e-6248-4f6d-aab6-d18cc3eec2b1" />


## ☂️🌂🌞 Level X is The Most Transacting 🌞🌂☂️

Despite similar recency in transactions across all activity levels (18-19 months), there’s a clear difference in engagement: Level X clients are the most active, averaging 3.28 transactions, while Level Z clients are the least active, with just 1.22 transactions. 
This suggests that activity level is driven more by transaction frequency over time than by recent transactions.

<img width="233" height="313" alt="image" src="https://github.com/user-attachments/assets/a1947aee-a118-46fa-912c-79ec4b685041" />



## ☂️🌂🌞 Comparing Profits of Gender 🌞🌂☂️

For comparing profits of gender, Male and female customers generate almost the same median profit, but female customers show a slightly higher upper range and maximum value — reaching up to 5,865.6 vs. 5,400 for males.

While both genders perform similarly on average, female customers have more high-profit outliers — a potential segment for upselling or premium targeting.

<img width="203" height="293" alt="image" src="https://github.com/user-attachments/assets/e7cd28ac-1fd3-45c0-90b6-624225f288d4" />


## ☂️🌂🌞 Proportion of Total Sales Based on Generations 🌞🌂☂️

The proportion of total sales, sales are fairly evenly distributed across generations, with Gen Z leading slightly at 25.6%, followed closely by Boomers and Gen X at 25.5%, and Gen Y at 23.5%. 

This indicates a balanced contribution to total sales, with no single generation dominating.

<img width="234" height="254" alt="image" src="https://github.com/user-attachments/assets/66a1058e-cd1e-4eb9-8687-e846fcbd843f" />



## ☂️🌂🌞 Proportion of Avg Sales Based on Generations 🌞🌂☂️
Gen X takes the lead! With the highest share of average sales at 27.1%, Gen X shows strong and consistent purchasing power. Gen Y follows closely at 26.2%, highlighting their value as a core consumer segment. Here is the objectives below:

Meanwhile, Boomers (24%) and Gen Z (22.7%) contribute slightly less—possibly reflecting different spending habits or lifestyle priorities. Shown as below :


<img width="230" height="254" alt="image" src="https://github.com/user-attachments/assets/04f4487e-6584-4f9b-9781-999bdf454a86" />


## ☂️🌂🌞 Proportion of Count of Sales Based on Generations 🌞🌂☂️

Boomers dominate the numbers. With a massive 51.3% of total sales, Boomers clearly drive the most transactions—likely due to higher purchase frequency or loyalty. Gen X also plays a strong role at 29.9%, while Gen Y contributes moderately (17.5%). 

Interestingly, Gen Z accounts for only 1.3%, signaling a major engagement gap.
Here is the objectives below:

<img width="232" height="254" alt="image" src="https://github.com/user-attachments/assets/c258ff61-474a-4a2a-8012-410a5f5c09bd" />


## ☂️🌂🌞 Increase Marketing vs Sales Performance 🌞🌂☂️
An increased number of direct promo messages generally leads to higher total sales, especially after surpassing 10 messages. However, fluctuations at certain points suggest that message quality, timing, or audience targeting may also significantly influence effectiveness.

<img width="325" height="194" alt="image" src="https://github.com/user-attachments/assets/016112b5-70e4-46b2-b206-1833f1a2e736" />


## ☂️🌂🌞 K-Means Clustering 🌞🌂☂️

Using this method K-Means is a simple, fast, and easy-to-interpret method, making it ideal for segmenting customers based on their behavior and targeting marketing strategies more effectively.


## ☂️🌂🌞 Data Preprocessing 🌞🌂☂️

To increase customer engagement with Bank products, we will segment customers based on total_sales_L36M and cnt_sales_L36M. These features were chosen as segmentation criteria due to their strong relevance to product usage at Bank.
Total Sales (total_sales_L36M): Represents the total amount spent by a customer over the last 36 months. Customers with higher total sales are likely more engaged, making them prime targets for marketing campaigns.
Count of Sales (cnt_sales_L36M): Represents the number of transactions over the last 36 months. Frequent buyers are typically loyal customers, and segmenting by this feature helps RevoBank focus on high-frequency users for additional products or services.

<img width="164" height="201" alt="image" src="https://github.com/user-attachments/assets/ec7130f0-1dab-4ba0-bb78-4dc73783e2d3" />


## ☂️🌂🌞 Robust Scaler 🌞🌂☂️

Received the recommendation to use RobustScaler as the method. RobustScaler is ideal for datasets with outliers because it scales the data based on the median and interquartile range (IQR), making it more robust to extreme values as below:

<img width="191" height="195" alt="image" src="https://github.com/user-attachments/assets/1729d3a5-eb90-4319-a7b8-21abed744196" />



## ☂️🌂🌞 Determine Cluster Number 🌞🌂☂️
Choosing k = 4 is ideal because it hits the elbow point where adding more clusters yields minimal improvement, maintains a strong silhouette score for clear separation, offers meaningful insights without overcomplicating the model, and balances accuracy with interpretability. Here is the objectives below:


<img width="208" height="307" alt="image" src="https://github.com/user-attachments/assets/8eb26cda-5e76-44d6-ad93-ca9dd1de29a1" />


## ☂️🌂🌞 K-Means Clustering Modelling 🌞🌂☂️

K-Means clustering as below :

Cluster 0 – "Dormant Shoppers" : Customers with low frequency and low total sales. (Focus: Re-engagement through promotions and reminders)
Cluster 1 – "Power Buyers" :  Most active and loyal customers with the highest total sales. (Focus: Retention, exclusive rewards, upselling)
Cluster 2 – "Big Spenders” : Infrequent shoppers but with high purchase amounts. (Focus: Increase purchase frequency with targeted incentives)
Cluster 3 – "Value Seekers" : Low transaction frequency but higher spending than Cluster 0. (Focus: Personalized high-value offers and loyalty building)

<img width="229" height="296" alt="image" src="https://github.com/user-attachments/assets/c4c7f966-cb51-4f22-8057-5d1519481f02" />


## ☂️🌂🌞 Segment Summary 🌞🌂☂️

Based on the no-sales proportion analysis, only Cluster 0 shows a potential issue with 13.7% of entries generating no sales, indicating underperforming or less relevant products or segments. In contrast, Clusters 1, 2, and 3 demonstrate strong performance with 0% no-sales proportion, making them ideal targets for retention and growth strategies due to their consistent contribution to sales.

<img width="559" height="70" alt="image" src="https://github.com/user-attachments/assets/b81d1e28-ea47-44cd-85e1-3648f1a61681" />

## ☂️🌂🌞 Details Action 🌞🌂☂️

In AI and data analysis, “Details Action” refers to a specific, well-defined step or behavior that the system takes in response to certain inputs or conditions, usually after a broader decision has been made. It focuses on how the AI executes a task at a granular level—such as retrieving particular data, generating specific outputs, or modifying elements within a process—to achieve a desired outcome. By breaking tasks into detailed actions, AI systems can operate more accurately, automate complex workflows, and provide clearer traceability in decision-making.

<img width="521" height="176" alt="image" src="https://github.com/user-attachments/assets/ecafa05b-80d4-47ae-8113-18247d63bf77" />



## ☂️🌂🌞 Insight and Recommendation 🌞🌂☂️

- The goal of these recommendations is to increase Bank’s credit card product usage.
- By targeting clusters with the right offers, we’ll align with the Performance Management team’s objective to increase customer engagement and drive higher product adoption.
- For Cluster 1, Cluster 2, and Cluster 3, the focus is on personalized offers and upselling to high-value users.
- For Cluster 0, the focus should be on re-engagement and boosting transaction frequency to activate customers who haven't engaged recently.

<img width="1996" height="188" alt="image" src="https://github.com/user-attachments/assets/343e710e-24d4-4e10-9b9d-bb3b2d46e79e" />




## ☂️🌂🌞 Licences 🌞🌂☂️
Copyright by Diantya Pitaloka
