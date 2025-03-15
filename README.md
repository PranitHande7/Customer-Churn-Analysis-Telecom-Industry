# Customer Churn Analysis - Telecom Industry

# Project Background

Customer churn is a critical issue in the telecom industry, where companies must retain existing customers while acquiring new ones. This project focuses on analyzing customer churn patterns, identifying key churn drivers, and predicting customers likely to churn using SQL, Power BI, and Machine Learning (Random Forest Classification ).

The objective of this project is to:
- Visualize & Analyze Customer Data at the following levels:
  - Demographic
  - Geographic
  - Payment & Account Information
  - Services Used
- Study churner profiles & identify areas for implementing targeted marketing campaigns.
- Identify a predictive model to forecast future churners.
- Analyze churn trends based on contract types, tenure, and service bundles.
- Predict potential churners using Random Forest classification.
- Provide actionable insights for customer retention strategies.

# Data Structure and Overview
The dataset comprises three key files:

- **Customer_Data.csv**: Contains customer demographics, service usage, and billing details.
- **Prediction_Data.xlsx**: Contains SQL views vw_ChurnData and vw_JoinData, created for Random Forest Classification.
- **Predictions.csv**: Output from the Random Forest model, predicting customers likely to churn. Later used as an input for **Churn Prediction** page of the dashboard.

# Data Processing Steps:

## SQL Queries (SSMS):
- Data cleaning and handling null values.
- Creating vw_ChurnData (customers who stayed or churned) and vw_JoinData (newly joined customers).
- Aggregation queries to analyze contract types, demographics, and revenue contributions.

## Power Query Transformations (Power BI):
- Created Churn Status (Binary: 1 = Churned, 0 = Stayed).
- Categorized customers into Monthly Charge Ranges, Age Groups and Tenure Groups.
- Unpivoted service columns for better visualization.

## Machine Learning (Random Forest Classification in Python):
- Encoded categorical variables and performed feature selection.
- Trained a Random Forest model with an accuracy of 84%.
- Used the model to predict potential churners and saved results in Predictions.csv.

The python code for the random forest classification can be found [here](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/ChurnPrediction.ipynb)
# Executive Summary
## Key Findings:
Overall Churn Rate: 26.99%, indicating significant customer losses.
High Churn Segments:
- **Demographics**: Females (64.15%) churn more than Males (35.85%).
- **Age Group**: Customers aged >50 have the highest churn rate (31.04%).
- **Tenure**: Short-term customers (<6 months) churn at 26.37%, highlighting early dissatisfaction.
- **Contract Type**: Month-to-month contracts have the highest churn rate (46.53%), whereas long-term contracts show better retention.
- **Service Type**: Fiber Optic users churn the most (41.10%), possibly due to competitive pricing.

## Churn Prediction
- 375 customers identified as high churn risk.
- Majority are female (242) compared to male (133).
- Most churners belong to the 35-50 age group, followed by those aged >50.
- High churn risk for customers with short tenures (<12 months).
- Month-to-month contracts dominate (358 churners), reinforcing contract length as a key churn factor.
- Top states with highest predicted churn: Uttar Pradesh, Maharashtra, and Tamil Nadu.
- Most at-risk customers have high monthly charges but few additional services.

  Below is the overview page from the PowerBI dashboard and more examples are included throughout the report. The entire dashboard can be viewed [here](https://github.com/PranitHande7/Green-Planet-Co.---Sales-Performance-Analytics/blob/main/PerformReport.pbix).

![Dashboard1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/ChurnAnalysisPage1.png)

![Dashboard2](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/ChurnAnalysisPage2.png)

## Overview of the Findings

## Churn Analysis - Summary (Page 1)

## **1. Churn by Demographics**
- Females account for 64.15% of total churn, indicating a higher likelihood of switching providers compared to males (35.85%).
- Older customers (>50 years) have the highest churn rate (31.04%), followed by the 35-50 age group (24.02%).
- Younger customers (<20) show minimal churn, possibly due to fewer subscribers in this segment.

 ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/1.png)

## **2. Churn by Contract & Payment Method**
- Month-to-month contracts have the highest churn (46.53%).
- Customers using Mailed Checks (37.82%) and Bank Transfers (34.43%) are more likely to churn.
- Customers on long-term contracts (One-Year, Two-Year) show significantly lower churn rates.

 ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/2.png)
 
## **3. Tenure-Based Churn**
- Customers with tenure over 24 months have the highest churn rate (27.50%), followed closely by 18-24 months (27.24%) and 6-12 months (27.16%).
- Short-tenure customers (<6 months) also exhibit high churn (26.37%), indicating early dissatisfaction.

 ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/3.png)

## **4. Churn by Location(Top 5 States) and Churn Category**
- Jammu has the highest churn rate (57.19%), followed by Assam (38.13%) and Jharkhand (34.51%). High churn in these regions suggests service quality issues, competitive pricing, or lack of customer engagement.
- Competition (761 cases) is the leading churn reason, indicating customers are switching to competitors.
- Customer attitude and dissatisfaction (601 combined cases) highlight gaps in service quality or customer experience.
- Price sensitivity (196 cases) suggests cost-effective alternatives may help improve retention.

 ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/4.png)

> [!NOTE]
> Hovering over the bars of the Churn categories gives a tooltip which gives detailed information of the reason the customers churned and the total number of customers for that specific reason.

 ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/ChurnReason.png)

## **5. Churn by Internet Type**
- Fiber Optic users have the highest churn rate (41.10%), followed by Cable (25.72%) and DSL (19.37%) users.
- Customers without an internet plan show the lowest churn rate (7.84%), likely because they are less engaged with the service.

  ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/5.png)

 ## **6. Churn by Services Used**
- Customers without value-added services are more likely to churn.
- 94% of churners had internet service, but many lacked additional services like Online Security and Backup.
- Paperless billing users (75%) show higher retention, suggesting a correlation between digital engagement and loyalty.
- Phone service (91% retention) and Unlimited Data (80% retention) reduce churn, indicating that bundled essential services improve customer stickiness.

  ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/6.png)


## Churn Analysis - Prediction (Page 2)

## **1. Demographic Breakdown and Marital Status**
- Female customers (242) are at a higher risk of churning compared to males (133).
- Older customers (>50) make up the largest predicted churn segment (134), followed by the 35-50 age group (125).
- Young customers (<20) have the lowest churn prediction (12), likely due to prepaid or family plans.
- Married and non-married customers show nearly equal churn risk (191 vs. 184), indicating that marital status does not significantly impact churn behavior.

  ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/ChurnPrediction1.png)

## **2.  Tenure & Contract-Based Churn Prediction**
- Customers with 24+ months tenure have the highest predicted churn (105).
- 6-12 month tenure customers (88) also show significant churn risk.
- Short-tenure customers (<6 months) account for 64 churners, indicating early-stage dissatisfaction.
- 358 predicted churners are on month-to-month contracts, reinforcing that flexible contracts lead to higher churn.
- Only 17 churners belong to one-year or two-year contracts, confirming long-term contracts improve retention.
  
  ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/ChurnPred2.png)

## **3. Geographic & Payment Method-Based Churn Prediction**
- Uttar Pradesh (41), Maharashtra (39), and Tamil Nadu (37) have the highest predicted churners.
- Credit card users (189) and bank withdrawal users (149) make up most predicted churners.
- Mailed check users (37) are the least likely to churn, possibly due to fewer alternatives or preference for traditional payment methods.

  ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/ChurnPred3.png)

## **Detailed Overview of the customer at risk table**
- This table gives an overview of the various details of the potential churners like Customer_id, Monthly_Charge, Total_Revenue, Total_Refunds, Number of Referrals.
- Some customers have higher monthly charges (e.g., $100+), making them high-priority for retention.
- Minimal refunds recorded suggest dissatisfaction isn't driven by refund-related issues but possibly service quality or pricing.

  ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/ChurnPred4.png)

# Recommendations
- **Strengthen Customer Retention Among High-Risk Segments**
  - Older customers (>50) and short-tenure users (<12 months) have the highest churn rates.
  - Implementing personalized retention programs for older customers, offering senior-friendly plans, simplified billing, and priority customer support.
  - Enhance the onboarding experience for new customers to reduce early churn. Provide tutorials, first-month discounts, and proactive customer service follow-ups.
  - Introduce milestone-based loyalty rewards to retain customers beyond the critical 6-month and 12-month churn risk periods.
  - Telecom companies have successfully reduced early churn by offering AI-driven chat support, proactive engagement via SMS/email, and discounts for contract renewals.
- **Address High Churn in Month-to-Month Contracts**
  - Month-to-month contract users have the highest churn rate (46.53%), while long-term contract users (1-2 years) have significantly lower churn.
  - Offer discounted long-term plans or flexible upgrade options to encourage contract extensions.
  - Introduce contract renewal perks, such as free add-ons (e.g., streaming services, data boosts) for customers committing to annual plans.
  - Bundled pricing and multi-year contract incentives have been proven to reduce churn in telecom and streaming services (e.g., Netflix’s yearly plans vs. monthly subscriptions).
- **Reduce Churn Among High-Value Customers**
  - Customers with high monthly charges (> $100) are at significant churn risk, representing a large revenue loss if they leave.
  - Introduce proactive retention outreach for high-value customers through account managers, ensuring they receive tailored service solutions.
  - Telecom giants like AT&T and Verizon use AI-driven churn prediction models to identify high-value customers at risk and offer them custom retention packages before they     leave.
- **Improve Customer Engagement & Upselling Strategies**
  - Customers without value-added services (security, backup, premium support) churn at a higher rate.
  - Encourage customers to adopt bundled services by offering discounts on package deals (e.g., Fiber + Device Protection + Online Backup).
  - Promote subscription-based value-added services that increase customer stickiness, such as priority customer support, premium streaming access, or security enhancements.
- **Address High Churn in Specific Regions**
  - High churn is concentrated in Jammu (57.19%), Assam (38.13%), and Jharkhand (34.51%), indicating potential service quality issues or competitive pressure.
  - Conduct region-specific surveys to understand service quality concerns and improve network coverage.
  - Offer localized promotions and region-specific incentives (e.g., discounted plans tailored to high-churn states).
  - Enhance customer support accessibility in these regions by providing regional language support, faster service resolution, and dedicated service teams.
- **Enhance Digital Engagement & Payment Methods**
  - Mailed check and bank withdrawal users churn at higher rates, while digitally engaged customers (paperless billing, auto-pay) show better retention.
  - Encourage paperless billing adoption by offering discounts for customers who opt-in for auto-pay.
  - Provide cashback incentives for digital payment users to drive adoption of credit card and online payment methods.
  - Companies offering autopay incentives (e.g., Amazon Prime, telecom providers) experience lower churn rates due to reduced friction in payments.
- **Leverage AI & Predictive Analytics for Proactive Retention**
  - 375 customers are predicted to churn, contributing over $42,000 in total revenue risk.
  - Use AI-driven churn prediction models to identify at-risk customers early and engage them proactively.
  - Deploy customer success teams to reach out to predicted churners and offer tailored solutions before they decide to leave.
  - Automate personalized retention offers based on user behavior (e.g., if a high-value customer reduces usage, trigger a special offer).
  - Predictive analytics has helped telecom leaders like T-Mobile and Vodafone reduce churn by up to 20% by engaging customers before they decide to switch.

---

# Glossary
