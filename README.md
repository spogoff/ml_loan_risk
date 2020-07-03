# ml_loan_risk

# Analysis

### Oversampling Algorithms:

The performances of both oversampling algorithms used in this analysis are quite similar. The both have  relatively high balanced accuracy scores (82% and 84%). However, accuracy as a metric fails to measure the effectiveness of this algorithm, because looking more closely at precision and recall, we see that the logistic regression model based on both algorithms has a very high success rate in catching low_risk loans and fails to what actually matters: high_risk loans. A 0.03 for naive random oversampling algorithm and 0.04 for SMOTE oversampling algorithm indicate a very low ratio of true positives when it comes to catching high_risk loans. The f1 score of 0.06 and 0.07 in the two algorithms respectively confirms the inadequacy of both algorithms. 

### Undersampling Algorithm:

Interestingly, the undersampling algorithm used here does not change the performance of the logistic regression model. The accuracy score of the model stays at around 83% the model still fails to catch the high_risk loans with a precision of 0.02 and f1 score of 0.04 for high_risk loans. In addition to these flaws, the undersampling algorithm shrinks the size of the sample significantly which means a lot of data could get lost. 

### Combination Algorithms

The combination algorithm for oversampling, similarly, does not change the performance of the logistic regression much. Again, accuracy score is around 83%, the precision for high_risk category is 0.03 and the f1 score is 0.06. 

## Conclusion 

While oversampling is necessary for this analysis due to the imbalanced nature of low and high risk categories in the sample, it seems like none of the algorithms improve the performance of this machine learning model. This indicates other models, rather than logistic regression, might explain and predict the patterns more effectively. 

***

### Ensemble Models:

Using the samples from the SMOTEENN oversampling method, two ensemble models were then used to explain the data. Below is a short summary of each model's performance.

#### BalancedRandomForestClassifier

The Balanced Random Forest Classifier model has an accuracy score of 65%. However, this could still be considered a better model than logistic regression, because it has a much higher precision score in predicting high_risk category. It also has a much higher f1 score (0.45). 

Looking at the list of features in order of their weight in defining the risk level, reveals a number of features that has no or close to none impact in predicting the outcome. It also includes a group of features that could indicate a correlation but might not be meaningful in the analysis, such as the issue_d column.

The model could be improved once the features are reviewed and filtered.

#### EasyEnsembleClassifier

The Easy Ensemble Classifier model 

The Easy Ensemble Classifier modelhas an accuracy of 90%, but that does not necessarily make it a better model for predicting high risk loans. With a precision of only 0.14, this model misses 86 out of 100 high risk predictions. It also has an f1 of 0.24 which is quite low.

