# outlier_detection
> **what is an Outlier ?**

An outlier is a data point that significantly differs from other observations in a dataset. 🧐
Think of it like a single bright red apple in a basket full of green apples. This red apple stands out because it's distinctly different from the rest.
Outliers can occur for various reasons:
1. Measurement errors: The measuring instrument might have been faulty.
2. Data entry errors: Typos can happen when data is manually entered.
3. Experimental errors: Mistakes during an experiment can lead to unusual readings.
4. Novelty or genuine rare events: Sometimes, an outlier represents a truly unusual and valid occurrence in the data. For example, a very high daily sales figure might be due to a legitimate, unexpected surge in demand.
It's important to identify outliers because they can skew statistical analyses and machine learning models, leading to misleading conclusions or poor performance. Depending on the cause and the goal of the analysis, outliers might be removed, corrected (if possible), or investigated further.

> **What are the ways to remove them and prevent skewness ?**
Outliers are often a primary cause of skewness in a dataset. Skewness refers to the asymmetry in a statistical distribution. Extreme values (outliers) on one side of the distribution can pull the mean in that direction, creating a skewed distribution. Therefore, addressing outliers is often a direct way to mitigate skewness.
**Methods:**
1. Z-Score: Data points falling outside a certain number of standard deviations (e.g., +/- 3) from the mean are considered outliers and removed. This method assumes a somewhat normal distribution.
2. Interquartile Range (IQR): This is a more robust method for non-normally distributed data. Outliers are identified as data points falling below Q1−1.5×IQR or above Q3+1.5×IQR, where Q1 is the first quartile and Q3 is the third quartile.
3. K-Means clustering: aims to partition n observations into k clusters in which each observation belongs to the cluster with the nearest mean (cluster centroid).
   Distance-based: After clusters are formed, calculate the distance of each point to its cluster centroid. Points that are very far from their centroid can be considered outliers. A threshold for this distance 
       would need to be defined (e.g., based on a multiple of the standard deviation of distances within the cluster or a percentile).
   Cluster size: If a cluster has a very small number of points compared to others, the points in that tiny cluster might be outliers, especially if the cluster is also distant from others.
   Removal: Once potential outliers are identified based on distance or small cluster size, they can be filtered out.
