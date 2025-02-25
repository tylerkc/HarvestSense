# HarvestSense-AAI-530-Team2

## Overview

Harvest Sense is an IoT-based precision agriculture platform designed to forecast crop yield and assess soil quality using advanced machine learning techniques. The project leverages a synthetic dataset spanning 2014 to 2023, which captures daily agricultural parameters across ten major crops and five distinct soil types. Data is collected from an extensive network of soil, crop, and environmental sensors, then processed and analyzed using a Long Short-Term Memory (LSTM) network for crop yield forecasting and a Random Forest regressor for soil quality prediction. The results of these models are integrated into an intuitive Tableau dashboard, enabling farmers to quickly identify areas requiring attention and optimize their practices. This repository includes all source code, data files, and documentation for the Harvest Sense project.

## Repository Contents

The repository contains the main Jupyter Notebook, which includes all code for data preprocessing, exploratory data analysis, model development, evaluation, and forecast integration. The file **Harvest_Sense_Notebook.ipynb** holds the complete project code. In addition, the CSV file **harvestsense_combined_forecasts_original_units.csv** consolidates historical and forecasted values for crop yield and soil quality (converted back to their original units), and **Harvest Sense Tableau Dashboard.pdf** provides a PDF version of the final Tableau dashboard that has been designed for ease of interpretation.

## Dataset

The project utilizes a synthetic dataset that provides a detailed representation of crop yield and environmental factors influencing agricultural productivity over a decade (2014-2023). This dataset contains daily observations and includes data on ten major crops such as Wheat, Corn, Rice, and Sugarcane, grown across five distinct soil types. It captures key variables including soil pH, nutrient levels (nitrogen, phosphorus, and potassium), temperature, humidity, wind speed, crop yield (expressed in metric tons per hectare), and a soil quality index that summarizes soil fertility. The dataset was generated using domain-specific synthetic modeling techniques that incorporate real-world agricultural principles, resulting in data that exhibit both short-term fluctuations and long-term trends. The dataset is available on Kaggle at:  
www.kaggle.com/datasets/madhankumar789/crop-yield-and-environmental-factors-2014-2023

## IoT System Design and Data Integration

Harvest Sense is built upon a scalable and modular IoT architecture that integrates sensor networks, edge computing, cloud processing, and real-time visualization. Soil, crop, and environmental sensors capture various parameters and transmit this data via LoRaWAN, Wi-Fi, or LTE using MQTT for efficient communication. Edge computing units preprocess the data by detecting anomalies, cleaning noise, and performing initial aggregation. The refined data is then transmitted to the cloud, where it is normalized and stored for further analysis. This design ensures that the system is highly scalable, allowing for the addition of new sensors and computational resources without major changes to the overall architecture.

## Methodology and Model Development

The methodological framework of Harvest Sense integrates deep learning and ensemble methods to extract actionable insights from the collected data. The LSTM network, employed for crop yield forecasting, is designed to capture long-term dependencies in sequential data. Using a sliding window approach of 30 days, the model learns from features such as soil pH, temperature, humidity, wind speed, and nutrient levels to predict future crop yield. The network comprises two stacked LSTM layers with dropout mechanisms to prevent overfitting and is trained using the Adam optimizer with early stopping based on validation loss. Evaluation metrics from the LSTM models, including Mean Squared Error and Mean Absolute Error, were used to ensure robust performance across crop types.

For soil quality prediction, a Random Forest regressor was chosen due to its ability to model complex, nonlinear interactions among features and to provide insights into feature importance. The model was tuned using GridSearchCV to optimize key hyperparameters such as the number of estimators and maximum depth. The resulting predictions demonstrated very low error values on test data, and the model’s feature importance scores highlighted the influence of soil pH and nutrient levels. Both crop yield and soil quality forecasts were generated for a six-month horizon and were subsequently combined with historical data to create a unified dataset. This comprehensive dataset forms the foundation for the final interactive Tableau dashboard.

## Tableau Dashboard

The final Tableau dashboard for Harvest Sense is designed with simplicity and clarity, featuring four core bar charts that provide a concise overview of both current and forecasted conditions. Two of the charts display current and predicted crop yields for each crop type, while the other two show the latest and six-month forecasted soil quality values. An intuitive color palette and well-defined industrial thresholds enable farmers to quickly assess which fields are performing well and which require intervention. Interactive filters allow users to refine the view by crop type or time period, ensuring that the dashboard is accessible and actionable for users with varying levels of technical expertise.

## Authors and Contributors

This project was developed by Team 2 at the University of San Diego. The team comprises AI Engineers:
- **Arifa Kokab (Team Lead)**
- **Muhammad Haris**
- **Tyler Clinscales**

## How to Run

To run this project, clone the repository and open the `Harvest_Sense_Notebook.ipynb` in Jupyter Notebook or JupyterLab. The notebook includes detailed instructions and code for preprocessing, model training, evaluation, and integration of forecast data. After executing the notebook, the CSV file containing the combined forecasts will be generated, and you can open the provided Tableau dashboard PDF to view the final visualization.

## Requirements

The project requires Python 3.x along with libraries such as Pandas, NumPy, Seaborn, Matplotlib, Scikit-learn, TensorFlow, and Keras. Detailed dependency information is provided within the notebook.
