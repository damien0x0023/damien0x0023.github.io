---
layout: post
title: Basic Econometrics - Unit 2 Regression Analysis Estimation
subtitle: 基础计量经济学（二）回归分析估计
category: money
tags: [ECON5002]
---


translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 2 Regression Analysis Estimation (Simple Regression)

## Video 2: Interpretation of the simple regression model

Consider the simple regression model:

$$ \tag{2.1} y =  \beta _0 + \beta _1 x + u  \label{simpleRegression1} $$

If the factors in \\( u \\) are held fixed when \\( x \\) changes by \\( \Delta x \\)

$$ (y+\Delta y) = \beta _0 + \beta _1 (x + \Delta x) + u \tag{2.2} \label{simpleRegression2} $$

Substracting \eqref{simpleRegression1} from \eqref{simpleRegression2} we got

$$ \Delta y = \beta _1 \Delta x \text{, if } \Delta u = 0 $$

Suppose

$$ wage = -16.45 + 2.9 educ + u$$

An additional year of education increase the wage by $2.9, if \\( u \\) doesn't change when \\( educ \\) changes, i.e.

$$ \Delta wage = 2.9 \Delta educ \text{, if } \Delta u = 0. $$

Suppose that

$$ lwage = 1.44 + 0.11 educ + u $$

What is the effect on wage of an additional year of education?

$$
  \Delta ln{wage} 
  = ln(wage+\Delta wage) - ln(wage)
  = ln \left( \frac{wage+\Delta wage}{wage}\right)
$$

If \\(\epsilon = \Delta wage / wage \\) is small

$$
  \Delta ln(wage) = ln(1+\epsilon) \approx \epsilon
$$

If \\( \Delta ln (wage) = \beta _1\\), then,

$$
  \beta _1 
  \approx \frac{\Delta wage} {wage} 
  \implies \\% \ \Delta wage 
  \approx 100 \beta _1
$$

Another year of education increases the predicted wage by 11%.


### Remarks

- \\( \beta _1 \\) measures the effect of  \\(x\\) on  \\(y\\) holding the other factors in \\(u\\) fixed.

- How can we learn the ceteris paribus effect of  \\(x\\)  on \\(y\\), when we are ignoring all the other factors?

-  If we assume \\( E(u|x) = 0 \\), then \\( \beta _1 \Delta x\\)  tell us how the average value of \\(y\\) changes with  \\(x\\) .  
An additional year of education increases the predicted wage by 11% on average, not for every worker.

### Takeaway

- If we assume that \\( E(u|x) = 0 \\), the slope \\( \beta _1 \\) can be interpreted as the average predicted change in y when x increases by one
unit.  
It can be also interpreted as the predicted change in y, if we are ready to assume that  \\(u\\)  remains fixed when \\(x\\) changes.

- The log transformation of the variables allow for constant (semi)-elasticity models.

## Video 3: Mechanics of Ordinary Least Squares

### Obtaining the OLS estimates

Given that data set \\( \lbrace (lwage_i, educ_i); i = 1, ..., n \rbrace \\), suppose that we are interested in the relationship between wages and education.

If we assume

$$ lwage_i \approx b_0 + b_1 educ_i $$

then we are interested in b0 and b1.

![]({{site.url}}/assets/images/2020/ECON5002/OLSestimates.jpg 'Figure 3.1: How do we pick up the "optimal" line?')

Given a data set \\( \lbrace (y _i, x _i) i = 1, ..., n \rbrace \\), for each observation, let

$$
  u _i (b _0, b _1) = y _i - (b _0 + b_1 x _i) 
  \tag{3.1} 
$$

and define the **ordinary least-square estimator** as

$$
  [\hat{\beta} _0, \hat{\beta} _1] = \mathop{\arg\min}\limits _{b _0, b _1} \hat{S} (b _0, b _1)
  \tag{3.2} \label{OLSestimator}
$$

where

$$
  \hat{S} (b _0, b _1) \sum\limits _{i=1} ^{n} u ^2 _i (b _0, b _1)
  \tag{3.3}
$$

### The OLS estimator

The solution of \eqref{OLSestimator} is

$$
  \left \lbrace \begin{array}{l} 
  \hat{\beta} _0 = \overline{y} -\hat{\beta} _1 \overline{x}
  \\\\ \hat{\beta} _1 = \frac 
    {\sum _{i=1} ^n (x _i - \overline{x}) (y _i - \overline{y})}
    {\sum _{i=1} ^n (x _i - \overline{x})^2}
  \end{array} \right.
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


![]({{site.url}}/assets/images/2020/ECON5002/OLSestimates2.jpg 'Figure 3.2: The sample regression function')

### Algebraic Properties of OLS statistics

Recall equation \eqref{OLSestimator}


<!-- inline equation:
\\(
   f(x) =  \frac{1}{2} x^2 = \dfrac{1}{2} x^2 = \tfrac{1}{2} x^2
\\)

display equation:  
$$
  f(x) =  \frac{1}{2} x^2 = \dfrac{1}{2} x^2 = \tfrac{1}{2} x^2
$$ -->


<!-- $$
    \left.\frac{dy}{dx}\right|_{x=0}
$$ -->

$$
  [\hat{\beta} _0, \hat{\beta} _1] 
  = \mathop{\arg\min}\limits _{b _0, b _1} \hat{S} (b _0, b _1)
  = \mathop{\arg\min}\limits _{b _0, b _1} \sum _{i=1}^{n} u _i ^2 (b _0, b _1)
$$

First order conditions:

$$
  \begin{array}{l}
    \left .\frac{\partial{\hat{S}(b _0, b _1)}}{\partial{b _0}} \right| 
      _{ \begin{array}{l} 
        b_0 = \hat{\beta} _0 
        \\\\ b_1 = \hat{\beta} _1 
        \end{array}}
    = \sum _{i=1}^n u _i \left(\hat{\beta} _0, \hat{\beta} _1 \right)
    = \sum _{i=1}^n \hat{u} _i 
    = 0
    \\\\
    \left .\frac{\partial{\hat{S}(b _0, b _1)}}{\partial{b _0}} \right| 
      _{ \begin{array}{l} 
        b_0 = \hat{\beta} _0 
        \\\\ b_1 = \hat{\beta} _1 
        \end{array}}
    = \sum _{i=1}^n u _i \left(\hat{\beta} _0, \hat{\beta} _1 \right) x _i
    = \sum _{i=1}^n \hat{u} _i x _i 
    = 0
  \end{array}
  \tag{3.4} \label{FOC}
$$

1. Deviations from regression line sum up to zero

$$
  \sum _{i=1}^n \hat{u} _i = 0
  \tag{3.5}
$$

2. The sample correlation between deviations and regressors is
zero

$$
  \sum _{i=1}^n \hat{u} _i x _i = 0
  \tag{3.6}
$$

3. Sample averages of y and x lie on the regression line

$$
  \overline{y} = \hat{\beta} _0 + \hat{\beta} _1 \overline{x}
  \tag{3.7}
$$

4. Properties 1 and 2 imply

$$
  \sum _{i=1}^n \hat{y} _i \hat{u} _i   = 0 
  \tag{3.8}
$$

5. Properties 1 implies

$$
  \overline{y} 
  = \frac{1}{n} \sum _{i=1}^n y _i
  = \frac{1}{n} \sum _{i=1}^n \hat{y} _i .
  \tag{3.9}
$$

Measures of Variation

- Total Sum of Squares (total sample variation of the \\(y_i\\) )

$$
  \text{SST} 
  = \sum _{i=1}^n ( y _i - \overline{y}) ^2
$$

- Explained Sum of Squares (total sample variation of the \\(\hat{y}_i\\) )


$$
  \text{SSE} 
  = \sum _{i=1}^n ( \hat{y} _i - \overline{y}) ^2
  = \sum  _{i=1}^n \hat{\beta} ^2 (x _i - \overline{x}) ^2
$$

- Sum of Squared Residuals (total sample variation of the \\(\hat{u}_i\\))

$$
  \text{SSR} 
  = \sum _{i=1}^n \hat{u}_i ^2.
$$

- Decomposition of total variation

$$
  \text{SST} = \text{SSE} +\text{SSR}
  \tag{3.10}
$$

i.e.

Total Variation = Explained Variation + Unexplained Variation

- Goodness offit measure(R-squared)

$$
  R ^2 = \frac{SSE}{SST} = 1- \frac{SSR}{SST},\ 0 \le R ^2 \le 1
$$

The \\(R ^2\\) measure the fraction of the total variation explained by the regression.

### Takeaway

= The algebraic properties of OLS follow from the rst order conditions in (4).

- To compute the estimators, we only assumed variation in the \\(
xi, i = 1 ... n\\)

- Learning how to handle OLS as a computational tool will be (hopefully) helpful with the usage and the interpretation of OLS as an estimator.

## Video4: Expected Value and Variance of the OLS Estimators

### Unbiasedness of OLS

**Assumption SLR.2 (random sampling)**

The random variables \\( \lbrace (y _1, x _1), ... , (y _i, x _i), ... , (y _n; x _n) \rbrace \\) are independent and identically distributed (i.i.d.)

**Assumption SLR.1 (linearity in the parameters)**

The random variables \\( (y _i, x _i) \\) satisfy the linear regression equation

$$
  y _i = \beta _0 + \beta _1 x _i + u _i
  \tag{4.1}
$$

where \\(\beta _0\\) and \\(\beta _1\\) are the (unknown) population *intercept* and *slope* parameters.

**Assumption SLR.3 (sample variation in x)**

(i) \\( 0 < Var(x _i) < 1 \\) .

(ii) The sample outcome \\( \lbrace x _1, ... , x _n \rbrace \\) are not all the same value.

Recall that

$$
   \hat{\beta} _1 = \frac 
    {\sum _{i=1} ^n (x _i - \overline{x}) (y _i - \overline{y})}
    {\sum _{i=1} ^n (x _i - \overline{x})^2}
$$

![]({{site.url}}/assets/images/2020/ECON5002/constantRegressor.jpg 'Figure 4.1: Constant regressor.')

**Assumption SLR.4 (Zero Conditional Mean)**

$$
  E(u _i \| x _i) = 0 
$$

- \\( E(U _i) = E[E(u _i \| x _i)] =0 \\).

- Assumption SLR.2 and SLR.4 imply that

$$
  E(y _i \| x _i, ... , x _n) = E(y _i \| x _i) = \beta _0 + \beta _1 x _i 
$$

&emsp;&emsp;that is the **(Population) Regression Function** is linear.

- If \\(y = log(wage)\\), \\(x = education\\) and \\(u = innate ability\\), assumption SLR.4 implies that the average level of innate ability does not depend on education.

**Theorem 2.1. Unbiasedness of OLS**

Under Assumption SLR.1-SLR.4

$$
  E(\hat{\beta} _0) =\beta _0, \text{ and }  E(\hat{\beta} _1) =\beta _1 . 
$$

### Variances of the OLS estimators

**Assumption SLR.5 (homoskedasticity)**

$$
  Var(u _i \| x _i) = \sigma ^2
$$

$$
  Var(u _i \| x _i) = E(u _i^2  \| x _i) - [E(u _i \| x _i)] ^2 = E(u _i^2  \| x _i)
$$

which means

$$
  Var(u _i) = E(u _i^2) = E[E(u _i^2  \| x _i)] = \sigma ^2 = Var(u _i \| x _i).
$$

![]({{site.url}}/assets/images/2020/ECON5002/Homoskedasticity.jpg 'Figure 4.2: Homoskedasticity')

![]({{site.url}}/assets/images/2020/ECON5002/Heteroskedasticity.jpg 'Figure 4.3: Heteroskedasticity 1')

![]({{site.url}}/assets/images/2020/ECON5002/Heteroskedasticity2.jpg 'Figure 4.4: Heteroskedasticity 2')

**Theorem 2.2 (The sampling variance of the OLS estimators)**

Under Assumptions SLR.1-SLR.5

$$
  Var(\hat{\beta} _1 \| x) 
  = \frac {\sigma ^2}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
  = \frac {\sigma ^2}{\text{SST} _x}
  \tag{4.2} \label{varianceEstimator1}
$$

and

$$
  Var(\hat{\beta} _0 \| x) 
  = \frac {\sigma ^2 n ^{-1} \sum _{i=1}^n x _i^2}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
  \tag{4.3} \label{varianceEstimator2}
$$

where \\( x = \lbrace x _1, ..., x _2 \rbrace \\) (sample values).

But \\( \sigma ^2\\) is unknown! And \\(u _i s\\) are not observable!

**Theorem 2.3 (The unbiased estimator of \\( \sigma ^2\\))**

$$
  E(\hat{\sigma} ^2) = \sigma ^2,
  \ \hat{\sigma} ^2 = \frac{\sum _{i=1}^n \hat{u} _i^2}{n-2}.
$$

Why (n - 2)? Recall the OLS first order conditions:

$$
  \sum _{i=1}^n \hat{u} _i = 0,
  \ \sum _{i=1}^n \hat{u} _i x _i = 0.
$$

- If \\( \hat{\sigma} ^2\\) is plugged in \eqref{varianceEstimator1} and \eqref{varianceEstimator2} we get an estimate of the variance.

- Similarly, the **standard errors (se)** of \\(\hat{\beta} _0 \\) and \\(\hat{\beta} _1 \\).

$$
  \begin{array}{m}
      se(\hat{\beta} _1) 
      = \hat{\sigma} 
        \sqrt{\frac{1}{\sum _{i=1}^n (x _i - \overline{x}) ^2}}
      \\\\ se(\hat{\beta} _0) 
      = \hat{\sigma} ^2 
        \sqrt{\frac{n ^{-1} \sum _{i=1}^n x _i^2}{\sum _{i=1}^n (x _i - \overline{x}) ^2}}
  \end{array}
$$

are estimates of the standard deviation of the estimators.

![]({{site.url}}/assets/images/2020/ECON5002/estimatedDensity.jpg 'Figure 4.5: The estimated density.')

### Takeaway

- Assumptions SLR.1-SLR.4 are sucient to show that \\(\hat{\beta} _0\\), \\(\hat{\beta} _1\\) are unbiased.

- SLR stands for Simple Linear Regression.

- Because \\( E(y _i \| x _i) = \beta _0 + \beta _1 x _i \\) (SLR.4), estimating \\(\hat{\beta} _0\\) and \\(\hat{\beta} _1\\) mean estimating the CEF.

- SLR.5 is added to obtain the variance of the OLS estimators.

- Mean and Variance refer to random variables! Here we considered the OLS estimators, not the estimates.

## 5. Counterfactual Outcomes and Causality

### Causal Effects

Let \\(x _i\\) a binary variable (either \\(x _i = 1 \text{ or } x _i = 0\\) ).

- \\(x _i = 1 \\) indicates a treatment.

- \\(x _i = 0 \\) indicates a non-treatment.

We are interested in the causal effect of \\(x _i\\)  on \\(y _i (x _i)\\). The difference between the two **potential** outcomes:

$$
  \tau _i = y _i (1) - y _i (0)
$$

is called the **causal** (or **treatment**) effect.

Example (the Perry Preschool Project):

- \\( y _i (1) \\) is the wage of the individual \\( i \\) if he/she entered the
preschool program (\treatment group").

- \\( y _i (0) \\) is the wage of the individual \\( i \\) if he/she received no
preschool education (\control group").

- For the individual \\( i \\) we only observe one the two potential
outcomes.

For each unit \\( i \\), the observed outcome \\( y _i \\) can be written

$$
  y _i 
  = (1-x _i)y _i (0) + y _i (1) x _i 
  = y _i (0) + [y _i(1) + y _i (0)]x _i 
  \tag{5.1} \label{observedOutcome}
$$

Check that

$$
  y _i =
  \begin{cases}
  y _i (1) \text{ if } x _i = 1,
  \\\\
  y _i (0) \text{ if } x _i = 0.
  \end{cases}
$$

Equation \eqref{observedOutcome} can be rewritten as

$$
  y _i = y _i(0) + \tau _i x _i
  \tag{5.2}
$$

We cannot hope to estimated \\( \tau _i \\) for each unit \\( i \\).

Our aim will be to estimate the **average treatment (or causal) effect (ATE)**:

$$
  \tau _{ate} = E(\tau _i) = E[y _i (1) - y _i (0)] = \alpha _1 - \alpha _0
$$

where 

$$
  \alpha _1 = E[y _i (1)] \text{, and } \alpha _0 = E[y _i (0)]
$$

Define

$$
  y _i (1) = \alpha _1 + u _i (1) 
  \text{  and  } 
  y _i (0) = \alpha _0 + u _i (0)
$$

Then, equation

$$
  y _i = y _i (0) + \tau _i  x _i
  \tag{5.3}
$$

can be written as

$$
  y _i = \alpha + \tau _{ate} \cdot x _i + u _i
  \tag{5.4}
$$

where \\( \tau _{ate} = \alpha _1 - \alpha _0\\), and 

$$
  u _i = u _i(0) + [u _i(1) - u _i(0)] x _i
  \tag{5.5}
$$

If the treatment is randomly assigned

$$
  x _i \models [u _i(0) , u _i(1)]
  \tag{5.6}
$$

![]({{site.url}}/assets/images/2020/ECON5002/specialCharEq.jpg 'Equation 5.6: The estimated density.')

(post here because the author has doubts of the character inside this equation)


<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>


