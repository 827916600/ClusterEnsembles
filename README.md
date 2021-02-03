# ClusterEnsembles

A Python package for cluster ensembles. Cluster ensembles generate a single consensus cluster using base clusters obtained from multiple clustering algorithms. The consensus cluster stably achieves a high clustering performance. 

Installation
------------

```
pip install ClusterEnsembles
```

Usage
-----

```python
>>> import ClusterEnsembles as CE

>>> base_clusters = np.random.randint(0, 9, (10, 1000))

>>> celabel = CE.cluster_ensembles(base_clusters, nclass=10, solver='hbgf')
```

- `nclass`: Number of classes in a consensus cluster
- `solver`: {'mcla', 'hbgf'}
    
    `mcla`: Meta-CLustering Algorithm [1]
    
    `hbgf`: Hybrid Bipartite Graph Formulation [2]


TODO
----

- Bayesian cluster ensembles [3]

Similar Project
---------------

`GGiecold/Cluster_Ensembles`: https://github.com/GGiecold/Cluster_Ensembles

References
----------

[1] A. Strehl and J. Ghosh, 
"Cluster ensembles -- a knowledge reuse framework for combining multiple partitions,"
Journal of Machine Learning Research, vol. 3, pp. 583-617, 2002.

[2] X. Z. Fern and C. E. Brodley, 
"Solving cluster ensemble problems by bipartite graph partitioning,"
In Proceedings of the Twenty-First International Conference on Machine Learning, p. 36, 2004.

[3] J. Ghosh and A. Acharya, 
"Cluster ensembles," 
Wiley Interdisciplinary Reviews: Data Mining and Knowledge Discovery, vol. 1, no. 4, pp. 305-315, 2011. 
