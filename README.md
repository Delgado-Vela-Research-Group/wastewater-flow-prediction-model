# wastewater-flow-prediction-model

The code provides a comprehensive analysis for time series data related to two wastewater treatment plants in the United States.  Each step in the code makes it accessible for understanding and modification. The libraries are essential for (1) data manipulation, (2) imputation techniques,  (3) machine learning models, and (4) data visualization for the manuscript. 

# Data Preprocessing
Time-based train-test splitting will be performed to separate training and testing datasets chronologically. Censored values in the training set are handled and missing values are generated from imputation. The code feature engineers data from rainfall, and missing data is imputed separately for Plant II. Cumulative distribution function plots are created to differentiate between dry and wet weather conditions as described in the manuscripy. Non parametric correlation analysis is used to determine the relationships between the target and independent variables.

# Model Selection and Evaluation:
The PyCaret library is utilized for streamlined model selection and evaluation. It performs a comparison of various regression models based on training time and a custom Overall Accuracy Index (OAI) calculated from R-squared, RMSE, and MAE.
The SMOGN algorithm is employed to handle the skewed distribution of the target variable ('flow'), aiming to improve the the ability of the models deployed in the study to predict rare cases effectively.
A loop is implemented to create synthetic datasets using the SMOGN algorithm with different hyperparameters, and the best set is selected based on the lowest mean squared error (MSE) and zero count for dummy variables.

Further, regression models are developed using the training set without resampling and the training set with synthetic data. The performance metrics (R-squared and MSE) are calculated for each model on the test set, and the results are plotted.
The script also includes the visualization of the cumulative distribution function for determining rare events in the flow data and several figures illustrating model predictions, including one with SHAP (SHapley Additive exPlanations) summary plots.

# Additional Figures:
Multiple figures of this work are plotted in the main document and SI, including Cumulative Distribution Function (Figure S3), time-series plots comparing measured and predicted flows for two plants (Figure 6), scatter plots comparing measured and predicted flows for different models (Figure 3), and various other plots, including SHAP summary plots and box plots comparing flow conditions during dry and wet conditions (Figures 7 and S5).

# Models 
Multiple Linear Regression

k-nearest neighbours 

Bayesian Ridge

Random forest

XGBoost

# Requirements
Python 3

Install https://www.anaconda.com/

NumPy

Pandas

PyCaret 3.0 

# References

https://scikit-learn.org/stable/

