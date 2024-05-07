# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplot libraries.
2. import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data
4. Predict the output and plot data graphs.
5. Display the outputs
  

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ADHITHIYAN.K
RegisterNumber:  212222230006
*/
```
```

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wess=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wess.append(kmeans.inertia_)
plt.plot(range(1,11),wess);
plt.xlabel("no of clusters")
plt.ylabel("wess")
plt.title("elbow method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income"],df0["Score"],c="red",label="cluster0")
plt.scatter(df1["Annual Income"],df1["Score"],c="black",label="cluster1")
plt.scatter(df2["Annual Income"],df2["Score"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income"],df3["Score"],c="green",label="cluster3")
plt.scatter(df4["Annual Income"],df4["Score"],c="red",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
## DATA.HEAD()

![172996931-802aaea1-a2f4-4aee-9c94-86d092c85541](https://github.com/AdhithiyanK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121029258/7c524684-c478-49cb-9752-62d0e8647fc3)

## DATA.INFO()

![172996266-c938bc5f-3d84-423f-a511-eb1b4ec2a8ec](https://github.com/AdhithiyanK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121029258/cf574f11-c26c-4ba5-942b-56015ccfe15f)

![172996301-7606d4bb-02a1-4a94-a376-67f5266c16bd](https://github.com/AdhithiyanK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121029258/5d7a5c68-d213-42ef-8414-c041dd62d999)


![172996315-b8213033-a0de-4c94-b5f7-76c903ce886b](https://github.com/AdhithiyanK/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121029258/472edb5e-82be-4656-8452-37b8dcd02046)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
