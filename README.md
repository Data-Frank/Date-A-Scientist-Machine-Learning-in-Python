# Introduction 
This project has anayzed data from the dating app OKCupid. Dating apps are relatively new and have a rich user base. These apps are a rich source user data new relations can be found through data analysis and machine learning 

**Data sources:**
The data set used, `profiles.csv`, was provided by Codecademy.com.

## Scoping
### Project Goals
Probably the most interesting data from such an app would be the matching choices by the users. However, since this wasn'in the data, the focus has been on whether one could predicts the income by the other variables. Since a lot of users have not stated their income and one would want to know it anyway, these models could be used to make a prediction yourself.  
A second goal is to predict whether someone smokes or not. In this data set 90.81% of the smoker/non-smoker values were present and can be used to predict the last 9.19%. 

### Data
The project uses one data set, which is provided by Codecademy called `profiles.csv`. In the data, each row represents an OkCupid user and the columns are the responses to their user profiles which include multi-choice and short answer questions.

### Analysis 
This analysis will first focus on how the indivisual features are distributed and will later be prepared for several different machine learning models to predict income and whether someone smokes or not. The models include neural networks, multiple linear regression, support vector machine, random forest and logistic regression. 

### Evaluation
Each model will be subjected to evaluation, to determine which one predicts the best. The models predicting income, which is an continous variable will be evaluated by the mean average error.

The output of the models predicing smoker/non-smoker, which is a binary variable, will be evaluated through a confusion matrix and classification metrics accuracy, precision, recall, F1 score. 

# Data exploration 
The income distribution originally is distributed as follows:
<img src="https://github.com/user-attachments/assets/a909d978-c3a9-48df-8b50-f52bf9cc74bf" style="width:600px;"/>

After removing values above 100K, these values remained: 

<img src="https://github.com/user-attachments/assets/4a7be6a3-7217-44fc-921c-7054f9a26947" style="width:600px;"/>

The age is distributed as follows:

<img src="https://github.com/user-attachments/assets/6827d6f1-eb5c-4d4d-a677-febed74709f4" style="width:600px;"/>


For a more in depth data exploration, see the jupyter notebook in this repository.

# Results

### Income
To predict income a neural network was used, as well as a multiple linear regression model. The mean average error of the models were:
- **MAE Neural network:** 20,151.34  
- **MAE Multiple linear regression:** 16,426.25

Both MAE's are pretty bad predictors, since the value range from 20,000 to 100,000. The mutlipe linear regression model did outperform the neural network and would be best for this data set to predict one's income.
  
### Smoker/non-smoker
To predict if one smokes a neural network, a support vector machine, a random forest classifier and a logistic regression model were used. The evaluation metrics are shown below:    
  
**Neural Network:**     
Accuracy:  0.764  
Precision: 0.620  
Recall:    0.167  
F1 Score:  0.263    
  
**SVM:**    
Accuracy:  0.707  
Precision: 0.401  
Recall:    0.395  
F1 Score:  0.398  
  
**Random Forest Classifier:**    
Accuracy:  0.764  
Precision: 0.550  
Recall:    0.320  
F1 Score:  0.405  
  
**Logistic Regression:**    
Accuracy:  0.789  
Precision: 0.628  
Recall:    0.356  
F1 Score:  0.454  

  
As can be seen below, the eveluation metrics are devided about the same between each model. They have a high accuracy score and the other metrics are significanty lower.

![Evaluation Metrics grouped by model1](https://github.com/user-attachments/assets/eda1b30e-51e8-49ca-bbb2-d1d17a6de840)


Below it is easier to compare the different evauation metrics. They all have about the same accuracy, while the neural network clearly has a higher F1 score.
![Evaluation Metrics grouped by Metric 1](https://github.com/user-attachments/assets/e1f85ce3-61a3-4266-be65-e84a986c900d)





# Conclusion

Accurately predicting an individual's income is a challenging task. However, if such a prediction must be made, a simple linear regression model outperformed a more complex neural network model.

When attempting to predict wheter an invidividual is a smoker a logistic regressions is likely the most suitable model. That said, the model's performance—reflected by an F1 score of 0.454—indicates that it is still far from reliable. In practice, a direct inquiry may be a more effective and accurate approach.
