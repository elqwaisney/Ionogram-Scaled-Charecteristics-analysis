# Ionogram TEC Time Series Analysis

Total Electron Content (TEC) is a crucial parameter in ionospheric studies, representing the total number of electrons present along a path between two points, typically between a satellite and the Earth's surface. This analysis focuses on the TEC data collected over a specific period, and various time series analysis techniques are employed to gain insights and forecast future values.

## Project Overview

This project aims to analyze the TEC data from `2022-05-01` to `2022-08-01` using time series analysis techniques. The steps involved include data wrangling, decomposition of the time series, testing for stationarity, and forecasting future TEC values.


## Data Source

The TEC data was queried from the Digital Ionogram Data Base (DIDBase). In the query, I chose the ATHENS (AT138) station as it was the closest to Egypt. The data was recorded by an ionosonde, which is an instrument used to measure the ionosphere's electron density profile.

[Database Link](https://giro.uml.edu/didbase/scaled.php)

## Importance of TEC and foF2 Frequency

TEC is useful in determining the critical frequency of the F2 layer of the ionosphere (foF2), which is the highest frequency at which a radio wave can be transmitted vertically and still be reflected back to Earth. The foF2 frequency is important because it affects high-frequency (HF) radio communications, satellite communications, and navigation systems. Understanding and predicting TEC and foF2 can help in improving the reliability and accuracy of these systems.

## Key Steps and Methods

1. **Data Wrangling**:
   - Handled missing data effectively.
   - Resampled the data to 1-hour intervals for consistent analysis.

2. **Time Series Decomposition**:
   - Explored the decomposition of the TEC time series into its trend, seasonality, and residual components to understand underlying patterns.

3. **Stationarity Testing**:
   - Conducted the Augmented Dickey-Fuller (ADF) test to determine if the mean and variance of the TEC time series are stationary (time-independent).

4. **Forecasting**:
   - Used AutoRegressive (AR) and ARIMA models to forecast TEC values for `2022-08-02`.
   - Implemented forward walk validation to assess the forecasting performance and ensure the robustness of the models.

## Results

- **Baseline Model**:
  - Baseline MAE: 5.44

- **AutoRegressive Model**:
  - Train MAE: 1.589
  - Test MAE: 1.885
  - Test MAE (walk forward validation): 1.64

- **ARIMA Model**:
  - Test MAE (walk forward validation) for order (24, 0, 2): 1.64

The analysis provided insights into the trends and seasonal patterns of TEC, and the forecasting models showed promising results in predicting future TEC values. The forward walk validation helped in fine-tuning the models for better accuracy.

## Conclusion

This project demonstrates a comprehensive approach to time series analysis and forecasting of TEC. The methods employed can be applied to similar datasets to gain valuable insights and make accurate predictions. Understanding and predicting TEC and foF2 frequencies can significantly enhance the reliability of communication and navigation systems.
