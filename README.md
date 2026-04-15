# Team Rocket - Round 1 (Neural Nexus 2.0)

## Our Domain is "Pharma"
### For Data cleaning -> (pipeline)
step 1. We read the dataset using pandas
step 2. We perform exploratory data analysis.
step 3. We removed all the columns which for of no use for eg. Patient_name , Father_name, Family_name, Location etc.
step 4. Then we noticed there are misleading values, noise , class imbalance and missing values in the given dataset.
step 5. For which we replaced the misleading values like "-99", "-", "not availabe", "no record", with NaN value.
step 6. For all sympthoms columns we calculated the count, mean, max, std, min and range.
step 7. We have grouped all the numerical columns in num_cols and similarly all text cols in cat_cols.
step 8. For nums_cols we have found the median value and filled all the NaN value with the median value.
step 9. For cat_cols we put the element with the highest frequency.
step 10. Then we removed all the duplicated rows.
step 11. Then we saved the dataframe as train_clean.csv and test_clean.csv.


### For Training 
step 1. We have used the XGBClassifier from the xgboost library which is best for tabular data.
step 2. we now import the cleaned dataset from our cleaning pipeline.
step 3. We split the dataset into training and testing part.
step 4. Then we created our model and we took parameter as -> multi:softmax, depth = 4, and learning rate = 0.1.
step 5. then we train our model.
step 6. then we predicted for test dataset.
step 7. then we just find the f1 score and accuracy.

# our model accuracy.
Model Accuracy for Genetic Disorder: 0.6076981132075472

Classification Report
              precision    recall  f1-score   support

           0       0.65      0.84      0.74      3729
           1       0.45      0.26      0.33       654
           2       0.50      0.32      0.39      2242

    accuracy                           0.61      6625
   macro avg       0.53      0.47      0.49      6625
weighted avg       0.58      0.61      0.58      6625


Model Accuracy for Disorder Subclass: 0.6235053492762744

Classification Report
              precision    recall  f1-score   support

           0       0.65      0.87      0.74      3473
           1       0.53      0.31      0.39       559
           2       0.56      0.33      0.42      2324

    accuracy                           0.62      6356
   macro avg       0.58      0.50      0.52      6356
weighted avg       0.61      0.62      0.59      6356
