---
id: w12-owenp3-labels-disagree-with-clusters
title: "When the Labels Disagree With the Clusters"
author: "Owen Park (owenp3)"
---

In Homework 12, my clustering skill tried K-means, hierarchical and spectral
clustering on 38 leukemia samples. Eight candidates were within 0.01 of the
best silhouette (0.273), so the choice came down to subsample stability, where
spectral clustering with three clusters (0.912) beat a four-cluster setting
(0.903). The three clusters matched the known ALL/AML labels with an adjusted
Rand index of only 0.508, because the 27 ALL samples split mainly into groups
of 18 and 8 while the AML samples stayed together.

Why can a clustering that disagrees with the known labels still be a
reasonable answer, and why would using those labels to choose the number of
clusters defeat the purpose of unsupervised learning? Compare silhouette and
subsample stability as selection criteria when the candidates are this close.
Propose what you would report when the winner depends on a tie-break, and say
what evidence would convince you that the split inside ALL is real structure
rather than noise.
