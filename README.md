# Calories Burn Prediction Model

## Presentation
https://docs.google.com/presentation/d/11PLAgfoAIN9d0kkmzPJ8kPF35NBkFoYXQ18-x84yrbE/edit?slide=id.g3617f8a6fc8_2_9#slide=id.g3617f8a6fc8_2_9

# Project Workflow
1. Data Preparation & Exploration
2. Feature Engineering
3. Data Visualization & EDA
4. Model Training & Evaluation
5. Hyperparameter Tuning
6. Advanced Predictions and Analysis
   
# Project Overview
This project leverages machine learning to predict calories burned during training sessions, based on physiological measurements, and generational fitness trends. The analysis includes classification of users into generations, heart rate zones, BMI categories, and provides model-driven recommendations for improving training outcomes.

# Dataset
* Source: CSV file containing 15,000 entries

# Columns:  
User_ID, Gender, Age, Height, Weight, Duration, Heart_Rate, Body_Temp, Calories

* Enrichment: Generational categorization, BMI & weight class assignment, mapping of recommended exercise and BPM ranges

# Objectives
* Explore relationships between physical characteristics and calories burned.
* Engineer features such as generation, BMI, weight category for more interpretable insights.
* Train, optimize, and compare machine learning regression models.
* Use model predictions to provide personalized improvement strategies.

# Project Workflow

1. Data Preparation & Exploration

* Imported libraries (pandas, numpy, scikit-learn, seaborn, matplotlib).
* Read and examined the data for structure, missing values, outliers.
* Summarized dataset stats (describe(), column datatypes, shape).

2. Feature Engineering

* Generation assignment: Based on age cutoffs (e.g., Millennials, Generation X, Baby Boomers, etc.)
* BMI calculation: Weight / (Height/100)^2
* Weight category segmentation: Classified as Underweight, Normal weight, Overweight, Obese.
* Label encoding: Converted categorical gender to numeric.
* Dummy variables: For generation and weight category to enable regression modeling.
* Additional Enrichment: Added columns with recommended exercises, heart rate (BPM) per generation.


3. Data Visualization & EDA

* Bar plots and counts of gender, generation, and weight categories.
* Boxplots for detecting outliers in Duration, Calories, and BMI.
* Scatterplots and pairplots to inspect relationships between variables.
* Correlation heatmaps to identify feature associations.
* Grouped analyses (e.g., avg. calories/duration by gender and generation).

4. Model Training & Evaluation
   
Preprocessing:
* Feature scaling with StandardScaler.
* Train-test split.

Models Used:
* K-Nearest Neighbors (KNN)
* Bagging Regressor (Decision Trees)
* AdaBoost Regressor
* Random Forest Regressor
* Gradient Boosting Regressor

Evaluation Metrics:
* R² (coefficient of determination)
* MAE (mean absolute error)
* RMSE (root mean squared error)

Results printouts and barplots:
* Compared each model’s performance on both train and test sets.

5. Hyperparameter Tuning
    
* Optimized Bagging Regressor parameters using RandomizedSearchCV.
* Searched across base decision tree depth, number of estimators, sample sizes, and bootstrapping options.

* Performance improved significantly:
  Baseline: RMSE ~8.78, R² ~0.98
  Tuned: RMSE ~5.27, R² ~0.993
  
6. Advanced Predictions and Analysis
   
* Integrated estimated max BPM and fitness recommendations by generation.
* Created a new feature set using demographic, categorical, and generational exercise context.
* Predicted calories burned for user records with recommended max BPM, enabling comparison of actual vs improved scenario.
* Added "Comparison" column indicating if the modeled scenario shows improvement.
* Visualized the distribution of users with “Improved” vs. “Not Improved” calorie burn.

# Results
* Best Model: Tuned Bagging Regressor (via RandomizedSearchCV) with tuned depth and splits.
* Key Features: Training duration, heart rate, and generational category were the most influential for prediction.
* Actionable Insight: Many users could further increase calories burned by aligning with recommended BPM and exercise types for their generation.

## Author
Vera Pinto  Claudio Do Prado

