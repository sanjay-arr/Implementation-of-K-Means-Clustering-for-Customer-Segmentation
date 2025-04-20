# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import the necessary packages using import statement.
2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3.Import KMeans and use for loop to cluster the data.
4.Predict the cluster and plot data graphs.
5.Print the outputs and end the program.
```

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: G.SANJAY
RegisterNumber:  212224230243
*/
```
```

import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('Mall_Customers.csv')

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### DATA HEAD:
![image](https://github.com/user-attachments/assets/01bf4174-2747-484c-bfd8-f96676666c52)
### DATA INFO:
![image](https://github.com/user-attachments/assets/e5fe2089-141a-4f5a-b1fb-af18a06cc5be)
### NULL:
![image](https://github.com/user-attachments/assets/0aa3002d-a6f2-4616-bbaa-d674f8ff7c8a)
### ELBOW METHOD:
![image](https://github.com/user-attachments/assets/c336fd70-08f8-49b5-8e59-0c3ffba1b1ae)
### KMEANS:
![image](https://github.com/user-attachments/assets/1b113c30-8b69-4e45-a4cb-f2926346a9c2)
### PREDICTION:
![image](https://github.com/user-attachments/assets/c780773b-1001-4953-8e96-4976f8556e71)
### CUSTOMER SEGMENT:
![image](https://github.com/user-attachments/assets/efa0aa72-707b-45bb-aa12-08b095a4959f)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
