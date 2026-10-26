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

View the full dax formulas here: [dax-measures.md](https://github.com/user-attachments/files/33964871/dax-measures.md)

## Data Visualization

### Customer Retention Dashboard

A full view of who's churning and why - demographics, account information, and service subscriptions in one place, so the Retention team can explore churn across any customer segment.

![churn report](https://github.com/user-attachments/assets/1188e86b-fb36-4329-a82a-700ac1b83db0)

### Customer Risk Analysis Dashboard

An interactive, filterable view built specifically to isolate high-risk segments - filter by churn risk, internet service type, tenure, or contract type to see exactly where retention effort will have the most impact.

![customer risk report](https://github.com/user-attachments/assets/feafc544-8f9b-4f0f-9d20-27c1313b50d1)

**[View the dashboards live on PowerBi](https://app.powerbi.com/view?r=eyJrIjoiMTg3MThkNmItN2IyYy00ZDZjLWEzZTgtYzk5NzU4MTcwMDlkIiwidCI6ImFlNmFhZDgzLWRmNmYtNDkwZi1iMTU5LWNhZDVjNjUyYjhmMCJ9)**

## Key Insights

- **Month-to-month contracts churn far more than annual ones.** Customers on flexible, no-commitment plans are the single largest churn-risk group - however, the churn rate drops sharply moving from month-to-month to one-year to two-year contracts.
- **Fiber optic customers churn at the rate of 28% higher than DSL customers** (43.96% vs. 34.37%), despite fiber typically being the premium, higher-margin product - a signal worth investigating on price or service-quality grounds rather than assuming premium service means low churn risk.
- **Electronic check payers churn more than any other payment method**, ahead of mailed check, bank transfer, and credit card - a friction or engagement signal, not just a billing preference.
- Demographic factors (age, gender, dependents) showed **weaker correlation with churn** than contract structure and billing behavior - meaning retention strategy should be built around account structure, not customer profile.

## Recommendations

- **Month-to-month customers:** introduce loyalty incentives or pricing benefits for switching to annual contracts - this is the largest, most addressable churn segment.
- **Fiber optic customers:** investigate service quality and pricing perception; a churn rate this high, on a premium product, points to a fixable gap rather than an inherent fiber-customer trait.
- **Electronic check payers:** promote a switch to autopay or card-based billing, which correlates with materially lower churn across the dataset.

## Business Impact

These Insights suggest that churn is driven more by **contract structure, pricing, and billing behavior** than by customer demographics - which means retention strategy can be targeted rather than broad. Prioritizing early-tenure, month-to-month, fiber-optic customers on manual payment methods should capture the majority of addressable churn risk without a blanket, unfocused retention campaign.

## Skills Demonstrated

`Power BI` • `Power Query (ETL)` • `DAX` • `Data Cleaning & Modeling` • `Customer Segmentation` • `Dashboard Design` • `Churn Analysis` 
• `Stakeholder Communication` • `Business Recommendation Writing`

## Tools

- **Power BI** — data modeling, DAX measures, interactive dashboards
- **Power Query** — data cleaning and transformation

### Portfolio project - Customer churn analysis for PhoneNow




