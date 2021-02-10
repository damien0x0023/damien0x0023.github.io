---
layout: post
title: Basic Econometrics - Unit 3 Multiple Regression Analysis - Inference
subtitle: 基础计量经济学（三）
category: money
tags: [ECON5002]
---


translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 3 Multiple Regression Analysis - Inference


- **Statistical inference in the regression model**

    - Hypothesis tests about population parameters.

    - Construction of confidence intervals.

- **Sampling distributions of the OLS estimators**

    - The OLS estimators are <u><font color=red>random variables</font></u>.

    - We already know their expected values and their variances.

    - However, for hypothesis tests we need to know their <u><font color=red>distributions</font></u>.

    - In order to derive their distributions we need additional assumptions.

### Normal distribution in a nutshell

![]({{site.url}}/assets/images/2020/ECON5002/normalDis.png "Normal Distribution 1")

![]({{site.url}}/assets/images/2020/ECON5002/normalDis2.png "Normal Distribution 2")

- If \\( X \sim N(\mu, \sigma ^2) \\), then 

$$
    Z = \frac{X - \mu}{\sigma} \sim N(0,1)
$$

- Let \\( X _1, \cdots, X _n\\) be mutually independent random variable with \\( X _i \sim N(\mu _i, \sigma _i^2) \\).  
Let \\( a _1, \cdots, a _n \\) and \\( b _1, \cdots, b _n \\) be fixed constants. Then,

$$
    Y = \sum _{i=1}^n (a _i X _i + b _i ) 
    \sim N \left( \sum _{i=1}^n (a _i \mu _i + b _i ), \sum _{i=1}^n a _i^2 \sigma _i^2 \right)
$$

- \\(𝑋_1,𝑋_2 \\) are jointly normal, then they are independent **IFF** \\(𝐶ov(𝑋 _1,𝑋 _2) = 0 \\)

- **Assumption MLR.6 (Normality of error terms)**

$$
    u _i \sim N(0, \sigma ^2), \  u_i
    \text{ independent of } x _{i1}, x _{i2}, \cdots, x _{ik}
$$

![]({{site.url}}/assets/images/2020/ECON5002/mlr5.png "assumptionMLR6")

![]({{site.url}}/assets/images/2020/ECON5002/yMean.png "y Mean")

- **Discussion of the normality assumption**

    - The error term is the sum of *many* different unobserved factors.

    - Number large enough? Possibly very heterogenuous distributions of individual factors. How independent are the different factors?

    - The normality of the error term is an empirical question

    - At least the error distribution should be closeto normal

    - In many cases, normality is questionable or impossible by definition Dependent variables are positive (wages), integer (# muders)....

    - Normality might be achieved trough transformation.

![]({{site.url}}/assets/images/2020/ECON5002/simulations.png "Simulations")

- ** Discussion of the normality assumption (cont.)**

    - Ultimately, normality is maintained for convenience.

    - It allows to perform <u>exact</u> statistical inference.

    - <u>Important:</u> The assumption of normality can be replaced by a large sample size.

- **Example: the simple regression** \\( 𝒚=𝜷 _𝟎 + 𝜷 _𝟏 𝒙 + 𝒖 \\)

$$
    \hat{\beta} _1 = \sum _{i=1}^n c _i y _i, 
    \to c _i = \frac{(x _i - \overline{x})}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
$$

Note that

$$
    \hat{\beta} _1 = \sum _{i=1}^n c _i (\beta _0 + \beta _1 x _i + u _i)
    = \sum _{i=1}^n c _i u _i
$$

because

$$
    \sum _{i=1}^n c _i = 0, \text{ and }
    \sum _{i=1^n} c _i x _i =1
$$

If \\( u _i \sim N (0, \sigma ^2) \\), then

$$
    \hat{\beta} _1 | X \sim N \left (\beta _1, \frac{\sigma ^2}{\sum _{i=1}^n(x _i - \overline{x}) ^2} \right )
$$

- **Terminology**

$$
    \underbrace{MLR.1 - MLR.5} _{\text{"Gauss-Markov assumptions"}} \quad
    \underbrace{MLR.1 - MLR.6} _{\text{"Classical Linear Regression Model (CLRM) assumptions"}}
$$

- **Theorem 4.1 (Normal sampling distributions)**

Under assumptions MLR.1 –MLR.6:

![]({{site.url}}/assets/images/2020/ECON5002/underAssumptions1to6.png "Under assumptions MLR.1 - MLR.6")

![]({{site.url}}/assets/images/2020/ECON5002/NDcruves.png "Normal Distribution cruves")

- <u> **Testing hypotheses about a single population parameter** </u>

- **Theorem 4.1 (t
-distribution for standardized estimators)**

&emsp;&emsp;Under assumptions MLR.1 –MLR.6:

![]({{site.url}}/assets/images/2020/ECON5002/underAssumptions1to6_2.png "Theorem 4.1")

- **Null hypothesis (Standard in Econometric Softwares)**

![]({{site.url}}/assets/images/2020/ECON5002/nullHypothesis.png "Null hypothesis")

![]({{site.url}}/assets/images/2020/ECON5002/NDc.png "Normal Distribution cruves 2")

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
