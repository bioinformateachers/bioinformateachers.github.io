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

![naive-bayes-tuning](img/naive_bayes_tuning.png)

