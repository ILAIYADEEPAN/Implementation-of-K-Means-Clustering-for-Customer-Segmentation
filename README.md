# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Start the program

2.Import pandas and matplotlib.pyplot.

3.Read the dataset and transform it.

4.Import KMeans and fit the data in the model.

5.Plot the Cluster graph.

6.End the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ILAIYADEEPAN K
RegisterNumber:  212223230080
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square.

for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![image](https://github.com/ILAIYADEEPAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147473334/18ee582c-ec16-4220-b9c4-ddad72552b57)
![image](https://github.com/ILAIYADEEPAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147473334/53d6e0d4-6fe6-48a1-8588-d2ee89494002)
![image](https://github.com/ILAIYADEEPAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147473334/df9830a2-0325-4c51-ab42-981a424d7ef6)
![image](https://github.com/ILAIYADEEPAN/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147473334/c4c5a3e4-1fff-4cd7-b18e-9bbd2d6d804d)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
