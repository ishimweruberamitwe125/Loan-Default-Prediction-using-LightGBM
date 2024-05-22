# Loan-Default-Prediction-using-LightGBM
This project aims to predict loan default risk for clients with little to no credit history using a LightGBM model. The absence of traditional credit data can often result in the denial of loans to individuals who may actually be creditworthy. By leveraging advanced data science techniques, we can improve the prediction accuracy and make loans more accessible to those who need them most.

Overview
Consumer finance providers typically use scorecards based on statistical and machine learning methods to predict loan risk. However, these models must be regularly updated to maintain their accuracy and stability. This project focuses on creating a robust model that balances performance and stability, ensuring that loans are issued to clients who are likely to repay them.

Home Credit, an international consumer finance provider, is the sponsor of this project. They focus on responsible lending to individuals with little or no credit history, broadening financial inclusion for the unbanked population.

Objective
The primary goal of this project is to build a LightGBM model that can accurately predict loan default risk, achieving a high Area Under the Curve (AUC) score and maintaining stability over time. The model's performance will be evaluated using a gini stability metric, which considers both the predictive ability and the stability of the model.

Evaluation Metric
The evaluation metric for this project is based on the gini stability metric, calculated as follows:

Gini Score Calculation:

Calculate the AUC for predictions corresponding to each WEEK_NUM.
Gini score is calculated as gini = 2 * AUC - 1.
Falling Rate Calculation:

Fit a linear regression a * x + b through the weekly gini scores.
Calculate the falling_rate as min(0, a), which penalizes models that drop off in predictive ability.
Variability Calculation:

Calculate the standard deviation of the residuals from the linear regression.
Apply a penalty to model variability.
Final Stability Metric:

stability_metric = mean(gini) + 88.0 * min(0, a) - 0.5 * std(residuals)
LightGBM Model
LightGBM (Light Gradient Boosting Machine) is a powerful machine learning algorithm that is well-suited for this task due to its efficiency and high performance. The model was trained on historical loan data and tuned to achieve an AUC score of 0.75.

Features
The model uses a variety of features, including but not limited to:

Client demographic information
Loan application details
Historical transaction data
Behavioral data
Training and Evaluation
The model was trained using cross-validation to ensure robustness and generalizability. The following steps were performed:

Data Preprocessing: Cleaning and transforming the data to make it suitable for model training.
Feature Engineering: Creating new features to capture relevant patterns in the data.
Model Training: Training the LightGBM model using the training dataset.
Model Evaluation: Evaluating the model using the validation dataset and calculating the gini stability metric.
Conclusion
The LightGBM model developed in this project achieved an AUC score of 0.75, demonstrating its effectiveness in predicting loan default risk. By maintaining a balance between performance and stability, this model can help consumer finance providers make more informed lending decisions and extend credit to individuals who have traditionally been underserved.
