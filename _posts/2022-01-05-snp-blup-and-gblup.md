---
layout: post
title: "SNP-BLUP and GBLUP"
author: "Filippo Biscarini"
date: "2022-01-05"
categories: STATISTICS GENOMIC-PREDICTIONS
---

We begin here a series of posts with the aim to clarify the **SNP-BLUP** and **GBLUP** approaches 
to the prediction of response (targets) variables from SNP genotype data:

- the two models and their equivalency/interchangeability
- how cross-validation apply to these two parameterizations of (essentially) the same problem
- applications in R

### Outline of the material
1. [Super-quick recap of linear mixed models](_posts/2022-01-05-linear-mixed-models.md)
2. Application of mixed models to genetics and breeding: from BLUP to GBLUP
3. An alternative (yet equivalent) parameterization: the SNP-BLUP
4. How to do cross-validation with SNP-BLUP
5. How to do cross-validation with GBLUP

