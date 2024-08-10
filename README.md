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

## Step 3: Recommendations to Encourage Platinum Sign Ups (not targeted *yet*)
- With the current data, we can conclude the tiers have similar purchasing habits.
- To push Platinum sign ups, we can:
  - Run tailored promotions aimed to make Platinum members spend more by providing deals and encourage Silver and Gold members to upgrade their plan to take advantage of savings.
    - A few examples of things to accomplish this can be a percentage off your purchase, or limited-edition items exclusive to Platinum members.
  - Introduce new products or services instead of temporary promotions to drive higher engagement and increase average order values. (This will be a key strategy when exploring who to target later.)
    - This is a longer term approach that allows Silver and Gold members to see items that only Platinum members have access to each time they visit, which will drive Platinum sign ups.
    - A few examples of this can include faster/free shipping for Platinum members, dedicated support, or exclusive access to events for Platinum members in addition to the exclusive products.
- Continuing, it will also be benficial to evaluate membership pricing to ensure each membership accurately reflects its value.
  - If perk changes between tiers is minimal, customers won't see a need to upgrade to a higher tier.
  - If memberships are priced too far apart, the value gained from a higher membership may be offset by the price creating a barrier to entry, which can keep customers from upgrading their tier.

## Step 4: Diving Deeper into Customer Behavior Using KQL
- Grabbed the top 5 most purchased ProductIDs based on subscription tier.
- Grabbed a table that showed the product names and count of purchases for the products based on subscription tier.
  - Silver showed top item was Petanque Balls, followed by Darts, 2 tents, then rain pants
    - The two tents account for 46.24% of sales within the top 5 items of Silver when grouped together
  - Gold showed similar results with Petanque Balls followed by Darts.
    - Here we have tennis shoes coming in at 3rd followed by the same two tents from before.
  - Platinum showed similar category results with a slight difference.
    - Top 2 items were tents this time with the top seller being a "Family Holiday" tent. The "Hurricane" tent seen in Silver and Gold is not present in the top 5, while Silver and Gold didn't show a "Family Holiday" tent in their results.
    - Pentanque Balls and 2 sets of Darts construct the other 3 results.
    - This can imply Platinum members are shopping for their family while Silver and Gold members are individual shoppers, but lets dig deeper.
- 
