# CAPSTONE_PROJECT 2

### Project Title : : Customer Segmentation for a Subscription Service. (F.M Services)

### Project Objective 
The primary objective of this project is to analyze the CustomerData to gain insights into customer behavior, subscription patterns, and regional trends. This analysis aims to identify key factors influencing customer retention, subscription cancellations, and the overall effectiveness of different subscription types. The findings will support strategic decision-making to enhance customer satisfaction and maximize revenue.

### Data Sources
The dataset was derived from  Customer Data provided from the Service Department of F.M Service. The Data given is a table that have an array of columns like customer ID, Customer Name, Region, SubscriptionStart, SubscriptionEnd, Canceled and Revenue.

 Tools Used
- Microsoft Excel for Data cleaning and analysis  [Download Here](https://www.microsoft.com/en-ng/)
- Structured Query Language(SQL) for quering of the Data
- Microsoft PowerBI for visualization
- Github for portfolio building

### Data Description
The CustomerData includes detailed information on:
- Customer demographics (e.g., region, age group)
- Subscription details (e.g., start and end dates, subscription type)
- Subscription status (active or canceled)
- Revenue associated with each subscription

### Key Goals
1. Understand Subscription Patterns:
- Analyze how subscription patterns vary by region and subscription type.
- Identify the most and least popular subscription types.

2. Customer Retention:
- Investigate the rate of subscription cancellations.

3. Subscription Duration Analysis:
- Calculate the average subscription duration to assess customer loyalty and satisfaction.

4. Revenue Insights:
- Calculate total revenue by subscription type and region.
- Identify which subscription types and regions contribute most to the overall revenue.

5. Regional Analysis:
- Determine which regions have the highest and lowest customer counts.

### Methodology:
1. Data Cleaning and Preparation:
- Removed duplicates to ensure data accuracy.

2. Exploratory Data Analysis:
- Used pivot tables in excel and visualizations in Power BI to uncover key trends and patterns.
  
3. SQL Queries:
- Executed queries to retrieve insights on subscription counts, durations, and revenue breakdowns.

### Expected Impact
- Enhanced understanding of customer behavior and subscription dynamics.
- Identification of actionable insights to improve customer retention and optimize revenue generation.
- Tailored marketing strategies based on regional and subscription type preferences.

### Key Deliverables
A. Detailed Reports: Using Pivot Table in Excel [Download Here](https://onedrive.live.com/personal/281b96814f584b5c/_layouts/15/doc.aspx?resid=845e85eb-85f5-409c-a830-3496c8d93a31&cid=281b96814f584b5c&wdOrigin=MARKETING.FREE.GO-TO-EXCEL%2CAPPHOME-WEB.FILEBROWSER.RECENT&wdPreviousSession=c3b51228-c0e6-46b7-af95-0618f2293007&wdPreviousSessionSrc=AppHomeWeb&ct=1730741765374)
- Analyze customer data using pivot tables to find subscription patterns.
- Calculate the average subscription duration and identify the most popular subscription types.
- Subscription churn analysis.
- Regional and subscription type performance.
- Customer lifetime value estimation.

B. SQL Queries:
- Repository of SQL queries used to extract key insights.
- Documentation of findings from the SQL analysis.

--- 1. retrieve the total number of customers from each region.---
- SELECT Region, COUNT(CustomerID) AS TotalCustomers
FROM CapstoneCustomerData
GROUP BY Region

--- 2. find the most popular subscription type by the number of customers.---
- SELECT SubscriptionType, COUNT(CustomerID) AS CustomerCount
FROM CapstoneCustomerData
GROUP BY SubscriptionType
ORDER BY CustomerCount DESC

--- 3. Find customers who cancelled their subscription within 6 months.---
- SELECT CustomerID, SubscriptionType, SubscriptionStart, SubscriptionEnd
FROM CapstoneCustomerData
WHERE SubscriptionEnd IS NOT NULL
AND DATEDIFF(SubscriptionEnd, SubscriptionStart) <= 180

--- 4. calculate the average subscription duration for all customers.---
- SELECT AVG(DATEDIFF(SubscriptionEnd, SubscriptionStart)) AS AverageSubscriptionDuration
FROM CapstoneCustomerData

--- 5. find customers with subscriptions longer than 12 months.---
- SELECT CustomerID, SubscriptionType, SubscriptionStart, SubscriptionEnd
FROM CapstoneCustomerData
WHERE DATEDIFF(SubscriptionEnd, SubscriptionStart) > 365

--- 6. calculate total revenue by subscription type.---
- SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue
FROM CapstoneCustomerData
GROUP BY SubscriptionType

--- 7. find the top 3 regions by subscription cancellations.---
- SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue
FROM CapstoneCustomerData
GROUP BY SubscriptionType

--- 8. find the total number of active and cancelled subscriptions.---
- SELECT Canceled, COUNT(CustomerID) AS TotalSubscriptions
FROM CapstoneCustomerData
GROUP BY Canceled

C. Interactive Power BI Dashboard:
- Visualizes key insights, including subscription counts, regional trends, revenue breakdowns, and customer segmentation.
- Includes slicers for dynamic filtering by region, subscription type, and status.

![image](https://github.com/user-attachments/assets/a6511cf2-70a6-4240-b8c1-d2bc5e3de409)

![image](https://github.com/user-attachments/assets/5161b16b-094e-497a-b201-0ca34c31030e)

![image](https://github.com/user-attachments/assets/72819719-bb4f-4df8-8a8c-38729dd059d1)

![image](https://github.com/user-attachments/assets/f3f0351b-af9c-49fd-aec0-823dcc02c477)

![image](https://github.com/user-attachments/assets/981e8611-90ff-49b7-a7b9-c4d73b5eb966)

![image](https://github.com/user-attachments/assets/c17a6d8f-8bce-4827-b312-b31762f661f3)

### DASHBOARD HIGHLIGHT KEY VISUALS

![image](https://github.com/user-attachments/assets/6134e805-12ad-498a-bc68-9fe0b611e0af)

### Key Findings:
1. Subscription Patterns
- Most Popular Subscription Type: Basic subscription type stands out as the most subscribed, indicating customer preference and potentially more effective marketing or service offerings.
- Average Subscription Duration: The average subscription duration is 365.35, which indicates insights into customer loyalty and satisfaction. If the duration isn't short, so, we can say there is no or little signifance effect.

2. Customer Retention and Churn
- Long-term Subscribers: Customers with subscriptions longer than 12 months are fewer but represent a loyal segment that could be targeted for upselling or loyalty rewards.

3. Revenue Distribution
- Revenue by Subscription Type: Basic subscription type contribute significantly more to total revenue. This indicates that Basic subscription types are more profitable and there should be focus marketing and resources on the others.
- Revenue by Region: Some regions contribute more to the overall revenue, suggesting higher customer density or effective regional strategies. Regions with lower contributions may require tailored marketing approaches.

4. Regional Insights
- Top-Performing Regions: East region have the highest number of active subscriptions, indicating strong market penetration or preference for the service in these areas.

### Recommendations:
1. Focus on Retention Strategies:
- Implement onboarding improvements and early engagement strategies to reduce early cancellations.
- Consider loyalty programs for long-term subscribers.

2. Targeted Marketing:
- Tailor marketing efforts to regions with lower revenue or higher cancellations to boost engagement.
- Promote the most profitable subscription types to maximize revenue.

3. Product Improvements:
- Based on feedback from canceled subscriptions, refine product offerings or pricing to better meet customer needs.

4. Enhance Regional Strategies:
- Leverage insights from top-performing regions to replicate success in underperforming areas.

### Conclusion
This project provides a comprehensive view of the customer base, helping the company to develop strategies that enhance customer satisfaction, optimize revenue, reduce churn, and drive sustainable growth.
