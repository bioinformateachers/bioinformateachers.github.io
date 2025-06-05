---
layout: post
title: "Bayesian Networks: a super-elementary overview"
author: "Filippo Biscarini"
date: "2025-06-05"
categories: STATISTICS BAYES GRAPHS
---

## Brief theoretical background

**Bayesian Networks** are <u>probabilistic graphical models</u> and are described by: 

1. a **DAG** (directed acyclic graph) $$G = (V,E)$$, with nodes $$ v_{i} \in V $$ (V for "vertex") that represent random variables 
$$X_{i}$$, 
and connections $$ e_{ij} = (v_i, v_j) $$ between nodes (E from "edges")
2. a **joint conditional probability distribution** of the $$X$$ variables $$P(X_1 = x_1, \ldots, X_n = x_n) = \Pi_{i=1} p(x_{i} | x_{p})$$

A DAG contains:

- **only directed connections** $$ v_{i} \rightarrow v_{j} $$
- **no bidirectional connections** $$ v_{i} \rightleftharpoons v_{j} $$
- **no loops** (connection of a node/variable with itself: $$ v_{i} \rightarrow v_{i} $$)
- **no cycles** (a sequence of connections that starts and ends in the same node/variable: $$v_{i} \rightarrow v_{j} \rightarrow \ldots \rightarrow v_{k} \rightarrow \v_{i} $$)

The objective of a Bayesian Network is to **calculate conditional probabilities** between variables: 
calculations --and predictions-- can be made about any variables, with no distinction between dependent (target) and explanatory (factor) variables.

Unlike many other statistical learning methods, Bayesian Networks can handle missing data.
Additionally, they scale well and allow for complex inferential relationships.
Bayesian Networks clearly show causal paths and highlight the presence of mediator variables, colliders, confounders etc. 


