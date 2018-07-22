# Sales-Forecast-By-Seasons

### Project Overview

The objective of this project is to study the relationship between various factors in sales data to predict which categories of items will be sold in which part of the year. These results will help us in understanding the demand and supply relationship of the items during the specific part of the year. 

#### Data Overview

![alt text](/images/Data-Overview.png "Data Overview")

It is a binary class classification problem with Class 1 -> Q1-Q2 ,  Class 0 -> Q3-Q4

#### Vizualizing Dataset

![alt text](/images/Vizualizing_dataset.png "Vizualizing_dataset")
As we can see, the data is misclassified around Z = 0 and between Z > -10 and Z <=0  

###                                                           Models

#### 1. Logistic Regression with Lasso plot 

![alt text](/images/Lasso-plot.png "Lasso-plot")

#### The RoC curve , with AUC of both classes = 0.81

![alt text](/images/Logistic_Regression_with_lasso-RoC-plot.png "Logistic_Regression_with_lasso-RoC-plot")

Accuracy = 84% and the classification Report was as follows:

          |Class |precision|recall | f1-score | support|
          |----- |---------|-------| ---------| -------|       
          | 0    |   0.76  | 0.57  |    0.65  |   2639 |
          | 1    |   0.86  | 0.94  |    0.90  |   7541 |
          |avg/T |   0.83  | 0.84  |    0.83  |  10180 |

#### 2. Logistic Regression without Regularization

The accuracy of the model increases by 1% when no regularization is applied on the model , but the model becomes complex as compared to the first model. So there is a trade off between error and complexity , and logistic regression tries to minimise these parameters. 

Accuracy = 85% and the classification Report was as follows:

          |Class |precision|recall | f1-score | support|
          |----- |---------|-------| ---------| -------|       
          | 0    |   0.76  | 0.66  |    0.71  |   2639 |
          | 1    |   0.89  | 0.93  |    0.91  |   7541 |
          |avg/T |   0.85  | 0.86  |    0.85  |  10180 |
          
#### The RoC curve , with AUC of both classes = 0.81
![alt text](/images/Logistic_Regression_without-lasso-RoC-plot.png "Logistic_Regression_without-lasso-RoC-plot")

### 3. SVM with Linear Kernel

A gridsearch of various Kernel Scale and Box Constraint values were validated to create a model with minimal overfitting , reduced error and comparatively simpler model. 

Accuracy = 85% and the classification Report as follows : 

          |Class |precision|recall | f1-score | support|
          |----- |---------|-------| ---------| -------|       
          | 0    |   0.74  | 0.66  |    0.70  |   2639 |
          | 1    |   0.89  | 0.92  |    0.90  |   7541 |
          |avg/T |   0.85  | 0.85  |    0.85  |  10180 |
          
#### The RoC curve , with AUC of both classes = 0.81
![alt text](/images/svm-RoC-plot.png "svm-RoC-plot")

### Ensemble of models

The three trained classification models (Logistic Regression with and without Lasso, SVM) were combined by the voting classifier and used a majority vote (hard voting)  and average predicted probabilities (soft voting) to predict the class labels. Such a classifier can be useful for a set of equally well performing model in order to balance out their individual weaknesses.

![alt text](/images/Ensemble.png "Ensemble")



#### Comparing accuracy across all the models:

![alt text](/images/Accuracy_comparison.png "Accuracy_comparison")

#### Comparing F1 across all the models:

![alt text](/images/F1_comparison.png "F1_comparison")

