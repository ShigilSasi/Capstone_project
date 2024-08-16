Dataset Name - Indian Election dataset
This database contains detailed candidate‐level data for elections to the lower houses of India’s national and state legislatures, i.e., the Lok Sabha and Vidhan Sabhas. The data span 1977‐2015, with each row representing a candidate that ran for office in that state‐year.

Data Description

Variable name : Storage: type Variable contents st_name : str35 : State

Year : Int : General election year

pc_no : Byte : Parliamentary constituency number

pc_name : str25 : Parliamentary constituency name

pc_type : str3 : Parliamentary constituency reservation status

cand_name : str70 : Candidate name

cand_sex : str1 : Candidate sex

partyname : str57 : Party name

partyabbre : str10 : Party abbreviation

totvotpoll : Long : Votes received

electors : Long : Number of registered voters

Potential Target Variables:

totvotpoll: The total votes polled for each candidate.

partyname: The party name if the analysis is focused on predicting or analyzing party performance.

cand_name: The candidate name if the analysis is focused on predicting the winning candidate.

For this dataset I am choosing the target variable:
Total Votes Polled (totvotpoll): This is a straightforward target for predicting the number of votes a candidate receives. It provides a quantitative outcome that can be modeled using regression techniques.

Building the model

As building the model the target variable is numerical outcomes we going to use Regression Algorithms.

The regression algorithms:

1.Linear Regression

2.Decision Tree Regression

3.Support Vector Regression

4.Lasso Regression

5.Random Forest Regression

6.Gradient Boosting Regression

Model Evaluation
Linear Regression

MAE: 0.1765

R²: 0.8964

MSE: 0.1015

RMSE: 0.3186

Analysis: The performance of Linear Regression has improved significantly compared to previous iterations. With an R² of 0.8964, the model now explains almost 90% of the variance, and the error metrics have decreased, showing that the model is making more accurate predictions.

Decision Tree

MAE: 0.0634

R²: 0.9709

MSE: 0.0285

RMSE: 0.1687

Analysis: The Decision Tree model continues to perform well, with an R² of 0.9709, indicating that it explains 97.1% of the variance. The low error metrics suggest that the model is still making accurate predictions, though slightly less accurate than before scaling and transformation adjustments.

Support Vector Regression (SVR)

MAE: 0.4779

R²: -0.1219

MSE: 1.0991

  RMSE: 1.0484
Analysis: The SVR model still underperforms, with a negative R² value indicating that it does worse than a simple mean model. Despite scaling, the SVR model seems unsuitable for this dataset.

Lasso

MAE: 0.1663

R²: 0.8625

MSE: 0.1347

RMSE: 0.3671

Analysis: The Lasso model shows decent performance with an R² of 0.8625, explaining about 86.2% of the variance. It performs similarly to Linear Regression but slightly worse, which is expected as Lasso includes regularization.

Random Forest

MAE: 0.0491

R²: 0.9794

MSE: 0.0201

RMSE: 0.1419

Analysis: The Random Forest model continues to perform exceptionally well, with a high R² and low error metrics. This model remains a strong contender, providing accurate predictions with minimal error.

Gradient Boosting

MAE: 0.0067

R²: 0.9996

MSE: 0.0004

RMSE: 0.0200

Analysis: Gradient Boosting continues to outperform all other models, with an R² close to 1 and extremely low error metrics. This model is the best performer for this dataset, providing highly accurate predictions.

As to select a model we will choose Linear regression but other model has performed well except support vector regression. Why I choosed linear regression other model can be overfitting. linear regression will be the best model.

HyperParameter Tuning

After Hyperparameter tuning I just used the linear regression model because the system I am using can't handle all the models as I selected the linear regression model for hyperparameter tuning.

Best Parameters:

fit_intercept: True

Performance Metrics:

Mean Absolute Error (MAE): 0.1765

R-squared (R²): 0.8964

Mean Squared Error (MSE): 0.1015

Root Mean Squared Error (RMSE): 0.3186

Analysis:

Fit Intercept: The best parameter found was to include the intercept(fit_intercept=True), which is standard in most linear regression problems.

R² Value: An R² of 0.8964 indicates that the model explains approximately 89.6% of the variance in the target variable. This is a strong performance for a linear model, especially after tuning.

Error Metrics: The MAE, MSE, and RMSE values are relatively low, suggesting that the model is making accurate predictions.

Conclusion: The Linear Regression model has performed well after Random Search tuning, achieving a good balance between simplicity and accuracy. With an R² close to 0.9, the model is explaining a substantial amount of the variance, and the error metrics indicate reasonable prediction accuracy.

If we are satisfied with these results, we can confidently use this model for prediction.
