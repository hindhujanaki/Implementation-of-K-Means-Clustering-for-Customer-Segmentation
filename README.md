# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset  
2.check for null values   
3.Import kmeans and fit it to the dataset    
4.Plot the graph using elbow method    
5.Print the predicted array    
6.Plot the customer segments    

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: G.HINDHU
RegisterNumber:  212223230079
*/
```
```python

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```
## Output:
### 1.DATA.HEAD():
![image](https://github.com/user-attachments/assets/e46b5d13-d25e-4570-8ebd-118150b199c3)




### 2.DATA.INF0():
![image](https://github.com/user-attachments/assets/fa15e5c4-adbb-4a5d-aa90-aa60088658b8)


### 3.DATA.ISNULL().SUM():

![image](https://github.com/user-attachments/assets/0244bd91-2670-4072-b256-52b00c2e4cc9)


### 4.PLOT USING ELBOW METHOD:
![image](https://github.com/user-attachments/assets/f213d473-9134-4482-a082-07ac44f00ffa)


### 5.K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/eb0bebd3-fd78-41c5-b916-f3925693d21c)



### 6.Y_PRED ARRAY:
![image](https://github.com/user-attachments/assets/8654c2e1-4ebe-4c76-b398-3bb7d5c3a177)



### 7.CUSTOMER SEGMENT:

![image](https://github.com/user-attachments/assets/bad79e9b-e2cf-4e28-97fa-2c1afc5e91b4)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
