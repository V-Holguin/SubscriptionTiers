# SubscriptionTiers

A case study on historical sales data from a sporting goods store over 5 years to investigate different purchasing behavior between members based on their subscription tier "Silver", "Gold", or "Platinum" 
in order to provide actionable insights that can be used to drive more Platinum subscription sign ups.

## Step 1: Exploring and Cleaning in Microsoft Azure Data Explorer using KQL
- Investigated and removed NULL values, 0s, duplicates, and outliers with these [queries.](https://github.com/V-Holguin/SubscriptionTiers/blob/main/KQL%20Queries/1.1.txt)
- Further explored the data to gain insights on things like how many unique customers and products exist using these [queries.](https://github.com/V-Holguin/SubscriptionTiers/blob/main/KQL%20Queries/1.2.txt)

## Step 2: Adjusting and Exploring in Power BI
- Used the Kusto import wizard on Power BI to load in data after specifying cluster, database, and table.
- Using "Transform Data", deleted a row, 2 columns, and replaced values in the "Customer Status" column to better group
  - The "Customer Status" column had two results for each subscription type. i.e. "Silver" and "SILVER", so I used "replace values" to replace all "SILVER" values with "Silver".
    - The process was repeated for Gold and Platinum.
- Built a pie chart and bar charts to compare the different fields as seen [here.](https://github.com/V-Holguin/SubscriptionTiers/blob/main/Visualization.png)
  - These didn't show distinctions between purchasing habits of customers based on their subscription, so we need to dig deeper.

## Step 3: Digging Deeper with KQL
- 
