 # **Customer Segmentation & Spending Behavior Analysis in Credit Card **

## **Table of Contents**

- [Problem Statement](#problem-statement)
- [Datasource](#data-source)
- [Data Cleaning and Data Transformation](#data-cleaning-and-data-transformation)
- [Data Analysis (DAX)](#data-analysis-dax)
- [Data Visualization Dashboard](#data-visualization-dashboard)
- [Insights](#insights)



## **Problem Statement**

Mitron Bank, a legacy financial institution headquartered in Hyderabad, seeks to launch a new line of credit cards to expand its product offerings and market presence. To evaluate the feasibility and potential success of this initiative, the bank has partnered with AtliQ Data Services for a pilot project.

AtliQ Data Services has been tasked with analyzing a sample dataset of 4,000 customers from five cities, containing details on their online spending and other demographic and behavioral attributes. The goal is to uncover actionable insights and trends that can help Mitron Bank tailor its credit card offerings to meet customer needs and align with market trends.

The analysis should deliver data-driven recommendations that address the following objectives:

 - Identify customer segments with the highest potential for credit card adoption.
 - Understand spending patterns and preferences to design targeted rewards and benefits.
 - Evaluate regional differences and city-specific trends to optimize marketing strategies.
 - Highlight any gaps or opportunities in the current market that the new credit card can address.

The success of this pilot project and the acquisition of the full project depends on AtliQ Data Services' ability to deliver a compelling and insightful analysis that demonstrates a clear value proposition to Mitron Bank's strategy director and his team.
    

## **Data source**
**File Name:** `dim_customers.csv`
                `Fact_Spend.csv`
- **Description:** Dataset provided by Mitron Bank for pilot analysis of 4,000 customers across five cities.
**Datasets** 
- Fact_spend: Details about spending behavior, including customer ID, spending month, payment type, spending, and spending category.
    Dim_customer: Customer details, such as customer ID, gender, city, age group, average income (for a period of 6 months), marital status, and occupation.
  
 **Columns:**
  - `Customer_ID`: Unique identifier for each customer.
  - `Age_group`: Age group of the customer.
  - `Gender`: Gender of the customer (`Male`, `Female`).
  - `City`: Customer's city of residence.
  - `Income_Level`: Income category (`Low`, `Medium`, `High`).
  - 'Avg_income_utilization% : average percentage of income utilized by the customer.
  - `Total_Spend`: Total spend across all categories.
  - `Current_Credit_Card`: Whether the customer owns a credit card (`Yes`, `No`).
  - `Credit_Score`: Customer's credit score.
  - `Spending_Category`: Major category of spend (`Travel`, `Shopping`, `Dining`, etc.).
  - `marital status`: Marital status of the customer (Single, Married).
  - `occupation`: Profession or occupation of the customer.
  - `Total_Spend`: Total amount spent by the customer.
  - `Month`: Total spends in Month wise
  - `Payment_type`: The payment method used (e.g., Credit Card, Debit Card, UPI, etc.).
  - `category`: The spending category (e.g., Travel, Dining, Groceries, etc.).
    
## **Data Cleaning and Data Transformation**
- Checked for null and duplicate values
- Categorized average income into three categories: low, middle, and high (conditional column).
- Created a custom column, payment category, to classify payment types into card and digital.
- Calculated average spending
## **Data Model**

![image](https://github.com/user-attachments/assets/a5b21d1d-bf67-42f2-80cd-5aeee7bfa6a9)


## **Data Analysis (DAX)**
 - avg income utilization % = AVERAGE('dim_customers'[Avg_income_utilization%])
   
 - TotalCreditCard Spending = CALCULATE([Total_Spend],fact_spends[payment_type] = "Credit Card")
   
 - Credit Card% = ([TotalCreditCard Spending]/[Total_Spend])
   
 - Average Spends = AVERAGE('fact_spends'[spend])
   
 - Total_Spend = SUM('fact_spends'[spend])

## **Data Visualization (Dashboard)**
[live Dashboard](https://www.novypro.com/profile_about/neha--jade?Popup=memberProject&Data=1735275957322x811402919594289800)

## Dashboard:
![image](https://github.com/user-attachments/assets/fe9b0d33-ea9b-41e9-9a65-3536cc7ce7c3)

![image](https://github.com/user-attachments/assets/9472efc1-0849-4f1d-8959-82944a52ae82)

![image](https://github.com/user-attachments/assets/13feea06-4620-4558-8c8e-c90048ef192f)

![image](https://github.com/user-attachments/assets/53bc64d1-e7fc-4df3-bd43-6e0ce4190be0)

## Drill-Through Functionality in Dashboard
To enhance data exploration, I implemented Drill-Through functionality in the dashboard, allowing users to interactively explore customer behavior and spending patterns. This feature enables detailed insights into customer segments, regions, payment methods, and spending categories, driving more informed decision-making.

Key Drill-Through Scenarios:

 - Customer Segmentation: View spending behavior, credit utilization, and payment methods for selected customer segments (e.g., High-Income, Middle-Income).
 - City-Wise Spending: Analyze spending, credit card adoption, and trends in specific cities.
 - Payment Method Insights: Explore how payment methods (Credit Card, Debit Card, UPI) impact spending.
  - Category-Specific Spending: Analyze trends, top customers, and payment preferences within categories like Electronics and Dining.

Benefits:

    Provides stakeholders with granular insights into customer behavior.
    
    Supports targeted marketing and strategic decision-making.

![image](https://github.com/user-attachments/assets/c372eb46-1544-4e37-9cc6-e7bfbfaf2c6c)

## **Insights**

Key Findings from the Data Analysis
The bank serves 4,000 customers across 5 cities, indicating a moderate customer base focused on urban regions.

**Customer Demographics**
- Male customers dominate at 65%, while female customers make up 35%.
    
- Customers aged 45+ earn the highest (~₹60K), indicating financial stability due to established careers or businesses.
    
- Customer distribution by city reveals significant concentrations in metropolitan areas, with Mumbai having the highest number of customers at 1,078.
    
- Business Owners: Highest earners (~₹70.09K) and represent a critical segment for wealth management or premium credit cards.

**Spending Behavior**

- Mumbai has the highest spending at ₹115M, followed by Delhi NCR (₹76M) and Bengaluru (₹69M).
    
- Customers aged 45+ and 35-44 spend the most, averaging ₹55K and ₹52K, respectively.
    
- Younger age groups (21-24) spend the least, averaging ₹21K.
    
- Spending Categories:Bills account for the largest spending category (19.76%), followed by Groceries (16.29%) and Electronics (12.36%).
    
- Monthly Spending Trend:Monthly spending has increased significantly from August (10%) to September (21.84%), indicating seasonal or promotional spending patterns.
  
- Salaried IT employees have the highest credit card spending (₹101,405).

**Payment Behavior** 

 - Credit Card Usage:Credit Card usage stands at 40.73% among all payment methods, highlighting it as a preferred choice.
    
 - Credit card usage percentages are similar across major cities, with Chennai at 42%, followed by Delhi NCR, Hyderabad, Mumbai, and Bengaluru, all around 40–42%.
    
 - Customer aged 25- 34 are the most active Credit card users with around 47% using this method.
    
 - Category-Specific Credit Card Spending:Electronics and Entertainment have the highest proportion of spending via credit cards. Food and Groceries account for lower usage of credit card.

**Income Utilities %** 

- Mumbai has the highest number of customers (1,078), with an average income utility percentage of 51.58%, the highest among all cities.

- Delhi NCR follows with 744 customers and an average income utility of 48.09%.

- Average Income Utilities by Occupation: Salaried IT employees exhibit the highest income utility percentage at 50.93% , Medium-income individuals have the highest income utility at 43.72%, slightly higher than lower-income (43.24%) and higher-income (41.38%) groups.
  
- Age Group Analysis:The age group 35–45 has the highest income utility percentage at 48.63%, followed by 25–34 at 45.71%.
  
- Gender Insights:Male customers consistently show higher income utility percentages compared to female customers across all age groups.
  
- City Income vs. Spending:Mumbai leads not only in the number of customers but also in average spending (₹26,598.40), reflecting a strong economic engagement.
    In contrast, Chennai has the lowest average spending at ₹15,961.53, correlating with its lower income utility percentage.

## **Recommendations** 

﻿**High-Earning Segments:**

    For business owners and customers aged 45+, offer higher credit limits to align with their high earning and spending potential. Provide premium credit cards with added benefits such as higher reward rates, concierge services, or travel perks.


**Younger Customers:**

    For 21–24 years old, introduce starter credit cards with lower credit limits, manageable interest rates, and educational materials on credit usage to promote financial responsibility.


**Increase Credit Card Adoption:**

    Educate customers aged 25–34, who are the most active credit card users (46.61%), about the benefits of higher credit utilization ratios for rewards and perks. Offer welcome bonuses or fee waivers to encourage adoption among new users.


**Seasonal Campaigns:**

    Launch interest-free EMIs or cashback offers during peak spending months (e.g., August to September) to increase credit card usage in categories like electronics, groceries, and entertainment.


**Spending Categories:**

    Provide higher reward rates (e.g., 5% cashback) for top categories like electronics (12.36%) and entertainment to encourage higher spending on credit cards.
    Introduce promotional cashback or discounts for food and Entertainment, which currently have lower credit card spending, to balance category-wise credit utilization.


**Technologies Used**

    Tools: Power BI for visualization, Excel and DAX for calculations.





