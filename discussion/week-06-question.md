---
id: w06-owenp3-roc-when-ranking-is-not-enough
title: "When is a high AUC not the model you want?"
author: "Owen Park (owenp3)"
---

In Homework 06, logistic regression and 45-nearest-neighbors had test AUCs of
0.9746 and 0.9741 on the same 171 breast-cancer cases, so by AUC they are
interchangeable. But AUC only scores the ranking of the test cases. It says
nothing about whether the probability 0.3 means 30 percent, and nothing about
the one cutoff a clinic would actually use, where a missed malignancy and a
false alarm have very different costs.

Suppose two models have the same ROC curve but one reports probabilities that
are systematically too confident. In what decisions would that matter and in
what decisions would it not? Propose a procedure, using only the training data,
for choosing between the two models when the real goal is a single decision
threshold with a required sensitivity of at least 0.95. Which quantities would
you estimate, how would you estimate them without reusing the test set, and
how would you report the uncertainty of the final choice?
