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

### <u>White test for heteroscedasticity</u>

![]({{site.url}}/assets/images/2020/ECON5002/whiteTest.png "White test")

- **Disadvantage of this form of the White test**

  - Including all squares and interactions leads to a large number of esti-mated parameters (e.g. k=6 leads to 27 parameters to be estimated)

- **Alternative form of the White test**

![]({{site.url}}/assets/images/2020/ECON5002/alterWhiteTest.png "Alternative White test")

- **Example:**

**Heteroscedasticity in (log) housing price equations**

$$
  R _{\hat{u} ^2}^2 = .0392, LM = 88(.0392) 
  \approx 3.45, p-value _{LM} = .178
$$

### <u>Weighted least squares estimation</u>

- Heteroscedasticity is known up to a multiplicative constant

![]({{site.url}}/assets/images/2020/ECON5002/multiCons.png "multiplicative constant")

- **Example:**

**Savings and income**

![]({{site.url}}/assets/images/2020/ECON5002/savIncome.png "Savings and Income")

- **The transformed model is homoscedastic**

$$
  E(u _i^{*2} | X _i) = E \left [(\frac{u _i}{\sqrt{h _i}}) ^2 | X _i \right]
  = \frac{E(u _i^2 | X)}{h _i}
  = \frac{\sigma ^2 h _i}{h _i} = \sigma ^2 
$$


**If the other Gauss-Markov assumptions hold as well, <u>OLS applied to the transformed model</u> is the best linear unbiased estimator!**

- **OLS in the transformed model is weighted least squares (WLS)**

![]({{site.url}}/assets/images/2020/ECON5002/wls.png "Weighted least squares (WLS)")

- **Why is WLS more efficient than OLS in the original model?**

  - Observations with a large variance are less informative than observa-tions with small variance and therefore should get less weight

- **WLS is a special case of generalized least squares (GLS)**

- **Example:**

**Financial wealth equation**

![]({{site.url}}/assets/images/2020/ECON5002/finWeaEqu.png "Financial wealth equation")

- **Important special case of heteroscedasticity**

  - If the observations are reported as averages at the city/county/state/-country/firm level, they should be weighted by the size of the unit

![]({{site.url}}/assets/images/2020/ECON5002/specCase.png "Important special case of heteroscedasticity")

If errors are homoscedastic at the employee level, WLS with weights equal to firm size mi should be used. If the assumption of homoscedasticity at the employee level is not exactly right, one can calculate robust standard errors after WLS (i.e. for the transformed model).

- **Unknown heteroscedasticity function (feasible GLS)**

![]({{site.url}}/assets/images/2020/ECON5002/feasiableGLS.png "Unknown heteroscedasticity function")

<u>Feasible GLS is consistent and asymptotically more efficient than OLS.</u>

- **Example:**

**Demand for cigarettes**

- **Estimation by OLS**

![]({{site.url}}/assets/images/2020/ECON5002/OLSest.png "Demand Estimation for cigarettes by OLS")

- **Estimation by FGLS**

![]({{site.url}}/assets/images/2020/ECON5002/FGLSest.png "Demand Estimation for cigarettes by FGLS")

- **Discussion**

  - The income elasticity is now statistically significant; other coefficients are also more precisely estimated (without changing qualit. results)

- <u>What if the assumed heteroscedasticity function is wrong?</u>

  - WLS is still consistent under MLR.1 – MLR.4
  - Robust standard errors should be computed.
  - How can we adjust the standard error to heteroskedasticity of unknown form?

- Consider the bivariate model

$$
  y _i = \beta _0 + \beta _1 x _i + u _i, \quad \hat{\beta} _1 
    = \frac{\sum _{i=1}^n (y _i - \overline{y})(x _i - \overline{x})}  {\sum _{i=1}^n (x _i - \overline{x})^2}
$$

- We proved that

$$
  \hat{\beta} _1 = \beta _1 + \frac{\sum _{i=1}^n (x _i - \overline{x}) u _i}{\sum _{i=1}^n (x _i - \overline{x})^2}
$$

and, conditional to *X*

$$
  Var(\hat{\beta} _1) = \frac {\sum _{i=1}^n (x _i - \overline{x})^2 E(u _i^2)} {\left [\sum _{i=1}^n (x _i - \overline{x})^2 \right]^2} 
$$

**White's Heteroscedasticity-robust standard variance**

$$
  \widehat{Var(\hat{\beta} _1) } _{HC} = \frac {\sum _{i=1}^n (x _i - \overline{x})^2 \hat{u} _i^2} {\left [\sum _{i=1}^n (x _i - \overline{x})^2 \right]^2} 
$$

  - HC stands for “Heteroscedasticity Consistent”.
  - It is a valid estimator in the presence of heteroscedasticity of any form (including homoscedasticity).
<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>