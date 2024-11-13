# Ex.No: 6 HOLT WINTERS METHOD

## Name:H.Berjin Shabeck
## Reg no:212222240018
## Date:21/09/2024

### AIM:
    To create and implement Holt Winter's Method Model using python.

### ALGORITHM:
1. You import the necessary libraries
2. You load a CSV file containing daily sales data into a DataFrame, parse the 'date' column as
datetime, and perform some initial data exploration
3. You group the data by date and resample it to a monthly frequency (beginning of the month
4. You plot the time series data
5. You import the necessary 'statsmodels' libraries for time series analysis
6. You decompose the time series data into its additive components and plot them:
7. You calculate the root mean squared error (RMSE) to evaluate the model's performance
8. You calculate the mean and standard deviation of the entire sales dataset, then fit a Holt-
Winters model to the entire dataset and make future predictions
9. You plot the original sales data and the predictions
### PROGRAM:
```
Name: H.Berjin Shabeck
Reg no:212222240018

import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.holtwinters import ExponentialSmoothing

# Create the dataset (Hours and Scores)
df = pd.read_csv('score.csv')



# Using 'Scores' as the time series data for Holt-Winters
scores_series = df['Scores']

# Fit the Holt-Winters model
hw_model = ExponentialSmoothing(scores_series, trend="add", seasonal=None, seasonal_periods=None).fit()

# Forecast the next 5 periods
forecast = hw_model.forecast(steps=5)

# Plot the original data and forecast
plt.figure(figsize=(10,6))
plt.plot(scores_series, label='Original Scores')
plt.plot(range(len(scores_series), len(scores_series)+5), forecast, label='Forecasted Scores', linestyle='--')
plt.title('Holt-Winters Method on Scores')
plt.xlabel('Time Index')
plt.ylabel('Scores')
plt.legend()
plt.show()

# Display forecasted values
print(forecast)
```

### OUTPUT:
![download](https://github.com/user-attachments/assets/8cee85ec-153b-42fd-8455-406b5e14c584)
25    60.193832
26    60.862119
27    61.530406
28    62.198693
29    62.866980
dtype: float64
### RESULT:
Thus the program run successfully based on the Holt Winters Method model.
