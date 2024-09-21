
# Bike Rental Prediction Project

This project involves predicting future bike rentals based on historical data from a bike-sharing service. We use various features such as weather conditions, seasonality, lagged features (previous days' rentals), and more to build predictive models.

## Project Overview

The dataset contains information on bike rentals aggregated at an hourly and daily level. Our goal is to predict the **total count of bikes rented** on future dates using regression models.

### Files
- `hour.csv`: Bike-sharing counts aggregated on an hourly basis.
- `day.csv`: Bike-sharing counts aggregated on a daily basis.

### Dataset Features:
- **instant**: Record index
- **dteday**: Date
- **season**: Season (1:spring, 2:summer, 3:fall, 4:winter)
- **yr**: Year (0:2011, 1:2012)
- **mnth**: Month (1 to 12)
- **weekday**: Day of the week
- **workingday**: Whether the day is a working day or not
- **weather_condition**: Weather condition (1 to 4)
- **temp**: Normalized temperature
- **casual**: Count of casual users
- **registered**: Count of registered users
- **total_count**: Total number of bikes rented (casual + registered)

## Approach

### 1. **Data Preprocessing**
   - Checked for missing values, handled outliers, and created additional features (e.g., lagged features like `cnt_lag_1` and `cnt_lag_7`).
   - Used `season`, `year`, `month`, `weekday`, `workingday`, `weather_condition`, and `temp` as the main features for modeling.

### 2. **Feature Engineering**
   - **Lagged Features**: Created lagged features to account for the bike rentals from the previous day (`cnt_lag_1`) and a week ago (`cnt_lag_7`).
   
### 3. **Modeling**
   - Used **Linear Regression** to predict the number of casual and registered users separately.
   - The total count of bike rentals is predicted by summing the casual and registered user predictions.

### 4. **Evaluation**
   - Evaluated model performance using metrics such as **Mean Squared Error** and **R-squared**.
   - Checked model assumptions like linearity, homoscedasticity, and normality of residuals.

### 5. **Future Predictions**
   - Predicted bike rentals for the next 30 days based on the trained model, using simulated future data for weather conditions, temperature, etc.

## Results

- The model achieved an **R-squared score** of approximately 0.97 on the training set, indicating a good fit for the data.
- Future predictions for bike rentals were generated and visualized for the next 30 days.

## Visualizations

- **Residuals Plot**: To check for linearity and homoscedasticity.
- **Correlation Matrix**: To analyze relationships between numerical variables.
- **Future Predictions Plot**: Visualized the predicted bike rentals for the next 30 days.
  
