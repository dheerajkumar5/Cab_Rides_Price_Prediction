**Cab_Ride_Price_Prediction_Major_Project**

_**Project Overview**_

This project aims to predict Uber ride prices based on cab ride and weather data. Through comprehensive preprocessing and modeling techniques, various regression models were applied, and their performance was evaluated using key metrics like R² Score, Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE).

_**Packages Used**_

The following Python packages were utilized in this project:

pandas: For data manipulation and preprocessing.

numpy: For numerical computations and statistical analysis.

seaborn: For visualizations and data exploration.

matplotlib.pyplot: For plotting graphs and analyzing data distributions.

sklearn: For machine learning workflows, including model evaluation, preprocessing, and hyperparameter tuning.

xgboost: For applying the XGBRegressor model.

_**Datasets Used**_

Cab_rides.csv: Contains ride-related attributes such as price, distance, cab type, etc.

Weather.csv: Provides weather data such as temperature, rain, and cloud cover.

These datasets were preprocessed to ensure compatibility and effective modeling.

_**Preprocessing Steps**_

1. Random Imputation:

Missing values in the price field were imputed using random values sampled from non-missing entries within the same field. This technique ensured that the distribution of the price field remained intact.

2. Column Renaming:

Columns were renamed for better readability and to match modeling requirements.

3. Sampling:

Due to memory constraints in Google Colab's free tier, a sample of the merged dataset was taken. This ensured efficient execution while retaining representative data.

4. Weather Dataset Cleaning:

Missing values in the rain field were replaced with 0 for days with no recorded rain.

Additional cleaning was performed to improve data quality.

5. Merging Datasets:

The Cab_rides.csv and Weather.csv datasets were merged using an inner join on the Source column to ensure only matching rows were included in the analysis.

6. Handling Categorical Data with ColumnTransformer:

Nominal Categorical Data:

Attributes such as Source and Destination were encoded using OneHotEncoder. This created dummy variables, allowing the models to treat these categories as distinct and non-ordinal.

_**Exploratory Data Analysis**_

1. Preprocessed Data:

The distributions of the data were reviewed before and after preprocessing to ensure that no distortions were introduced during data cleaning.

2. Visual Analysis:
   
Using seaborn and matplotlib.pyplot, the data was analyzed to identify trends and outliers. Key visualizations included:

Ride price distribution.

Weather conditions vs. price variations.

_**Machine Learning Models:**_

Multiple regression models were applied to predict Uber ride prices. Below are the models along with their metrics:

|     **Model**     |**R² Score** |**Mean Squared Error**| **Root Mean Squared Error** | **Mean Absolute Error** |
|-------------------|-------------|----------------------|-----------------------------|-------------------------|
| Linear Regression |   0.7225    |       23.804         |           4.878             |          3.556          |
| Lasso Regression  |   0.6928    |       26.350         |           5.133             |          3.613          |
| Ridge Regression  |   0.7225    |       23.803         |           4.878             |          3.556          |
| **Random Forest** |  **0.9337** |     **5.687**        |         **2.384**           |        **1.139**        |
|     _XGBoost_     |   _0.9208_  |       _6.792_        |           _2.606_           |          _1.374_        | 


_**Key Findings**_

1. Best Model: _**Random Forest**_
 
_Random Forest emerged as the top-performing model, achieving an R² Score of 93.37%, along with the lowest RMSE and MAE values. This suggests that Random Forest effectively captured the relationship between features and price._

2. XGBoost:

While XGBoost also performed well (92.08% R² Score), it slightly lagged behind Random Forest in terms of error metrics.

3. Handling Categorical Data:

Encoding categorical data using ColumnTransformer, OneHotEncoder, and OrdinalEncoder improved the performance of models, ensuring accurate handling of relationships between categories.

_**Conclusion**_

This project demonstrates the power of machine learning models, specifically Random Forest, in predicting ride prices with high accuracy. The process involved comprehensive preprocessing, exploratory analysis, and model evaluation to arrive at actionable insights.

**Next Steps**

_Future improvements to this project could include:_

Hyperparameter Tuning: Further optimize Random Forest and XGBoost using tools like GridSearchCV.

Feature Engineering: Incorporate additional features like traffic data or time of day to enhance predictions.

Scaling: Experiment with feature scaling techniques to evaluate their impact on simpler models like Linear Regression.
