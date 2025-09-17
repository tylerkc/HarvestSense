# Harvest Sense

## Overview

Harvest Sense is an IoT-based precision agriculture platform designed to forecast crop yield and assess soil quality using advanced machine learning techniques. The project leverages a synthetic dataset spanning 2014 to 2023, which captures daily agricultural parameters across ten major crops and five distinct soil types. Data is collected from an extensive network of soil, crop, and environmental sensors, processed and analyzed using a Long Short-Term Memory (LSTM) network for crop yield forecasting and a Random Forest regressor for soil quality prediction. The outcomes are integrated into an intuitive Tableau dashboard, enabling farmers to quickly identify areas requiring attention and optimize their practices. This repository includes all source code, data files, and documentation for the Harvest Sense project.

## Repository Contents

- **Harvest_Sense_Notebook.ipynb**  
  The main Jupyter Notebook containing the complete project code. It covers data preprocessing, exploratory data analysis, model development and evaluation for both LSTM and Random Forest approaches, and the integration of forecast outputs.

- **harvestsense_combined_forecasts_original_units.csv**  
  A CSV file that consolidates historical actual values and six-month forecasted values for both crop yield and soil quality in their original units. This file is intended for import into Tableau for dashboard creation and further analysis.

- **Harvest Sense Tableau Dashboard.pdf**  
  A PDF version of the final Tableau dashboard, which provides a user-friendly interface for farmers to monitor current and forecasted crop performance and soil quality.

- **IoT Crop Monitor Architecture Device.pdf**  
  The IoT system diagram illustrating the sensor network, edge computing, data processing, and cloud integration that form the backbone of Harvest Sense.

## Dataset

The project utilizes a synthetic dataset that provides a detailed representation of crop yield and environmental factors influencing agricultural productivity over a decade (2014–2023). This dataset contains daily observations of ten major crops—including Wheat, Corn, Rice, and Sugarcane—grown across five distinct soil types. It captures key variables such as soil pH, nutrient levels (nitrogen, phosphorus, and potassium), temperature, humidity, wind speed, crop yield (in metric tons per hectare), and a soil quality index that summarizes soil fertility. Generated using domain-specific synthetic modeling techniques based on real-world agricultural principles, the dataset exhibits both short-term fluctuations and long-term trends. The dataset is available on Kaggle at:  
[www.kaggle.com/datasets/madhankumar789/crop-yield-and-environmental-factors-2014-2023](https://www.kaggle.com/datasets/madhankumar789/crop-yield-and-environmental-factors-2014-2023)

## IoT System Design and Data Integration

Harvest Sense is built upon a scalable, modular IoT architecture that integrates sensor networks, edge computing, cloud processing, and visualization. Soil, crop, and environmental sensors capture various parameters—such as soil pH, nutrient levels, crop type, temperature, humidity, and wind speed—and transmit this data using communication protocols like LoRaWAN, Wi-Fi, or LTE, with MQTT ensuring efficient data transfer. Edge computing units preprocess data through real-time anomaly detection and cleaning, thereby reducing network load and latency. Processed data is then normalized and stored in the cloud, where it is available for machine learning analysis and visualization. The included IoT system diagram, **IoT Crop Monitor Architecture Device.pdf**, provides a detailed illustration of these processes.

## Methodology and Model Development

Harvest Sense employs a dual-model approach to generate actionable insights from the collected data. For crop yield forecasting, an LSTM network is implemented to capture long-term dependencies in the sequential data. The model uses a sliding window of 30 days, incorporating features such as soil pH, temperature, humidity, wind speed, and nutrient levels to predict future crop yield. The network is structured with two stacked LSTM layers and dropout layers to prevent overfitting, and is trained using the Adam optimizer with early stopping based on validation loss. Evaluation metrics, including Mean Squared Error and Mean Absolute Error, ensure robust performance across different crops.

For soil quality prediction, a Random Forest regressor is utilized due to its ability to model complex nonlinear relationships and provide interpretable feature importance. After tuning key hyperparameters using GridSearchCV, the Random Forest models yield highly accurate predictions for soil quality. Both crop yield and soil quality forecasts extend six months into the future and are combined with historical data for comprehensive analysis.

## Tableau Dashboard

The final Tableau dashboard is designed to present complex predictive insights in a user-friendly format for farmers. The dashboard features four core bar charts that display current and forecasted values for crop yield and soil quality. The top charts compare actual crop yield with six-month forecasts, while the bottom charts do the same for soil quality. A clear, industrial color palette and predefined thresholds enable farmers to quickly identify fields that require attention. Interactive filters allow users to refine the view by crop type or time period, ensuring that the dashboard remains both accessible and actionable.

## Authors and Contributors

This project was developed by Team 2 at the University of San Diego.  
**AI Engineers:**  
- Arifa Kokab (Team Lead)  
- Muhammad Haris  
- Tyler Clinscales  

## How to Run

1. **Clone the Repository:**  
   Open your terminal and run:  
   ```bash
   git clone <repository-url>
   ```
2. **Open the Notebook:**  
   Launch Jupyter Notebook or JupyterLab and open `Harvest_Sense_Notebook.ipynb`. Follow the instructions within the notebook to execute the code sequentially.

3. **Review Outputs:**  
   The final CSV file `harvestsense_combined_forecasts_original_units.csv` will be generated, and the PDF files (Tableau dashboard and IoT system diagram) can be reviewed for further insights.

4. **Dashboard Integration:**  
   Import the CSV file into Tableau to explore and customize the dashboard as required.

## Requirements

- Python 3.x  
- Libraries: Pandas, NumPy, Seaborn, Matplotlib, Scikit-learn, TensorFlow, Keras  
- Additional dependencies are specified in the notebook.
