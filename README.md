# Telecom Customer Churn Analysis

## Table of Contents

   [Project Overview](#project-overview)

   [Data Source](#data-sources)
   
   [Recommendations](#recommendations)

### Project Overview

This data analysis project aims to provide insights into customer churn behavior in a telecom company. By analyzing various aspects of customer and usage data, we aim to identify churn trends, build predictive models, and gain a deeper understanding of customer retention challenges.

### Data Sources

Customer Data: The primary dataset used for this analysis is the "Customer_Data.xls" file, containing detailed information about customer demographics, service usage, billing, contract types, and churn labels.

### Tools

- SQL Server [Download here](https://microsoft.com)
- Power BI  
- Python (Jupyter Notebook – pandas, scikit-learn, seaborn)  

### Key Project Components

1. **ETL Process in SQL Server**  
   Extracted raw data from multiple tables and performed data transformations using SQL joins and views. The cleaned, structured data was loaded into a central reporting table for analysis.

2. **Data Cleaning in SQL Server**  
   Handled missing values, duplicates, and inconsistent formats using SQL queries. Created calculated fields and applied business rules to enhance data quality.

3. **Power BI Transformations**  
   Used Power Query to filter, reshape, and enhance data. Built relationships and created new columns and measures to support dashboarding.

4. **Power BI Visualization & Enhancing Visuals**  
   Designed an interactive Power BI dashboard with KPIs, charts, slicers, and drill-down features. Visualized churn rates by segment, tenure, contract type, and monthly trends.

5. **Build Machine Learning Model – Random Forest in Jupyter Notebook**  
   Conducted exploratory data analysis (EDA) and feature engineering in Python. Trained a Random Forest classifier to predict customer churn with ~85% accuracy using key behavioral features.

6. **Visualize Predicted Data in Power BI – Predicted Churner Profile**  
   Imported model predictions into Power BI to identify high-risk customers. Built visuals to compare predicted churners vs. loyal customers by key characteristics, enabling strategic retention efforts.

### Data Cleaning/Preparation

In the initial data preparation phase, we performed the following tasks:  
1. Data loading and inspection.  
2. Handling missing values.  
3. Data cleaning and formatting.

### Exploratory Data Analysis

EDA involved exploring the telecom customer data to answer key questions, such as:  

- What is the overall churn rate trend?  
- Which customer segments have the highest churn rates?  
- What are the key factors influencing customer churn?

## Power BI Dashboard

- Created an interactive Power BI dashboard to visualize telecom churn insights.
- Dashboard features include:
  - Churn rate trends over time.
  - Customer segmentation by demographics and contract type.
  - Key metrics such as Monthly Charges, Tenure, and Customer Lifetime Value (LTV).
  - Dynamic slicers and filters for exploring high-risk churn groups.
- The dashboard helps stakeholders quickly identify churn drivers and monitor retention efforts.

## Machine Learning Model

- Built a Random Forest classifier in Python (Jupyter Notebook) to predict customer churn.
- Key steps involved:
  - Data preprocessing and feature engineering based on cleaned telecom data.
  - Splitting data into training and testing sets.
  - Training and hyperparameter tuning of the Random Forest model.
  - Model evaluation using accuracy, precision, recall, and ROC-AUC metrics.
- Achieved ~85% accuracy and 0.90 ROC-AUC, indicating strong predictive power.
- Exported predicted churn probabilities for visualization and further analysis in Power BI.

  ## Results / Findings

- The overall churn rate was highest among customers with month-to-month contracts (~35%).  
- Customers with longer contract durations showed significantly lower churn rates.  
- Higher monthly charges and shorter customer tenure were strongly associated with increased churn risk.  
- The Random Forest machine learning model achieved an accuracy of approximately 85%, with an ROC-AUC score of 0.90, demonstrating strong ability to predict churn.  
- The Power BI dashboards provided clear visual insights into churn patterns, helping stakeholders identify at-risk customer segments.  
- Customers predicted to churn with high probability should be prioritized for targeted retention campaigns and personalized marketing efforts.

  ### Recommendations

Based on the analysis, we recommend the following actions:  
- Invest in targeted retention campaigns focusing on high-risk churn customers to reduce churn rates.  
- Promote longer-term contract plans to improve customer loyalty and reduce month-to-month churn.  
- Implement personalized offers and loyalty programs for customers with high Monthly Charges and low tenure.  
- Use customer segmentation insights to tailor marketing strategies for different demographic groups.

### Limitations

Certain limitations impacted the analysis:  
- Some missing or inconsistent customer data had to be imputed or removed, which might affect the model accuracy.  
- Outliers in monthly charges and tenure could skew the predictions despite preprocessing efforts.  
- External factors like market competition or seasonal trends were not included in the dataset.  
- The model may require periodic retraining as customer behavior and telecom offerings evolve.

### References

1. SQL for Businesses by werty.  
2. [Stack Overflow](https://stackoverflow.com) – for coding and query troubleshooting.  
3. Scikit-learn documentation – for machine learning model implementation.  
4. Power BI official documentation – for dashboard creation and transformations.
