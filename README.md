# OIBSIP_DataAnalytics_Task5


Professional Project Report: House Price Prediction (Level-2 Internship)
Executive Summary
This project implements a machine learning solution to predict house prices using a structured housing dataset. The main goal was to build a Linear Regression model that can estimate property prices based on features such as area, number of bedrooms, and amenities. We loaded the data from Housing.csv using pandas (which “reads a CSV file into [a] DataFrame”) and performed data quality checks (no missing values or duplicates were found). Key features were preprocessed (binary and ordinal encoding for categorical fields), and an exploratory data analysis (EDA) was conducted to uncover relationships (e.g. area vs price correlation, price distribution, etc.).

The model was trained on an 80% split of the data and evaluated on the remaining 20%. The final Linear Regression achieved the following performance on the test set:

Metric	Value
MAE (₹)	979,679
MSE (₹²)	1.7717511e+12
RMSE (₹)	1,331,071
R² Score	0.649475

A 65.0% (approximately) variance explanation (R² = 0.649475) indicates a moderately strong model fit. The model’s coefficients reveal that Bathrooms (+1,097,117) and Air Conditioning (+785,551) are the largest positive drivers of price, while Furnishing Status has a negative coefficient (–210,397), suggesting fully furnished homes were, on average, priced lower in this dataset. These insights can help stakeholders understand price drivers: e.g., adding bathrooms or amenities like air conditioning tends to significantly increase property value.

Key project components: Data ingestion with pandas, thorough EDA with visualization (histograms, scatter plots, correlation heatmap, etc.), and model building using scikit-learn’s LinearRegression. Evaluation used standard regression metrics (MAE, MSE, R²). The complete deliverable includes the analysis report, code, trained model (house_price_model.pkl), GitHub README, presentation materials, and deployment assets.

Objectives
Predictive Modelling: Develop a machine learning model (Linear Regression) to predict house prices from features such as area, bedrooms, bathrooms, and property amenities.
Feature Analysis: Identify which property features have the strongest impact on price.
Data Processing: Demonstrate end-to-end data preprocessing and cleaning (handling categorical data, splitting data).
Performance Evaluation: Quantify model accuracy using regression metrics (MAE, RMSE, R²) and interpret what these results mean in business terms.
Documentation & Communication: Produce a professional report and supporting materials (GitHub README, LinkedIn post, etc.) suitable for technical and non-technical audiences.
Dataset Description
The dataset (Housing.csv) contains 545 records (rows) and 13 columns, as follows:

Features (12):

area (numeric): Size of the house in square feet.
bedrooms (int): Number of bedrooms.
bathrooms (int): Number of bathrooms.
stories (int): Number of floors/stories.
mainroad (binary): Access to a main road (yes/no).
guestroom (binary): Availability of a guest room (yes/no).
basement (binary): Basement present (yes/no).
hotwaterheating (binary): Hot water heating available (yes/no).
airconditioning (binary): Air conditioning (yes/no).
parking (int): Number of parking spaces.
prefarea (binary): In preferred area (yes/no).
furnishingstatus (categorical): Status (‘unfurnished’, ‘semi-furnished’, ‘furnished’).
Target:

price (numeric): Selling price of the house (in currency units).
We loaded the data using pandas.read_csv("<path/to/Housing.csv>"). A quick preview (df.head()) confirmed the columns and data types. Calling df.info() printed a concise summary of the dataset (number of columns, data types, non-null counts), showing 13 columns (6 numeric, 7 categorical) and no missing values. The statistical summary df.describe() gave measures of central tendency and spread for numerical features (mean, median, quartiles, etc.).

Data Preprocessing
To prepare the data for regression, we performed the following steps:

Binary Encoding: Converted yes/no features (mainroad, guestroom, basement, hotwaterheating, airconditioning, prefarea) into 0/1 values.
Ordinal Encoding: Mapped furnishingstatus to ordinal numbers (e.g., unfurnished = 0, semi-furnished = 1, furnished = 2).
Feature Matrix and Target: Separated the encoded data into feature matrix X (all columns except price) and target vector y (price).
Train-Test Split: Divided the data into an 80% training set and 20% test set (random state fixed for reproducibility). This split ensures that model evaluation is done on unseen data.
Placeholder note: In actual code, replace '<path/to/Housing.csv>' and '<model.pkl>' with the real paths/filenames. For example, we might save the trained model as "house_price_model.pkl".

Exploratory Data Analysis (EDA)
We created several visualizations to understand the data and relationships between features. Key highlights include:

Price Distribution: A histogram of price shows how house prices are distributed (e.g. skewness or outliers). This provides context for the model’s prediction range.
Area vs Price Scatter: A scatter plot of area against price reveals a strong positive correlation, indicating that larger homes tend to cost more.
Bedrooms/Bathrooms vs Price: Box plots of bedrooms vs price and bathrooms vs price suggest that more bedrooms or bathrooms generally correspond to higher prices (with some variability).
Correlation Heatmap: A correlation matrix (heatmap) of all numeric features shows how features interrelate. For instance, area, bedrooms, and bathrooms all positively correlate with price.
Categorical Effects: Count plots and box plots for categorical features (e.g. furnishingstatus) illustrate how categories relate to price.
Sample Visuals and Interpretations:

Figure – Price Distribution: Most homes are priced in a certain mid-range, with a right-skew suggesting a few expensive outliers.
Figure – Area vs Price: Points cluster along an upward trend; linear regression assumptions seem reasonable.
Figure – Bedrooms vs Price: Median price increases with more bedrooms, though variance grows (outliers present).
Figure – Bathrooms vs Price: Similar upward trend as bathrooms increase.
Figure – Correlation Matrix: Highlights that area has one of the highest correlations with price, as expected.
Figure – Actual vs Predicted Plot: (post-modeling) shows how well predictions align with actual prices (ideally along the diagonal line).
Figure – Residual Plot: Scatter of residuals vs predictions indicating no obvious pattern (good sign for linear regression).
These EDA insights guided the modeling approach. For brevity, the report does not include all plots here, but the final deliverables include the full set of visualizations and captions (see “Suggested Visuals” section).

Modelling Approach
We selected Ordinary Least Squares Linear Regression (scikit-learn’s LinearRegression) to predict house price as a linear combination of features. This method finds coefficients that minimize the residual sum of squares between actual and predicted prices. Linear Regression was chosen for its interpretability (coefficients directly show feature impact) and because the EDA suggested roughly linear relationships.

The process was:

Feature-Target Split: X contains all encoded features, y contains price.
Train-Test Split: 80% train, 20% test (random_state=42 for reproducibility).
Model Training: Instantiate LinearRegression() and fit on the training data.
Prediction: Use the trained model to predict prices on the test set.
Evaluation: Compute MAE, MSE, RMSE, and R² on test predictions.
The relevant scikit-learn code (in Appendix) used: LinearRegression().fit(X_train, y_train) and predictions via model.predict(X_test). For evaluation, we used scikit-learn metrics: mean_absolute_error, mean_squared_error, and r2_score.

Training and Evaluation Results
After training, we evaluated performance on the test set. The results are tabulated below:

Metric	Value	Interpretation
MAE (₹)	979,679	Average absolute error; on average, predictions miss by ~₹980K.
MSE (₹²)	1.7717511e+12	Mean squared error; penalizes large errors more.
RMSE (₹)	1,331,071	Root MSE; typical prediction error magnitude (~₹1.33M).
R² Score	0.649475	~64.9% variance explained by the model. Best possible is 1.0.

The R² score of 0.649475 indicates that the model explains about 65% of the variance in house prices on the test set. (R² ranges up to 1.0; values closer to 1.0 are better.) In practical terms, the model has moderate accuracy. The MAE of ~₹979,679 means the average prediction error is under ₹1 million – which could be acceptable depending on price scale (the dataset’s prices range broadly). Overall, these metrics confirm that the linear model captures major price trends but leaves room for improvement (e.g., unmodeled non-linear effects or omitted variables).

Model Coefficients and Feature Impact
The fitted linear model provides coefficients for each feature, indicating how much the price changes for a one-unit increase in that feature (holding others constant). The table below summarizes the feature importance:

Feature	Coefficient	Interpretation
Bathrooms	+1,097,117	Largest positive impact: each additional bathroom adds ~₹1.10M.
Air Conditioning	+785,551	+₹0.79M: presence of AC significantly raises price.
Hot Water Heating	+687,881	+₹0.69M: homes with hot-water heating sell higher.
Pref Area	+629,902	+₹0.63M: being in preferred area increases value.
Stories	+406,223	+₹0.41M per additional story (floor).
Basement	+393,160	+₹0.39M: basement adds value.
Main Road	+366,824	+₹0.37M: main road access has a positive effect.
Guest Room	+360,512	+₹0.36M: guest room inclusion adds value.
Parking	+340,555	+₹0.34M per parking space.
Bedrooms	+329,420	+₹0.33M per bedroom.
Area (sqft)	+6,460	+₹6.46K per additional sq ft. (smallest positive effect).
Furnishing Status	–210,397	–₹0.21M: negative; fully furnished homes tend to be priced lower (baseline: unfurnished=0, furnished=2).

Note: “Furnishing Status” was encoded as 0=unfurnished, 1=semi-furnished, 2=furnished. The negative coefficient (–210,397) suggests that fully furnished homes (value 2) were, on average, priced about ₹210K lower than equivalent unfurnished ones. This may reflect that older or less-updated homes are more likely to be “furnished,” or it could indicate a nuance in buyer preferences.

Overall, Bathrooms has the strongest positive influence: every extra bathroom adds roughly ₹1.1M to the predicted price. In contrast, Area (in square feet) had a relatively small coefficient; perhaps the effect of area is already captured by correlated features like bedrooms/bathrooms. These coefficients provide actionable insights: adding bathrooms, air conditioning, or a basement could substantially increase a property’s market value.

Limitations and Future Improvements
Linear Model Assumption: Linear Regression assumes a linear relationship between features and price. If the true relationship is non-linear (e.g., diminishing returns on area), this model won’t capture it. Non-linear models (e.g., Random Forest, Gradient Boosting) could be tried in future work.
Data Size: With only 545 samples, the model has limited data. More data could improve robustness.
Feature Scope: Important features (e.g., location coordinates, age of building, market conditions) are not included here. Including more relevant data may improve accuracy.
Validation: We used a simple train/test split. For more reliable assessment, cross-validation and hyperparameter tuning could be applied.
Outliers and Distribution: The price distribution had outliers. Techniques like log-transforming the target or robust regression could be explored.
Business Insights & Recommendations
Focus on High-Impact Upgrades: Investing in additional bathrooms, air conditioning, and hot-water heating is likely to yield significant price increases (as evidenced by the large coefficients).
Market Segmentation: Since fully furnished homes were not commanding higher prices, sellers might emphasise other improvements or target buyers valuing location and amenities over furnishings.
Pricing Strategy: Use the model to generate price estimates for new listings, helping sellers set competitive yet profitable prices. The feature analysis can guide which upgrades to market prominently.
Further Data Collection: Gather more data on factors like neighborhood quality or economic indicators, to refine the model.
Overall, the model offers a quantitative basis for understanding house price drivers. Stakeholders (developers, agents, buyers) can use these insights to make data-driven decisions, such as prioritizing certain renovations (e.g. adding bathrooms) or identifying undervalued properties.

Conclusion
This project demonstrated an end-to-end machine learning workflow for house price prediction. Using pandas for data handling and scikit-learn for modeling, we built and evaluated a Linear Regression model with moderate accuracy (R²≈0.65). The model identified key features (bathrooms, AC, etc.) that strongly influence price. While the linear model has limitations, the results provide valuable business insights. The complete deliverables include this report, the analysis code, visualizations, the trained model (house_price_model.pkl), and supplementary materials (README, poster, etc.), which together document and showcase the work in a professional and accessible format.

Appendix
A. Key Code Snippets
(Representative excerpts from the project code – for full code, see the notebook.)

python
Copy
# Load data
import pandas as pd
df = pd.read_csv('<path/to/Housing.csv>')  # replace with actual path

# Preprocess categorical variables
from sklearn.preprocessing import LabelEncoder
encoder = LabelEncoder()
binary_cols = ['mainroad','guestroom','basement','hotwaterheating','airconditioning','prefarea']
for col in binary_cols:
    df[col] = encoder.fit_transform(df[col])  # yes→1, no→0
df['furnishingstatus'] = df['furnishingstatus'].map({'unfurnished':0,'semi-furnished':1,'furnished':2})

# Define features X and target y
X = df.drop('price', axis=1)
y = df['price']

# Split data
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.20, random_state=42)

# Train Linear Regression model
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train, y_train)  # fits coefficients to minimize residual sum of squares

# Make predictions
y_pred = model.predict(X_test)

# Evaluate performance
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score
mae = mean_absolute_error(y_test, y_pred)
mse = mean_squared_error(y_test, y_pred)
rmse = mse ** 0.5
r2 = r2_score(y_test, y_pred)
print(f"MAE: {mae}, RMSE: {rmse}, R2: {r2}")
python
Copy
# Feature importance (coefficients)
coeff_df = pd.DataFrame({
    "Feature": X.columns,
    "Coefficient": model.coef_
}).sort_values(by="Coefficient", ascending=False)
print(coeff_df)
# Output shows largest coefficients (Bathrooms, Air Conditioning, etc.)

# Save the trained model to file
import joblib
joblib.dump(model, '<model.pkl>')  # Replace <model.pkl> with desired filename
print("Model saved successfully.")
B. Model Artifact
Serialized Model: The trained LinearRegression model is saved as house_price_model.pkl. This can be loaded in Python via joblib.load('house_price_model.pkl') for making predictions on new data.
Environment: Python 3.x, with libraries pandas, numpy, scikit-learn, and matplotlib. (A requirements.txt is provided in the repository for reproducibility.)
factors (e.g., bathrooms, air conditioning) and evaluates model performance (R² ≈ 0.65 on test data).
negative coefficient.
