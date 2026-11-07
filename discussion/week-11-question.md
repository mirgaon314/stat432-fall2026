---
id: w11-owenp3-same-data-different-clusters
title: "Same Data, Different Clusters"
author: "Owen Park (owenp3)"
---

In Homework 11, I ran my own K-means on 10 points from two random starting
assignments. Both runs converged in 2 iterations, but one ended at a
within-cluster sum of squares of 8.251 and the other at 8.297, and the two
partitions differed by a single point that sat between the groups. On the
cars data, complete linkage gave three readable groups while single linkage
chained almost every car into one cluster.

Why can an algorithm that never increases its objective still stop at
different answers, and why does the linkage rule change the tree this much on
the same distances? Propose a procedure for reporting a clustering result,
including how many random starts or which linkages to try, and say what
evidence would convince you that a cluster reflects real structure rather than
the starting point or the linkage choice.
