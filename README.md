# ClusterEnsembles

[![CircleCI](https://circleci.com/gh/tsano430/ClusterEnsembles.svg?style=shield)](https://app.circleci.com/pipelines/github/tsano430/ClusterEnsembles)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A Python package for cluster ensembles. Cluster ensembles generate a single consensus cluster using base clusters obtained from multiple clustering algorithms. The consensus cluster stably achieves a high clustering performance. 

Installation
------------

```
pip install ClusterEnsembles
```

Usage
-----

```python
>>> import numpy as np

>>> import ClusterEnsembles as CE 

>>> base_cluster1 = np.array([1, 1, 1, 2, 2, 3, 3])

>>> base_cluster2 = np.array([2, 2, 2, 3, 3, 1, 1])

>>> base_cluster3 = np.array([4, 4, 2, 2, 3, 3, 3])

>>> base_cluster4 = np.array([1, 2, np.nan, 1, 2, np.nan, np.nan]) # `np.nan`: missing value

>>> base_clusters = np.array([base_cluster1, base_cluster2, base_cluster3, base_cluster4])

>>> celabel = CE.cluster_ensembles(base_clusters, nclass=3, solver='hbgf')

>>> print(celabel)
[0 0 0 2 2 1 1]
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
