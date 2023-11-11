# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplot libraries.
2. import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data.
4. Predict the output and plot data graphs.
5. Display the outputs

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Nandhini S
RegisterNumber:212222220028  
*/
import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1) (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
WCSS=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  WCSS.append(kmeans.inertia_)

  plt.plot(range(1,11), WCSS)
plt.xlabel("No. of clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
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
plt.title("Customer segments")
```

## Output:
Data.head():
![Screenshot 2023-11-11 102006](https://github.com/nandhu6523/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123856724/ff74bce5-74a1-489e-addc-0cfe03701238)

Data.info():
![Screenshot 2023-11-11 102019](https://github.com/nandhu6523/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123856724/67606852-4519-44eb-a3e9-e272eda11977)

Data.isnull() and sum():
![Screenshot 2023-11-11 102031](https://github.com/nandhu6523/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123856724/b5389d0b-3d3b-47cb-8b00-76c531ab4ff6)

Elbow method graph:
 ![Screenshot 2023-11-11 102131](https://github.com/nandhu6523/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123856724/dadc5b56-17ea-468f-b3d5-6889102617dc)

KMeans clusters:
![Screenshot 2023-11-11 102116](https://github.com/nandhu6523/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123856724/f9a504eb-e3b6-4d89-80ce-6c92f8e0d327)

Y_prediction():
![Screenshot 2023-11-11 102144](https://github.com/nandhu6523/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123856724/6cb6e388-51dd-452d-a138-bf11c1a80c0d)

Customers segments graph:
![Screenshot 2023-11-11 102157](https://github.com/nandhu6523/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/123856724/c19cff4c-a58c-4b61-bfb4-ecffed4e1b36)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
