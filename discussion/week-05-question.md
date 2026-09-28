---
id: w05-owenp3-correlation-helps-knn-when
title: "When does correlation help KNN?"
author: "Owen Park (owenp3)"
---

In Homework 05, 5NN on 30 covariates went from a test MSE of 0.59 to 0.17 when the
covariates were given a common correlation of 0.8, while the lasso barely moved
(0.27 to 0.26). The usual story is that correlation is bad news, because it
makes coefficients unstable. Here it rescued a distance-based method, because
the 27 irrelevant coordinates collapsed onto the same shared factor as the three
relevant ones, so Euclidean distance stopped being dominated by noise.

My question is whether that is a general property or an artifact of this
particular covariance. Suppose instead that the relevant covariates were
correlated only among themselves and the irrelevant ones only among themselves,
or that the response depended on the difference $X_1 - X_2$ of two highly
correlated covariates. Would KNN still benefit? More broadly, is there a way to
read off from the covariance structure, before fitting anything, whether
Euclidean neighborhoods will be informative for a given response, or is the
honest answer that we have to try it and cross-validate?
