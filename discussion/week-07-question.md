---
id: w07-owenp3-screening-without-labels
title: "Screening Predictors Without Looking at the Labels"
author: "Owen Park (owenp3)"
---

In Homework 07, keeping the 40 pixels with the largest marginal variance let
QDA run on the zip digits at all, with a test error near 16 percent, while the
10 highest-variance pixels gave 34 percent. The screening rule never used the
digit labels, so it cannot leak the test labels into the fit, but it also has
no reason to keep the pixels that actually separate the classes.

Suppose you replace it with a supervised screen, for example ranking pixels
by a between-class F statistic computed on the training set. Why does that
rule have to be recomputed inside every cross-validation fold rather than once
on the full training data, and what goes wrong with the estimated error if it
is not? Compare the two screens on bias and variance: which one risks keeping
useless predictors, and which one risks an optimistic error estimate? Propose
a procedure for choosing the number of screened predictors for QDA that keeps
every class covariance invertible, and state what you would report so that a
reader could check that no label information reached the screening step from
outside the training folds.
