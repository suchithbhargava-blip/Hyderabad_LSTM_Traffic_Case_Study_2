# Hyderabad Traffic Flow & Congestion Prediction Using LSTM

## Project Overview

This project focuses on analyzing traffic patterns and predicting traffic flow and congestion levels in Hyderabad, Telangana, using Deep Learning techniques.

A Multivariate Long Short-Term Memory (LSTM) neural network is developed to forecast the next 15-minute traffic speed and congestion index at selected traffic hotspots.

The project uses time-series analysis, data preprocessing, exploratory data analysis, LSTM model training, and performance evaluation to demonstrate how deep learning can be applied to traffic prediction.

**Important:** The current implementation uses synthetic demonstration traffic data rather than real-world measured Hyderabad traffic data. Therefore, the results demonstrate the model pipeline and should not be interpreted as actual traffic measurements.

---

## Project Objectives

- Analyze traffic patterns across selected Hyderabad traffic hotspots.
- Understand the relationship between traffic speed and congestion.
- Perform data preprocessing and exploratory data analysis.
- Develop a multivariate LSTM deep learning model.
- Predict traffic speed and congestion for the next 15-minute interval.
- Evaluate model performance using MAE, RMSE, and R².
- Generate traffic forecasts and visualizations.

---

## Project Details

| Parameter | Description |
|---|---|
| Project Name | Hyderabad LSTM Traffic Case Study |
| Domain | Deep Learning / Traffic Prediction |
| Location | Hyderabad, Telangana, India |
| Model | Multivariate LSTM |
| Number of Locations | 8 Traffic Hotspots |
| Dataset Duration | 30 Days |
| Sampling Interval | 15 Minutes |
| Historical Input | Previous 24 Observations |
| Prediction Horizon | Next 15 Minutes |
| Prediction Targets | Traffic Speed and Congestion Index |
| Evaluation Metrics | MAE, RMSE, R² |

---

## Technologies Used

### Programming Language
- Python

### Libraries and Frameworks
- NumPy – Numerical computations.
- Pandas – Data manipulation and preprocessing.
- Matplotlib – Data visualization.
- Seaborn – Statistical visualization.
- Scikit-learn – Data scaling and model evaluation.
- TensorFlow – Deep learning framework.
- Keras – LSTM model development.
- Joblib – Saving preprocessing scalers.

### Development Environment
- Google Colab
- Jupyter Notebook
- GitHub

---

## Project Workflow

The project follows these major stages:

1. Dataset loading
2. Data cleaning and preprocessing
3. Feature engineering
4. Exploratory Data Analysis (EDA)
5. Data normalization
6. Time-series sequence generation
7. LSTM model development
8. Model training and validation
9. Model evaluation
10. Traffic prediction and forecasting
11. Saving the trained model and prediction results

---

## Dataset Description

The project uses a synthetic traffic demonstration dataset representing traffic conditions across 8 selected locations in Hyderabad.

The dataset contains 30 days of demonstration history with observations collected at 15-minute intervals.

### Dataset Features

| Feature | Description |
|---|---|
| timestamp | Date and time of observation |
| location | Traffic hotspot identifier |
| current_speed_kmph | Current traffic speed |
| free_flow_speed_kmph | Reference free-flow speed |
| congestion_index | Traffic congestion indicator |
| rainfall_mm | Rainfall measurement |
| temperature_c | Temperature measurement |

### Data Preprocessing

The following preprocessing operations are implemented:

- Timestamp conversion and validation.
- Sorting records by location and time.
- Handling missing numerical values using median imputation.
- Converting numerical columns into appropriate data types.
- Extracting hour, day of week, and weekend information.
- Applying cyclical encoding to time-related features.
- Normalizing input and target variables using MinMaxScaler.

---

## Exploratory Data Analysis (EDA)

Exploratory Data Analysis is performed to understand traffic patterns and identify trends.

The project generates visualizations such as:

- Traffic speed variations across different locations.
- Congestion index comparison across traffic hotspots.
- Average congestion levels throughout the day.
- Training and validation loss curves.
- Actual versus predicted traffic speed.
- Actual versus predicted congestion index.

---

## LSTM Model Architecture

The project uses a Multivariate LSTM architecture to learn temporal dependencies from historical traffic observations.

### Model Structure

| Layer | Configuration |
|---|---|
| Input Layer | 24 time steps, 10 features |
| LSTM Layer 1 | 64 units |
| Dropout | 0.2 |
| LSTM Layer 2 | 32 units |
| Dropout | 0.2 |
| Dense Layer | 16 units, ReLU |
| Output Layer | 2 neurons |

### Model Configuration

- Optimizer: Adam
- Loss Function: Mean Squared Error (MSE)
- Training Epochs: Maximum 30
- Batch Size: 64
- Validation Split: 15%
- Early Stopping: Patience of 6 epochs
- Training and testing split: Chronological 80:20 split for each location.

### Prediction Approach

The model uses the previous 24 observations, representing 6 hours of historical traffic information.

Based on these observations, it predicts:

1. Traffic speed for the next 15-minute interval.
2. Congestion index for the next 15-minute interval.

Each traffic location is processed as a separate time series.

---

## Model Evaluation

The model performance is evaluated using three statistical metrics.

### 1. Mean Absolute Error (MAE)

Measures the average absolute difference between actual and predicted values.

Lower MAE indicates better prediction accuracy.

### 2. Root Mean Squared Error (RMSE)

Measures the square root of the average squared prediction errors.

Lower RMSE indicates smaller prediction errors.

### 3. R-Squared (R²)

Measures how well the model explains variations in the target values.

A value closer to 1 generally indicates a better fit.

**Note:** Actual evaluation scores are calculated when the model is executed. No fixed accuracy or performance values are assumed in this repository.

---

## Project Outputs

After successful execution, the project generates the following files:

| File Name | Description |
|---|---|
| hyderabad_lstm_predictions.csv | Actual and predicted traffic values |
| hyderabad_lstm_metrics.csv | Model evaluation metrics |
| hyderabad_next_15min_forecast.csv | Next 15-minute traffic forecasts |
| hyderabad_traffic_lstm.keras | Trained LSTM model |
| hyderabad_x_scaler.pkl | Saved input scaler |
| hyderabad_y_scaler.pkl | Saved target scaler |

---

## Installation and Execution

### Step 1: Clone the Repository

```bash
git clone https://github.com/suchithbhargava-blip/Hyderabad_LSTM_Traffic_Case_Study_2.git
```

### Step 2: Open the Project

```bash
cd Hyderabad_LSTM_Traffic_Case_Study_2
```

### Step 3: Install Required Libraries

```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow joblib
```

### Step 4: Open Google Colab

Open the original project notebook:

[Open Hyderabad LSTM Traffic Project in Google Colab](https://colab.research.google.com/drive/1WSJ7VtYaKz-c1QnhsAtgggoJteNloy3a)

### Step 5: Upload the Dataset

Upload the required CSV file:

```text
hyderabad_traffic_15min_30days_demo.csv
```

### Step 6: Execute the Notebook

Run the notebook cells sequentially to:

- Load and preprocess the dataset.
- Perform exploratory data analysis.
- Build and train the LSTM model.
- Evaluate prediction performance.
- Generate next 15-minute forecasts.
- Save model files and prediction results.

---

## Future Enhancements

The project can be extended with the following improvements:

- Integrate real-time traffic data from permitted traffic APIs.
- Collect real traffic information using road sensors or CCTV-derived observations.
- Increase the number of traffic monitoring locations.
- Develop a real-time traffic monitoring dashboard.
- Compare LSTM with GRU and other time-series forecasting models.
- Integrate weather and special-event information.
- Deploy the trained model through a web application or REST API.
- Generate traffic congestion alerts based on predicted conditions.

---

## Limitations

- The current dataset contains synthetic demonstration data.
- Predictions are intended to demonstrate the deep learning workflow.
- Results do not represent actual measured Hyderabad traffic conditions.
- Real-world deployment requires collecting and validating actual traffic observations.
- Model performance depends on data quality, sampling frequency, and the selected features.

---

## Conclusion

This project demonstrates the application of Multivariate Long Short-Term Memory networks for traffic flow and congestion prediction.

By combining time-series preprocessing, feature engineering, exploratory analysis, and deep learning, the system forecasts traffic speed and congestion levels for the next 15-minute interval.

The implementation provides a foundation for developing more advanced traffic forecasting systems using real-world traffic data.

---

## Author

**Suchith Bhargava**

GitHub: [@suchithbhargava-blip](https://github.com/suchithbhargava-blip)

Project Repository: [Hyderabad LSTM Traffic Case Study](https://github.com/suchithbhargava-blip/Hyderabad_LSTM_Traffic_Case_Study_2)

---

*Developed using Python, TensorFlow, Keras, and Google Colab.*
