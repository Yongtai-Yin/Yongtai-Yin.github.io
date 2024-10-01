---
layout: post
title: Convex Functions
date: 2024-10-01 20:12:00
description: Notes for ENGG 5501 Foundations of Optimization 2024-25 Term 1
tags: optimization
categories: courses
toc:
  sidebar: left
---

## Basic Definitions
### Convex Functions
Let $f : \mathbb{R}^n \rightarrow \mathbb{R} \cup \{+\infty\}$ be an extended real-valued function that is not identically $\{+\infty\}$.
We say that $f$ is convex if $\forall x_1, x_2 \in \mathbb{R}^n$, $\alpha \in [0,1]$, we have
$$
f(\alpha x_1 + (1 - \alpha)x_2) \leq \alpha f(x_1) + (1 - \alpha)f(x_2)
$$
> Remark: Here, $\alpha + \infty = \infty + \alpha = \infty$, $\forall \alpha \in \mathbb{R}$; and $\infty \leq \infty$.

See the illustration:
![Convex Functions](/assets/img/course_opt/convex_functions.svg)
### Epigraph
The epigraph of $f$ is the set:
$$\text{epi}(f) = \{ (x,t) \in \mathbb{R}^n \times \mathbb{R} : f(x) \leq t \} \in \mathbb{R}^{n+1}$$
See the illustration: (y-axis corresponds to $t$)
![epigraph of a function](/assets/img/course_opt/epigraph.svg)
### Effective Domain
The effective domain of $f$ is the set:
$$\text{dom}(f) = \{ x \in \mathbb{R}^n : f(x) < +\infty \} \in \mathbb{R}^n$$
Some examples:
![effective domain of some functions](/assets/img/course_opt/effective_domain.svg)
### Indicator Function
Let $S \subseteq \mathbb{R}^n$ be a set, the indicator function associated with $S$ is
$$\mathbb{1}_S(x) = \left\{\begin{aligned}0, \; & \text{if} \; x \in S \\ +\infty, \; & \text{otherwise}\end{aligned}\right.$$

> [!NOTE] Example for indicator function (constrained to unconstrained)
> $$\underbrace{\inf_{x \in S} f(x)}_{constrained} \Longleftrightarrow \underbrace{\inf_{x \in \mathbb{R}^n} \{ f(x) + \mathbb{1}_S(x) \}}_{unconstrained}$$
> - convert the original constrained problem into unconstrained problem, very useful!
### Proposition
Let $f : \mathbb{R}^n \rightarrow \mathbb{R} \cup \{ +\infty \}$ be given. Then,
- $f$ is convex (==as a function==) $\Longleftrightarrow$ $\text{epi}(f)$ is convex (==as a set==)

Let $S \subseteq \mathbb{R}^n$ be given. Then,
- $S$ is convex (==as a set==) $\Longleftrightarrow$ $\mathbb{1}_S$ is convex (==as a function==)
> Try to prove this proposition as an exercise.
### Corollary (Jensen's Inequality)
Let $f : \mathbb{R}^n \rightarrow \mathbb{R} \cup \{ +\infty \}$ be given. Then,
- $f$ is convex $\Longleftrightarrow$ For any $x_1, x_2, \dots, x_k \in \mathbb{R}^n$, $\alpha_1, \dots, \alpha_k \geq 0$, $\sum_{i=1}^{k} \alpha_i = 1$, we have $f(\sum_{i=1}^{k} \alpha_i x_i) \leq \sum_{i=1}^{k} \alpha_i f(x_i)$.
> Jensen's inequality can be proved by the [[#Proposition]] easily.
## Convexity-preserving Operations
### Non-negative combination
Let $f_1, f_2, \dots, f_k$ be convex (functions), $\alpha_1, \dots, \alpha_k \geq 0$ be non-negative scalars. Then,
$f = \sum_{i=1}^{k} f_i$ is convex.
> Try to prove it as an exercise.
### Pointwise Supremum
Let $I$ be an index set and $\{ f_i \}_{i \in I}$ be a collection of convex functions (*infinite is allowed*). Then, $f = \sup_{i \in I} f_i$ is convex.
> [!NOTE] Remark
> $\text{epi}(f) = \cap_{i \in I} \text{epi}(f_i)$, try to prove it as an exercise.

See the illustration:
![pointwise supremum](/assets/img/course_opt/pointwise_supremum.svg)