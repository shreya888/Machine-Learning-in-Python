# K-means Clustering
[K-means clustering](https://stanford.edu/~cpiech/cs221/handouts/kmeans.html) is an unsupervised learning algorithm, which aims to group the unlabelled observations into specified (k) number of similar clusters. 
It is a hierarchical agglomerative clustering algorithm. 
It iteratively tries to find local optimum clusters defined using centroids or exemplars.
After each step, the distance of each cluster point from its cluster centre is revaluated.

This code uses NumPy Python Library and implements the EM algorithm.

## Important points to remember
  * Different **initialization of cluster centres** can change the resulting clusters as this method finds locally optimal solutions. It does not guarantee a globally optimal solution.
  Hence choosing correct initial centroids is very critical as good initialization will lead to a more optimal clustering. 
  * Choosing the correct **value of K** is very important. It can be achieved using the elbow method.
  The [elbow method](https://www.scikit-yb.org/en/latest/api/cluster/elbow.html) runs k-means clustering on the dataset for a range of values for k (say from 1-10) and then for each value of k computes an average score for all clusters.
  Some sort of scoring method is employed to visualize and determine the best value for k.
  If the line chart looks like an arm, then the “elbow” (the point of inflection on the curve) is the best value of k. The “arm” can be either up or down, but if there is a strong inflection point, it is a good indication that the underlying model fits best at that point.

## EM (Expectation Maximization) algorithm
The model parameters are randomly initialized in EM. Then the algorithm iterates over **E-step** - assigning values to hidden variables based on parameters and **M-step** - computing parameters based on fully observed data, until convergence.
  * **E-Step: Coming up with values to hidden variables**, based on parameters. If you work out the math of choosing the best values for the class variable based on the features of a given piece of data in your data set, it comes out to "for each data-point, chose the centroid that it is closest to, by euclidean distance, and assign that centroid's label." The proof of this is within your grasp! See lecture.
  * **M-Step: Coming up with parameters, based on full assignments**. If you work out the math of choosing the best parameter values based on the features of a given piece of data in your data set, it comes out to "take the mean of all the data-points that were labelled as c."
