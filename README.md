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
- Grabbed a table that showed the product names and count of purchases for the products based on subscription tier seen [here.](https://github.com/V-Holguin/SubscriptionTiers/blob/main/KQL%20Queries/2.1.txt)
  - Silver showed top item was Petanque Balls, followed by Darts, 2 tents, then rain pants
    - The two tents account for 46.24% of sales within the top 5 items of Silver when grouped together
  - Gold showed similar results with Petanque Balls followed by Darts.
    - Here we have tennis shoes coming in at 3rd followed by the same two tents from before.
  - Platinum showed similar category results with a slight difference.
    - Top 2 items were tents this time with the top seller being a "Family Holiday" tent. The "Hurricane" tent seen in Silver and Gold is not present in the top 5, while Silver and Gold didn't show a "Family Holiday" tent in their results.
    - Pentanque Balls and 2 sets of Darts construct the other 3 results.
    - This can imply Platinum members are shopping for their family while Silver and Gold members are individual shoppers, but lets dig deeper.
- Checked regular customers by subscription type by defining a regular customer as one that has at least 3 purchases [here.](https://github.com/V-Holguin/SubscriptionTiers/blob/main/KQL%20Queries/2.2.txt)
  - We have 9,014 Silver, 8,338 Gold, and 3 Platinum regular customers.
  - And 43,603 Silver, 43,453 Gold, and 3,974 Platinum unique customers.
  - Which means 20.7% of Silver customers are reapeat customers. 19.2% of Gold are reapeat. 0.08% of Platinum are repeat.
  - Rate of repeat customers that are Platinum members is dramatically low.
  - We now know Platinum members shop for their family and are not repeat customers.
- Investigated regular customers more by looking at their order totals [here.](https://github.com/V-Holguin/SubscriptionTiers/blob/main/KQL%20Queries/2.3.txt)
  - Silver non repeat: $140.87, Silver repeat: $138.20 (1.9% Drop)
  - Gold non repeat: $138.90, Gold repeat: $136.82 (1.5% Drop)
  - Platinum non repeat: $139.91, Platinum repeat: $120.01 (14.2% Drop)
  - There is a significant difference in order total but we need to keep in my that Platinum members make up 7.07% of customers and of that, 0.08% of them are repeat customers so we are looking at a small sample
- Lastly, I investigated which items repeat customers were buying grouped by their subscription tier [here.](https://github.com/V-Holguin/SubscriptionTiers/blob/main/KQL%20Queries/2.4.txt)
  - Silver showed no difference between repeat and non-repeat customers.
  - Gold had similar results.
  - Platinum showed a complete shift away from Sports items towards Clothing items.
    - Tennis shoes, women's polo, backpack, women's shirt.
    - This can mean regular Platinum customers shop for clothing, but again this is a very small sample.

## Step 5: Conclusions and Specified Recommendations
- 
