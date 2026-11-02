---
id: w10-owenp3-mtry-one-wins
title: "When mtry = 1 Wins"
author: "Owen Park (owenp3)"
---

In Homework 10, I tuned a random forest on the first 20 principal components
of MNIST digits 1, 6 and 7. The OOB error was lowest at `mtry = 1` (2.14%) and
rose to about 5% at `mtry = 20`, while the default `mtry = 10` gave 4.28%. In
the bias-variance simulation from the same homework, `mtry = 1` was the worst
setting because two of the five predictors were pure noise.

Why can the same tuning parameter be best in one problem and worst in another?
Compare how uncorrelated principal components and correlated raw predictors
with a few noise variables change the trade-off between stronger single splits
and less correlated trees. Propose a rule for choosing the `mtry` grid before
looking at the OOB errors, and say what result would make you distrust an OOB
winner that differs from the next setting by only one or two observations.
