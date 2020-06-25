# UnsupervisedLearning

## Clustering

- This is a type of unsupervised learning in which we try to cluster/form groups of unknown data points. Basically we want to find where one belongs if we have many groups. Application: focused marketing campaigns, create groups and then build predictive models on each group
- Just that when we use distance, if scales of a features are very different, then the higher scale feature will dominate the cluster [age vs salary] and thus we use standardization/normalization
- There are 2 types of this clustering algorithm → Flat (K means) and Hierarchical(Agglomerative and Divisive)
- **Hierarchical clustering**: as the name suggests forms an hierarchy/connection between different data points and merges them into one as per the similarity, there are 2 kinds of hierarchical clustering
    - Divisive (top down) → we start with one big all-encompasing point and keep dividing until it is not possible
    - Agglomerative (bottom up) → we start at the bottom and group data points which are similar until we have one big group that contains all the points
        1. We form a dendrogram which starts at the bottom and goes to the top and each point is joined based on the similarity, we choose distance [eucliden/manhattan] as a measure for the same 
        2. Advantage is that we can break the dendrogram at any point and find the number of clusters which gives a better understanding of the data, but the issue is that this method is computationally expensive and if there are huge number of data points, we cannot understand the dendrogram easily 
- Resources: [https://www.youtube.com/watch?v=ijUMKMC4f9I](https://www.youtube.com/watch?v=ijUMKMC4f9I) , [https://www.youtube.com/watch?v=0jPGHniVVNc&list=TLPQMjIwNjIwMjCx8SrVv100UQ&index=2](https://www.youtube.com/watch?v=0jPGHniVVNc&list=TLPQMjIwNjIwMjCx8SrVv100UQ&index=2)
- **K means clustering:** Select K [number of clusters] and the algorithm will classify all the datapoints into the mentioned number of clusters based on the distance - as simple as that.
    - Working of the algorithm is as follows:
        1. Select K i.e. number of clusters 
        2. Initialize K number of centroids randonly [just choosing]
        3. Find points nearer to each centroid using euclidean distance and form groups
        4. Find the mean of each point from the centroid and create a new centroid and repeat from step 2 until we get fixed number of groups/clusters 
    - We can choose the number of clusters using an elbow plot
    - The issue with K means is that:
        1. Before clustering we have to give the number of clusters 
        2. Sometimes there might be no clusters but the algo will still form if we mention it. 
        3. The algo is also susceptible to outliers. 
    - Resources: [https://www.youtube.com/watch?v=4b5d3muPQmA&list=TLPQMjIwNjIwMjD23RtChckTWw&index=2](https://www.youtube.com/watch?v=4b5d3muPQmA&list=TLPQMjIwNjIwMjD23RtChckTWw&index=2) , [https://www.youtube.com/watch?v=AWKCCK5YHsE&list=TLPQMjIwNjIwMjD23RtChckTWw&index=3](https://www.youtube.com/watch?v=AWKCCK5YHsE&list=TLPQMjIwNjIwMjD23RtChckTWw&index=3)
- **DBSCAN [Density based Spatial clustering of application with noise]:** This takes 2 values epsilon and min points, epsilon stands for neighbourhood size and min points is the number of points that needs to be present in a neighbourhood to consider itself as cluster, the points that are not assigned at the end of it are outliers
    - Epsilon is the size parameter i.e. it will be considered when we want to have a big neighbourhood or a small one for a specific point. Epsilon can also be considered while deciding the number of groups, if high, the size will be high and the number of groups will be lower. If low, the size will be low and the number of grps will be high.
    - Min points is the quantity that will make a point active or inactive i.e. if we keep high min points, a particular circle/neighbourhood will have to have high number of points to be active and if we keep low min point value, any circle that has very less number of points in the neighbourhood can become active, this one will have direct impact on checking if specific point is extreme/outlier or not.
    - This removes the main issue of outliers and the fact that we do not have to give the number of clusters
