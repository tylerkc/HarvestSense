# Harvest Sense: AI-Powered Crop Yield and Soil Quality Prediction

## 📌 Project Overview
Harvest Sense is an advanced AI-driven solution for **predicting crop yield and soil quality** using deep learning (LSTM) and machine learning (Random Forest) models. The project leverages **historical environmental data, soil conditions, and agricultural trends** to generate accurate, data-driven insights for precision farming and sustainable agriculture.

This repository contains the complete workflow for **data preprocessing, feature engineering, model training, evaluation, and visualization** of predictions. The final output is exported to **Tableau for interactive data exploration**.

## 📂 Dataset Description
The dataset used in this project spans **10 years (2014-2023)** and includes daily agricultural observations such as:
- **Crop Types**: Wheat, Corn, Rice, Barley, Soybean, Cotton, Sugarcane, Tomato, Potato, Sunflower
- **Soil Types**: Sandy, Clay, Loamy, Peaty, Saline
- **Environmental Factors**: Temperature, Humidity, Wind Speed
- **Soil Nutrients**: Nitrogen (N), Phosphorus (P), Potassium (K), Soil pH
- **Target Variables**:
  - **Crop Yield (metric tons per hectare)**
  - **Soil Quality Index**
  
Link to dataset: www.kaggle.com/datasets/madhankumar789/crop-yield-and-environmental-factors-2014-2023

## ⚙️ Implementation Workflow
### 1️⃣ Data Preprocessing
- Loaded dataset from Google Drive
- Converted date column to **datetime format**
- Encoded categorical variables (**Crop Type and Soil Type**)
- Checked for missing values and performed cleaning

### 2️⃣ Feature Engineering
- Created **lag features** for crop yield trends
- Generated **moving average features** to capture seasonal patterns
- Normalized numerical data for **LSTM model compatibility**
- Created a **duplicate dataset** for training the Random Forest model

### 3️⃣ Model Development
#### 🔹 LSTM Model for Crop Yield Prediction
- Implemented a **deep learning model** with two **LSTM layers** and dropout for regularization
- Optimized using **Adam optimizer** and trained for **20 epochs**
- Evaluated using **Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² score**

#### 🔹 Random Forest Model for Soil Quality Prediction
- Trained a **Random Forest Regressor** with **100 estimators**
- Used **environmental factors and soil conditions** as input features
- Evaluated model accuracy using **MAE, RMSE, and R² score**

### 4️⃣ Visualization and Analysis
- Generated **EDA visualizations**, including:
  - Crop yield trends over time
  - Soil quality trends by soil type
  - Feature correlation heatmap
  - Temperature vs. crop yield scatterplot
  - Nutrient levels per crop type
- Exported predictions to a **CSV file** for Tableau dashboard visualization

## 📊 Model Performance
### **LSTM Model for Crop Yield Prediction**
- **MAE**: 2.39
- **RMSE**: 3.87
- **R² Score**: 0.978

### **Random Forest Model for Soil Quality Prediction**
- **MAE**: 4.42e-14
- **RMSE**: 5.82e-14
- **R² Score**: 1.0

## 📁 Files and Directories
- **`harvest_sense.ipynb`** → Jupyter Notebook containing full code
- **`model_predictions_tableau.csv`** → Model predictions for Tableau
- **`README.md`** → Project documentation

## 🚀 How to Use
### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/harvest-sense.git
cd harvest-sense
```

### Step 2: Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow
```

### Step 3: Run the Notebook
Open **`harvest_sense.ipynb`** in Jupyter Notebook or Google Colab and execute the cells.

### Step 4: Visualize in Tableau
Load **`model_predictions_tableau.csv`** into Tableau to create interactive dashboards.

## 🏆 Conclusion
Harvest Sense successfully demonstrates the power of **AI in agriculture**, leveraging **LSTMs for time-series forecasting** and **Random Forest for soil quality analysis**. With high accuracy and detailed environmental insights, this project provides a **strong foundation for precision farming and data-driven agricultural decision-making**.

---
**🌱 Empowering Agriculture with AI 🌾**

