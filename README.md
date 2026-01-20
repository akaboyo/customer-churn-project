# CUSTOMER CHURN ANALYSIS 

## Executive Summary

This project analyses customer churn for a telecom client (PhoneNow) to understand why customers leave and identify patterns that signal churn risk. Using a PwC-provided dataset with customer demographics, account details, and service usage fields, the work combines data cleaning, exploratory analysis, and interactive visualization in Power BI to reveal key churn drivers. The resulting dashboards help stakeholders spot high-risk segments and make data-informed decisions to improve retention strategies and reduce revenue loss from churn

## Project Overview
This project examines customer churn for a telecom company, PhoneNow, with the objective of understanding churn patterns and supporting proactive retention strategies. The analysis uses Power BI to clean, model, and visualise customer behaviours that correlate with churn.

## Business Objective

- Understand the factors that contribute to customers leaving the service.
- Provide visual insights to help the Retention Manager and stakeholders focus on high-risk customer segments.
- Support data-driven decisions to reduce churn and improve retention.

## Data Source

The dataset was provided in Excel format and includes:
- Customer demographic details
- Account and service subscription information
- Billing and contract fields
View the dataset here [02 Churn-Dataset.xlsx](https://github.com/user-attachments/files/17340030/02.Churn-Dataset.xlsx)

## Data Preparation

1. Imported the dataset into Power BI.
2. Cleaned and transformed columns using Power Query:
   - Handled missing values (e.g., “Total charges” nulls replaced).
   - Corrected and standardised data types.
   - Created derived features like tenure categories for deeper analysis.

## Exploratory Data Analysis (EDA): 

The dataset was analysed across key segments:
- **Demographics:** churn by age, gender, partner/dependents
- **Contracts:** churn by contract type (month-to-month, yearly, etc.)
- **Services:** churn patterns across internet service types and add-ons
- **Billing:** payment method and monthly charge correlations with churn 

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

## Business Implications

These insights suggest that churn is driven more by contract structure, pricing, and customer lifecycle stage than by demographic characteristics. Retention strategies should therefore prioritize early-stage customers, promote longer-term contracts, incentivize automated payments, and closely monitor high-value customers on flexible plans.
