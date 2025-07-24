# Power Query Transformations

## Add a New Column in `prod_Churn`

1. **Churn Status**  
   ```powerquery
   if [Customer_Status] = "Churned" then 1 else 0
   ```
2. **Change Churn Status data type** to **Number**
3. **Monthly Charge Range**  
   ```powerquery
   if [Monthly_Charge] < 20 then "< 20"
   else if [Monthly_Charge] < 50 then "20-50"
   else if [Monthly_Charge] < 100 then "50-100"
   else "> 100"
   ```

---

## Create a New Table Reference: `mapping_AgeGrp`

1. Keep only the **Age** column and **remove duplicates**
2. **Age Group**  
   ```powerquery
   if [Age] < 20 then "< 20"
   else if [Age] < 36 then "20 - 35"
   else if [Age] < 51 then "36 - 50"
   else "> 50"
   ```
3. **AgeGrpSorting**  
   ```powerquery
   if [Age Group] = "< 20" then 1
   else if [Age Group] = "20 - 35" then 2
   else if [Age Group] = "36 - 50" then 3
   else 4
   ```
4. Change **data type** of `AgeGrpSorting` to **Number**

---

## Create a New Table Reference: `mapping_TenureGrp`

1. Keep only the **Tenure_in_Months** column and **remove duplicates**
2. **Tenure Group**  
   ```powerquery
   if [Tenure_in_Months] < 6 then "< 6 Months"
   else if [Tenure_in_Months] < 12 then "6-12 Months"
   else if [Tenure_in_Months] < 18 then "12-18 Months"
   else if [Tenure_in_Months] < 24 then "18-24 Months"
   else ">= 24 Months"
   ```
3. **TenureGrpSorting**  
   ```powerquery
   if [Tenure Group] = "< 6 Months" then 1
   else if [Tenure Group] = "6-12 Months" then 2
   else if [Tenure Group] = "12-18 Months" then 3
   else if [Tenure Group] = "18-24 Months" then 4
   else 5
   ```
4. Change **data type** of `TenureGrpSorting` to **Number**

---

## Create a New Table Reference: `prod_Services`

1. **Unpivot** service columns
2. **Rename Columns**:  
   - `Attribute` → `Services`  
   - `Value` → `Status`

---

# DAX Measures

## Summary Page - Measures

```dax
Total Customers = COUNT(prod_Churn[Customer_ID])

New Joiners = CALCULATE(
    COUNT(prod_Churn[Customer_ID]),
    prod_Churn[Customer_Status] = "Joined"
)

Total Churn = SUM(prod_Churn[Churn Status])

Churn Rate = [Total Churn] / [Total Customers]
```

---

## Churn Prediction Page - Measures

```dax
Count Predicted Churner = COUNT(Predictions[Customer_ID]) + 0

Title Predicted Churners = 
    "COUNT OF PREDICTED CHURNERS : " & COUNT(Predictions[Customer_ID])
```