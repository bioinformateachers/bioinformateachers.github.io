---
layout: post
title: "Naive Bayes classifier – a naive introduction (with R)"
author: "Filippo Biscarini"
date: "2022-06-22"
categories: STATISTICS CLASSIFICATION BAYES R
---

[**Supervised** (non-linear) **classification method**]

Naive Bayes is a probabilistic classifier based on i) **Bayes' theorem** and 
ii) a strong ("**Naive**") **assumption** on the **independence of all $$p$$ features** (variables) within each class.

### Naive Bayes: the gist of it

- resource efficient & fast
- scales well
- works well when the number of samples $$n$$ is small relative to the number of features $$p$$

From Bayes' theorem, our objective is to estimate the posterior (conditional) probability for an observation of belonging to class *k* 
given its predictor variables: $$ P(Y=k | X) $$. 
A bit of nomenclature:

- observations: our records (e.g. individual subjects)
- class *k*: the class to which each observation belongs (e.g. case/control)
- (predictor) variables: "things" that have been measured on our observations (e.g. blood parameters)
- prior: initial probability of belonging to class *k*

> **posterior = (prior * likelihood) / evidence**

We therefore need:

- estimates of the priors $$p_k$$ for each class (e.g. **relative frequencies** of the *k* classes in the training data)
- estimates of the **likelihood** $$f_k(x)$$ (probability of the data for each class *k*)
- evidence: **sum of the probability of the data** (likelihood) **over all classes** (total probability of the data)

Under the naive assumption of independence of the predictor variables within classes, we non longer need to calculate complex joint probability distributions of the *p* variables, 
and the likelihood of the data for each class is given by the product of the densities of each of the *p* predictors in that class:

$$
f_k(x) = f_{k1}(x_1) \cdot f_{k2}(x_2) \cdot\ldots f_{kp}(x_p)
$$

Mind you that these are the densities for individual variables in each class, i.e. the sub-components of the likelihood 
(and of the evidence when summed over the *k* classes). 
These sub-components (**predictor variable densities per class**) are the **key ingredients** of the **Naive Bayes classifier**, 
and can be estimated in a number of ways:

- from **univariate normal distributions**: $$ x_p | k \sim N(mean(x_{pk}), var(x_{pk})) $$
- non parametrically, as the fraction of the training observations in the $$ k_{th} $$ class that belong to the same **histogram bin** for the different values (ranges) of $$x_p$$
- using a **kernel density estimator** (a smoothed version of the above histogram)
- if $$x_p$$ is qualitative, from the relative frequencies of observations in class *k* having the different values of $$x_p$$ (e.g. proportions of males and females in the class)

The assumption of Naive Bayes is clearly far from true, but provides a good approximation, 
especially when *n* is not large enough relative to *p* to provide effective estimates of $$f_k(x)$$.

By simplifying the problem, **Naive Bayes** introduces some *bias* but **reduces the variance** of the classifier.
We expect to see a great pay-oﬀ to using naive Bayes in instances where *p* is large or *n* is small, 
so that **reducing the variance is very important** (the bias-variance trade-off).

![naive-bayes-tuning](img/naive_bayes_tuning.png)


