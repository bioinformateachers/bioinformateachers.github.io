---
layout: post
title: "Super-quick recap of linear mixed models"
author: "Filippo Biscarini"
date: "2022-01-05"
categories: STATISTICS QUANTITATIVE-GENETICS LINEAR-ALGEBRA
---

We begin our mini-series of posts on [GBLUP and SNP-BLUP]().

Linear mixed models are a very powerful statistical tool that, simply put, allow to mix "fixed" (systematic) and "random" effects in one model equation.

Linear mixed models find applications in practically all fields of science: from economics, to soil science, to ecology. 
As an example, for instance, you can think of analysing the math scores of students from different schools as a function of their socioeconomic status. 
The socioeconomic status can be interesting for the distribution of individual values (one per student) and its overall variance 
(how much it contributes to the total observed variation in math scores (i.e. how much it explains the target variable under study). 
Naturally, since we have multiple schools, we may want to correct (include in the model) for characteristics of the school, like the type 
(e.g. private, public, catholic school) and the average math score (more or less "liberality" in giving out scores). 
These characteristics of the school are interesting for their "group coefficients", i.e. the correction values for each school. 
Under this perspective, the socioeconomic status will be a **random variable**, while the type of school and the school's average math score will be **fixed variables**. 
In mathematical notation, we can write down the following (simplified) model:

$$
\text{math_score}_{ijkz} = \mu + \text{school_type}_j + \text{school_avg}_k + \text{socioeconomic_status}_z + e_{ijkz}
$$

where $\mu$ is the intercept and $e_{ijkz}$ is the residual term.

In this mini-series of posts we will concentrate on **applications to life sciences**, specifically **genetics** and **breeding** (plant & animal).

Given that some amount of **algebraic notation** is needed to discuss mixed models, we have prepared a rendered html page for our theoretical background, 
plus an R worked-out illustration in an R markdown file that you can find in our github repo.

Next up: from BLUP to GBLUP!
