# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the required libraries.
2.Upload the csv file and read the dataset.
3.Check for any null values using the isnull() function.
4.From sklearn.tree inport DecisionTreeRegressor.
5.Import metrics and calculate the Mean squared error.
6.Apply metrics to the dataset, and predict the output.

## Program:
```
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: v.charan sai
RegisterNumber:  212221240061
```
~~~
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"] = le.fit_transform(data["Position"])
data.head()
x = data[["Position","Level"]]
y = data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2 = metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
~~~
## Output:
### Data Head:

![a](https://user-images.githubusercontent.com/94296221/172993453-3d7fbae3-dd90-451a-9ca1-ba51c8123464.png)

### Data Info:
![b](https://user-images.githubusercontent.com/94296221/172993459-af1994d2-dd10-48c9-867f-5d5d876a1059.png)

### Data Head after applying LabelEncoder():
![c](https://user-images.githubusercontent.com/94296221/172993468-fb945377-b0ec-49d6-b993-b9b2d47dc430.png)

### MSE:
![d](https://user-images.githubusercontent.com/94296221/172993474-70327e6f-eb81-45ea-bb6d-04068f7b8933.png)

### r2:
![e](https://user-images.githubusercontent.com/94296221/172993480-d7b57944-245d-4b83-9df5-957a3426f83e.png)

### Data Prediction:
![f](https://user-images.githubusercontent.com/94296221/172993486-af9247f3-0126-4982-a5ec-44004a4cfff2.png)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
