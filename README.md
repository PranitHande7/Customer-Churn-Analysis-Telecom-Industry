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

 ![image1](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/Images/DataModel.png)

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
- Overall Churn Rate: 26.99%, indicating significant customer losses.
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

  Below is the overview page from the PowerBI dashboard and more examples are included throughout the report. The entire dashboard can be viewed [here](https://github.com/PranitHande7/Customer-Churn-Analysis-Telecom-Industry/blob/main/ChurnAnalysis.pbix).

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

# Model Performance Overview
```
Classification Report:
	              precision    recall   f1-score   support

Non Churners   0       0.86         0.93      0.89      1258
Churners       1       0.80         0.64      0.71       545

      accuracy                                0.84      1803
     macro avg         0.83         0.79      0.80      1803
  weighted avg         0.84         0.84      0.84      1803

```
- The model achieved 84% accuracy, meaning it correctly identified churn and non-churn cases 84% of the time.
- Model acheived 86% precision for non-churners - when the model predicts a customer will stay, it is correct 86% of the time.
- For churners 80% precision – some false positives exist, but the model remains reliable.
- Non-churners: 93% recall indicating most non-churners were correctly identified.
- Churners: 64% recall means some at-risk churners were misclassified.
- The model is effective at predicting customers who will stay, but some churners are missed (false negatives), impacting retention strategies.
- The model can be refined further by optimizing features, adjusting thresholds, and balancing class weights.

## SQL Queries

### **1. Check Distinct Values**
```SQL
SELECT Gender, Count(Gender) as TotalCount,
Count(Gender) * 1.0 / (Select Count(*) from stg_Churn)  as Percentage
from stg_Churn
Group by Gender
```

```SQL
SELECT Contract, Count(Contract) as TotalCount,
Count(Contract) * 1.0 / (Select Count(*) from stg_Churn)  as Percentage
from stg_Churn
Group by Contract
```

```SQL
SELECT Customer_Status, Count(Customer_Status) as TotalCount, Sum(Total_Revenue) as TotalRev,
Sum(Total_Revenue) / (Select sum(Total_Revenue) from stg_Churn) * 100  as RevPercentage
from stg_Churn
Group by Customer_Status
```

```SQL
SELECT State, Count(State) as TotalCount,
Count(State) * 1.0 / (Select Count(*) from stg_Churn)  as Percentage
from stg_Churn
Group by State
Order by Percentage desc
```

### **2. Check Nulls**
```SQL
SELECT 
    SUM(CASE WHEN Customer_ID IS NULL THEN 1 ELSE 0 END) AS Customer_ID_Null_Count,
    SUM(CASE WHEN Gender IS NULL THEN 1 ELSE 0 END) AS Gender_Null_Count,
    SUM(CASE WHEN Age IS NULL THEN 1 ELSE 0 END) AS Age_Null_Count,
    SUM(CASE WHEN Married IS NULL THEN 1 ELSE 0 END) AS Married_Null_Count,
    SUM(CASE WHEN State IS NULL THEN 1 ELSE 0 END) AS State_Null_Count,
    SUM(CASE WHEN Number_of_Referrals IS NULL THEN 1 ELSE 0 END) AS Number_of_Referrals_Null_Count,
    SUM(CASE WHEN Tenure_in_Months IS NULL THEN 1 ELSE 0 END) AS Tenure_in_Months_Null_Count,
    SUM(CASE WHEN Value_Deal IS NULL THEN 1 ELSE 0 END) AS Value_Deal_Null_Count,
    SUM(CASE WHEN Phone_Service IS NULL THEN 1 ELSE 0 END) AS Phone_Service_Null_Count,
    SUM(CASE WHEN Multiple_Lines IS NULL THEN 1 ELSE 0 END) AS Multiple_Lines_Null_Count,
    SUM(CASE WHEN Internet_Service IS NULL THEN 1 ELSE 0 END) AS Internet_Service_Null_Count,
    SUM(CASE WHEN Internet_Type IS NULL THEN 1 ELSE 0 END) AS Internet_Type_Null_Count,
    SUM(CASE WHEN Online_Security IS NULL THEN 1 ELSE 0 END) AS Online_Security_Null_Count,
    SUM(CASE WHEN Online_Backup IS NULL THEN 1 ELSE 0 END) AS Online_Backup_Null_Count,
    SUM(CASE WHEN Device_Protection_Plan IS NULL THEN 1 ELSE 0 END) AS Device_Protection_Plan_Null_Count,
    SUM(CASE WHEN Premium_Support IS NULL THEN 1 ELSE 0 END) AS Premium_Support_Null_Count,
    SUM(CASE WHEN Streaming_TV IS NULL THEN 1 ELSE 0 END) AS Streaming_TV_Null_Count,
    SUM(CASE WHEN Streaming_Movies IS NULL THEN 1 ELSE 0 END) AS Streaming_Movies_Null_Count,
    SUM(CASE WHEN Streaming_Music IS NULL THEN 1 ELSE 0 END) AS Streaming_Music_Null_Count,
    SUM(CASE WHEN Unlimited_Data IS NULL THEN 1 ELSE 0 END) AS Unlimited_Data_Null_Count,
    SUM(CASE WHEN Contract IS NULL THEN 1 ELSE 0 END) AS Contract_Null_Count,
    SUM(CASE WHEN Paperless_Billing IS NULL THEN 1 ELSE 0 END) AS Paperless_Billing_Null_Count,
    SUM(CASE WHEN Payment_Method IS NULL THEN 1 ELSE 0 END) AS Payment_Method_Null_Count,
    SUM(CASE WHEN Monthly_Charge IS NULL THEN 1 ELSE 0 END) AS Monthly_Charge_Null_Count,
    SUM(CASE WHEN Total_Charges IS NULL THEN 1 ELSE 0 END) AS Total_Charges_Null_Count,
    SUM(CASE WHEN Total_Refunds IS NULL THEN 1 ELSE 0 END) AS Total_Refunds_Null_Count,
    SUM(CASE WHEN Total_Extra_Data_Charges IS NULL THEN 1 ELSE 0 END) AS Total_Extra_Data_Charges_Null_Count,
    SUM(CASE WHEN Total_Long_Distance_Charges IS NULL THEN 1 ELSE 0 END) AS Total_Long_Distance_Charges_Null_Count,
    SUM(CASE WHEN Total_Revenue IS NULL THEN 1 ELSE 0 END) AS Total_Revenue_Null_Count,
    SUM(CASE WHEN Customer_Status IS NULL THEN 1 ELSE 0 END) AS Customer_Status_Null_Count,
    SUM(CASE WHEN Churn_Category IS NULL THEN 1 ELSE 0 END) AS Churn_Category_Null_Count,
    SUM(CASE WHEN Churn_Reason IS NULL THEN 1 ELSE 0 END) AS Churn_Reason_Null_Count
FROM stg_Churn;
```

### **3. Remove null and insert the new data into Prod table**
```SQL
SELECT 
    Customer_ID,
    Gender,
    Age,
    Married,
    State,
    Number_of_Referrals,
    Tenure_in_Months,
    ISNULL(Value_Deal, 'None') AS Value_Deal,
    Phone_Service,
    ISNULL(Multiple_Lines, 'No') As Multiple_Lines,
    Internet_Service,
    ISNULL(Internet_Type, 'None') AS Internet_Type,
    ISNULL(Online_Security, 'No') AS Online_Security,
    ISNULL(Online_Backup, 'No') AS Online_Backup,
    ISNULL(Device_Protection_Plan, 'No') AS Device_Protection_Plan,
    ISNULL(Premium_Support, 'No') AS Premium_Support,
    ISNULL(Streaming_TV, 'No') AS Streaming_TV,
    ISNULL(Streaming_Movies, 'No') AS Streaming_Movies,
    ISNULL(Streaming_Music, 'No') AS Streaming_Music,
    ISNULL(Unlimited_Data, 'No') AS Unlimited_Data,
    Contract,
    Paperless_Billing,
    Payment_Method,
    Monthly_Charge,
    Total_Charges,
    Total_Refunds,
    Total_Extra_Data_Charges,
    Total_Long_Distance_Charges,
    Total_Revenue,
    Customer_Status,
    ISNULL(Churn_Category, 'Others') AS Churn_Category,
    ISNULL(Churn_Reason , 'Others') AS Churn_Reason

INTO [db_Churn].[dbo].[prod_Churn]
FROM [db_Churn].[dbo].[stg_Churn];
```

### **4. Create View for Power BI**
```SQL
Create View vw_ChurnData as
	select * from prod_Churn where Customer_Status In ('Churned', 'Stayed')


Create View vw_JoinData as
	select * from prod_Churn where Customer_Status = 'Joined'

```

## DAX Measures

### **1. Summary Page 1 - Measures**
```DAX
Total Customers = Count(prod_Churn[Customer_ID])

New Joiners = CALCULATE(COUNT(prod_Churn[Customer_ID]), prod_Churn[Customer_Status] = "Joined")

Total Churn = SUM(prod_Churn[Churn Status]) 

Churn Rate = [Total Churn] / [Total Customers]

```

### **2. Churn Prediction Page 2 - Measures**
```DAX
Count Predicted Churner = COUNT(Predictions[Customer_ID]) + 0

Title Predicted Churners = "COUNT OF PREDICTED CHURNERS : " & COUNT(Predictions[Customer_ID])

```
