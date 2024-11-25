## Project Topic:
Machine Learning Model for Predicting the Occurence of Flood. 

## Dataset Description:
This data set contains 20544 rows and 19 columns with 4493 entries missing in the target class. 

## Techniques:
I applied data cleaning techniques and renamed some columns to better capture their meanings. Due to the large amount of data that was missing from the target class, a simple filling of the missing data is not advisable hence the decision to build a predictive model that can predict the missing data in the target class. To achieve this, I split the data into 2 datasets based on missing and non-missing. 

Afterwards, the numerical part of the dataset without missing entries was preprocessed using StandardScaler, MinMaxScaler, and Normalizer to ensure that it is adjusted to a scale which improves the performance of the machine learning models.

Subsequently, One Hot Encoder was used to transform the categorical columns of the dataset into a format that can be easily utilized by the algorithm which usually require a numerical input.  

## Data Exploration:
Several plots were plotted to understand the relationship between the variables. 

  - Pair plot graph to determine the relation between rainfall and wind speed. 
![Screenshot 2024-11-25 194211](https://github.com/user-attachments/assets/86814b8d-ce08-438f-8070-ec74faba2b2e)

#### Key Observations

There is a weak positive correlation between wind speed and rainfall. The weak correlation suggests that while wind speed might contribute to rainfall, it's not the sole determining factor. Other factors like atmospheric pressure, humidity, and temperature likely play a significant role.

## Model Development:
A logistic regression model was initially used to build a model which was used to predict the missing entries in the target class of the dataset with missing data. The 2 datasets (dataset without missing entries and the dataset with missing entries which was predicted with the logistic regression model) were consolidated to form a complete dataset (full_df). I subsequently build multiple models to determine which is the best fit for predicting the occurence of flood. The models include;
  - Random Forest Classifier
  - SVM Classifier
  - KNN Classifier
  - Ridge Classifier
  - XG Boost

![image](https://github.com/user-attachments/assets/bc2dfb20-a96d-425c-8f7a-ed89555c6716)
![image](https://github.com/user-attachments/assets/0adb5707-0d35-4a07-b688-ec88f818eaf7)

All 5 models performed excellently with the least performing model (Ridge Classifier Model) having an accuracy of 0.97. To further determine the best performing of the models, a confusion matrix was plotted for all five models. Of the 5 models, the Random Forest Classifier model is the most preferred because 

![image](https://github.com/user-attachments/assets/587496d6-57a3-4d0c-81ca-c0cb2013ccb0)
 
##### Breaking Down the Numbers for clarity:
  - True Positive (TP) - 3988 means the model correctly predicted 3988 instances of the positive class.
  - False Positive (FP) - 2 means the model incorrectly predicted 2 instances as positive when they were actually negative.
  - False Negative (FN) -  1 means the model incorrectly predicted 1 instance as negative when it was actually positive.
  - True Negative (TN) - 4045 means the model correctly predicted 4045 instances of the negative class.

### Conclusion:
Based on this confusion matrix, the model is performing very well. It is making very minimal errors, as indicated by the low number of false positives and false negatives.


