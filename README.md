# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/dd064d6a-51d5-4ad6-8ce9-92d5420338dc)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/29acc36b-21f7-4bd7-9978-f611b5167f36)
```
dt.shape
dt.head(4)
dt.tail(4)
dt.set_index("PassengerId",inplace=True)
```
![image](https://github.com/user-attachments/assets/5fcb57ab-d1d2-4157-a6d1-d06e3936cc34)
```
dt.describe()
dt.nunique()
dt["Survived"].value_counts()
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/d98d42be-d453-4dcc-8f02-e6e4c51928f3)
```
sns.countplot(data=dt,x="Survived")
dt
dt.Pclass.unique()
dt.rename(columns = {"Sex":"Gender"},inplace = True)
dt
```
![image](https://github.com/user-attachments/assets/c7ba14cb-85ad-4490-97ec-314799ec4293)

![image](https://github.com/user-attachments/assets/66eded0d-1480-45dd-9ed6-f7ca195af3af)

![image](https://github.com/user-attachments/assets/21a2910e-30d4-4657-9222-b166be11801a)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/125121d6-21b5-4974-bde0-a1962cb6e410)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/00be9553-683d-480a-b6d7-cd6f946a71eb)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/81503e9a-b735-4f90-91dc-4f45cd76553a)
```
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x="Pclass",y='Age',hue='Gender',data=dt)
```
![image](https://github.com/user-attachments/assets/4662968d-ca62-42ae-86ce-f8210a425953)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/2b10e0ed-fbe2-4052-83b8-70db58cc383e)
```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/ce9cb037-4975-42a5-997b-24fde894c8d3)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/dc18bbdd-5bcf-4cc5-b692-9c971dc6eb83)

![image](https://github.com/user-attachments/assets/0e286834-dada-4056-8b4f-37535f287455)

# RESULT
  Thus, Exploratory Data Analysis for the given dataset is done successfully.
