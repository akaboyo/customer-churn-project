# CUSTOMER CHURN ANALYSIS 

## Project Overview
The primary objective of this project was to analyze customer churn for a telecom client (PhoneNow) and provide actionable insights to help reduce churn rates and improve customer retention. The project was conducted in response to a request from the client’s Retention Manager, who emphasized the high cost of acquiring new customers and the need for a proactive approach to retaining existing customers.
The analysis was carried out in several key phases, each aimed at building a comprehensive understanding of customer churn and creating self-explanatory dashboards for strategic decision-making.

## Problem Statement
The Retention Manager(Janet), at PhoneNow sent me a mail enumerating that the company faces significant challenges with customer churn, and acquiring new customers is costly and time-consuming. For PhoneNow, the overall churn rate is about a quarter of the total customers, indicating a substantial risk to revenue and long-term customer relationships. Janet has asked me to create visualisation dashboards that analyses customer churn and risks of churn, and provide insights. The insights from this dashboard will be used in communicating findings and recommendations to the Engagement Partner.

## Data Collection and Preparation
### Data Sources: 
The dataset was provided by PWC in an Excel worksheet document and it included 7,043 rows and 23 columns which contains customer demographic information, account details, and service subscription data, all of which are crucial for identifying churn patterns. 
View the dataset here [02 Churn-Dataset.xlsx](https://github.com/user-attachments/files/17340030/02.Churn-Dataset.xlsx)

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
Two interactive dashboards were created in Power BI to provide a detailed view of customer churn and retention:

a) Customer Retention Dashboard
- Metrics Displayed:
   - Total customers, number of tickets (tech and admin), total monthly charges, and yearly charges.
   - Churn by demographic factors and service usage patterns.
- Visuals:
   - Pie charts for customer demographics, tenure, and churn by service usage.
   - Bar charts for churn by payment method, contract type, and tenure in years.
- Purpose: This dashboard allows the Retention Manager to explore churn across various customer segments and understand which groups are most likely to churn, enabling 
  targeted interventions.

![churn report](https://github.com/user-attachments/assets/1188e86b-fb36-4329-a82a-700ac1b83db0)

b) Customer Risk Analysis Dashboard
- Interactive Filters:
    - Filters for churn risk, internet service type, tenure in months, and contract type.
- Visuals:
    - Churn rate by internet service type, tenure, and payment method.
    - Churn by customer contract type and monthly charges by internet service type.
    - Gauge for overall churn rate and total customers with their churn risk status.
- Purpose: This dashboard provides a dynamic and comprehensive view of the factors influencing churn, enabling the client to isolate high-risk segments and make informed 
  decisions to address churn risks.

![customer risk report](https://github.com/user-attachments/assets/feafc544-8f9b-4f0f-9d20-27c1313b50d1)

[View the dashboards here](https://app.powerbi.com/view?r=eyJrIjoiMTg3MThkNmItN2IyYy00ZDZjLWEzZTgtYzk5NzU4MTcwMDlkIiwidCI6ImFlNmFhZDgzLWRmNmYtNDkwZi1iMTU5LWNhZDVjNjUyYjhmMCJ9)

## Insights and Recommendations
The analysis led to several key insights and strategic recommendations:

- High-Risk Customer Segments:

    - Month-to-Month Contracts: Customers with month-to-month contracts had the highest churn rates. Implementing loyalty programs or offering incentives for switching to 
      longer contracts could help retain these customers.
    - Fiber Optic Internet Service: Customers with fiber optic service showed a higher likelihood of churning. Reviewing service quality or pricing could help reduce churn in 
      this group.
    - Electronic Check Payment: The churn rate was higher among customers using electronic check payment. Encouraging alternative payment methods like credit cards or 
      paperless billing may improve retention.
      
- Retention Strategies:

    - Personalized Offers: Tailor retention offers to high-risk segments based on contract type and tenure. For example, long-term discounts for new contract sign-ups could 
      appeal to month-to-month customers.
    - Service Quality Improvement: For fiber optic users, invest in service quality enhancements or bundled packages to increase perceived value.
    - Payment Method Promotions: Provide incentives for customers to switch to more secure payment methods to increase satisfaction and reduce churn rates.

## Implementation and Handover
After the dashboards were finalized, they were presented to the client with a demonstration of how to navigate and use the filters to explore various scenarios. Training sessions were conducted to ensure that the client’s team can independently monitor and analyze customer churn going forward.

## Conclusion
By leveraging Power BI, the PwC team provided the telecom client with an insightful and actionable solution to manage customer churn. The dashboards developed serve as powerful tools for the Retention Manager and other stakeholders to understand churn dynamics, implement retention strategies, and ultimately improve customer satisfaction and reduce churn rates.

The dashboards will also enable ongoing monitoring, making it easier for the client to respond to changing trends in customer behavior, ensuring that the retention strategies remain effective and up-to-date.
