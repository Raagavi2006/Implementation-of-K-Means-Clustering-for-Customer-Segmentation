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
Developed by: RAAGAVI R M
RegisterNumber: 212224220074

import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv("/content/drive/MyDrive/datasetml/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1, 11):
  kmeans = KMeans(n_clusters=i, init="k-means++", n_init='auto', random_state=42)
  kmeans.fit(data.iloc[:, 3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")

km = KMeans(n_clusters=5, init="k-means++", n_init='auto', random_state=42)
km.fit(data.iloc[:, 3:])

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]

plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="red", label="cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="black", label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="blue", label="cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="green", label="cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="magenta", label="cluster4")

plt.legend()
plt.title("Customer Segments")

*/
```

## Output:

### Data Details :

<img width="422" height="207" alt="image" src="https://github.com/user-attachments/assets/db9d7be0-3d2b-4f2b-baf1-5f9a6cc5529e" />

### Graph :

<img width="786" height="465" alt="image" src="https://github.com/user-attachments/assets/cf95d25d-3b5a-45e7-889f-4b804caf322c" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
