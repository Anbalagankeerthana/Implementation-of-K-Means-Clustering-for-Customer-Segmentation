# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.Importing essential libraries for data handling, visualization, and clustering.

2.Load the customer dataset into a pandas DataFrame.

3.Preview the dataset.

4.Use only the relevant numerical features: Annual Income and Spending Score.

5.Calculate WCSS (Within-Cluster Sum of Squares) for different cluster counts.

6.Plot the results to visually determine the "elbow point" where adding more clusters doesn’t significantly reduce WCSS.

7.Train the KMeans model with n_clusters=5.

8.Predict cluster labels for each customer.

9.Assign each data point to its respective cluster.

10.Use a scatter plot to visualize how customers are grouped based on Annual Income and Spending Score.


 

## Program:
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KEERTHANA
RegisterNumber:212224220046  
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
print("Name: Sukirthana.M\n Reg.no: 212224220112")
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
plt.xlabel("NO. of. clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

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
plt.title("Customer Segments")
```
## Output:
<img width="558" height="278" alt="image" src="https://github.com/user-attachments/assets/4da01d77-119b-4992-a7d1-72f58f31d79f" />


<img width="401" height="155" alt="image" src="https://github.com/user-attachments/assets/0e9aa9b2-0073-41aa-923c-af21f88dec6c" />


<img width="880" height="601" alt="image" src="https://github.com/user-attachments/assets/9efcc573-0ab9-4ead-95b2-0b90e7eba4aa" />


<img width="815" height="231" alt="image" src="https://github.com/user-attachments/assets/1edf222c-ce52-4eef-8c45-6d7f4344183b" />


<img width="819" height="587" alt="image" src="https://github.com/user-attachments/assets/6e0d763f-46c8-4728-ab72-bac3c3512bda" />







## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
