# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import necessary libraries (pandas, matplotlib, sklearn.cluster.KMeans).
2. Load the dataset using pd.read_csv().
3. Explore the data using .head() and .info() to understand its structure.
4. Use Elbow Method: Loop through 1 to 10 clusters, fit KMeans, and store inertia values.
5. Plot the inertia values to find the optimal number of clusters.
6. Apply KMeans with the chosen number of clusters (e.g., 5), and predict cluster labels.
7. Visualize the clusters using a scatter plot of Annual Income vs Spending Score.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
*/

import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
data = pd.read_csv("Mall_Customers (1).csv")
data.head()
data.info()
l = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    l.append(kmeans.inertia_)
plt.plot(range(1,11),l)
plt.show()
km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
data["clusters"]=y_pred
df0=data[data["clusters"]==0]
df1 = data[data["clusters"]==1]
df2=data[data["clusters"]==2]
df3=data[data["clusters"]==3]
df4=data[data["clusters"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],color="pink")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],color="green")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],color="yellow")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],color="blue")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],color="gray")
plt.show()
```

## Output:

![image](https://github.com/user-attachments/assets/f26423e9-527d-4c36-ba32-928ccbb95832)

![image](https://github.com/user-attachments/assets/e92ef264-4354-4f80-8d27-ab75da2b8c0a)

![image](https://github.com/user-attachments/assets/ad488bde-9059-4087-bedf-1a28c9fe0c18)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
