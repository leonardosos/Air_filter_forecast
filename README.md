# CO2 Forecasting with Machine Learning

This university project aims to predict CO2 concentration in a bedroom using several machine learning models. The goal is to forecast CO2 levels 20 minutes into the future based on data collected from a one-hour window CO2 concentration environmental sensors. Four different supervised learning models were developed and compared, including:

- **K-Nearest Neighbors (KNN)**
- **Random Forest Regressor**
- **Linear Regression**
- **Neural Network**

![forecast-comparation](https://github.com/user-attachments/assets/8a707374-a552-4e03-b2e0-f0bceb5cb613)

## Dataset
The dataset contains environmental sensor readings, primarily focused on CO2 measurements, along with PM1, PM2.5, PM10, temperature, and humidity. Data has been collected over a span of two years, with a time interval of 4 minutes between each reading.

The dataset required extensive cleaning due to:
- Sensor faults: Zero or unrealistic values like readings below 400 ppm for CO2 were filtered.
- Missing values: Zeros and missing data points (`NaN`) were replaced or interpolated.
- Time series segmentation: 80-minute windows were derived to allow a 60-minute observation window and a 20-minute forecast horizon.

![co2_2days](https://github.com/user-attachments/assets/1772a7c7-bb4f-46d1-b8b5-960cee91e42e)


## Model Training and Evaluation
The models were trained on 80% of the data and tested on the remaining 20%. Neural Networks were trained using an additional 15% validation set for early stopping.

- **Neural Network:** Best performer in terms of Mean Absolute Error (MAE). 
- **Random Forest Regressor:** Competitive performance, close to the Neural Network.
- **Linear Regression:** Offered decent performance but limited by its linear assumptions.
- **K-Nearest Neighbors (KNN):** Sub-optimal performance, with the lowest accuracy among the models.

### Model MAE Performance:
- **Neural Network:** 89.11
- **Random Forest Regressor:** 90.94
- **Linear Regression:** 91.48
- **KNN (N=27):** 96.03

## Conclusion
The **Neural Network** achieved the best forecasting accuracy, followed closely by the **Random Forest Regressor**. The **KNN** model struggled with this dataset, while **Linear Regression** showed moderate results, limited by its linear nature. This analysis highlights the effectiveness of advanced models like Neural Networks for time-series forecasting tasks, especially in environmental data with complex patterns.

### Future Improvements
- Explore correlation between features such as particulate matter and humidity for improving the prediction model.
- Integrate seasonality factors to refine prediction accuracy over long-term data.

---

**Author**: Leonardo Brighenti  
**Last Modified**: September 2024
