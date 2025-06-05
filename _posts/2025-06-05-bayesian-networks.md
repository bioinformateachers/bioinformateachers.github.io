---
layout: post
title: "Bayesian Networks: a super-elementary overview"
author: "Filippo Biscarini"
date: "2025-06-05"
categories: STATISTICS BAYES GRAPHS
---

## Brief theoretical background

**Bayesian Networks** are described by: 

1. a **DAG** (directed acyclic graph) $$G = (V,A)$$, with nodes $$v_i \in V$$ that represent random variables $$X_i$$
2. a **probability distribution**

The objective of a Bayesian Network is to calculate conditional probabilities between variables:

$$
P(X) = \pi_{i=1}^N P(X_i | \pi_{X_i}; \Theta_{X_i})
$$


| predictions | Observed 1 | Observed 0 |
|:------------|:-----------|:-----------|
| 1           | TP         | FP         |
| 0           | FN         | TN         |

$$
\phi = \frac{(TP \cdot TN - FB \cdot FN)}{\sqrt{(TP+FP) \cdot (TP+FN) \cdot (TN+FP) \cdot (TN+FN)}}
$$

- $$ \mathbb{E}(y\hat{y}) = \frac{TP}{N} $$ (where $$N$$ is the sample size): this comes from TP being the intersection between $$y=1$$ and $$\hat{y}=1$$
- $$ \mathbb{E}(y) = \frac{TP+FN}{N} $$: this is the fraction of all "positive" observations ($$y=1$$)
- $$ \mathbb{E}(\hat{y)} = \frac{TP+FP}{N} $$: this is the fraction of all "positive" predictions ($$\hat{y}=1$$)

Therefore:

$$
Cov(y,\hat{y}) = TP \cdot N - (TP+FN) \cdot (TP+FP)
$$


#### Numerical proof of equivalence

We generate two random vectors of 0s and 1s: observed and predicted binary classes.

```r
set.seed(123)
y = sample(x = 0:1, size = 20, replace = TRUE)
y_hat = sample(x = 0:1, size = 20, replace = TRUE)
```

1. first, we load the `R` library `mltools`, which includes a function to calculate MCC
2. we prepare the **confusion matrix** from the vectors of observed and predicted classes
3. finally, we use the `mcc()` function to calculate the MCC



### Related topics

MCC is one of many metrics that can be used to evaluate the performance of binary classification models when the data are imbalanced. 
Examples include ROC-AUC and Cohen's kappa, which may be the topics of future posts.
Also, the extension of MCC --and related metrics-- to multi-class classification problems is possible, and will be treated in future posts.


