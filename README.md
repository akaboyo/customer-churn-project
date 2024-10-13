# CUSTOMER CHURN ANALYSIS 

## Project Overview
The primary objective of this project was to analyze customer churn for a telecom client (PhoneNow) and provide actionable insights to help reduce churn rates and improve customer retention. The project was conducted in response to a request from the client’s Retention Manager, who emphasized the high cost of acquiring new customers and the need for a proactive approach to retaining existing customers.
The analysis was carried out in several key phases, each aimed at building a comprehensive understanding of customer churn and creating self-explanatory dashboards for strategic decision-making.

## Problem Statement
The Retention Manager(Janet), at PhoneNow sent me a mail enumerating that the company faces significant challenges with customer churn, and acquiring new customers is costly and time-consuming. For PhoneNow, the overall churn rate is about a quarter of the total customers, indicating a substantial risk to revenue and long-term customer relationships. Janet has asked me to create visualisation dashboards that analyses customer churn and risks of churn, and provide insights. The insights from this dashboard will be used in communicating findings and recommendations to the Engagement Partner.

## Data Collection and Preparation
### Data Sources: 
The dataset was provided by PWC in an Excel worksheet document and it included 7,043 rows and 23 columns which contains customer demographic information, account details, and service subscription data, all of which are crucial for identifying churn patterns. View the dataset here [02 Churn-Dataset.xlsx](https://github.com/user-attachments/files/17340030/02.Churn-Dataset.xlsx)

### Data Cleaning: 
The dataset was first cleaned in powerquery to handle missing values, correct inconsistencies, and ensure accuracy. Categorical and numerical variables were transformed and  normalized for model readiness in Microsoft PowerBI.

- I Checked for blank cells and missing values using the column quality check. The Total charges column had 11 empty values(Null), which were replaced with 0 to represent no total charges for those customers.
- I changed data type of columns with wrong type to the right one.
- I converted the Tenure column to a conditional column so as to analyse the age of customer contractas in relation to churning. 

### Exploratory Data Analysis (EDA): 
Initial EDA was conducted to examine distributions, correlations, and trends related to churn, such as the churn rate by tenure, contract type, and payment method. The findings indicated that customer demographics, account information, and service subscriptions were significant contributors to churn behavior.
- Demographics Analysis: Analyzed churn rate by customer demographics, including gender, senior citizen status, and the presence of dependents and partner.
- Service Usage Analysis: Examined churn rate across different service subscriptions, such as phone service, streaming options, and internet service types (Fiber optic, DSL).
- Account Information: Investigated how payment methods, monthly charges, and contract types relate to customer churn, with specific focus on month-to-month contracts and 
  electronic check payments that showed higher churn rates.

#### DAX Measures
In addition to data cleaning and transformation, I created DAX measures to derive critical insights. These measures encompass calculations for the following:

1. ChurnRate = 
(DIVIDE(
    CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes"),
    COUNT(Churn[customerID]),
    0
) * 100/100)

2. % SeniorCitizen = 
((CALCULATE(COUNT(Churn[customerID]), Churn[SeniorCitizen] = 1, Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100 /100)

3. % with Dependents = 
((CALCULATE(COUNT(Churn[customerID]), Churn[Dependents] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

4. % with DeviceProtection = 
((CALCULATE(COUNT(Churn[customerID]), Churn[DeviceProtection] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

5. % with MultipleLines = 
((CALCULATE(COUNT(Churn[customerID]), Churn[MultipleLines] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

6. % with OnlineBackup = 
((CALCULATE(COUNT(Churn[customerID]), Churn[OnlineBackup] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

7. % with OnlineSecurity = 
((CALCULATE(COUNT(Churn[customerID]), Churn[OnlineSecurity] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

8. % with Partner = 
((CALCULATE(COUNT(Churn[customerID]), Churn[Partner] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

9. % with PhoneService = 
((CALCULATE(COUNT(Churn[customerID]), Churn[PhoneService] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

10. % with StreamingMovies = 
((CALCULATE(COUNT(Churn[customerID]), Churn[StreamingMovies] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

11. % with StreamingTV = 
((CALCULATE(COUNT(Churn[customerID]), Churn[StreamingTV] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

12. % with TechSupport = 
((CALCULATE(COUNT(Churn[customerID]), Churn[TechSupport] = "Yes", Churn[Churn] = "Yes") / 
CALCULATE(COUNT(Churn[customerID]), Churn[Churn] = "Yes")) * 100/100)

13. Count of Churn for Yes = 
CALCULATE(COUNTA('Churn'[Churn]), 'Churn'[Churn] = "Yes" )

14. CustomerLifetimeValue ($) = 
CALCULATE(
    SUM(Churn[MonthlyCharges]) * AVERAGE(Churn[Tenure])
)

## Data Visualization
Data visualization for the Customer Churn analysis was done in Microsoft PowerBI Desktop. Here are the visuals:

![churn report](https://github.com/user-attachments/assets/1188e86b-fb36-4329-a82a-700ac1b83db0)

![customer risk report](https://github.com/user-attachments/assets/feafc544-8f9b-4f0f-9d20-27c1313b50d1)
