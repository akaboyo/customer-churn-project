![Image](https://github.com/user-attachments/assets/efba1050-5912-4ca3-a4e2-8411d23a0346)

# CUSTOMER CHURN ANALYSIS 
**Why are PhoneNow customers leaving, and which segments should Retention focus on first?**

An end-to-end churn analysis built in Power BI for a telecom client, using PwC-provided customer data.

## VERDICT
**Churn is concentrated, not random.** 26.54% of PhoneNow's 7,043 customers have churned-and that risk is heavily loaded onto three identifiable groups: **month-to-month contract holders**, **fiber optic subscribers**, and customers paying by **electronic check**. Fixing retention for those three segments alone would address the majority of churn risk, rather than requiring a broad, unfocused retention campaign.

## Executive Summary

**PhoneNow,** a telecom provider, needed to understand why customers were leaving and where to focus
retention spend. Using a PwC-provided dataset of customer demographics, account details, and
service usage, I cleaned and modeled the data in Power BI and built two interactive dashboards
that let the Retention team isolate high-risk segments instead of guessing at them.

**The headline numbers:**

| Metric | Value |
|---|---|
| Total customers | 7,043 |
| Overall churn rate | 26.54% |
| Total charges | $16.06M |
| Highest-risk contract type | Month-to-month |
| Highest-risk internet service | Fiber optic (41.89% churn rate) |
| Highest-risk payment method | Electronic check |

## Table of Contents

- [Business Objective](#business-objective)
- [Data Source](#data-source)
- [Data Preparation](#data-preparation)
- [Dashboards](#dashboards)
- [Key Insights](#key-insights)
- [Recommendation](#recommendation)
- [Business Impact](#business-impact)
- [Skills Demonstrated](#skills-demonstrated)
- [Tools](#tools)

## Business Objective

- Understand the factors that contribute to customers leaving the service.
- Provide visual insights to help the Retention Manager and stakeholders focus on high-risk customer segments.
- Support data-driven decisions to reduce churn, improve retention, and protect revenue.

## Data Source

The dataset was provided by PwC in Excel format and includes:
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
3. Built 14 DAX measures to power the dashboards — churn rate, customer lifetime value, and service-adoption breakdowns among them.

Full formulas: [`/docs/dax-measures.md`](docs/dax-measures.md)

## Data Visualization

### Customer Retention Dashboard

A full view of who's churning and why - demographics, account information, and service subscriptions in one place, so the Retention team can explore churn across any customer segment.

![churn report](https://github.com/user-attachments/assets/1188e86b-fb36-4329-a82a-700ac1b83db0)

### Customer Risk Analysis Dashboard

An interactive, filterable view built specifically to isolate high-risk segments - filter by churn risk, internet service type, tenure, or contract type to see exactly where retention effort will have the most impact.

![customer risk report](https://github.com/user-attachments/assets/feafc544-8f9b-4f0f-9d20-27c1313b50d1)

[View the dashboards here](https://app.powerbi.com/view?r=eyJrIjoiMTg3MThkNmItN2IyYy00ZDZjLWEzZTgtYzk5NzU4MTcwMDlkIiwidCI6ImFlNmFhZDgzLWRmNmYtNDkwZi1iMTU5LWNhZDVjNjUyYjhmMCJ9)

**[Explore both dashboards live on Power BI](https://app.powerbi.com/view?r=eyJrIjoiMTg3MThkNmItN2IyYy00ZDZjLWEzZTgtYzk5NzU4MTcwMDlkIiwidCI6ImFlNmFhZDgzLWRmNmYtNDkwZi1iMTU5LWNhZDVjNjUyYjhmMCJ9)**
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
