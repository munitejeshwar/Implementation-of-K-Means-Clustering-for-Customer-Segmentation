# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program
## Program:

Program to implement the K Means Clustering for Customer Segmentation.
Developed by : K.Muni tejeshwar
RegisterNumber : 212223040102 

```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r'Mall_Customers.csv')

data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
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
### Head()
![image](https://github.com/Abburehan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849336/7c884c3f-0e7f-45ff-8145-163228e48127)

### Info()
![image](https://github.com/Abburehan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849336/f86d447a-d2d4-4e5c-88e4-3cd74e18198e)

### isnull.sum()
![image](https://github.com/Abburehan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849336/63ae7533-b9f2-46ad-bd50-6c333a4fa5d0)

### Elbow Method
![image](https://github.com/Abburehan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849336/66266a1c-c893-493b-a5f4-b2f6243fa070)

### Fitting the no. of clusters
![image](https://github.com/Abburehan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849336/a5570fc4-bfad-498e-b97d-f80a85e5e5b8)

### Prediction of Y
![image](https://github.com/Abburehan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849336/e70b8c6a-e5d6-433d-8348-5769b1612a83)

### Customer Segments
![image](https://github.com/Abburehan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/138849336/a6adf032-80e7-4055-9fac-feaaacba1115)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
