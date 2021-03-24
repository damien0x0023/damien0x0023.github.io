---
layout: post
title: Basic Econometrics - Unit 7/A Further Issues Using OLS with Time Series Data
subtitle: 基础计量经济学（七/甲）使用最小二乘法处理时序数据的一些问题
category: money
tags: [ECON5002]
---

translated by damien from Marco Avarucci

#  Basic Econometrics - Unit  7/A Further Issues Using OLS with Time Series Data  
&emsp;计量经济学基础-第7/甲单元 使用OLS和时间序列数据的进一步问题

-   **The assumptions used so far seem to be too restricitive**  
&emsp;**目前使用的假设似乎过于严格**

    -   Strict exogeneity, homoscedasticity, and no serial correlation are very demanding requirements, especially in the time series context.  
    &emsp;严格的外生性、同质性和无序列相关性是非常苛刻的要求，特别是在时间序列环境中。

    -   A key requirement for large sample analysis of time series is that the time series in question are stationary and weakly dependent  
    &emsp;时间序列的大样本分析的一个关键要求是所讨论的时间序列是平稳的和弱相依的

-   Stationary stochastic processes  
&emsp;平稳随机过程

A stochastic process \\(x _t: t =1,2, \cdots \\) is <u>stationary</u>, if for every collection of indices \\( 1 \le t _1 \le t _2 \le \cdots \le t _m\\) the joint distribution of (\\(x _{t _1}, x _{t _2}, \cdots, x _{t _m}\\)) is the same as that of (\\(x _{t _1 + h}, x _{t _2 +h}, \cdots, x _{t _m +h} \\)) for all integers \\(h \ge 1\\).  
&emsp;一个随机过程\\(x _t: t =1,2, \cdots \\)是平稳的，如果对每一个指数集合\\( 1 \le t _1 \le t _2 \le \cdots \le t _m\\), (\\(x _{t _1}, x _{t _2}, \cdots, x _{t _m}\\))的联合分布，与 (\\(x _{t _1 + h}, x _{t _2 +h}, \cdots, x _{t _m +h} \\))在所有整数\\(h \ge 1\\)上的联合分布相同。

-   Covariance stationary processes  
&emsp;协方差平稳过程

A stochastic process \\(x _t: t =1,2, \cdots \\) is <u>covariance stationary</u>, if its expected value, its variance, and its covariances are constant over time:  
&emsp;一个随机过程\\(x _t: t =1,2, \cdots \\)是协方差平稳的，如果它的期望值、方差和协方差随时间是常数：

$$
    1)\ E(x _t)= \mu, \quad 2) Var(x _t) = \sigma ^2, \quad 3)Cov(x _t, x _{t+h}) = f(h)
$$

##   <u>Weakly dependent time series</u>  
&emsp;弱相依时间序列

A stochastic process \\(x _t: t =1,2, \cdots \\) is <u>weakly dependent</u>, if \\(x _t\\) is "almost independent" of \\( x _{t+h}\\) if \\(h\\) grows to infinity (for all *t*).  
&emsp;随机过程\\(x _t: t =1,2, \cdots \\)是弱相依的，如果 \\(x _t\\)几乎独立于\\( x _{t+h}\\)，如果 \\(h\\)增长到无穷大（对于所有*t*）。

-   Discussion of the weak dependence property  
&emsp;弱相依性的讨论

    -   An implication of weak dependence is that  
    &emsp;弱依赖的一个含义是

        $$
            Cov(x _t, x _{t+h}) \to 0 \text{  as  } h \to \infty
        $$

    -   LLN and the CLT requires conditions on the dependence.  
    &emsp;LLN和CLT需要依赖的条件。

###   <U>Examples for weakly dependent time series</U>  
&emsp;Examples for weakly dependent time series

-   Moving average process of order one (MA(1))  
&emsp;一阶滑动平均过程（MA（1））

![]({{site.url}}/assets/images/2020/ECON5002/ma.png "Moving Average process")

The process is weakly dependent because observations that are more than one time period apart have nothing in common and are therefore uncorrelated.  
&emsp;这个过程是弱相关的，因为相隔超过一个时间段的观测没有共同点，因此不相关。

-   Autoregressive process of order one (AR(1))  
&emsp;一阶自回归过程（AR（1））

![]({{site.url}}/assets/images/2020/ECON5002/autoregress.png "Auto-regressive process")

If the stability condition \\(\|\rho _1\| < 1\\) holds, the process is weakly dependent because serial correlation converges to zero as the distance between observations grows to infinity.  
&emsp;如果稳定条件\\(\|\rho _1\| < 1\\)成立，则过程是弱相关的，因为序列相关性随着观测值之间的距离增大而收敛到零。
 
-   Example: Efficient Markets Hypothesis(EMH)  
&emsp;例如：有效市场假说（EMH）

The EMH in a strict form states that information observable to the market prior to week t should not help to predict the return during week t. A simplification assumes in addition that only past returns are considered as relevant information to predict the return in week t.This implies that  
&emsp;有效市场假说以严格的形式指出，t周之前市场观察到的信息不应有助于预测t周的收益率。此外，简化假设只有过去的收益率被视为预测t周收益率的相关信息。这意味着

$$
    E(return _t | return _{t-1}, return _{t-2}, \cdots) = E (return _t)
$$

A simple way to test the EMH is to specify an AR(1) model. Under the EMH assumption,TS.3‘ holds so that an OLS regression can be used to test whether this week‘s returns depend on last week‘s.  
&emsp;检验有效市场假说的一个简单方法是指定AR（1）模型。在有效市场假说下，TS.3'成立，因此OLS回归可用于检验本周收益率是否依赖于上周收益率。
 
![]({{site.url}}/assets/images/2020/ECON5002/emh.png "Efficient Markets Hypothesis")

##   <u>Asymptotic properties of OLS</u>  
&emsp;OLS的渐近性质

-   Assumption TS.1‘ (Linear in parameters)  
&emsp;假设TS.1'（参数线性）

    -   Same as assumption TS.1 but now the dependent and independent variables are assumed to be <u>stationary</u> and <u>weakly dependent</u>  
    &emsp;与假设TS.1相同，但现在假设因变量和自变量是<u>平稳的</u>和<u>弱相依的</u>

-   Assumption TS.2‘ (No perfect collinearity)  
&emsp;假设TS.2'（无完全共线）

    -   Same as assumption TS.2  
    &emsp;与假设TS.2相同

-   Assumption TS.3‘ (Zero conditional mean)  
&emsp;假设TS.3'（零条件平均值）

    -   Now the explanatory variables are assumed to be only contempo-raneously exogenous rather than strictly exogenous, i.e.  
    &emsp;现在的解释变量被假定为仅是同时代的外生变量而不是严格的外生变量，即。

![]({{site.url}}/assets/images/2020/ECON5002/AssumpTS3.png "Assumption TS.3")

-   <u>Theorem 11.1 (Consistency of OLS)</u>  
&emsp;定理11.1（OLS的一致性）

$$
    TS.1' - TS.3' \quad \Rightarrow \quad plim \hat{\beta} _j = \beta _j, \quad j = 0, 1, \cdots, k
$$

<u>important note:</u> For consistency it would even suffice to assume that the explanatory variables are merely contemporaneously uncorrelated with the error term.  
&emsp;<u> 重要提示：</u>为了保持一致性，假设解释变量只是与错误项同时不相关就足够了。

-   Why is it important to relax the strict exogeneity assumption?  
&emsp;为什么放松严格的外生假设很重要？

    -   Discussed last week  
    &emsp;上周讨论过

-   **Why do lagged dependent variables violate strict exogeneity?**  
&emsp;**为什么滞后因变量违反严格的外生性？**

![]({{site.url}}/assets/images/2020/ECON5002/lagDependentVar.png "Lagged dependent variables violate strict exogeneity")


-   **OLS estimation in the presence of lagged dependent variables**  
&emsp;**存在滞后因变量时的OLS估计**

    -   Under contemporaneous exogeneity, OLS is consistent but biased  
    &emsp;在同生外源性条件下，OLS是一致的，但有一定的偏误

-   Assumption TS.4‘ (Homoscedasticity)  
&emsp;假设TS.4'（同方差）

![]({{site.url}}/assets/images/2020/ECON5002/AssumpTS4.png "Assumption TS.4")

-   Assumption TS.5‘ (No serial correlation)  
&emsp;假设TS.5'（无序列相关）

![]({{site.url}}/assets/images/2020/ECON5002/AssumpTS5.png "Assumption TS.5")

-   Theorem 11.2 (Asymptotic normality of OLS)  
&emsp;定理11.2（OLS的渐近正态性）

    -   Under assumptions TS.1‘ – TS.5‘, the OLS estimators are asymptotically normally distributed. Further, the usual OLS standard errors, t-statistics and F-statistics are asymptotically valid.  
    &emsp;在假设TS.1'-TS.5'下，OLS估计是渐近正态分布的。此外，通常的OLS标准差、t统计量和F统计量是渐近有效的。

-   <u>Using trend-stationary series in regression analysis</u>  
&emsp;在回归分析中使用趋势平稳序列

    -   Time series with deterministic time trends are nonstationary  
    &emsp;具有确定性时间趋势的时间序列是非平稳的

    -   If they are stationary around the trend and in addition weakly dependent, they are called trend-stationary processes  
    &emsp;如果它们在趋势周围是平稳的，并且是弱相依的，则称为趋势平稳过程

    -   Trend-stationary processes also satisfy assumption TS.1‘  
    &emsp;趋势平稳过程也满足假设TS.1'

-   Using highly persistent time series in regression analysis  
&emsp;高持久性时间序列在回归分析中的应用

    -   Unfortunately many economic time series violate weak dependence  
    &emsp;不幸的是，许多经济时间序列具有弱依赖性

    -   In this case OLS methods are generally invalid (Spurious Regression)  
    &emsp;在这种情况下，OLS方法通常无效（伪回归）

    -   In some cases transformations to weak dependence are possible  
    &emsp;在某些情况下，可能转换为弱依赖


##   **Random walks**  
&emsp;**随机行走**

![]({{site.url}}/assets/images/2020/ECON5002/randomWalks1.png "Random walks")

The value today is the accumulation of all past shocks plus an initial value. This is the reason why the random walk is highly persistent: The effect of a shock will be contained in the series forever.  
&emsp;今天的价值是过去所有冲击的累积加上一个初始值。这就是为什么随机游走是高度持久的：冲击的影响将永远包含在这个系列中。

![]({{site.url}}/assets/images/2020/ECON5002/randomWalks2.png "Random walks (cont.)")

-   **Examples for random walk realizations**  \
&emsp;**随机游走实现示例**

![]({{site.url}}/assets/images/2020/ECON5002/randomWalksRealizations.png "Random walks Realizations")

-   **Three-month T-bill rate as a possible example for a random walk**  
&emsp;**以三个月期国库券利率作为随机游走的一个可能例子**

![]({{site.url}}/assets/images/2020/ECON5002/tBillRate.png "Three-month T-bill rate")

![]({{site.url}}/assets/images/2020/ECON5002/U.S.EconTS.png "U.S. Economic Time Series")

##   **Transformations on highly persistent time series**  
&emsp;**高持久时间序列的转换**


-   Order of integration  
&emsp;整合顺序

    -   Weakly dependent time series are integrated of order zero (= I(0))  
    &emsp;弱相关时间序列是零阶积分（=I（0））

    -   If a time series has to be <u>differenced</u> one time in order to obtain a weakly dependent series, it is called integrated of order one (= I(1))  
    &emsp;如果时间序列必须<u>差分</u>一次才能获得弱依赖序列，则称为一阶积分（=I（1））

-   Examples for I(1) processes  
&emsp;I（1）过程的示例

![]({{site.url}}/assets/images/2020/ECON5002/IProcess.png "Examples for I(1)")


<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>