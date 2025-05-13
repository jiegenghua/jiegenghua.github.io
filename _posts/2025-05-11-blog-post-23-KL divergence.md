---
title: 'KL-divergence, Wassersten distance, cross entropy'
date: 2025-05-11
permalink: /posts/2025/05/blog-post-23/
tags:
  - ML
  - Metrics
  - Probability
---

In the optimal transport class, I learned a new conception called Wasserstein distance, which is used as metric in probability space.
It then reminds me of some other metrics in the probability space and I think it is necessary to understand the difference between them.

## KL-Divergence
**KL-Divergence (Relative entropy)** is the measure of the relative difference between two probability distributions for a given random variable.
In discrete case, the relative entropy from $Q$ to $P$ is defined as:
```math
D_{KL}(P||Q)=\sum_{x\in \mathcal{X}} P(x)\log \frac{P(x)}{Q(x)}
```
In continuous case, it is defined as
```math
D_{KL}(P||Q) = \int_{-\infty}^{\infty} p(x)\log \frac{p(x)}{q(x)}dx
```

**Properties**:
- It is not symmetric and does not satisfy the triangle inequality.
- It is always a non-negative real number, with value 0 iff the two distributions are identical.

In applications, $P$ represents the ''true'' distribution of data, observations, or a precisely calculate theoretical distributed, while $Q$ represents a theory, model, description, or an approximation of $P$.
One can minimize the KL divergence in order to find a distribution $Q$ that is closest to $P$.

**Applications**
- Variational auto encoder
- Generative Adversarial Networks (GAN)


## Cross entropy
**Cross entropy** is a measure of the difference between two probability distributions, saying, $p$, $q$, for a given random variable.




## Wasserstein distance
**Wasserstein distance** is a distance function defined between probability distributions on a given metric space $M$. It is also known as the earth mover's distance.
**Definition**: Let $(M,d)$ be a metric space that is a Polish space. For $p\in [1, \infty]$, the Wasserstein $p
$ distance between two probability measures $\mu$
 and $\nu$ with finite $p$-moments is
 ```math
W_p(\mu, \nu) = \inf_{\pi \in \Pi(\mu, \nu)}(\mathbb{E}_{(x,y)\sim \pi} d(x,y)^p)^{\frac{1}{p}}
 ```
 where $\Pi(\mu, \nu)$ is the set of all couplings of $\mu$ and $\nu$.
 When $p=2$, $W_2$; when $p=\infty$, $W_{\infty}$. 
 If you observe carefully, you will find that this definition is quite similar to the Eucledian distance defined in Eucledaian space.

**$W_2$ between Normal distributions**

**Applications in machine learning**


**Difference between KL-Divergence and Wasserstein distance**
Wasserstein is a metric, and thus it has all of the properties a metric should have, for example, symmetric.


## Examples
Here, I will provide one example to show their difference.
Fig.





## Reference
- [1] https://en.wikipedia.org/wiki/Kullback%E2%80%93Leibler_divergence
- [2] https://en.wikipedia.org/wiki/Wasserstein_metric
- [3] https://stats.stackexchange.com/questions/295617/what-is-the-advantages-of-wasserstein-metric-compared-to-kullback-leibler-diverg
- [4] https://www.reddit.com/r/MachineLearning/comments/fftpfh/d_in_what_situation_would_one_rather_use/
- [5] https://openreview.net/forum?id=1qfdCAXn6K&referrer=%5Bthe%20profile%20of%20Peihua%20Li%5D(%2Fprofile%3Fid%3D~Peihua_Li1)
- [6] https://arxiv.org/abs/1908.09211
- [7]


















