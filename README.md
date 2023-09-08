# Python.CustomerSegmentation
Read my code here: https://colab.research.google.com/drive/1FbgaAECbObLFIB5iGo32A_9AvtCf3ogQ#scrollTo=2ed64ddd

**Customer Segmentation using RFM Model - Python Project**
**Problem:**
The objective of this project is to perform customer segmentation based on the RFM (Recency - Frequency - Monetary) model. Customer segmentation allows businesses, in this case, SuperStore Company, to understand their customers better and tailor marketing campaigns and special care to each customer group, thereby increasing customer loyalty and revenue.

**Context:**
SuperStore Company is a global retail company with a large customer base. To express gratitude to customers for their support during the past year and attract potential customers to become loyal patrons, the Marketing Department plans to run marketing campaigns during Christmas and New Year. However, due to the large dataset, manual segmentation is not feasible anymore. Thus, the Data Analysis Department has been requested to implement a classification system to segment customers based on the RFM model using Python programming.

**My Approach:**
- Prepare the Dataset: Obtain the dataset suitable for the RFM model. This dataset will contain customer transaction data, including the purchase dates and amounts for each customer.

- Calculate R, F, M Scores: Calculate the Recency, Frequency, and Monetary scores for each customer. The Recency score (R) will be calculated as of December 31, 2017, which is the reference date. The scores will be assigned using a scale of 1 to 5 based on the quintile method of Statistics.

- Customer Grouping: Based on the calculated RFM scores, group each customer into segments. Customers with similar RFM scores will be grouped.

- Data Visualization: Visualize the number of customers in each segment using appropriate data visualizations. This will help in understanding the distribution of customers across different segments.

- Analysis and Recommendations: Analyze the current situation of the company based on the customer segments. Provide suggestions to the Marketing team on how to tailor marketing campaigns for each segment to improve customer loyalty and sales.

- Retail Model Suggestions: Provide recommendations to the Marketing and Sales teams regarding which RFM index (Recency, Frequency, or Monetary) they should prioritize the most. This will help in focusing their efforts on the most critical aspect of customer segmentation.

**Project Deliverables:**
## I/ General information**
The dataset includes 4 different related tables including transaction information, product information, returned orders of customers purchasing products from 2014 to 2017, and RFM classification
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/1de6f121-cd6b-4b88-952c-3ddec3400343)

- **Returned orders dataframe**: We have to filter orders that were not returned before RFM analysis.
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/34ca37fb-56c9-4958-bda3-d38261b2984e)


- **Segmentation data frame**: 'Product ID' is not unique because some products have the same Product ID but have different Product Name => drop 'Product Name' then remove duplicate records so that 'Product ID' will be unique.
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/ae2765b9-2df6-41b7-81b1-a9c3271c9a62)


- **Products data frame**: We have to split each RFM score into single rows

   ![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/5457971c-e88e-4408-85e1-2731c603a400)


## II/ RFM model & Visualisation**
- RFM is a method used for analyzing customer value. It is commonly used in database marketing and direct marketing and has received particular attention in the retail and professional services industries
- RFM stands for the three dimensions:
    1. Recency – How recently did the customer purchase?
    2. Frequency – How often do they purchase?
    3. Monetary Value – How much do they spend?
- RFM analysis numerically ranks a customer in each of these three categories, generally on a scale of 1 to 5 (the higher the number, the better the result). The “best” customer would receive a top score in every category.

![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/4c3c241e-5968-4463-b4dd-724233d1edba)
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/50a6b42f-912a-4b0b-9a90-7c9af5b1644c)
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/1e670bc0-b134-4aee-8903-53876d94082b)
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/9bad4e13-6c6c-4569-9c30-38622f8ed0ad)
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/9081c659-0f6c-49d0-a8c9-84a000c75ebe)
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/9ad7f3ad-3734-44c1-881a-b5d124e10b75)
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/10e252cb-aa2e-4c0f-a416-3314707faed7)
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/2fd6f611-82f2-4b60-8da7-55891e5bafbd)
![image](https://github.com/JennVu/Python.CustomerSegmentation/assets/140695442/02a928a8-5801-4704-b323-91cb06a3e5f9)

## III. Insights
### 1. Recency, Frequency, and Monetary Value of Superstore:
- As a retailer, Superstore should prioritize Recency and Frequency over their Monetary since their most loyal shoppers may make many purchases throughout the year at lower Average Transaction Sizes. However, Superstore's Recency and Frequency do not have many positive signs
The mean Frequency is 6 times, which is low for a retail company. This means customer loyalty is not high
- Mean of Recency ~ 166 days, while the median is 83 days, this represents a lot of high Recency values. The larger this index, the higher the customer's tendency to leave.
### 2. 11 segments of Superstore:
- 2 segments with the highest proportion of customers are Potential Loyalist (14.29%) and At Risk (12.14%)
- Negative segments such as Hibernating and Lost accounted for a high proportion of customers, 11.38% and 10.49%, respectively. However, these two groups account for less than 8% of revenue
- The two most positive segments account for less than 17% of the proportion of customers (Champions, 8.98%, and Loyal, 7.84%).
- Potential Loyalist (the ideal segment) has the highest proportion of customers (14.29%), but its revenue proportion is only 9.02%. Meanwhile, the negative segment, At Risk, accounts for 18.24% of revenue
=> In this Christmas - New Year marketing campaign, SuperStore needs to prioritize its efforts to promote the Potential Loyalist group to become Loyal and Champions and find ways to reconnect with customers in the At Risk group
### 3. Potential Loyalist and At Risk segments
#### 3a. Potential Loyalist
The cart_value decreased in 2 categories Furniture and Technology in 2017 despite the increase in the number of orders and the increase in revenue, specifically:
- Furniture group in 2017 increased the number of orders by 53% (from 62 to 95 orders) but the cart_value decreased by 18% (from 326 USD to 226 USD)
- Technology group in 2017 increased the number of orders by 38% (from 40 to 74 orders) but the cart_value decreased by 31% (from 383 USD to 266 USD)
There was a change in the buying behavior of 2 channels Consumer and Home Office in 2017. They tend to place more orders but the value of each order is lower, specifically:
The consumer group in 2017 increased orders by 40% (from 112 to 186 orders) but cart_value decreased by 26% (from 292 USD to 214 USD).
- Home Office in 2017 increased orders by 76% (from 30 to 53 orders) but cart_value decreased by 22% (from 276 USD to 225 USD
#### 3b. At Risk
In 2017, all 3 Categories showed a decrease in orders and revenue, 2 Categories Office Supplies and Technology experienced a decrease in cart value:
- Cart value of Office Supplies group in 2017 decreased by 23% (from 263 USD to 203 USD)
- Cart Value of Technology group in 2017 decreased by 22% (from 836 USD to 651 USD)
- Meanwhile, the Furniture group has an increase in the cart value from 350 USD to 476 USD
In 2017, while the Consumer and Corporate channels experienced a decrease in the number of orders, revenue, and cart value, the Home Office channel, despite a decrease in the number of orders, still recorded an increase in revenue and cart value:
The consumer group reduced the number of orders by 17% and cart value by 38%
- Corporate group reduced the number of orders by 26% and cart value by 5%
- Office group  reduced the number of orders by 25% but cart value increased by 73%

## IV. Recommendations
Superstores should focus more on enhancing Recency and Frequency performance.
In the Christmas-mas - New Year marketing campaign, SuperStore needs to prioritize its efforts to promote the Potential Loyalist group to become Loyal and Champions and find ways to reconnect with customers in the At Risk group
Recommendations on the or Potential Loyalist segment:**

- Special promotions are needed for customers who buy products in the same category and reach a cart value above 238.68 USD (current average cart value of this segment) to motivate customers to buy related products and increase the cart value.
- Offer membership/loyalty program, focusing on 2 channels Consumer and Home Office, and 2 categories Furniture and Technology.
- Recommend to customers the best-selling Sub-category such as Paper, Binders, Furnishings, Storage and Art

**Recommendations for At Risk segment:**

- Channels and Categories with a high number of return orders all have a decrease in the number of orders, revenue, and cart value There needs to be a deeper analysis of the correlation between these factors
- Start a new program (exchange points/gifts/vouchers) for customers in these groups to get them to survey to find out the main reason why these customers have not come back for a long time.
- Since nearly 60% of orders use Ship mode Standard Class, the free upgrade to Second Class policy can be included in the new campaign
- Send personalized emails to provide useful information and recommend to customers best-selling Sub-categories such as Binders, Paper, Furnishings, Phones, and Storage
