# **Solution Summary**

This solution is for "Predict Future Sales" competition hosted on Kaggle. This is the link to the competition: https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales 

In the solution, I have used a LightGBM model and an Ensemble model with RMSE for metric optimization. The Ensemble model combines the predictions of the LightGBM model
and a Linear Regression model. Their predictions are then used as meta-features to a meta Linear Regression
model. The result of the ensemble model was comparable to the LightGBM model alone, but it was more
computationally expensive. Replacing the linear regression with another model or training the LightGBM in the
ensemble model for a longer time is expected to enhance the ensemble model result compared to the LightGBM
alone.

I have used three categories of features. The first category is simple features extracted from the data such as the
month and year of a transaction, the average of item price at a shop per month, the average number of items sold
for each shop per month, and the average number of pieces sold for each item per month. The second category
is “lag” features representing values of some variables/features (such as the number of pieces/sales sold per
month for a shop, an item, or a pair of shops and items and the average item’s price for a shop) at prior time steps
(1, 2, 3, 6, and 12 months). The third category of features is the mean encodings of some variables namely:
"item_id", “shop_id”, and “item_category_id” features. The most important features for the model were the
mean encoding features and the lag feature of the number of pieces sold (sales).

