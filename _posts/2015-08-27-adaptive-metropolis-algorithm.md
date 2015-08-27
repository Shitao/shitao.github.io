---
layout: post
title: Adptive Metropolis Algorithm
tags: [Monte-Carlo,Metropolis]
---

>Adaptive Metropolis (AM) Algorithm aims to efficiently sample a high dimensional
>complex probability distribution. The propose of this post is to document what I
>learn from this Algorithm.

Most of the notations and concepts here are following Haario et al. 2001.

### Metropolis Algorithm 

Metropolis algorithm was named one of the top 10 most influential algorithms of the
20th century, at least by the editors of CiSE (Computing in Science and
Engineering).

Goal: Sample from a high dimensional and complicated distribution. 

Reason: In high dimensions, our intuition for volume breaks down. For example, a
proposal distribution in high dimensions that may seems to be a good one can
fail because it may put a lot probability mass in the low dimension part.

MCMC: The algorithm trys to move to a region of high probability and then trys
to stay near the high probability region.

### Algorithm

At time $t-1$, we have sampled the states $X_0,X_1,\ldot,X_{t-1}$. A candidate
point $Y$ is sampled from a proposal distribution
$q_t(\cdot|X_0,\ldot,X_{t-1})$.
The accept criteria for Y is as follows:
$$\alpha(X_{t-1},Y)=min(1,\frac{\pi(Y)}{\pi(X_{t-1})})$$
in which case we set $X_t=Y$, and otherwise $X_t = X{t-1}$

## Adaptive Metropolis

The basic idea is to update the proposal distribution by using the knowledge we
have so far or how the covariance of the proposal distribution depends on the
history of the clain.

### Algorithm


### Reference

Haario, H., E. Saksman, and J. Tamminen, 2001: An adaptive metropolis algorithm.
Bernoulli, 7, 223–242. [Available online at http://www.jstor.org/stable/3318737.]