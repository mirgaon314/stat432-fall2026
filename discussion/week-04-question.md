---
id: w04-owenp3-elastic-net-noise-tradeoff
title: "Elastic net keeps the pair, but at what price?"
author: "Owen Park (owenp3)"
---

In Homework 04 the lasso split the two 0.999-correlated covariates almost
perfectly: at $\lambda = 0.12$ it kept exactly one of them 95% of the time and
both only 2%. Switching to an elastic net with an equal mix fixed that, both were
kept together in about 95% of the runs, but the same change pushed the noise
covariates' selection rate from 19% to 50%. Even at the largest penalty on the
grid, one in five pure-noise variables still got in.

So the elastic net bought "keep correlated partners together" with "let in more
junk," and the assignment's fixed grid never reached a penalty where both goals
were met at once. My question is whether that trade is fundamental or an artifact
of comparing at the same numerical $\lambda$. If we retuned the elastic net so its
$\ell_1$ threshold matched the lasso's ($\lambda \cdot \alpha$ equal), would the
pair still stay together? And in a real problem where we do not know which
variables are correlated partners and which are noise, what would we cross-validate
to decide how much of this trade to accept?
