# Credit-Card-Clustering
This project applies unsupervised learning to segment credit card customers based on their spending and payment behavior. Using clustering algorithms like K-Means and Agglomerative Clustering, the goal is to identify groups of customers with similar financial activity patterns to help with customer segmentation, marketing, and risk analysis.

# Dataset

File: CC GENERAL.csv

Shape: (8,950 rows × 18 columns)

https://www.kaggle.com/datasets/arjunbhasin2013/ccdata

Steps Performed

A. Data Preprocessing

Loaded dataset with pandas.read_csv.

Dropped / imputed missing values.

Scaled all numeric features using StandardScaler to normalize data for clustering.

Created derived features like ratios.

B. Dimensionality Reduction

Applied PCA to project high-dimensional data to 2D for visualization.

Used t-SNE for a more non-linear view of clusters.

C. Clustering Algorithms

K-Means Clustering (optimal K determined with Silhouette Score / Davies-Bouldin).

Agglomerative Hierarchical Clustering.

(Can be extended to DBSCAN / Gaussian Mixture Models).

D. Evaluation Metrics

Because clustering is unsupervised:

Silhouette Score – Higher is better (compact & well-separated clusters).

Davies-Bouldin Index – Lower is better (less intra-cluster variance).

| Algorithm         | Silhouette Score | Davies-Bouldin Index |
| ----------------- | ---------------- | -------------------- |
| **K-Means**       | 0.2067           | 1.6594               |
| **Agglomerative** | 0.1674           | 1.8496               |

E. Visualization

Plotted clusters in PCA 2D and t-SNE 2D space.

Plotted cluster sizes.

Profiled each cluster by average feature values.


# Cluster Profiles (Average Feature Values)

| Cluster | Balance  | Purchases | Cash Advance | Credit Limit | Payments | Tenure |
| ------- | -------- | --------- | ------------ | ------------ | -------- | ------ |
| **0**   | 4,540.78 | 577.33    | 4,506.32     | 7,458.28     | 3,581.20 | 11.39  |
| **1**   | 942.29   | 302.35    | 529.76       | 3,221.34     | 927.73   | 11.39  |
| **2**   | 1,289.08 | 2,185.67  | 235.27       | 5,165.47     | 2,168.60 | 11.74  |


# Insights

Cluster 0: High balances, high cash advances, low purchases → Possibly high-risk customers.

Cluster 1: Low balance, low usage → Inactive or new customers.

Cluster 2: Moderate balance, high purchases, low cash advance → Likely “good” customers using credit card primarily for purchases.

This segmentation can be used for targeted marketing or credit limit decisions.
