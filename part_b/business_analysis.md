# Part B: Business Case Analysis
## Scenario: Promotion Effectiveness at a Fashion Retail Chain
### B1. Problem Formulation
(a) The target variable is Items_Sold, which represents the total number of units sold for a given store, month, promotion, and product category. This clearly defines sales volume without ambiguity. The input features include Location_Type, Month, Promotion_Type, Store_Size, Local_Competition, Event_Flag, Event_Type, Avg_Customer_Age, Gender_Distribution, Avg_Income_Level, Customer_Segment, and Product_Category.

This is a Supervised Learning regression problem, as we are predicting a continuous value. This approach is justified because the business goal is to maximise sales by selecting the best promotion, which requires predicting the number of items sold under different conditions. Features like product category, seasonality, events, and customer demographics help capture real-world demand patterns.

(b) Items sold (sales volume) is a more reliable target because it directly reflects customer demand, while price and discount act as influencing factors captured in the input features. Revenue can be misleading due to price fluctuations, but items sold clearly shows how demand changes across different promotions. This also illustrates that the target variable should be closely aligned with the business objective, which in this case is selecting the most effective promotion for each store. Choosing items sold ensures the model directly supports this decision by identifying which promotion leads to higher sales, whereas a poorly chosen target could result in incorrect promotion strategies despite good model performance.

(c) A single global model may not perform well because stores in different locations can respond differently to the same promotion. An alternative approach is to group similar stores based on factors like location, customer demographics, and sales patterns using business logic or clustering.
Then, separate regression models can be trained for each group. For example, a flat discount may work better in urban stores, while a buy-one-get-one (BOGO) offer may be more effective in rural stores for the same product. This approach captures group-specific behaviour and leads to more accurate predictions and better promotion decisions.

### B2. Data and EDA Strategy
(a) The tables can be joined using Store_ID and Date, where transactions are linked with store attributes using Store_ID, and with promotion and calendar data using Date.
The grain of the dataset is one row per store, month, promotion, and product category. For example, one row can represent Store A, January, Flat Discount, TV category with total items sold.
Before modelling, transaction data should be aggregated to calculate total items sold and summary features like average customer metrics and event indicators for each row.

(b) Before building the model, I would perform EDA to understand data quality, patterns, and relationships. I would check missing values, outliers, and consistency in the dataset.
1.	Promotion Type vs Items Sold (Boxplot or Bar Chart): We check which promotions lead to higher sales and how consistent they are. This helps in selecting important features and possibly creating interaction features between promotion and location.
2.	Month vs Items Sold (Line Plot): We look for seasonality patterns such as higher sales in certain months. This helps in creating time-based features or seasonal indicators.
3.	Location Type vs Items Sold (Boxplot): We analyze how sales differ across urban, semi-urban, and rural stores. This can justify grouping stores or adding interaction features with promotion type.
4.	Product Category vs Items Sold (Bar Chart): We examine which categories sell more and how they respond to promotions. This helps in creating category-level features and improving model accuracy.

(c) Since 80% of the transactions have no promotion, the model may become biased and mostly learn patterns for non-promotion cases, ignoring how promotions actually impact sales.
To handle this, we can use resampling techniques. For example, if we have 800 no-promotion and 200 promotion records, we can either reduce no-promotion data to 200 (under sampling) or increase promotion data to 800 (oversampling) to balance the dataset. This helps the model learn the true effect of promotions more accurately.
 








