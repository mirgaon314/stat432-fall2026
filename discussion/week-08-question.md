---
id: w08-owenp3-inside-the-margin
title: "Inside the Margin but Still Correct"
author: "Owen Park (owenp3)"
---

In Homework 08, the fixed rule $f(x)=0.8x_1+0.6x_2$ left six of twenty
observations inside the margin, but only two of them were on the wrong side
of the boundary. The other four were classified correctly and still had a
functional margin $y_if(x_i)$ below 1.

Why does a soft-margin SVM charge a slack penalty to those four correctly
classified points at all, and how does that make its loss different from
simply counting misclassifications? Suppose the cost parameter $C$ is made
very large, then very small. Describe what happens to the width of the margin
and to the number of support vectors in each case, and explain which setting
risks overfitting and which risks underfitting. Propose how you would choose
$C$ with cross-validation, and say what you would report so that a reader
could tell whether the selected boundary depends on a handful of points.
