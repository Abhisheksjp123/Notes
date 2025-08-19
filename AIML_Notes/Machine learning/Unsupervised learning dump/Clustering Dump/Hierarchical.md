1. Starts with each data point as its own cluster 
2. Merges the closest clusters iteratively. 
3. Stops when all data points are in one cluster or a stopping condition is met
![[638856174834642899.png]]
	
Hierarchical clustering is usually accompanied by a "dendrogram" 
It indicates both the similarity and the order that the clusters were formed
Cluster #1 was formed first and is most similar. It has the shortest branch

But how do we determine the similarity ? each color has its value (based on Color scale) , we Calculate the distance b/w 2 genes based on Euclidian distance
![[638856175099896279.png]]

also,
Do you remember how we merged genes #1 an #3 into cluster #1 and compared it to other genes? Well, there are different ways to compare clusters, too. One simple idea is to use the average of the measurements from each sample. 
But there are lots more.
![[638856175467225060.png]]

[[Hierarchical Code and hyper parameter]]
