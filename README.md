# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.  Import the required packages.
2. Print the present data and placement data and salary data.
3. Using logistic regression find the predicted values of accuracy confusio
4. Display the results.

## Program:
```
Developed by: T.Hudaifa Mahzumia 
RegisterNumber: 212224040119
import pandas as pd
 from sklearn.preprocessing import LabelEncoder
 data = pd.read_csv('/content/Placement_Data.csv')
 data.head()
 data1 = data.copy()
 data1 = data1.drop(["sl_no", "salary"], axis = 1)
 data1.head()
 data1.duplicated().sum()
 from sklearn.preprocessing import LabelEncoder
 le=LabelEncoder()
 data1["gender"] = le.fit_transform(data1["gender"])
 data1["ssc_b"] = le.fit_transform(data1["ssc_b"])
 data1["hsc_b"] = le.fit_transform(data1["hsc_b"])
 data1["hsc_s"] = le.fit_transform(data1["hsc_s"])
 data1["degree_t"] = le.fit_transform(data1["degree_t"])
 data1["workex"] = le.fit_transform(data1["workex"])
 data1["specialisation"] = le.fit_transform(data1["specialisation"])
 data1["status"] = le.fit_transform(data1["status"])
 data1
 x = data1.iloc[:, :-1]
 x
 y = data1["status"]
 y
 from sklearn.model_selection import train_test_split
 
 x_train, x_test, y_train, y_test = train_test_split(x, y, test_size = 0.2, 
from sklearn.linear_model import LogisticRegression
 lr = LogisticRegression(solver = "liblinear")
 lr.fit(x_train, y_train)
 y_pred = lr.predict(x_test)
 y_pred
 from sklearn.metrics import accuracy_score
 accuracy = accuracy_score(y_test, y_pred)
 accuracy
 from sklearn.metrics import confusion_matrix
 confusion = (y_test, y_pred)
 confusion
 from sklearn.metrics import classification_report
 classification_report1 = classification_report(y_test, y_pred)
 print(classification_report1)
 lr.predict([[1, 80, 1, 90, 1, 1, 90, 1, 0, 85, 1, 85]])

```

## Output:

## Placement Data:
![image](https://github.com/user-attachments/assets/e760c509-a1cb-4c7b-a344-3b2c33774e4a)

## Checking null function:
![image](https://github.com/user-attachments/assets/8af8241f-44fe-4f84-9e65-e87c319063d3)

##Print Value:
![image](https://github.com/user-attachments/assets/311195ad-6d84-4182-8494-f5a3f6bbd705)

## Y Prediction Value:
![image](https://github.com/user-attachments/assets/0ec629dc-17f6-4932-8ccf-8bdaea6da891)

## Confusion Array:
![image](https://github.com/user-attachments/assets/1c716cb3-04ff-4fd6-8428-24d9bd38f699)

## Classification Report:
![image](https://github.com/user-attachments/assets/ea675014-d420-429d-b81b-787649d50306)

## Prediction of LR:
![image](https://github.com/user-attachments/assets/8e969ab2-63e6-43f8-b418-6811149c5a03)




## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
