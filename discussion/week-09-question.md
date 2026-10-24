---
id: w09-owenp3-kernel-within-the-noise
title: "When the Best Kernel Is Within the Noise"
author: "Owen Park (owenp3)"
---

In Homework 09, I compared 19 SVM settings on `SAheart` using the same five
folds. A quadratic kernel had the lowest mean cross-validation error (0.262),
but three linear settings were within one standard error of it, and every
polynomial and radial kernel got worse as $C$ grew.

Why can a more flexible kernel win a cross-validation comparison without
being better on new data, and why does reusing the same folds for every
candidate make the winning error optimistic? Compare choosing the lowest mean
CV error with a one-standard-error rule that prefers the simplest kernel, and
say which kernel settings you would count as simpler. Propose how you would
check whether the chosen kernel is stable, for example by redrawing the folds
with another seed, and state what result would make you change your choice.
