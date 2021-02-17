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

Given that data set \\( \lbrace (lwage_i, educ_i); i = 1, \cdots, n \rbrace \\), suppose that we are interested in the relationship between wages and education.

If we assume

$$ lwage_i \approx b_0 + b_1 educ_i $$

then we are interested in b0 and b1.

![]({{site.url}}/assets/images/2020/ECON5002/OLSestimates.png "Figure 3.1: How do we pick up the 'optimal' line?")

Given a data set \\( \lbrace (y _i, x _i) i = 1, \cdots, n \rbrace \\), for each observation, let

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

The fitted or predicted values, \\( \hat{y} _i \\), is defined by the **Sample Regression Function** (SRF)

$$
  \hat{y} _i = \hat{\beta} _0 + \hat{\beta} _1 x _i
$$

The deviations from the SRF (or fitted regression line)

$$
  \hat{u} _i = y _i - \hat{y} _i, \  i = 1,\cdots, n
$$

are called **residuals**.

Remark: We defined \\(   u _i (b _0, b _1) = y _i - (b _0 + b_1 x _i)  \\). Then, \\( \hat{u} _i =  u _i( \hat{\beta} _0, \hat{\beta} _1) \\).


![]({{site.url}}/assets/images/2020/ECON5002/OLSestimates2.png 'Figure 3.2: The sample regression function')

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

= The algebraic properties of OLS follow from the first order conditions in (4).

- To compute the estimators, we only assumed variation in the \\(
xi, i = 1 \cdots n\\)

- Learning how to handle OLS as a computational tool will be (hopefully) helpful with the usage and the interpretation of OLS as an estimator.

## Video4: Expected Value and Variance of the OLS Estimators

### Unbiasedness of OLS

**Assumption SLR.2 (random sampling)**

The random variables \\( \lbrace (y _1, x _1), \cdots , (y _i, x _i), \cdots , (y _n; x _n) \rbrace \\) are independent and identically distributed (i.i.d.)

**Assumption SLR.1 (linearity in the parameters)**

The random variables \\( (y _i, x _i) \\) satisfy the linear regression equation

$$
  y _i = \beta _0 + \beta _1 x _i + u _i
  \tag{4.1}
$$

where \\(\beta _0\\) and \\(\beta _1\\) are the (unknown) population *intercept* and *slope* parameters.

**Assumption SLR.3 (sample variation in x)**

(i) \\( 0 < Var(x _i) < 1 \\) .

(ii) The sample outcome \\( \lbrace x _1, \cdots , x _n \rbrace \\) are not all the same value.

Recall that

$$
   \hat{\beta} _1 = \frac 
    {\sum _{i=1} ^n (x _i - \overline{x}) (y _i - \overline{y})}
    {\sum _{i=1} ^n (x _i - \overline{x})^2}
$$

![]({{site.url}}/assets/images/2020/ECON5002/constantRegressor.png 'Figure 4.1: Constant regressor.')

**Assumption SLR.4 (Zero Conditional Mean)**

$$
  E(u _i | x _i) = 0 
$$

- \\( E(U _i) = E[E(u _i \| x _i)] =0 \\).

- Assumption SLR.2 and SLR.4 imply that

$$
  E(y _i | x _i, \cdots , x _n) = E(y _i | x _i) = \beta _0 + \beta _1 x _i 
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
  Var(u _i | x _i) = \sigma ^2
$$

$$
  Var(u _i | x _i) = E(u _i^2  | x _i) - [E(u _i | x _i)] ^2 = E(u _i^2  | x _i)
$$

which means

$$
  Var(u _i) = E(u _i^2) = E[E(u _i^2  | x _i)] = \sigma ^2 = Var(u _i | x _i).
$$

![]({{site.url}}/assets/images/2020/ECON5002/Homoskedasticity.png 'Figure 4.2: Homoskedasticity')

![]({{site.url}}/assets/images/2020/ECON5002/Heteroskedasticity.png 'Figure 4.3: Heteroskedasticity 1')

![]({{site.url}}/assets/images/2020/ECON5002/Heteroskedasticity2.png 'Figure 4.4: Heteroskedasticity 2')

**Theorem 2.2 (The sampling variance of the OLS estimators)**

Under Assumptions SLR.1-SLR.5

$$
  Var(\hat{\beta} _1 | x) 
  = \frac {\sigma ^2}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
  = \frac {\sigma ^2}{\text{SST} _x}
  \tag{4.2} \label{varianceEstimator1}
$$

and

$$
  Var(\hat{\beta} _0 | x) 
  = \frac {\sigma ^2 n ^{-1} \sum _{i=1}^n x _i^2}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
  \tag{4.3} \label{varianceEstimator2}
$$

where \\( x = \lbrace x _1, \cdots, x _2 \rbrace \\) (sample values).

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

![]({{site.url}}/assets/images/2020/ECON5002/estimatedDensity.png 'Figure 4.5: The estimated density.')

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

![]({{site.url}}/assets/images/2020/ECON5002/specialCharEq.png 'Equation 5.6: The estimated density.')

(post the clip here because the author has doubts of the character inside this equation)

Hence,

$$
  E[u _i (0) | x _i] = E[u _i (0)], \ E[u _i (1) | x _i] = E[u _i (1)]
  \tag{5.7}
$$

implying

$$
  E[u _i | x _i] 
  = E[u _i (0) | x _i] + E[u _i (1) - u _i (0) | x _i] x _i 
  = 0 
  \tag{5.8}
$$

The OLS estimators are unbiased for the \\(\alpha _0 \\) and \\( \tau _{ate} \\)!

### Takeaway

- \\( \tau _{ate} \\) can be estimated by OLS.

- Random assignment implies that \\(E[u _i \| x _i]  = 0 \\). We conclude that \\( \hat{\tau} _{ate} \\)  is unbiased.

## Video 6: Multiple regression analysis

### Motivation

Consider an extension of the regression of *lwage* on *educ*:

$$
  lwage = \beta _0 + \beta _1 educ + \beta _2 IQ +u
$$

*IQ* is the Intelligence Quotient score (In population, the *IQ* score has mean 100 and standard deviation 15.)

Primarily interested in \\(\beta _1\\), but \\(\beta _2\\) is of some interest, too. Including *IQ* in the equation, it is taken out of the error term.  
If *IQ* is a good proxy for intelligence, this may lead to a more
persuasive estimate of the causal effect of schooling.

A model with two independent variables can be written as

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + u,
  \tag{6.1}
$$

- \\(\beta _0\\) is the intercept.

- \\(\beta _1\\) measures the change in y with respect to \\(x _1 \\), holding other factors fixed.

- \\(\beta _2\\) measures the change in y with respect to \\(x _2 \\), holding other factors fixed.

- *u* is the unobserved component (error).

In the model with two explanatory variables, the key assumption about how u is related to \\(x _1 \\) and \\(x _2 \\) is

$$
  E(u  | x _1, x _2)  = 0 .
  \tag{6.2}
$$

Then \\( E (y \| x _1, x _2 ) = \beta _0 + \beta _1 x _1 + \beta _2 x _2\\) and 

$$
  y = E (y | x _1, x _2 ) + u
$$

In the wage equation, the assumption is \\( E(u \| educ, IQ) = 0\\).

Now *u* no longer contains intelligence (we hope), and so this assumption has a better chance of being true.

In the simple regression model, we had to assume *IQ* and *educ* were unrelated to justify \\( E(u \| educ) = 0\\)  (*IQ* was in *u*).

Other factors, such as workforce experience and @motivation," are part of u. Motivation is very dicult to measure. Measuring experience is easier:

$$
  lwage = \beta _0 + \beta _1 educ + \beta _2 IQ + \beta _3 exper + u
$$

### The Model with k Explanatory Variables

The **multiple linear regression model** can be written in the population as

$$
   y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \cdots +\beta _k x _k + u
$$

\\( \beta _0\\) is the **intercept**, \\( \beta _1\\) is the parameter associated with \\( x _1 \text{, } \beta _2\\) is the parameter associated with  \\( x _2\\), and so on.

Contains *k* + 1 (unknown) population parameters. We call \\( \beta _1, \cdots, \beta _k \\) the **slope parameters**.

Multiple regressions allows more flexible functional forms.

$$
  lwage = \beta _0 + \beta _1 educ + \beta _2 IQ + \beta _3 exper 
    + \beta _4 exper^2+ u 
$$

&emsp;so that exper is allowed to have a quadratic effect on *lwage*.

Let \\( x _1 = educ, x _2 = IQ, x _3 = exper, and x _4 = exper ^2 \\).

Note that \\(x _4\\) is a a nonlinear function of \\(x _3\\), but the model is still linear in the parameters!

We already know that \\(100 \cdot \beta _1\\) is the ceteris paribus percentage change in *wage* when *educ* increases by one year. 

 \\(100 \cdot \beta _2\\) has a similar interpretation (for \\(\Delta IQ = 1\\)).

\\( \beta _3\\)  and \\( \beta _4\\) are harder to interpret. Using calculus,

$$
  \frac{\partial lwage} {\partial exper} 
  = \beta _3 + 2 \beta _4 exper
$$

&emsp; Multiply by 100 to get the percentage effect.

### Takeaway

The multiple regression model allows us:

- to control for many other factors that simultaneously affect the dependent variables (ceteris paribus interpretation),
 
- to model non-linear relationships (linearity is in the parameters!).


## Video 7: Mechanics and Interpretation of the Ordinary Least Squares

### Interpreting the OLS Regression Line

Consider the case *k* = 2:

$$
  \hat{y} = \hat{\beta} _0 + \hat{\beta} _1 x _1 + \hat{\beta} _2 x _2
  \tag{7.1}
$$

The intercept\\( \hat{\beta} _0 \\)is the predicted value of *y* when \\( x _1 = x _2 = 0 \\)

The estimates \\( \hat{\beta} _1, \ \hat{\beta} _2\\) have **partial effects**, or **ceteris paribus** interpretations.

If we "hold \\(x _2 \\) fixed"

$$
  \Delta \hat{y}
  = \hat{\beta} _1 \Delta x _1 
  \text{ if } \Delta x _2 = 0
$$

\\( \beta _1\\) measures the predicted change in *y* due a one-unit increase in \\(x _1 \\), holding \\(x _2 \\) fixed.

Similarity,

$$
  \hat{\beta} _2 = \frac{\Delta \hat{y}}{\Delta x _2} 
  \text{ if } \Delta x _1 = 0
$$

**Example**

Dataset1 WAGE2.DTA(Wooldridge, online resources):

$$
  \begin{array}{m}
    \widehat{lwage} = 1.142 + .099 educ
    \\\\n = 759
  \end{array}
$$

and 

$$
  \begin{array}{m}
    \widehat{lwage} = .728 + .073 educ + .0076IQ
    \\\\n = 759
  \end{array}
$$

The predicted return to a year of education falls from about 9:9% to about 7:3% when we control for differences in *IQ*.

- The simple regression does not allow us to compare people with the same *IQ* score.

- The larger estimated return from simple regression is because we are attributing part of the *IQ* effect to education.

- Not surprisingly, \\( Corr(educ, IQ) = :573 \\).

### Comparing Simple and Multiple Regression Estimates

Consider the simple and multiple OLS regression functions:

$$
  \widetilde{y} _i = \widetilde{\beta} _0 + \widetilde{\beta} _1 x _{1i}
  \tag{7.2}
$$

$$
  \hat{y} _i = \hat{\beta} _0 + \hat{\beta} _1 x _{1i} + \hat{\beta} _2 x _{2i}
  \tag{7.3} 
$$

using the same *n* observations.

Question: Is there a relationship between \\( \beta _1\\) (which does not
control for \\( x _2\\) ) and \\( \beta _1\\) (which does)?

Yes, but we need to define another simple regression.

Regressing \\( x _2\\) on \\( x _1\\) and a constant we obtain

$$
  x _{2i} = \widetilde{\delta} _0 + \widetilde{\delta} _1 x _{1i} + \widetilde{r} _i
  \tag{7.4}
$$

Then,

$$
  \begin{align}
    \hat{y} _i & = \hat{\beta} _0 + \hat{\beta} _1 x _{1i} + \hat{\beta} _2 x _{2i} \tag{7.5}
    \\\\ & = \left( \hat{\beta} _0 + \hat{\beta} _1 \widetilde{\delta} _0 \right)
    + \left( \hat{\beta} _1 + \hat{\beta} _2 \widetilde{\delta} _1 \right) x _{1i} + \hat{\beta} _2 \widetilde{r} _i \tag{7.6}
  \end{align}
$$

&emsp;where \\( \sum _{i=1}^n x _1 \widetilde{r} _i =0 \\) by construction.

Regressing y on \\( x _1\\) and a constant only or on \\([x _1, \widetilde{r}]\\) and a constant gives the same estimate of the coecient of \\( x _1\\).

For any sample

$$
  \widetilde{\beta} _1 
  = \hat{\beta} _1 + \hat{\beta} _2 \widetilde{\delta} _1
  \tag{7.7}
$$

If the partial effect of \\( x _2\\) on *y* is positive, so \\( \widetilde{\beta} _2 > 0\\), and \\( x _1\\) and \\( x _2\\) are positive correlated in the sample, so \\( \widetilde{\delta} > 0 \\), then

$$
  \widetilde{\beta} _1 > \hat{\beta} _1
$$

**Example**

![]({{site.url}}/assets/images/2020/ECON5002/example.png "lwage example")

### Takeaway

- In the multiple regression model, the slopes measure the partial effects of the corresponding regressor on the dependent variable, holding all other regressors fixed.

- Comparing the single and the bivariate model will be helpful to understand the omitted variable bias.

## Video 8: Expected Value and Variance of the OLS estimators

### The Expected Value of the OLS Estimators

As for the simple regression, we can specify a set of assumptions under which OLS is unbiased.

We will also explicitly consider the bias caused by omitting a variable that appears in the population model.

The assumptions are labelled \MLR" (multiple linear regression).

**Assumption MLR.2 (Random Sampling)**

We have a random sample of size n from the population, \\( \lbrace [x _{1i}, x _{2i}, \cdots, x _{ki}, y _i]: i = 1, \cdots,n \rbrace \\)

**Assumption MLR.1 (Linear in Parameters)**

For every unit "i", the model in the population can be written as

$$
  y _i = \beta _0 + \beta _1 x _{1i} + \beta _2 x _{2i} + \cdots
    + \beta _k x _{ki} + u _i
$$

where the \\(\beta _k\\) are the population parameters and ui is the unobserved error.

**Assumption MLR.3 (No Perfect Collinearity)**

In the sample (and in the population), none of the explanatory variables is constant, and there are no exact linear relationships among them.

We must rule out the case that one of the explanatory variables is an exact linear function of the others.

Under perfect collinearity, there are no unique OLS estimators.

Usually perfect collinearity arises from a bad model specification.

Perfect collinearity could also arise because of small sample size or bad luck in drawing. e.g. *educ/IQ *= constant.

Assumption MLR.3 can only hold if \\( n > k + 1 \\).

**Assumption MLR.4 (Zero Conditional Mean)**

$$
  E(u _i | x _{1i}, x _{2i}, \cdots, x _{ki}) = 0
$$

**EXAMPLE: Effects of Class Size on Student Performance**

Suppose, for a standardized test score,

$$
  score = \beta _0 + \beta _1 classize + \beta _2 income + u
$$

Even at the same income level, families differ in their interest and concern about their children's education.

Family support and student motivation are in *u*.

If the omitted factors are correlated with *classize* and *income*，**Assumption MLR.4 fails**.

**Theorem 2.1. Unbiasedness of OLS**

Under Assumption MLR.1-MLR.4

$$
  E \left( \hat{\beta} _j \right) = \beta _j \text{, for } j = 0, 1, \cdots, k
$$

### Inclusion of Irrelevant Variables

Suppose, then, that we specify the model

$$
  lwage = \beta _0 + \beta _1 educ + \beta _2 exper 
    + \beta _3 mothexper + u 
$$

where MLR.1 through MLR.4 hold.

Suppose that \\( \beta _3 = 0 \\), but we do not know that. We estimate:

$$
  \widehat{lwage} = \hat{\beta} _0 + \hat{\beta} _1 educ + \hat{\beta} _2 exper + \hat{\beta} _3 motheDUC + u 
$$

We know from the unbiasedness result that

$$
  E \left ( \hat{\beta} _j \right) = \beta _j 
  \text{, } j = 0,1,2 \text{, and }
  E \left ( \hat{\beta} _3 \right) = 0
$$

### Omitted Variable Bias

Leaving a variable out when it should be including in multiple regression could lead to the **omitted variable bias**.

Assume that the correct model has two explanatory variables:

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2  + u
$$

But suppose we leave out \\( x _2\\) and use simple regression of *y* on \\( x _1\\).

We should have estimated

$$
 \hat{y} = \hat{\beta} _0 + \hat{\beta} _1 x _1 + \hat{\beta} _2 x _2
$$

but we estimate

$$
  \widetilde{y} = \widetilde{\beta} _0 + \widetilde{\beta} _1 x _1
$$

Recall that

$$
  \widetilde{\beta} _1 = \hat{\beta} _1 + \hat{\beta} _2 \widetilde{\delta} _1
$$

where

$$
  \hat{x} _2 = \widetilde{\delta} _0 + \widetilde{\delta} _1 x _1
$$

Conditional on the sample values of \\( x _1\\) and \\( x _2\\).

$$
  E \left( \widetilde{\beta} _1 | x \right ) 
  = E \left( \hat{\beta} _1 | x \right) 
    + \widetilde{\delta} _1 E \left( \hat{\beta} _2 | x \right) 
  = \beta _1 + \beta _2 \widetilde{   \delta} _1
$$

Bias \\( \left( \widetilde{\beta} _1 \| x \right) = E \left( \widetilde{\beta} _1 \| x \right) - \beta _1 = \beta _2 \widetilde{\delta} _1 \\)

The bias can be computed for any \\( \lbrace (x _{1i}, x _{2i}), i = 1, \cdots,n \rbrace \\), but if \\(i n \\rightarrow \infty \\) the bias will approach

$$
  \frac{Cov(x _{1i}, X _{2i})} {Var (x _{1i})} \beta _2
$$

The simple regression estimator is unbiased (for the given outcomes \\( \lbrace (x _{1i}, x _{2i}), i = 1, \cdots,n \rbrace \\) in two cases:

1. \\( \beta _2 = 0 \\) ( \\(x_2\\) does not appear in the population model),

2. \\( \widehat{Corr} (x _{1i}, x _{2i}) = 0 \\) (in the sample), entailing \\( \widetilde{\delta} _1 = 0 \\) 

### The Variance of the OLS Estimators

**Assumption MLR.5 (Homoskedasticity)**

The conditional variance of the error, ui, does not change with any of \\( x _{1i}, x _{2i}, \cdots, x _{ki} \\) :

$$
  Var( u _i | x _{1i}, x _{2i}, \cdots, x _{ki}) = Var(u _i) = \sigma ^2
$$

Assumptions MLR.1 through MLR.5 are called the **Gauss Markov
assumptions**.

**Theorem 3.2 (Sampling Variances of OLS Slope Estimators)**

Under Assumptions MLR.1 to MLR.5, and condition on the values
of the explanatory variables in the sample,

$$
  Var \left ( \hat{\beta} _ j | x \right)
  = \frac{\sigma ^2} {SST _j (1-R _j^2)}
  \text{, } j = 1, 2, \cdots, k.
$$

where

- \\( SST _j = \sum _{i=1}^n (x _{ji} - \overline{x} _j) ^2\\)

- \\( R _j^2\\) is the \\(R ^2\\) of the regression

$$
  x _{ji} \text{ on } x _{1i}, x _{2i}, \cdots, x _{j-1,i}, x _{j+1,i},\cdots, x _{k,i}
$$

- Adding explanatory variables reduces \\( \sigma ^2 \\).

- It is easier to estimate how \\( x _j \\) affects *y* if we see more variation in \\( x _j \\) , and/or *n* is large.

- If \\( x _j \\) is unrelated to all other independent variables, it is easier to estimate its ceteris paribus effect on *y*.

- As \\( R _j^2 \\rightarrow 1\text{, } Var( \hat{\beta} _j) \\rightarrow 1 \\) (the estimate of \\(\beta _j \\) is not precise).

### Variances in Misspecified Models

As for bias calculations, we can study the variances of the
OLS estimators in misspecified models.

Assume that the model

$$
  y = \beta _0 +\beta _1 x _1 + \beta _2 x _2 +u
$$

satisfies the Gauss-Markov assumptions.

We run the misspecified and the correctly specified
regressions,

$$
  \begin{array}{m}
  \widetilde{y} = \widetilde{\beta} _0 + \widetilde{\beta} _1 x _1
  \\\\ \hat{y} = \hat{\beta} _0 + \hat{\beta} _1 x _1 + \hat{\beta} _2 x _2
  \end{array}  
$$

We know from the previous analysis that

$$
  Var \left ( \hat{\beta} _ j | x \right)
  = \frac{\sigma ^2} {SST _1 (1-R _1^2)}
$$

conditional on {\\( [x _{1i}, x _{2i}]: i = 1,\cdots, n \\)}.

What about the simple regression estimator? Can show 

$$
  Var \left ( \widetilde{\beta} _ j | x \right)
  = \frac{\sigma ^2} {SST _1 }
$$

Whenever \\( x _{1i} \\) and \\( x _{2i} \\) are correlated, \\( R _1^2 > 0 \\), and

$$
  Var \left ( \widetilde{\beta} _ j | x \right)
  = \frac{\sigma ^2} {SST _1 }
  < \frac{\sigma ^2} {SST _1 (1-R _1^2)}
  < Var( \hat{\beta} _1 | x)
$$

- So, by omitting \\(x _2\\), we can in fact get an estimator with a
smaller variance, even though it is biased.

- When we look at bias and variance, we have a trade-off between simple and multiple regression.

- Conditioning on the same explanatory variables, we ignored
the difference in the variance of the error term.

- \\(\sigma ^2\\) will be higher for the simple regression model (conditioning in \\( x _1\\) only)!

### Estimating the Error Variance

**Theorem: (Unbiased Estimation of \\( \sigma ^2 \\))**

Under the Gauss-Markov assumptions (MLR.1 through MLR.5)

$$
  \hat{\sigma} ^2 
  = (n - k - 1) ^{-1} \sum _{i=1}^n \hat{u} _i^2 
  = SSR/df 
$$

is an unbiased estimation of \\( \sigma ^2 \\)

- The square root of \\( \hat{\sigma} ^2, \hat{\sigma} \\), is reported by all regression packages (**standard error of the regression**, or **RMSE**).

- Note that *SSR* falls when a new explanatory variable is added, but *df* falls, too. So \\( \hat{\sigma} \\) can increase or decrease!

### Efficiency of OLS

**THEOREM 3.4 (Gauss-Markov)**

Under Assumptions MLR.1 through MLR.5, the OLS estimators \\( \hat{\beta} _0, \hat{\beta} _1, \cdots, \hat{\beta} _k \\) are the **best linear unbiased estimators (BLUEs)**.

- Best: smaller variance

- Linear: can be expressed as a linear function of { \\(y _1, \cdots, y _n\\)},

$$
  \hat{\beta} _j = \sum _{i=1}^n w _{ji} y _i
$$

where each \\( w _{ji} \\) is a function of the sample values of all
independent variables.

### Takeaway

- Under the Gauss-Markov Assumptions the OLS estimator are
unbiased.

- Omitting relevant variables causes OLS to be biased.

- Adding irrelevant variables generally increases the variance of
the OLS estimators.

## Video 9: Potential Outcomes and Causal Effects

### Causality

- *Causality* has different means to different people.

- Researchers working in different disciplines have found it useful to think of causal relationships in terms of potential outcomes.

- The difference between these potential outcomes was said to be causal effect of the treatment.

- We saw that regression can be used to estimate the average treatment effect.

- Suppose that there are two individuals, Amy and Ben, and both have the possibility of being high-school graduates or college graduates.

- 2 possible states of the world: college and high-school graduation; 2 potential outcomes specific to each individual.

- Amy would have earned $20/hour as college graduated, $10/hour as high school graduate.

- Ben would have earned $12/hour as college graduated, $8/hour as high school graduate.

- Suppose we have a population of 32 individuals with equal numbers of Amies and Bens.

- Suppose further that the individual type is unobservable.

- The causal effect of going to college is $10 for Amy, $4 for Ben. The average causal effect is $7.

- Is this what we learn from the regression analysis?

Now suppose that while in high school all students take an aptitude test.

- If a student gets a high (*H*) score he/she goes to college with probability 3/4.

- If a student gets a low (*L*) score he/she goes to college with probability 1/4.

- Suppose further that Amy gets an aptitude score of *H* with probability 3/4. Ben gets a score of *H* with probability 1/4.

$$
  \begin{align}
    Pr(col | Amy) 
    & = Pr(col | H) Pr(H | Amy) + Pr(col | L) Pr(L | Amy)
    \\\\ & = (3/4) ^2 + (1/4) ^2 = 0.625
  \end{align}
$$

where *col* is the short for college. Similarly, \\( Pr(col \| Ben) = 0.375 \\).

![]({{site.url}}/assets/images/2020/ECON5002/distributions.png "Figure 9.1: Distributions")

- Let *col* denote a binary variable taking value 1 for a college graduate, 0 otherwise. From Table 1 we get

$$
  E[wage | col] = 8.75 + 8.25 col
$$

- $8.25 overstates the average causal effect of $7.

- $8.25 is not the *Average Causal Effect* (ACE) of attending college, but it is the observed difference in realized wages in population.

- The decision to attend college is not independent of the unobservable individual type (Amy or Ben).

- Additional education is not randomly assigned!

- To estimate the *Average Causal Effect* we need to condition on the appropriate variables.

- The decision to attend the college is based on the aptitude test score, and not on the individual type.

- Thus education and type are independent once we condition on the test score.

- Let *hscore* be a binary variable taking value 1 if the student receives a hight test score (*H*), 0 otherwise.

- Denote \\( wage _i(1), wage _i(0) \\) the potential outputs for \\( col _i = 1 \text{ and } col _i = 0 \\), respectively.

- **Conditional Independence Assumption (CIA)**

$$
  [wage _i(1), wage _i(0)] \models col _i | hscore _i
$$

- Among the students with a hight test score, 3/4 are Amies and 1/4 are Bens.

- Thus, the ACE for students with score *H* is

$$
  (3/4) \times (20 - 10) + (1/4) \times (12 - 8) = $8.5.
$$

- Among the students with a low test score, 1/4 are Amies and 3/4 are Bens.

- Thus, the ACE for students with score L is

$$
  (3/4) \times (20 - 10) + (3/4) \times (12 - 8) = $5.5.
$$

- Would we be able to learn the ACE from a regression analysis?

![]({{site.url}}/assets/images/2020/ECON5002/jointDistribution.png "Figure 9.2: Joint Distributions")

From the table above we compute

$$
  E[wage | col, hscore]
  = 8.50 + 1.00 hscore + 5.50 col + 3.00 (hscore \times col)
$$

The ACE for students with low test scores is indeed

$$
  E[wage(1) | hscore = 0] - E[wage(0) | hscore = 0] = $5.50
$$

Next we consider

$$
  E[wage(1) | hscore = 1] - E[wage(0) | hscore = 1] = $8.50
$$

Since half of the students achieve a high score test, and half a low
score test

$$
  (5.50 + 8.50) \times 1/2 = $7,
$$

that is average causal effect in the population.

Similarly, we could consider the regression model

$$
  wage(col, hscore, u) = 8.50 + 1.00 hscore + 5.50 col + 3.00 ( hscore \times col) + u
$$

If *u* and *hscore* remain fixed when *col* changes, then the causal
effect of *col* on *wage* can be computed as

$$
  wage(1, hscore, u) - wage(0, hscore, u) 
  = \begin{cases}
    $8.50 & \text{if  } hscore = 1,
    \\\\ $5.50 & \text{if } hscore = 0.
  \end{cases}
$$

Let

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2
    = \ell ( x _1, x _2, u)
$$

The causal effect of x1 on y is sometimes defined as

$$
  \nabla \ell ( x _1, x _2, u),
$$

the change in *y* due a change in \\(x _1\\), holding \\(x 21\\) and *u* constant, where

$$
  \nabla \ell ( x _1, x _2, u) =
  \begin{cases}
    \ell ( 1, x _2, u) - \ell ( 0, x _2, u) & \text{x binary}
    \\\\ \ell ( x _1 +1, x _2, u) - \ell ( x _1, x _2, u) & \text{x discrete}
    \\\\ \frac{\partial{\ell ( x _1, x _2, u) }}{\partial{x _1}} & \text{x continous}
  \end{cases}
$$

### Takeaway

- If the CIA holds, use can use the regression to estimate causal effects.

- Conditioning on the aptitude test score, education can be treated as randomly assigned.

## Video 10: Multiple Regression Analysis: Further Issues

### Models with Quadratics

- Assume we have estimated the model

$$
  \begin{array}{m}
    \widehat{lwage} = \underbrace{-.192} _{(.291)} + \underbrace{.136} _{(.011)} educ + \underbrace{.123} _{(.037)} exper - \underbrace{.0038} _{(.0017)} exper ^2
    \\\\n = 759 \text{, } R ^2 = .196
  \end{array}
$$

- The estimated return to education is 13.6%. The model assumes this is the same for all years of experience and
education.

- On average, an additional year of education increases the wage by 13.6%, regardless present level of education.

- By contrast, each year of experience is worth less than the preceding year.

- Taking the partial derivative with respect to exper, we find

$$
  \frac{\Delta \widehat{lwage}}{\Delta exper}
  \approx .123 - 2(.0038) exper 
  = .123 - .0076 exper 
  \tag{10.1}
$$

- We can think of 12:3% as approximately the return to the first year of experience { essentially starting off in the workforce.

- The return in going from 10 to 11 is about

$$
  .123 - .0076(10) = .0.47
$$

or 4.7%

- We could be more precise. Holding educ fixed

$$
  \begin{array}{l}
    \quad lwage(exp =1) -lwage(exp =10) \tag{10.2}
    \\\\ = [.123(11) - .0038(11) ^2] - [.123(10) - .0038(10)^2] = .043
  \end{array}
$$

or 4.3%, which is reasonably close.

- The quadratic function

$$
  .123 exper - 0.0038 exper ^2 \tag{10.3}
$$

turns at about 

$$
  exper ^* = .123/[2 \cdot (.0038)] \approx 16.2 \tag{10.4}
$$

- But fewer than 2% of the observations have exper > 16, so not much worry.

quadraticRelationship

![]({{site.url}}/assets/images/2020/ECON5002/quadraticRelationship.png "Figure 10.1: Quadratic relationship between lwage and experience.")

### Models with Interaction Terms

- Suppose we have two explanatory variables and start with the usual model:

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + u
$$

- The partial effect (PE) of \\(x _1\\) on y is \\(\beta _1\\) and the PE of \\(x _2\\) on y is \\(\beta _2\\).

- Sometimes it is natural to think the partial effect of one
variable, say education, could depend on the level of another variable, say intelligence.

- We add an **interaction term**, \\(x _1 x _2\\), to the usual model:

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \beta _3 x _1 x _2 + u
$$

- Holding \\(x _2\\)  (and *u*) fixed, the partial effect of \\(x _1\\)  on *y* is now

$$
  \frac{\Delta y}{\Delta x _1}
  \approx \beta _1 + \beta _3 x _2
$$

so that effect of \\(x _1\\) depends on \\(x _2\\) unless \\(\beta _3 = 0\\)

- Similarly,

$$
  \frac{\Delta y}{\Delta x _2}
  = \beta _2 + \beta _3 x _1
$$

**Example**

- Do education and IQ have an interactive effect in the ln(*wage*) equation?

$$
  \widehat{lwage} = -.762 + .195 educ + .022 IQ - . 001(educ \cdot IQ) \tag{10.6}
$$

- According to these estimates, schooling is worth more for those with lower intelligence.

$$
  \frac{\Delta \widehat{lwage}}{\Delta educ}
  \approx .195 - .001 IQ
$$

- The interpretation of the parameters on the original variables can be tricky.

- \\(\beta _1\\) would be interpreted as the effect of an additional year of education for those with *IQ* = 0.

- This effect is not of much practical interest!

### Goodness-of-Fit

- Using the same set of data and the same dependent variable, the \\(R ^2\\) can never fall when another independent variable is added to the regression.

- This means that, if we focus on \\(R ^2\\), we might include silly variables among the \\(x _j\\) .

- Adding another *x* cannot make *SSR* increase. The *SSR* falls unless the coecient on the new variable is identically zero.

- Adding regressors, decreases the number of degrees of freedom.

### Adjusted R-Squared

- Sometimes we want to compare models for the same dependent variable.

- Comparing non-nested models using the \\(R ^2\\) can be unfair if the number of regressors is different.

- The adjusted \\(R ^2\\) can be helpful in these cases.

- As usual, start with

$$
  y = \beta _0 + \beta _1 x _1 + \cdots +\beta _k x _k + u \tag{10.7}
$$

- The formula for the \\(R ^2\\) can be written as

$$
  R ^2 = 1- \frac{SSR}{SST} = 1 - \frac{SSR/n}{SST/n} \tag{10.8}
$$

- We think of \\(R ^2\\) as using *SSR/n* to estimate *Var(u)* and *SST/n* to estimate *Var(y)*.

- These estimators are consistent, i.e.

$$
  \frac{SSR}{n} \xrightarrow p Var(u), 
  \ \frac{SST}{n} \xrightarrow p Var(y),
$$

but biased.

- Instead, use

$$
  \frac{SSR}{n-k-1} \text{  and  } \frac{SST}{n-1}
$$

as the unbiased estimators.

The **adjusted R-squared** is defined as

$$
  \begin{align}
    \overline{R} ^2 
    & = 1 - \frac{[SSR / (n-k-1)]}{[SST / (n-1)]} \tag{10.9} 
    \\\\ & = 1 - \frac{\hat{\sigma} ^2}{\hat{\sigma} _y^2} \tag{10.10}
  \end{align}
$$

where \\( \hat{\sigma} ^2\\) is the usual variance parameter estimator of \\( Var(u _i) \\).

- When more regressors are added, *SSR* falls, but so does \\( df = n - k -1. \ \overline{R} ^2\\) can increase or decrease.

- For \\( k > 1, \overline{R} ^2 < R ^2 \\) (unless *SSR* = 0).

- It is possible that \\( \overline{R} ^2 < 0 \\), especially if \\(df\\) is small.

- \\( R ^2 > 0 \\) always.

### Takeaway

- Quadratic and interaction terms make the regression function more fexible but the interpretation of the parameters can be tricky.

- The adjusted R-squared penalizes for adding regressors with little explanatory power.

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

