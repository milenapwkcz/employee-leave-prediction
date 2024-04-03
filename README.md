# employee-leave-prediction
This project helps to make the prediction if the employees left the company based on the specific variables by using the ML models.

## Overview
1. The database used for this project was downloaded from [Kaggle](www.kaggle.com).
2. The project was made as the collaboration of two people involved.
3. The language used for coding is the language R.
4. The description in the HTML file is made in Polish and the basic summary of it is involved below.

## Purpose of the research
ML techniques enable the acquisition of information that can later be used to optimize business operations. In this case, the company's problem is to predict employee turnover. Based on the results obtained, the management board can obtain information on whether an employee with a given experience, age or year of joining the company will leave the company. Excessive turnover of overly experienced employees is a negative phenomenon for the company, as the process of introducing a new person is time-consuming and expensive for the company. The results can enable managers to analyze whether there are factors that connect people leaving their jobs and thus partially prevent the undesirable departure of the most valuable employees. Based on the study, they will also know which employees should be motivated more, as the probability that they will stay in the company for a longer period is much greater. The model itself can be used in the future for a newer group of employees.

## Basic statistics
For each variable there is the description of the basic statistics with the interpretation. In case of the quantitative variable, it contains the information about mean, standard deviation, median, skew, kurtosis and min and max value and in case of the categorical variable, it contains the information about the frequency. There is also a combination of dependancy between the specific variables.

## Preprocessing
Before we go into the creating the model, there is a need to make the below steps:
1. Data transformation of the categorical variables.
2. Removing variables that do not influence the dependent variable.
3. Balancing the dataset.
4. Creating the dummy variables.

## Methods used for prediction
Im the project there are several methods which could help to describe this problem. Usage of multiple models could guarantee the pick of the most accurate model for the described problem.

### SVM
The SVM, or Support Vector Machine, method involves finding the optimal hyperplane, i.e. a plane with one dimension less than space, between two or more, that best divides samples from different classes. In order to find the optimal hyperplane, the SVM algorithm searches for a support vector (i.e. weight vector) that maximizes the margin between the hyperplane and the closest samples from both classes, which are support vectors. If the data is not linearly separable, i.e. one hyperplane cannot be determined, the SVM algorithm can apply the data transformation technique to a space with a larger number of dimensions. In such a data space, they can become linearly separable, which will allow the determination of a separation hyperplane.

### Random Forest
The Random Forest method is based on the concept of decision trees and teams of classifiers. A random forest consists of many decision trees that are built on the basis of a randomly selected training set and randomly selected subsets of features. Each tree in the forest makes an independent prediction and the results are averaged to obtain the final classification. The algorithm learns by creating many decision trees, each of which is built on the basis of a randomly selected training set. Each tree uses randomly selected subsets of features to make predictions for new data. In the case of classification, the final decision is made based on voting among all trees.

### Decision trees
A decision tree enables predictions based on a tree structure in which each node represents a test for one feature of the data, and each edge leads to the next node or leaf that contains the predicted value. In the case of classification, based on the input features, the tree makes a series of decisions leading to assigning the object to one of the predefined classes, and in the case of regression, the tree predicts a numerical value based on the input features. The process of training a decision tree involves dividing the data set into subsets based on a feature that maximizes inter-group and intra-group homogeneity. The implementation is done through recursive divisions that create a tree structure. Once the tree is created, it can be used to predict values ​​for new observations by traversing the tree from root to leaf based on feature values.

## Interpretability analysis
The next step of the project is to analyze interpretability based on ceteris-paribus profiles, partial dependence plots and SHAP values. From the ceteris-paribus profile charts, it can be seen that for the tested observation, a change in the level of education would have the greatest impact on the change in the prediction (while keeping the values ​​of the other variables unchanged). Analyzing the partial dependence charts, it can be noticed that the expected value of the prediction changes the most for the Education_Masters, *JoiningYear_2018* and *PaymentTier_2* variables. SHAP is the feature value of the average marginal contribution among all possible feature combinations.

## Final conclusions
1. The assumed relationships between variables, consistent with the observation of the environment, are not illustrated in the data set. Greater education or experience does not affect the level of earnings.
2. Variables indicating age, whether a given employee has ever been removed from a project for a long time and experience in a given field turned out to be irrelevant for predicting whether a given employee left the company.
3. The default set was unbalanced, so before starting work, an overfitting technique had to be used in which tuples with the value 1 were duplicated.
4. The cross-validation results for the SVM and Random Forest methods are similar and oscillate around 0.2.
5. For a decision tree, pruning should be at level 3.
6. In the case of predicting whether an employee had left his job, the Random Forest method achieved the best result.
7. In the case of predicting whether an employee left his job, the best result was achieved by the decision tree method.
8. According to the ceteris-paribus (PCP) profiles for the random forest model for selected observation No. 10 from the training set, the greatest impact on the change in prediction (keeping other variables unchanged) would have a change in the value of the Education_Masters variable.
9. Based on the partial dependency plots (PDP), the variables Education_Masters, JoiningYear_2018 and PaymentTier_2 have the greatest impact on the potential change in the expected value of the prediction.
10. Based on the SHAP values, the variables *Education_Masters* = 1 and *PaymentTier_2* = 1 had the greatest influence on the prediction value for observation No. 10 being "1", while the fact that the *JoiningYear_2017* variable had the value 1 in this observation reduced the final prediction result .
