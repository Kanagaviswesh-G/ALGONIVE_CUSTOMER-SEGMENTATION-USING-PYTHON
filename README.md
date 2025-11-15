Task_1 - Algonive_Customer segmentation using python

https://colab.research.google.com/drive/1uB-28MnhdoOIk8yGe6BlPNwpKqk_KilS?usp=sharing\

# Customer Segmentation Analysis

This notebook performs customer segmentation using the RFM (Recency, Frequency, Monetary) model and K-Means clustering.

## Project Overview
The goal of this project is to segment customers based on their purchasing behavior from an online retail dataset. This can help businesses understand their customer base better and tailor marketing strategies.

## Steps Performed:

1.  **Load Data**: Loaded the 'Online Retail.xlsx' dataset.
2.  **Data Cleaning**: 
    - Dropped rows with missing `CustomerID`.
    - Converted `CustomerID` to integer type.
    - Removed cancelled invoices (InvoiceNo starting with 'C').
    - Filtered out rows with non-positive `Quantity` or `UnitPrice`.
    - Converted `InvoiceDate` to datetime objects.
    - Calculated `TotalPrice` for each transaction.
3.  **Exploratory Data Analysis (EDA)**:
    - Analyzed transactions by country, showing the top 10 countries.
    - Visualized the distribution of `Quantity`.
    - Visualized the log-transformed distribution of `TotalPrice`.
4.  **Feature Engineering (RFM)**:
    - Calculated `Recency` (days since last purchase), `Frequency` (number of unique purchases), and `Monetary` (total spend) for each customer.
    - Applied log transformation to `Monetary` and `Frequency` for better distribution and clustering performance.
    - Scaled the RFM features using `StandardScaler`.
5.  **Elbow Method**: Used the elbow method to determine the optimal number of clusters for K-Means.
6.  **K-Means Clustering**: 
    - Applied K-Means clustering with k=4 (based on elbow method).
    - Assigned cluster labels to each customer.
    - Generated a summary of each cluster's average Recency, Frequency, Monetary, and customer count.
7.  **PCA Visualization**: Reduced the dimensionality of the scaled RFM features to 2 principal components (PC1, PC2) for visualization.
    - Plotted customer segments in a 2D scatter plot using PC1 and PC2, colored by cluster.
8.  **Save Output**: Saved the final customer segments (including RFM features, log-transformed features, cluster assignments, and PCA components) to 'Customer_Segments_Final.csv'.

## Cluster Summary:
```
         Recency  Frequency  Monetary  Count
Cluster                                     
0          58.11       1.52    387.13   1379
1          45.94       4.22   1654.59   1453
2         259.41       1.37    386.83    938
3          19.75      15.89   9877.79    568
```

This summary shows that Cluster 3 represents the most valuable customers (high frequency, high monetary, low recency), while Cluster 2 represents dormant customers (high recency, low frequency, low monetary).
<img width="1134" height="738" alt="image" src="https://github.com/user-attachments/assets/27c1e8e3-368e-43c3-803b-dcb6da2eff29" />
<img width="697" height="564" alt="image" src="https://github.com/user-attachments/assets/25949fc4-8eea-441f-8657-4efeec51ff8d" />
<img width="699" height="567" alt="image" src="https://github.com/user-attachments/assets/f556539f-5c4e-4aad-b48b-e811c5bcf4c6" />

***Final principal component analysis visualization***

<img width="749" height="793" alt="image" src="https://github.com/user-attachments/assets/eb724809-1d35-4a6a-ab22-5cbf07faa805" />


