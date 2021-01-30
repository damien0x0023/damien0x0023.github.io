---
layout: post
title: Basic Econometrics - Unit 2 Regression Analysis Estimation
subtitle: 基础计量经济学（二）回归分析估计
category: money
tags: [ECON5002]
---


translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 2 Regression Analysis Estimation (Simple Regression)

## Interpretation of the simple regression model

Consider the simple regression model:

$$ \tag{1} y =  \beta _0 + \beta _1 x + u  \label{simpleRegression1} $$

If the factors in \\( u \\) are held fixed when \\( x \\) changes by \\( \Delta x \\)

$$ (y+\Delta y) = \beta _0 + \beta _1 (x + \Delta x) + u \tag{2} \label{simpleRegression2} $$

Substracting \eqref{simpleRegression1} from \eqref{simpleRegression2} we got

$$ \Delta y = \beta _1 \Delta x \text{, if } \Delta u = 0 $$

Suppose

$$ wage = -16.45 + 2.9 educ + u$$

An additional year of education increase the wage by $2.9, if \\( u \\) doesn't change when \\( educ \\) changes, i.e.

$$ \Delta wage = 2.9 \Delta educ \text{, if } \Delta u = 0. $$

Suppose that

$$ lwage = 1.44 + 0.11 educ + u $$

What is the effect on wage of an additional year of education?


**Obtaining the OLS estimates**

Given that data set \\( \lbrace (lwage_i, educ_i); i = 1, ..., n \rbrace \\}, suppose that we are interested in the relationship between wages and education.

If we assume

$$ lwage_i \approx b_0 + b_1 educ_i $$

then we are interested in b0 and b1.

![]({{site.url}}/assets/images/2020/ECON5002/OLSestimates.jpg 'Figure 1: How do we pick up the "optimal" line?')

Given a data set \\( \lbrace (y _i, x _i); i = 1, ..., n \rbrace \\}, for each observation, let
$$
  u _i (b _0, b _1) = y _i - (b _0 + b_1 x _i) 
  \tag{1} 
$$

and define the **ordinary least-square estimator** as

$$
  [\hat{\beta} _0, \hat{\beta} _1] = \mathop{\arg\min}\limits _{b _0, b _1} \hat{S} (b _0, b _1)
  \tag{2} \label{OLSestimator}
$$

where

$$
  \hat{S} (b _0, b _1) \sum\limits _{i=1} ^{n} u ^2 _i (b _0, b _1)
  \tag{3}
$$

The solution of \eqref{OLSestimator} is


$$
  \left\\{\begin{array}{l} 
  \hat{\beta} _0 = \overline{y} -\hat{\beta} _1 \overline{x}
  \\\\ \hat{\beta} _1 = \frac 
    {\sum _{i=1} ^n (x _i - \overline{x}) (y _i - \overline{y})}
    {\sum _{i=1}^n (x _i - \overline{x})^2}
  \end{array}\right.
$$

assuming that \\( SST _x = \sum _{i=1} ^n (x _i - \overline{x})^2 > 0. \\)

The fitted or predicted values, \\( \hat{y} _i \\), is defined by the **Sample
Regression Function** (SRF)

$$
  \hat{y} _i = \hat{\beta _0} + \hat{\beta _1} x _i
$$

The deviations from the SRF (or fitted regression line)

$$
  \hat{u} _i = y _i - \hat{y} _i, \  i = 1,..., n
$$
are called **residuals**.

Remark: We defined \\(   u _i (b _0, b _1) = y _i - (b _0 + b_1 x _i)  \\). Then, \\( \hat{u} _i =  u _i( \hat{\beta} _0, \hat{\beta} _1) \\).


![]({{site.url}}/assets/images/2020/ECON5002/OLSestimates2.jpg 'Figure 2: The sample regression function')

**Algebraic Properties of OLS statistics**

Recall equation \eqref{OLSestimator}

$$
  [\hat{\beta} _0, \hat{\beta} _1] 
  = \mathop{\arg\min}\limits _{b _0, b _1} \hat{S} (b _0, b _1)
  = \mathop{\arg\min}\limits _{b _0, b _1} \sum _{i=1}^{n} u _i ^2 (b _0, b _1)
$$

First order conditions:

$$

$$

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>


