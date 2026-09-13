---
id: w03-owenp3-one-se-rule-overshrinks
title: "When the one-SE rule shrinks too much"
author: "Owen Park (owenp3)"
---

In Homework 03 the ten-fold CV curve for the real-estate data was almost flat
near its minimum, and the fold-to-fold standard error was large: about 19 on a
minimum MSE of about 83. Because of that, the one-standard-error rule picked a
penalty nearly eighty times larger than lambda_min, cut the effective degrees of
freedom from about 6.8 to 3, and raised test MSE by roughly a fifth. GCV, by
contrast, landed almost exactly on lambda_min.

The one-SE rule is usually sold as a safe, conservative default. Here it was the
only choice that clearly hurt. Is the problem the rule itself, or the fact that
SE was estimated from ten folds of thirty-three noisy house prices each? What
signal in the CV output, before looking at any test data, should tell me to
trust lambda_min over lambda_1se, and is there a principled way to set the
size of the tolerance instead of always using one SE?
