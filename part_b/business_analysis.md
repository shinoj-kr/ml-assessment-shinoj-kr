# Part B: Business Case Analysis
## Scenario: Promotion Effectiveness at a Fashion Retail Chain
### B1. Problem Formulation
(a) The target variable is Items_Sold, which represents the total number of units sold for a given store, month, promotion, and product category. This clearly defines sales volume without ambiguity. The input features include Location_Type, Month, Promotion_Type, Store_Size, Local_Competition, Event_Flag, Event_Type, Avg_Customer_Age, Gender_Distribution, Avg_Income_Level, Customer_Segment, and Product_Category.

This is a Supervised Learning regression problem, as we are predicting a continuous value. This approach is justified because the business goal is to maximise sales by selecting the best promotion, which requires predicting the number of items sold under different conditions. Features like product category, seasonality, events, and customer demographics help capture real-world demand patterns.

(b) Items sold (sales volume) is a more reliable target because it directly reflects customer demand, while price and discount act as influencing factors captured in the input features. Revenue can be misleading due to price fluctuations, but items sold clearly shows how demand changes across different promotions. This also illustrates that the target variable should be closely aligned with the business objective, which in this case is selecting the most effective promotion for each store. Choosing items sold ensures the model directly supports this decision by identifying which promotion leads to higher sales, whereas a poorly chosen target could result in incorrect promotion strategies despite good model performance.

(c) A single global model may not perform well because stores in different locations can respond differently to the same promotion. An alternative approach is to group similar stores based on factors like location, customer demographics, and sales patterns using business logic or clustering.
Then, separate regression models can be trained for each group. For example, a flat discount may work better in urban stores, while a buy-one-get-one (BOGO) offer may be more effective in rural stores for the same product. This approach captures group-specific behaviour and leads to more accurate predictions and better promotion decisions.




