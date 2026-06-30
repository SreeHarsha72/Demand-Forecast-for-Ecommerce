# Demand Forecasting Project: Store-Item Daily Sales Forecasting

## About This Project
In this project, I built a machine learning model to forecast daily product demand for different store-item combinations.

The goal of this project is to predict future sales using historical sales data. This type of forecasting can help businesses plan inventory, reduce overstock, avoid stockouts, and improve operational planning.

## Business Problem

Businesses need to know how much demand to expect in the future.

If demand is predicted correctly, the business can:
- Stock the right amount of products
- Reduce product waste
- Avoid out-of-stock situations
- Plan staff and operations better
- Improve customer experience

## Dataset

I used Kaggle dataset: https://www.kaggle.com/competitions/demand-forecasting-kernels-only

The dataset contains daily sales data for multiple stores and items.

## Project Workflow

## 1. Data Loading

I loaded the sales dataset and converted the date column into a proper datetime format.

I also sorted the data by store, item, and date so that time-based features could be created correctly.

## 2. Data Quality Checks

I checked the dataset for:
- Missing values
- Duplicate records
- Basic statistics
- Date ranges

## 3. Exploratory Data Analysis

I analyzed the sales data to understand demand patterns.

The EDA included:
- Total daily demand over time
- Sales distribution
- Total sales by store
- Top-selling items
- Average sales by month
- Average sales by day of week

## 4. Feature Engineering

I created useful forecasting features from the date and historical sales data.

Features included:
- Year
- Month
- Day
- Day of week
- Day of year
- Week of year
- Quarter
- Weekend flag
- Sales lag features
- Rolling mean features
- Rolling standard deviation features

Lag and rolling features were created separately for each store-item combination to avoid mixing sales patterns between products.

## 5. Train-Test Split

Since this is a forecasting problem, I trained the models on past data and tested them on future data.
The last 90 days were used as the test set.

## 6. Models Used

I trained and compared multiple models:

### Baseline Model

The baseline model used the previous 7-day sales value as the prediction.

### Linear Regression

I used Linear Regression as a simple machine learning model to compare against the baseline.

### Random Forest Regressor

I used Random Forest to capture non-linear sales patterns.

### XGBoost Regressor

I used XGBoost because it works well for tabular machine learning problems and can capture complex relationships in the data.

## 7. Model Evaluation

I evaluated the models using:
- MAE
- RMSE
- MAPE
- R² Score

I compared the models and selected the best-performing one based on MAPE.

## 8. Actual vs Predicted Analysis

After selecting the best model, I compared actual sales with predicted sales.
This helped me understand how closely the model was able to follow real demand trends.

## 9. Feature Importance

I analyzed feature importance to understand which features had the most impact on demand prediction.

This helped explain what the model learned from the data.

## 10. Error Analysis

I also performed error analysis to find where the model performed poorly.

I checked:
- Highest prediction errors
- Store-level forecast errors
- Actual vs predicted differences

## 11. Future Forecasting

I created a simple future forecasting section to predict demand for the next 30 days.

The future forecast output includes:
- Date
- Store
- Item
- Forecasted sales
