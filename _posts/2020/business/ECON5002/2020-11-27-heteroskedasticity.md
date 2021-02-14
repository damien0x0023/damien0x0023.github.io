---
layout: post
title: Basic Econometrics - Unit 5 Heteroskedasticity 
subtitle: 基础计量经济学（五）异方差性
category: money
tags: [ECON5002]
---

translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 5 Heteroskedasticity 

-   Heteroscedasticity:

$$
    Var(u | x _1, x _2, \cdots, x _k) \neq Var(u)
$$

MLR.5 is violated.

-   **Example (Saving and Income):**

when incomes grow, people have more discretionary income and hence more scope for choice about the disposition about their income.

-   OLS is still unbiased and consistent under MLR.1-MLR.4.

-   MLR.5 was not used to obtain either of these properties.

-   OLS can used to estimate the parameters of the linear model.

-   The \\(R ^2\\) (and \\(\overline{R} ^2\\)) remain consistent estimators of the population counterparts (\\(SSR/n \to \sigma _u^2\\) whether or not \\(Var(u) = Var(u || x) \\) )

![]({{site.url}}/assets/images/2020/ECON5002/rSquare.png "R squared")

## <u>Consequences of heteroscedasticity for OLS (inference)</u>

-   Heteroscedasticity invalidates variance formulas for OLS estimators

-   t-tests and confidence intervals cannot be trusted under heteroscedasticity (even in large samples!)

-   Joint hypotheses tests using the usual *𝐹* are no longer valid in presence of heteroscedasticity (for any *𝑛*)

-   Under heteroscedasticity, OLS is no longer the best linear unbiased estimator (BLUE); there may be more efficient linear estimators

-   Witout MLR.5, there are still good reasons to use OLS, but we need to modify the usual test statistics to make them valid in the presence of heteroskedasticity.

-   We are not talking about a new estimation method. It is still OLS estimation to obtain the β \\(\hat{\beta} _j \\), but we need to use **heteroskedasticity-robust inference** after OLS estimation.

-   Fortunately, standard errors and all test statistics can be modified to be valid in the presence of **heteroskedasticity of unknown form**.

-   This includes the possibility of homoskedasticity. So we can compute CIs and conduct statistical inference without worrying about whether MLR.5 holds.

-   Most regression packages include an option with OLS estimation that computes **heteroskedasticity-robust standard errors**, which then produces **h.r.** ***t*** **statistics** and **h.r. C.I.s**.

-   The heteroskedasticity-robust test statistics and CIs only have asymptotic justification, even if the full set of CLM assumptions hold.

-   With smaller sample sizes, the heteroskedasticity-robust statistics might be more biased than the usual statistics.

-   Example:


**Hourly wage equation**

![]({{site.url}}/assets/images/2020/ECON5002/hourWage.png "hourly wage equation")

## <u>Testing for heteroscedasticity</u>

We start with the linear model

$$
    y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \cdots + \beta _k x _k + u
$$

and assume that MLR.1-MLR4 hold true.

-   **Breusch-Pagan test for heteroscedasticity**

![]({{site.url}}/assets/images/2020/ECON5002/breuschPagan1.png "Breusch-Pagan Test I")

![]({{site.url}}/assets/images/2020/ECON5002/breuschPagan2.png "Breusch-Pagan Test II")

**Steps in Computing the Breusch-Pagan Test**

1.  Estimate the equation \\(  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \cdots + \beta _k x _k + u \\) by OLS, saving the OLS residuals, \\(\hat{u} _i \\). Compute the squared residuals, \\(\hat{u} _i^2 \\). (There is a squared residual for each of the *n* observations.)

2.  Regress \\(\hat{u} _i^2 \\) on all explanatory variables and compute the usual *F* test of joint significance of the explanatory variables.

3.  If the *p*-value of the test in step 2 is sufficiently small, reject the null of homoskedasticity and conclude Assumption MLR.5 fails.

-   Example:

**Heteroscedasticity in housing price equations**

![]({{site.url}}/assets/images/2020/ECON5002/heteroscedasticityHousingPrice.jpg "Heteroskedasticity in housing price equations")














<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>