# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Ramishka Madhushan

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
Upon submitting my initial predictions, I encountered syntax issues and had to refer to additional documentation to correctly execute the model. Initially, I faced difficulties running the tasks locally, which led me to switch to SageMaker Studio. This transition helped enhance my results, reducing my score from above 1.3 to below 0.5.


### What was the top ranked model that performed?
My top score was achieved my the completing the second run with more features but no tuning og hyperparameters. The score was 0.46870 and was better than the one with the tuning.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The exploratory analysis revealed normally distributed temperature categories and necessitated the breakdown of the datetime into additional features such as year, month, day, and hour—this significantly boosted model performance. The analysis also highlighted four seasonal categories and three weather conditions, with binary fields for workday and holiday, and skewed distributions for humidity and windspeed.

### How much better did your model preform after adding additional features and why do you think that is?
Segmenting the datetime significantly enhanced the model's accuracy, contributing to a 66% improvement. This improvement likely stems from the model's increased ability to capture temporal dynamics affecting bike usage.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
While the model's performance improved compared to the initial setup, it slightly lagged behind the run with additional features alone. I utilized AutoGluon's recommended hyperparameter settings for tabular data, but further tuning was constrained by a lack of deeper understanding needed to optimize these settings.

### If you were given more time with this dataset, where do you think you would spend more time?
Given more time, I would focus on enhancing feature engineering. Techniques like one-hot encoding or adjustments accounting for seasons or work hours could potentially yield better results.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|score|
"initial"|1.39373
"add_features"|0.46870
"hpo"|0.49696

### Create a line plot showing the top model score for the three (or more) training runs during the project.



![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.



![model_test_score.png](img/model_test_score.png)

## Summary
The most significant gains were achieved through feature engineering, with substantial insights derived from exploratory data analysis. Moving forward, I plan to refine the model by considering variables like work hours and seasonal variations, which have notable impacts on bike sharing demand.
