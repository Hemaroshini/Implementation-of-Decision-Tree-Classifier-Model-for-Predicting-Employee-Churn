# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import pandas library to read csv or excel file.
2. Import LabelEncoder using sklearn.preprocessing library.
3. Transform the data's using LabelEncoder.
4. Import decision tree classifier from sklearn.tree library to predict the values.
5. Find accuracy.
6. Predict the values.
7. End of the program.

## Program:
```

Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: HEMAROSHINI M
RegisterNumber: 212219220015

import pandas as pd
data=pd.read_csv("Employee.csv")
data.head()
data.info()
data.isnull().sum()
data["left"].value_counts()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics 
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
dt.predict([[0.5,0.8,9,260,6,0,1,2]])

```

## Output:
HEAD:

![image](https://user-images.githubusercontent.com/107909531/174949233-d5f76848-b396-4829-8a5e-13451873255a.png)


INFO:

![image](https://user-images.githubusercontent.com/107909531/174949255-aec73c9c-a2e9-45e7-bccb-5d5bcdf5a60e.png)


ISNULL:

![image](https://user-images.githubusercontent.com/107909531/174949276-a7429288-41cf-4fbe-9cef-7679f3616877.png)


LEFT:

![image](https://user-images.githubusercontent.com/107909531/174949322-59e15636-1eff-45e4-a708-0cdffb0c27ca.png)


HEAD USING LABELENCODER:

![image](https://user-images.githubusercontent.com/107909531/174949345-851ba437-4ba7-4b7a-9c97-d307ded22e8b.png)


ACCURACY:

![image](https://user-images.githubusercontent.com/107909531/174949375-746f5acc-f5cf-469f-8dd3-49481915ee18.png)


PREDICT:

![image](https://user-images.githubusercontent.com/107909531/174949404-3dae55da-1cfc-4c5f-ab25-ac0f3b876796.png)



## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
