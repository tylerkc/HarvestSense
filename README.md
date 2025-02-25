# HarvestSense-AAI-530-Team2

## Overview

Harvest Sense is an IoT-based precision agriculture platform designed to forecast crop yield and assess soil quality using advanced machine learning techniques. The project leverages a synthetic dataset spanning 2014 to 2023 to capture daily agricultural parameters across ten major crops and five distinct soil types. Data is collected from an extensive network of soil, crop, and environmental sensors, processed through rigorous preprocessing and feature engineering, and analyzed using a Long Short-Term Memory (LSTM) network for crop yield forecasting and a Random Forest regressor for soil quality prediction. The outputs are integrated and presented through an intuitive Tableau dashboard, providing actionable insights that enable farmers to optimize their practices.

## Repository Contents

- **Harvest_Sense_Notebook.ipynb**  
  The main Jupyter Notebook containing all the code used for data preprocessing, exploratory data analysis, model development (LSTM and Random Forest), model evaluation, and the integration of forecast outputs.

- **harvestsense_combined_forecasts_original_units.csv**  
  A CSV file that consolidates historical actual values and six-month forecasted values for both crop yield and soil quality in their original units. This file is intended for import into Tableau for dashboard creation and further analysis.

- **Harvest Sense Tableau Dashboard.pdf**  
  A PDF version of the final Tableau dashboard. The dashboard is designed with a clear color palette and industrial thresholds to help farmers quickly identify areas of concern regarding crop yield and soil quality.

## System Design and Methodology

Harvest Sense integrates an IoT-enabled sensor network with sophisticated machine learning methods to drive precision agriculture. The IoT architecture consists of a sensor network that collects data on soil pH, nutrient levels (N, P, K), crop types, environmental factors (temperature, humidity, wind speed), and corresponding performance metrics such as crop yield and a soil quality index. This data is preprocessed—dates are converted, categorical features are one-hot encoded, and numerical features are standardized—before being used to train the machine learning models.

For crop yield forecasting, an LSTM network is employed because of its ability to capture long-term dependencies in sequential data. The model is trained on a sliding window of 30 days of sensor data, enabling it to learn the temporal dynamics that influence yield. In parallel, a Random Forest model is developed to predict soil quality. This ensemble method effectively handles nonlinear relationships and provides interpretable insights via feature importance analysis. The models are evaluated using metrics such as Mean Squared Error and Mean Absolute Error, and the results from these evaluations inform further refinements.

The final outputs—both the actual historical values and the six-month forecasts—are merged into a unified dataset. This dataset is then inverse-transformed to restore the original measurement units and serves as the foundation for the Tableau dashboard, which provides farmers with a simple and interactive interface to monitor crop performance and soil health.

## Tableau Dashboard

The final Tableau dashboard is designed with simplicity and clarity, featuring four primary bar charts. The upper charts compare current crop yield with forecasted crop yield, while the lower charts provide a similar comparison for soil quality. The dashboard uses an easy-to-understand color palette and pre-defined industrial thresholds, enabling farmers to quickly identify fields that require intervention. Interactive filters allow users to drill down by crop type or time period, further enhancing the usability and practical impact of the system.

## Authors and Contributors

This project was developed by Team 2 at the University of San Diego. The team members and their roles are as follows:

- **Arifa Kokab (Team Lead)** – AI Engineer responsible for project coordination and technical leadership.
- **Muhammad Haris** – AI Engineer with a focus on data preprocessing, model development, and analysis.
- **Tyler Clinscales** – AI Engineer contributing to model evaluation, visualization, and forecast integration.

## How to Run

1. **Clone the Repository:**  
   Open your terminal and run:  
   ```bash
   git clone <repository-url>
   ```

2. **Open the Notebook:**  
   Launch Jupyter Notebook or JupyterLab and open `Harvest_Sense_Notebook.ipynb`. Follow the instructions in the notebook to run the code sequentially.

3. **Review the Outputs:**  
   The final CSV file, `harvestsense_combined_forecasts_original_units.csv`, will be generated along with the Tableau dashboard PDF, `Harvest Sense Tableau Dashboard.pdf`.

4. **Dashboard Integration:**  
   Import the CSV file into Tableau to explore and customize the dashboard as needed.

## Requirements

- Python 3.x
- Pandas, NumPy, Seaborn, Matplotlib, and Scikit-learn
- TensorFlow and Keras
- Additional libraries as specified in the notebook (refer to the notebook for full dependency details)
