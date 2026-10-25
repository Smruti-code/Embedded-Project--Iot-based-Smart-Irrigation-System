IOT-BASED SMART IRRIGATION SYSTEM WITH ENVIRONMENTAL AND CLOUD MONITORING

## 📌 Project Overview

The **IoT-Based Smart Irrigation System with Environmental and Cloud-Based Monitoring** is designed to automate plant irrigation by monitoring soil moisture and environmental conditions in real time.

The system uses an **ESP32 microcontroller**, a capacitive soil moisture sensor, and a DHT11 temperature and humidity sensor to monitor the plant's environment. A relay controls a mini water pump according to the soil moisture level, helping reduce unnecessary watering and manual intervention.

Sensor readings and pump status are stored in **Firebase Realtime Database**. A **Python Streamlit dashboard** displays live sensor readings, historical trends, pump activity, and machine-learning-based soil moisture predictions.

The project also includes data analysis using real sensor readings and synthetic data to support model development and evaluation.

## 🎯 Objectives

- Monitor soil moisture, temperature, and humidity in real time.
- Automatically control a water pump based on soil moisture.
- Store sensor readings and pump status in Firebase Realtime Database.
- Visualize current sensor values and historical trends through a dashboard.
- Combine collected real sensor data with synthetic data for experimentation.
- Predict future soil moisture using a machine learning model.
- Analyze prediction performance using evaluation metrics and comparison graphs.

## ✨ Key Features

- **Real-time monitoring:** Displays soil moisture, temperature, and humidity.
- **Automatic irrigation:** Switches the pump ON when the soil is dry and OFF when sufficient moisture is detected.
- **Cloud integration:** Stores sensor readings and system status in Firebase Realtime Database.
- **Interactive dashboard:** Visualizes live readings and historical sensor data using Streamlit.
- **Historical data analysis:** Displays changes in soil moisture, temperature, humidity, and pump status.
- **Machine learning prediction:** Uses a Random Forest Regressor to estimate future soil moisture.
- **Model evaluation:** Compares predictions against actual readings and a baseline model.
- **Combined dataset:** Supports experimentation using real sensor data and generated synthetic data.
- **Data export:** Supports downloading available dashboard data as a CSV file.

## 🛠️ Hardware Requirements

| Component | Purpose |
|---|---|
| ESP32 Dev Module | Reads sensors and controls irrigation |
| Capacitive soil moisture sensor | Measures soil moisture |
| DHT11 sensor | Measures temperature and humidity |
| Single-channel relay module | Switches the water pump |
| Mini DC water pump (3–6 V) | Supplies water to the plant |
| Breadboard | Circuit connections |
| Jumper wires | Connects components |
| USB cable | Programs and powers the ESP32 |
| Suitable external power supply | Powers the pump as required |
| Water tube and plant pot | Delivers water to the plant |

## 💻 Software and Technologies

- **Embedded system:** ESP32
- **Programming language:** C++ for Arduino firmware; Python for data analysis and dashboard
- **Development environment:** Arduino IDE and Visual Studio Code
- **Cloud database:** Firebase Realtime Database
- **Dashboard:** Streamlit
- **Data processing:** Pandas
- **Data visualization:** Plotly
- **Machine learning:** Scikit-learn
- **Model storage and loading:** Joblib
- **Data formats:** CSV

## 🔌 Hardware Connections

| Component | ESP32 Pin |
|---|---|
| Soil moisture sensor analog output (AO) | GPIO 34 |
| DHT11 data pin | GPIO 4 |
| Relay module input (IN) | GPIO 25 |
| Sensor VCC and GND | According to the module specifications |
| Relay VCC and GND 


## ⚙️ Working Principle

1. The ESP32 reads the soil moisture value from the capacitive sensor.
2. The DHT11 sensor measures the surrounding temperature and humidity.
3. The ESP32 compares the soil moisture reading against a configured threshold.
4. If the soil is dry, the relay activates the pump.
5. If sufficient moisture is detected, the pump is switched off.
6. Sensor readings and pump status are uploaded to Firebase Realtime Database.
7. The Python dashboard retrieves available readings and displays current values and historical graphs.
8. A trained machine learning model estimates future soil moisture from the available sensor features.
9. Model predictions are compared with actual readings and a baseline to evaluate performance.

### Soil Moisture Threshold

The current project uses a configurable threshold of approximately **2400 ADC units**. This value must be calibrated for the specific sensor and soil conditions.

| Condition | Rule | Expected action |
|---|---|---|
| Dry soil | Soil moisture reading > 2400 | Pump ON |
| Sufficient moisture | Soil moisture reading ≤ 2400 | Pump OFF |

The sensor produces raw analog readings, so the threshold is not a universal percentage of soil moisture. 

## 🧠 Machine Learning and Data Analytics

The project includes a predictive analytics component to estimate future soil moisture.

### Model

- **Algorithm:** Random Forest Regressor
- **Library:** Scikit-learn
- **Input features:** Soil moisture, temperature, humidity, and pump status
- **Prediction target:** Future soil moisture reading, approximately 10 minutes ahead when the dataset is correctly time-aligned
- **Model persistence:** Joblib

### Data Sources

The project uses two types of data:

- **Real sensor data:** Collected from the ESP32 and Firebase Realtime Database.
- **Synthetic data:** Generated programmatically to supplement the collected dataset during experimentation.

The two sources can be combined for model development and compared with a model trained only on real sensor data.

### Dashboard Analytics

The dashboard supports three types of analytics:

1. **Descriptive analytics:** Displays current readings and historical sensor trends.
2. **Predictive analytics:** Estimates future soil moisture using the trained model.


## ✅ Advantages

- Reduces the need for continuous manual monitoring.
- Automates pump operation based on soil conditions.
- Supports remote access to stored sensor readings.
- Provides historical data for analysis.
- Demonstrates integration of embedded systems, IoT, cloud storage, dashboards, and machine learning.

## 🔮 Future Enhancements

- Add rainfall and weather information.
- Introduce plant-specific irrigation thresholds.
- Add notifications for dry soil, pump failures, or low water supply.
- Deploy the dashboard for secure remote access.
- Evaluate additional forecasting models and compare their performance.
- Add safeguards such as pump time limits and sensor-failure detection.




