---
layout: post
title: Basic Econometrics - Unit 7/B Serial Correlation in Time Series Regressions
subtitle: 基础计量经济学（七/乙）时间序列回归中的序列相关性
category: money
tags: [ECON5002]
---

translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 7/B Serial Correlation in Time Series Regressions

-   Strict exogeneity ⇒ OLS is unbiased.

-   Contemporaneous exogeneity ⇒ OLS is consistent (provided the time series are weakly dependent).

-   Unbiasedness/Consistency did not require assumptions on error autocorrelation.

-   There are situations where the nature of the \\(x _{jt}\\) mean that serial correlation in \\(u _t\\) implies that \\(u _t\\) correlated with  \\(x _{jt}\\).


##   <u>Testing for serial correlation</u>

-   **Testing for AR(1) serial correlation with <u>strictly exog. regressors</u>**


![]({{site.url}}/assets/images/2020/ECON5002/AR1.png "AR(1) serial correlation with strictly exog. regressors")

-   Large sample justification (unobservable residuals)

-   Durbin-Watson test under classical assumptions

    -   Under assumptions TS.1–TS.6, the Durbin-Watson test is an exact test (whereas the previous t-test is only valid asymptotically).

![]({{site.url}}/assets/images/2020/ECON5002/durbinWatsonTest.png "Durbin-Watson test")

![]({{site.url}}/assets/images/2020/ECON5002/durbinWatsonTest2.png "Durbin-Watson test(cont.)")

-   When strictly exogeneity does not hold, one or more \\(x_{jt}\\) might be correlated with with \\(u _{t-1}\\).

-   𝑡−test and DW test are not valid (even asymptotically)

-   Example: lagged dependent variables as regressors: \\(y_{t-1}\\) and \\(u _{t-1}\\) are obviously correlated.

-   Consider the AR(1) test.

-   **Testing for AR(1) serial correlation with general regressors**

    -   The t-test for autocorrelation can be easily generalized to allow for the possibility that the explanatory variables are not strictly exogenous:

    ![]({{site.url}}/assets/images/2020/ECON5002/AR1SerialCorrelation.png "Testing for AR(1) serial correlation")    

    -   The test may be carried out in a heteroscedasticity robust way

-   General Breusch-Godfrey test for AR(q) serial correlation

![]({{site.url}}/assets/images/2020/ECON5002/breuschGodfrey.png " Breusch-Godfrey test for AR(q) serial correlation")    

##  <u>Correcting for serial correlation with strictly exog. regressors</u>

-   Under the assumption of AR(1) errors, one can transform the model
so that it satisfies all GM-assumptions. For this model, OLS is BLUE.

![]({{site.url}}/assets/images/2020/ECON5002/correcting.png "Correcting for serial correlation")  

-   Problem: The AR(1)-coefficient is not known and has to be estimated (FGLS)

## <u>Serial correlation-robust inference after OLS</u>

-   In the presence of positive serial correlation, OLS standard errors overstate statistical significance
-   One can compute serial correlation -robust std. errors after OLS
-   This is useful because FGLS requires strict exogeneity and assumes a very specific form of serial correlation (AR(1) or, generally, AR(q))
-   Serial correlation-robust standard errors:

    ![]({{site.url}}/assets/images/2020/ECON5002/serialSEs.png "Serial correlation-robust standard errors")  

-   Serial correlation-robust F-and t-tests are also available

-   Correction factor for serial correlation (Newey-West formula)

![]({{site.url}}/assets/images/2020/ECON5002/neweyWestFormula.png "Correction factor for serial correlation")  

-   **Discussion of serial correlation-robust standard errors**

    -   he formulas are also robust to heteroscedasticity; they are therefore called "heteroscedasticity and autocorrelation consistent" (=HAC)
    -   For the integer g, values such as g=2 or g=3 are normally sufficient (there are more involved rules of thumb for how to choose g)
    -   Serial correlation-robust standard errors are only valid asymptotically; they may be severely biased if the sample size is not large enough
    -   The bias is the higher the more autocorrelation there is; if the series are highly correlated, it might be a good idea to difference them first
    -   Serial correlation-robust errors should be used if there is serial corr. and strict exogeneity fails (e.g. in the presence of lagged dep. var.)


<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

