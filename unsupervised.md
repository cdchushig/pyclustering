One method to validate the number of clusters is the **elbow method**.
The idea of **elbow method** is to run k-means clustering on the dataset
for a range of values o **k** and for each value of **k** calculate the sum
of squared errors (SSE). Like this.

```javascript
var sse = {};
for (var k = 1; k <= maxK; ++k) {
    sse[k] = 0;
    clusters = kmeans(dataset, k);
    clusters.forEach(function(cluster) {
        mean = clusterMean(cluster);
        cluster.forEach(function(datapoint) {
            sse[k] += Math.pow(datapoint - mean, 2);
        });
    });
}
```
