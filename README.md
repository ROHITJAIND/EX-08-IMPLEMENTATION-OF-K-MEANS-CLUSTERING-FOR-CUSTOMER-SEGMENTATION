# EX-08 Implementation of K Means Clustering for Customer Segmentation
### AIM:
To write a program to implement the K Means Clustering for Customer Segmentation. &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**DATE:**
### Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook
### Algorithm:
1. Import pandas and matplotlib.pyplot.
2. Read the dataset and transform it.
3. Import KMeans and fit the data in the model.
4. Plot the Cluster graph.
### Program:
```Python
import pandas as pd                      
import matplotlib.pyplot as plt          
data = pd.read_csv("CSVs/Mall_Customers.csv")
data.head()
data.info() 
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster. 
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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="clusterl")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
```
Developed By: ROHIT JAIN D
Register No : 212222230120
```

### Output:
**df.head()** &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; **df.info()**<br>
<img height=% width=% valign=top src="https://github.com/ROHITJAIND/EX-08-IMPLEMENTATION-OF-K-MEANS-CLUSTERING-FOR-CUSTOMER-SEGMENTATION/assets/118707073/b02fa2bc-c801-479a-93c2-d615d3c97713">
<img height=% width=% valign=top src="https://github.com/ROHITJAIND/EX-08-IMPLEMENTATION-OF-K-MEANS-CLUSTERING-FOR-CUSTOMER-SEGMENTATION/assets/118707073/22f91f45-06a5-4383-8411-c14d3ef79745">

<br>

**df.isnull().sum()** &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; **K-Means Cluster**<br>
<img height=% width=% valign=top src="https://github.com/ROHITJAIND/EX-08-IMPLEMENTATION-OF-K-MEANS-CLUSTERING-FOR-CUSTOMER-SEGMENTATION/assets/118707073/1b72a67d-5db8-43a3-8435-acf9e8a52e46">
<img height=% width=% valign=top src="https://github.com/ROHITJAIND/EX-08-IMPLEMENTATION-OF-K-MEANS-CLUSTERING-FOR-CUSTOMER-SEGMENTATION/assets/118707073/3b9e45dd-493f-40ee-a8ab-7a6384bc24f3">

<br>

**Elbow Method Graph** &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; **Customer Segments Graph**<br>
<img height=% width=% valign=top src="https://github.com/ROHITJAIND/EX-08-IMPLEMENTATION-OF-K-MEANS-CLUSTERING-FOR-CUSTOMER-SEGMENTATION/assets/118707073/b0d61645-43ef-46fb-9245-d08003c265cb">
<img height=% width=% valign=top src="https://github.com/ROHITJAIND/EX-08-IMPLEMENTATION-OF-K-MEANS-CLUSTERING-FOR-CUSTOMER-SEGMENTATION/assets/118707073/d6df2f05-ae51-466c-881e-0809be83f58a">



### Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
