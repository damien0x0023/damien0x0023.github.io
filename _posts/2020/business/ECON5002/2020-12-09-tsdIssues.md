---
layout: post
title: Basic Econometrics - Unit 7/A Further Issues Using OLS with Time Series Data
subtitle: 基础计量经济学（七）使用最小二乘法处理时序数据的一些问题
category: money
tags: [ECON5002]
---

translated by damien from Marco Avarucci

#  Basic Econometrics - Unit  7/A Further Issues Using OLS with Time Series Data

-   **The assumptions used so far seem to be too restricitive**
    -   Strict exogeneity, homoscedasticity, and no serial correlation are very demanding requirements, especially in the time series context.
    -   A key requirement for large sample analysis of time series is that the time series in question are stationary and weakly dependent

-   Stationary stochastic processes

A stochastic process \\(x _t: t =1,2, \cdots \\) is <u>stationary</u>, if for every collection of indices \\( 1 \le t _1 \le t _2 \le \cdots \le t _m\\) the joint distribution of (\\(x _{t _1}, x _{t _2}, \cdots, x _{t _m}\\)) is the same as that of (\\(x _{t _1 + h}, x _{t _2 +h}, \cdots, x _{t _m +h} \\)) for all integers \\(h \ge 1\\).

-   Covariance stationary processes

A stochastic process \\(x _t: t =1,2, \cdots \\) is <u>covariance stationary</u>, if its expected value, its variance, and its covariances are constant over time:

$$
    1)\ E(x _t)= \mu, \quad 2) Var(x _t) = \sigma ^2, \quad 3)Cov(x _t, x _{t+h}) = f(h)
$$

-   <u>Weakly dependent time series</u>

A stochastic process \\(x _t: t =1,2, \cdots \\) is <u>weakly dependent</u>, if \\(x _t\\) is "almost independent" of \\( x _{t+h}\\) if \\(h\\) grows to infinity (for all *t*).

-   Discussion of the weak dependence property
    -   An implication of weak dependence is that
        $$
            Cov(x _t, x _{t+h}) \to 0 \text{  as  } h \to \infty
        $$
    -   LLN and the CLT requires conditions on the dependence.

-   <U>Examples for weakly dependent time series</U>

-   Moving average process of order one (MA(1))

![]({{site.url}}/assets/images/2020/ECON5002/ma.png "Moving Average process")

    The process is weakly dependent because observations that are more than one time period apart have nothing in common and are therefore uncorrelated.

-   Autoregressive process of order one (AR(1))

![]({{site.url}}/assets/images/2020/ECON5002/autoregress.png "Auto-regressive process")

    If the stability condition \\(\|\rho _1\| < 1\\) holds, the process is weakly dependent because serial correlation converges to zero as the distance between observations grows to infinity.

-   Example: Efficient Markets Hypothesis(EMH)

The EMH in a strict form states that information observable to the market prior to week t should not help to predict the return during week t. A simplification assumes in addition that only past returns are considered as relevant information to predict the return in week t.This implies that

$$
    E(return _t | return _{t-1}, return _{t-2}, \cdots) = E (return _t)
$$

A simple way to test the EMH is to specify an AR(1) model. Under the EMH assumption,TS.3‘ holds so that an OLS regression can be used to test whether this week‘s returns depend on last week‘s.

![]({{site.url}}/assets/images/2020/ECON5002/emh.png "Efficient Markets Hypothesis")

-   <u>Asymptotic properties of OLS</u>

-   Assumption TS.1‘ (Linear in parameters)

    -   Same as assumption TS.1 but now the dependent and independent variables are assumed to be <u>stationary</u> and <u>weakly dependent</u>

-   Assumption TS.2‘ (No perfect collinearity)

    -   Same as assumption TS.2

-   Assumption TS.3‘ (Zero conditional mean)

    -   Now the explanatory variables are assumed to be only contempo-raneously exogenous rather than strictly exogenous, i.e.

![]({{site.url}}/assets/images/2020/ECON5002/AssumpTS3.png "Assumption TS.3")

-   <u>Theorem 11.1 (Consistency of OLS)</u>

$$
    TS.1' - TS.3' \quad \Rightarrow \quad plim \hat{\beta} _j = \beta _j, \quad j = 0, 1, \cdots, k
$$

<u>ortant note:</u> For consistency it would even suffice to assume that the explanatory variables are merely contemporaneously uncorrelated with the error term.

-   Why is it important to relax the strict exogeneity assumption?

    -   Discussed last week

-   **Why do lagged dependent variables violate strict exogeneity?**

![]({{site.url}}/assets/images/2020/ECON5002/lagDependentVar.png "Lagged dependent variables violate strict exogeneity")


-   **OLS estimation in the presence of lagged dependent variables**

    -   Under contemporaneous exogeneity, OLS is consistent but biased

-   Assumption TS.4‘ (Homoscedasticity)

![]({{site.url}}/assets/images/2020/ECON5002/AssumpTS4.png "Assumption TS.4")

-   Assumption TS.5‘ (No serial correlation)

![]({{site.url}}/assets/images/2020/ECON5002/AssumpTS5.png "Assumption TS.5")

-   Theorem 11.2 (Asymptotic normality of OLS)

    -   Under assumptions TS.1‘ – TS.5‘, the OLS estimators are asymptotically normally distributed. Further, the usual OLS standard errors, t-statistics and F-statistics are asymptotically valid.

-   <u>Using trend-stationary series in regression analysis</u>
    -   Time series with deterministic time trends are nonstationary
    -   If they are stationary around the trend and in addition weakly dependent, they are called trend-stationary processes
    -   Trend-stationary processes also satisfy assumption TS.1‘

-   Using highly persistent time series in regression analysis
    -   Unfortunately many economic time series violate weak dependence
    -   In this case OLS methods are generally invalid (Spurious Regression)
    -   In some cases transformations to weak dependence are possible


-   **Random walks**

![]({{site.url}}/assets/images/2020/ECON5002/randomWalks1.png "Random walks")

The value today is the accumulation of all past shocks plus an initial value. This is the reason why the random walk is highly persistent: The effect of a shock will be contained in the series forever.

![]({{site.url}}/assets/images/2020/ECON5002/randomWalks2.png "Random walks (cont.)")

-   **Examples for random walk realizations**

![]({{site.url}}/assets/images/2020/ECON5002/randomWalksRealizations.png "Random walks Realizations")

-   **Three-month T-bill rate as a possible example for a random walk**

![]({{site.url}}/assets/images/2020/ECON5002/tBillRate.png "Three-month T-bill rate")

![]({{site.url}}/assets/images/2020/ECON5002/U.S.EconTS.png "U.S. Economic Time Series")

##   **Transformations on highly persistent time series**

-   Order of integration

    -   Weakly dependent time series are integrated of order zero (= I(0))
    -   If a time series has to be <u>differenced</u> one time in order to obtain a weakly dependent series, it is called integrated of order one (= I(1))

-   Examples for I(1) processes

![]({{site.url}}/assets/images/2020/ECON5002/IProcess.png "Examples for I(1)")


<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>