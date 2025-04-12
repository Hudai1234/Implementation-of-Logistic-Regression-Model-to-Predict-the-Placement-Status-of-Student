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
## Placement Data
![Screenshot 2025-04-12 175352](https://github.com/user-attachments/assets/a08483e2-d938-4725-9510-0f8058b85ba3)
## Checking the null() function
![Screenshot 2025-04-12 175927](https://github.com/user-attachments/assets/d2a16d6a-e773-4603-9753-407fc37d1dea)
## Print Value
![Screenshot 2025-04-12 180400](https://github.com/user-attachments/assets/510a02cf-b23f-46df-8f12-298a76e4748d)
## Y-Prediction Value
![Screenshot 2025-04-12 180737](https://github.com/user-attachments/assets/7b94c790-85ec-4086-bca4-9166936b328b)
## Confusion array
![Screenshot 2025-04-12 190107](https://github.com/user-attachments/assets/e8b549c8-0556-4bfd-b55e-97c799cf079a)
## Classification report
![Screenshot 2025-04-12 182100](https://github.com/user-attachments/assets/8f87bb0d-886d-473c-8b4f-558a9115b8fc)
## Prediction of LR
![Screenshot 2025-04-12 181839](https://github.com/user-attachments/assets/31fe8988-79bb-4a13-abb8-7b138701be90)







## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
