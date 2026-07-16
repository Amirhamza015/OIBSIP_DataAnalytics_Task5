# OIBSIP_DataAnalytics_Task5

---

# 📌 Project Overview

House prices are influenced by numerous factors such as property size, location, amenities, and infrastructure. This project develops a Machine Learning model capable of predicting house prices using Linear Regression.

The project follows a complete Machine Learning workflow, including data preprocessing, exploratory data analysis, feature engineering, model training, evaluation, and interpretation of results.

---

# 🎯 Objectives

- Predict house prices using Machine Learning.
- Perform data preprocessing and cleaning.
- Explore relationships between housing features.
- Build a Linear Regression model.
- Evaluate prediction performance.
- Identify the most influential features affecting house prices.
- Generate business insights for real-estate stakeholders.

---

# 🛠️ Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib

---

# 📂 Dataset Information

Dataset Name:

Housing.csv

Dataset Size

- 545 Records
- 13 Columns

Features

- Area
- Bedrooms
- Bathrooms
- Stories
- Parking
- Main Road
- Guest Room
- Basement
- Hot Water Heating
- Air Conditioning
- Preferred Area
- Furnishing Status

Target Variable

- House Price

---

# ⚙️ Steps Performed

## 1. Data Collection

- Loaded Housing.csv using Pandas.

## 2. Data Cleaning

- Verified missing values.
- Checked duplicate records.
- Verified data types.

## 3. Data Preprocessing

- Binary Encoding
- Ordinal Encoding
- Feature Selection
- Train-Test Split (80-20)

## 4. Exploratory Data Analysis

Performed:

- Price Distribution
- Area vs Price
- Bedrooms vs Price
- Bathrooms vs Price
- Correlation Heatmap
- Category Analysis

## 5. Model Building

Algorithm Used

- Linear Regression

Library

- Scikit-learn

## 6. Model Evaluation

Evaluation Metrics

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

---

# 📈 Model Performance

| Metric | Value |
|---------|---------:|
| MAE | ₹979,679 |
| MSE | 1.7717511e+12 |
| RMSE | ₹1,331,071 |
| R² Score | 0.649475 |

The model explains approximately **65%** of the variation in house prices, demonstrating a moderate predictive performance suitable for baseline price estimation.

---

# 📊 Exploratory Data Analysis

The project includes the following visualizations:

- Price Distribution
- Area vs Price Scatter Plot
- Bedrooms vs Price Boxplot
- Bathrooms vs Price Boxplot
- Correlation Heatmap
- Actual vs Predicted Plot
- Residual Plot
- Feature Importance Chart

---

# 🔍 Key Findings

- Bathrooms have the strongest positive impact on house prices.
- Air Conditioning significantly increases property value.
- Hot Water Heating positively affects pricing.
- Houses located in preferred areas command higher prices.
- Larger houses generally sell for higher prices.
- Furnishing Status showed a slight negative coefficient within this dataset.

---

# 💡 Business Insights

The analysis indicates that property value is strongly influenced by structural features and amenities.

Developers and homeowners can increase property valuation by investing in:

- Additional Bathrooms
- Air Conditioning
- Basement Construction
- Better Parking Facilities
- Prime Locations

---

# ✅ Outcome

This project successfully demonstrates an end-to-end Machine Learning pipeline for predicting house prices using Linear Regression.

From data preprocessing and visualization to model training and evaluation, the project showcases practical applications of Python for predictive analytics and business decision-making.

---

# 🚀 Future Improvements

- Random Forest Regression
- XGBoost
- Hyperparameter Tuning
- Cross Validation
- Feature Engineering
- Web Application Deployment
- Power BI Dashboard Integration

---

# 🎯 Skills Demonstrated

- Machine Learning
- Data Cleaning
- Feature Engineering
- Exploratory Data Analysis
- Regression Modeling
- Model Evaluation
- Data Visualization
- Business Analytics
- Python Programming

---

# 📂 Project Structure

```
OIBSIP_DataAnalytics_Task2/
│
├── Dataset/
│   └── Housing.csv
│
├── Notebook/
│   └── House_Price_Prediction.ipynb
│
├── Model/
│   └── house_price_model.pkl
│
├── Images/
│   ├── price_distribution.png
│   ├── area_vs_price.png
│   ├── bedrooms_boxplot.png
│   ├── bathrooms_boxplot.png
│   ├── correlation_heatmap.png
│   ├── actual_vs_predicted.png
│   ├── residual_plot.png
│   └── feature_importance.png
│
├── Report/
│   └── House_Price_Prediction_Report.pdf
│
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
```

---

# ▶️ How to Run

Clone the repository

```bash
git clone https://github.com/your-username/OIBSIP_DataAnalytics_Task2.git
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run the notebook using

- Google Colab
- Jupyter Notebook

---

# 📌 Repository Status

- ✅ Task Completed
- ✅ Notebook Included
- ✅ Dataset Included
- ✅ Trained Model Included
- ✅ Visualizations Included
- ✅ Report Included
- ✅ Documentation Included

---

# 🙏 Acknowledgement

This project was completed as part of the **Data Analytics Internship Program at Oasis Infobyte (OIBSIP)**.

I sincerely thank **Oasis Infobyte** for providing this valuable learning opportunity and helping me strengthen my practical skills in Machine Learning, Data Analytics, and Python.

---

# 👨‍💻 Author

**Sayed Amir Hamza**

Data Analytics Intern – Oasis Infobyte

Anjuman-I-Islam's Kalsekar Technical Campus (AIKTC)

---

⭐ If you found this project useful, consider giving this repository a Star!
