# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Compute the distance matrix between all data points. 
2.Identify the two closest cluster and merge them. 
3. Update the distance matrix to reflect the new cluster. 
4. Repeat steps 2 and 3 until only one cluster remains.

## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: Sree Viveka V.S
RegisterNumber: 2305001031
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage, fcluster # Changed 'dendogram' to 'dendrogram'
from sklearn.preprocessing import StandardScaler

df=pd.read_csv('/content/Hclus_EX8.csv')
df.head()

X=df[['StudentID','Marks']].values
X

#Perform hierarchical clustering (agglomerative)
Z=linkage(X, method='complete')

#Plot dendogram
plt.figure(figsize=(5,2))
plt.title("Dendogram for Student Segmentation")
labels=range(1,len(df)+1)
dendrogram(Z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()

#Cut the dendrogram to form clusters(let's say we want 5 clusters)
max_clusters=2
clusters=fcluster(Z,max_clusters,criterion='maxclust')
clusters

#Scatter plot with different colors for each cluster
plt.figure(figsize=(5,2))
plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented (Hierarchical Clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()

Z=linkage(X, method='single')

#Plot dendogram
plt.figure(figsize=(5,2))
plt.title("Dendogram for Student Segmentation")
labels=range(1,len(df)+1)
dendrogram(Z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()

#Cut the dendrogram to form clusters(let's say we want 5 clusters)
max_clusters=2
clusters=fcluster(Z,max_clusters,criterion='maxclust')
clusters

#Scatter plot with different colors for each cluster
plt.figure(figsize=(5,2))
plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented (Hierarchical Clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
```

## Output:
![WhatsApp Image 2024-10-17 at 14 11 27_870f4629](https://github.com/user-attachments/assets/9be095ea-3d86-43b4-a33c-070eaaa737cc)
![WhatsApp Image 2024-10-17 at 14 11 37_b6cfd4a2](https://github.com/user-attachments/assets/42f7f058-6a84-4428-bea9-20d406306d9b)
![WhatsApp Image 2024-10-17 at 14 11 46_a138d3d6](https://github.com/user-attachments/assets/f1c9a0a7-cf1f-4129-8141-3182d61d0f03)
![WhatsApp Image 2024-10-17 at 14 11 56_ed449b69](https://github.com/user-attachments/assets/702f50cb-d12c-4f4f-93bc-43dccf0c0ce0)
![WhatsApp Image 2024-10-17 at 14 12 07_72fbbf84](https://github.com/user-attachments/assets/a667cb40-3ee6-4de0-87c4-e9b100626993)
![WhatsApp Image 2024-10-17 at 14 12 32_359ec7c0](https://github.com/user-attachments/assets/71f339c2-df09-42cd-ac33-61cfdab737e9)
![WhatsApp Image 2024-10-17 at 14 12 40_61f26529](https://github.com/user-attachments/assets/2791cd13-5272-46aa-a9f0-ff412ac8b9c0)
![WhatsApp Image 2024-10-17 at 14 12 50_132d2316](https://github.com/user-attachments/assets/9411d397-8f77-4eb5-9513-5ba5c9c3b59d)
![WhatsApp Image 2024-10-17 at 14 12 59_9da3dbea](https://github.com/user-attachments/assets/74bbc7ac-67ae-4c1d-a7eb-d4d1054c42f0)

## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
