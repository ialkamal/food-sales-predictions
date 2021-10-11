# Food Sales Predictions

BigMart have collected 2013 sales data for 1559 products across 10 stores in different cities. Also, certain attributes of each product and store have been defined. The aim is to build a predictive model and predict the sales of each product at a particular outlet.

## Dataset
src: https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/
- Entries: 8,522
- Features: 12

| **Variable** | **Description** |
| -------------- | ---------------- |
| Item_Identifier | Unique product ID |
| Item_Weight     | Weight of product |
| Item_Fat_Content | Whether the product is low fat or not |
| Item_Visibility | The % of total display area of all products in a store allocated to the particular product |
| Item_Type | The category to which the product belongs |
| Item_MRP | Maximum Retail Price (list price) of the product |
| Outlet_Identifier | Unique store ID |
| Outlet_Establishment_Year | The year in which store was established |
| Outlet_Size | The size of the store in terms of ground area covered |
| Outlet_Location_Type | The type of city in which the store is located |
| Outlet_Type | Whether the outlet is just a grocery store or some sort of supermarket |
| Item_Outlet_Sales | Sales of the product in the particular store. **This is the outcome variable to be predicted.** |

## Observations

##### Q1. Do more visible items sell more?

From the graph comparing the 200 most visible items with the least 200 visible items, it seems that the more visible items sell a bit less than the less visible items which is quite surprising. There maybe something wrong with the visibilty data especially anything that has a visiblity of 0.

<img src="/images/visible.png"/>

##### Q2. Do Low Fat Items gross more in sales?

There is no significant different in gross sales between low fat content items and regular content items with a number of low fat content outliers grossing much more than their regular counterparts.

<img src="/images/fat.png"/>

##### Q3. What outlets do better in terms of total item sales?

The data indicates that Outlet 27 outperforms the others in terms of item sales and both outlets 10 and 19 underperforms.

<img src="/images/outlets.png"/>

##### Q4. Do more expensive items bring in more sales?

The data shows that more expensive items gross more in sales. This needs more investigation to justify the findings.

<img src="/images/outlet_sales.png"/>

## Prediction Models and their Performance

| Model| R<sup>2</sup> | RMSE |
|---|---|---|
|Baseline| -.48% | 1,664.98|
|Linear Regression| 56.71% | 1092.86|
|Decision Tree| 58.57% | 1,069.13|
|Bagging Trees| 55.23% | 1,111.40|
|Random Forest| 60.68% | 1,041.61|

**Random Forest** did the best with an R<sup>2</sup> score of 60.68% and a root mean sqaure error of 1,041.61.
