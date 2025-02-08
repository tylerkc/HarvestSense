# Final Team Project - Crop Yield Prediction  

## Team 2  
Arifa Kokab, Muhammad Haris, Tyler Clinscales  

## Project Overview  
This project utilizes IoT-based environmental data and machine learning to predict crop yields with high accuracy. By analyzing factors such as temperature, humidity, soil type, and seedling stages, the model provides data-driven insights to improve agricultural productivity.  

A **Random Forest Regression model** was trained on real-world crop data, achieving an **R² score of 0.9775**, indicating strong predictive performance. The project includes data preprocessing, feature engineering, correlation analysis, and real-time data visualization using **Tableau**.  

---

## Key Features  

### 1. Data Collection & Preprocessing  
The dataset used in this project was sourced from **Kaggle**:  
📂 **[Nigeria Agri-Econ Indicators (1950-2023)](https://www.kaggle.com/datasets/akinniyiakinwande/nigeria-agri-econ-indicators-1950-2023)**
- **Feature Engineering:** One-hot encoding for categorical variables (crop type, soil type, seedling stage)  
- **Missing Data Handling:** Verified dataset contains no missing values  

### 2. Exploratory Data Analysis (EDA) & Visualization  
- **Correlation Analysis:**  
  - Temperature and humidity have a strong influence on crop yield  
  - MOI (Management of Irrigation) shows a weaker correlation  
- **Feature Importance Analysis:**  
  - Temperature is the most significant predictor  
  - Crop type and seedling stage also impact yield  
- **Visualizations:**  
  - Heatmaps for correlation matrix  
  - Pair plots for variable relationships  
  - Bar charts for feature importance  

### 3. Machine Learning Model - Random Forest Regressor  
- **Training & Testing Split:** 80% training, 20% testing  
- **Performance Metrics:**  
  - **Root Mean Squared Error (RMSE):** 0.0927 (Low error, high accuracy)  
  - **R² Score:** 0.9775 (Explains 97.75% of variance)  
- **Feature Importance Insights:**  
  - Temperature and MOI play the biggest role  
  - Certain crop types (e.g., wheat) have a higher impact on yield  

### 4. Predictions & Model Evaluation  
- **Predicted vs. Actual Crop Yields:** Predictions align closely with real-world data  
- **Results saved as `predicted_crop_yields.csv` for further analysis**  
- **Graphical representation of actual vs. predicted yields**  

### 5. Deployment & Future Work  
- **IoT Integration:**  
  - Environmental data collected from IoT sensors  
  - Processed in real-time for yield predictions  
- **Tableau Integration:**  
  - Data transmitted to Tableau for real-time visualization  
- **Future Enhancements:**  
  - Edge AI for real-time analysis on IoT devices  
  - Alert system for extreme yield predictions

## Repository Structure  
- `Final_Team_Project.ipynb` - Contains all machine learning implementations.
- `IoT_System_Diagram_v3.png` - System architecture diagram for IoT data processing.
- `data` - Includes dataset from Kaggle and additional preprocessed data files.
- `README.md` - This documentation.

---

## How to Run the Model  
...

## Results & Business Impact  
### 1. Model Performance  
- **High accuracy:** 97.75% R² score  
- **Low error:** RMSE of 0.0927  
- **Feature Insights:** Identified key agricultural factors influencing yield  

### 2. Applications  
- **Yield Optimization:** Helps farmers maximize crop production  
- **Climate Impact Analysis:** Assesses environmental factors affecting yield  
- **Agricultural Planning:** Supports decision-making for crop selection 

## Contributors  
- Arifa Kokab  
- Muhammad Haris    
- Tyler Clinscales  

For contributions or improvements, please submit a **pull request** or open an **issue** in the repository.  
