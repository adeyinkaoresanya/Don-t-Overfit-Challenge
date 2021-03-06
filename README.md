# Don-t-Overfit-Challenge

The goal of this project is to build a model on a small dataset without overfitting, while achieving an AUC score greater than 0.8.

# About the data
The dataset, downloaded from [Kaggle](https://www.kaggle.com/sahiltinky/org-dataset-dont-overfitii), contain 302 variables and 250 observations in the train set, while the test set has 19750 observations with 301 variables Training on a small dataset with many feature is a perfect candidate for overfitting(curse of dimensionality!)

There are no available variable names, which constrained feature engineering.

## Exploratory Analysis
* All of the variables are numeric and contain no missing values.

* The target variable has two distinct classes that are imbalanced. Thus, this was treated as a classification task.

 ![alt text](https://github.com/adeyinkaoresanya/Don-t-Overfit-Challenge/blob/main/Images/target.PNG "Distribution of the target variable")

* Most of the features have weak linear correlation with the target feature. 

* There is no collinearity among the selected features.

* None of the features is skewed.

## Feature Engineering

Since there were no variable names, much feature engineering could not be implemented, except for feature scaling. Hence, attention was given to appropriate crossvalidation strategy (because of the few training examples) and hyperparameter optimization of the selected algorithm.

## Model Building and Evaluation

*	Out of seven models that were built, Logistic regression model had the best validation AUC score. Thus, this was further optimized through hyperparameter tuning to see if it would improve the score.

![alt text](https://github.com/adeyinkaoresanya/Don-t-Overfit-Challenge/blob/main/Images/Models_table.PNG "Models")

* SelectFromModel was used for feature selection to see if the model would improve. This decreased the validation score to 0.718. Hence all the features were fed into the model.


* Upon hyperparameter optimization, the validation AUC score improved to 0.788. Thus the model was retrained on the whole train set because of the small size.

 * This led to public and private scores of 0.848 and 0.837 on Kaggle leaderboard, thus meeting the project requirement.
