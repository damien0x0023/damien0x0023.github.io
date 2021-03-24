---
layout: post
title: Basic Econometrics - Unit 7/B Serial Correlation in Time Series Regressions
subtitle: 基础计量经济学（七/乙）时间序列回归中的序列相关性
category: money
tags: [ECON5002]
---

translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 7/B Serial Correlation in Time Series Regressions  
&emsp;计量经济学基础 第7/乙单元 时间序列回归中的序列相关性

-   Strict exogeneity ⇒ OLS is unbiased.  
&emsp;严格的外生性⇒OLS是无偏的。

-   Contemporaneous exogeneity ⇒ OLS is consistent (provided the time series are weakly dependent).  
&emsp;同期外生性⇒OLS是一致的（前提是时间序列具有弱依赖性）。

-   Unbiasedness/Consistency did not require assumptions on error autocorrelation.  
&emsp;无偏性/一致性不需要假设误差自相关。

-   There are situations where the nature of the \\(x _{jt}\\) mean that serial correlation in \\(u _t\\) implies that \\(u _t\\) correlated with  \\(x _{jt}\\).  
&emsp;有些情况下，\\(x _{jt}\\)的性质意味着，\\(u _t\\) 中的序列相关意味着，\\(u _t\\)与\(x _{jt}\\)相关。


##   <u>Testing for serial correlation</u>  
&emsp;测试序列相关性

-   **Testing for AR(1) serial correlation with <u>strictly exog. regressors</u>**  
&emsp;**AR（1）序列相关性测试与<u>exog.回归函数</u>**


![]({{site.url}}/assets/images/2020/ECON5002/AR1.png "AR(1) serial correlation with strictly exog. regressors")

-   Large sample justification (unobservable residuals)  
&emsp;大样本调整（不可观测残差）

-   Durbin-Watson test under classical assumptions  
&emsp;经典假设下的Durbin-Watson检验

    -   Under assumptions TS.1–TS.6, the Durbin-Watson test is an exact test (whereas the previous t-test is only valid asymptotically).  
    &emsp;在假设TS.1–TS.6下，Durbin-Watson检验是精确检验（而之前的t检验仅渐近有效）。

![]({{site.url}}/assets/images/2020/ECON5002/durbinWatsonTest.png "Durbin-Watson test")

![]({{site.url}}/assets/images/2020/ECON5002/durbinWatsonTest2.png "Durbin-Watson test(cont.)")

-   When strictly exogeneity does not hold, one or more \\(x_{jt}\\) might be correlated with with \\(u _{t-1}\\).  
&emsp;当严格外生性不成立时，一个或多个\\(x_{jt}\\)可能与\\(u _{t-1}\\)相关。

-   𝑡−test and DW test are not valid (even asymptotically)  
&emsp;𝑡−检验和DW检验无效（甚至是渐近的）

-   Example: lagged dependent variables as regressors: \\(y_{t-1}\\) and \\(u _{t-1}\\) are obviously correlated.  
&emsp;例如：作为回归变量的滞后因变量：\\(y_{t-1}\\)和\\(u _{t-1}\\)有明显的相关性。

-   Consider the AR(1) test.  
&emsp;考虑AR（1）测试

-   **Testing for AR(1) serial correlation with general regressors**  
&emsp;**AR（1）序列相关性的一般回归检验**

    -   The t-test for autocorrelation can be easily generalized to allow for the possibility that the explanatory variables are not strictly exogenous:  
    &emsp;自相关的t检验可以很容易地推广，以允许解释变量不是严格的外生变量的可能性：

    ![]({{site.url}}/assets/images/2020/ECON5002/AR1SerialCorrelation.png "Testing for AR(1) serial correlation")    

    -   The test may be carried out in a heteroscedasticity robust way  
    &emsp;检验可以异方差稳健的方式进行

-   General Breusch-Godfrey test for AR(q) serial correlation  
&emsp;AR（q）序列相关的一般Breusch-Godfrey检验

![]({{site.url}}/assets/images/2020/ECON5002/breuschGodfrey.png " Breusch-Godfrey test for AR(q) serial correlation")    

##  <u>Correcting for serial correlation with strictly exog. regressors</u>  
&emsp;用严格exog回归函数校正序列相关性

-   Under the assumption of AR(1) errors, one can transform the model so that it satisfies all GM-assumptions. For this model, OLS is BLUE.  
&emsp;在AR（1）误差的假设下，可以对模型进行变换，使其满足所有GM假设。对于这个模型，OLS是蓝色的。

![]({{site.url}}/assets/images/2020/ECON5002/correcting.png "Correcting for serial correlation")  

-   Problem: The AR(1)-coefficient is not known and has to be estimated (FGLS)  
&emsp;问题：AR（1）-系数未知，必须估计（FGLS）

## <u>Serial correlation-robust inference after OLS</u>  
&emsp;OLS后的序列相关稳健推理

-   In the presence of positive serial correlation, OLS standard errors overstate statistical significance  
&emsp;在正序列相关的情况下，OLS标准差夸大了统计显著性

-   One can compute serial correlation -robust std. errors after OLS  
&emsp;我们可以在OLS之后计算序列相关稳健标准误差

-   This is useful because FGLS requires strict exogeneity and assumes a very specific form of serial correlation (AR(1) or, generally, AR(q))  
&emsp;这是有用的，因为FGLS需要严格的外生性，并假设一种非常特殊的序列相关形式（AR（1）或，通常，AR（q））

-   Serial correlation-robust standard errors:  
&emsp;序列相关稳健标准误差：

    ![]({{site.url}}/assets/images/2020/ECON5002/serialSEs.png "Serial correlation-robust standard errors")  

-   Serial correlation-robust F-and t-tests are also available  
&emsp;序列相关稳健F检验和t检验也可用

-   Correction factor for serial correlation (Newey-West formula)  
&emsp;序列相关校正系数（Newey-West公式）

![]({{site.url}}/assets/images/2020/ECON5002/neweyWestFormula.png "Correction factor for serial correlation")  

-   **Discussion of serial correlation-robust standard errors**  
&emsp;**讨论序列相关稳健标准误差**

    -   The formulas are also robust to heteroscedasticity; they are therefore called "heteroscedasticity and autocorrelation consistent" (=HAC)  
    &emsp;公式对异方差也很稳健，因此称为“异方差和自相关一致”（=HAC）

    -   For the integer g, values such as g=2 or g=3 are normally sufficient (there are more involved rules of thumb for how to choose g)  
    &emsp;对于整数g，像g=2或g=3这样的值通常就足够了（对于如何选择g，有更复杂的经验法则）

    -   Serial correlation-robust standard errors are only valid asymptotically; they may be severely biased if the sample size is not large enough  
    &emsp;序列相关稳健标准误差仅渐近有效；如果样本量不够大，它们可能会严重偏误

    -   The bias is the higher the more autocorrelation there is; if the series are highly correlated, it might be a good idea to difference them first  
    &emsp;偏差越大，自相关就越多；如果序列高度相关，最好先将它们区分开来

    -   Serial correlation-robust errors should be used if there is serial corr. and strict exogeneity fails (e.g. in the presence of lagged dep. var.)  
    &emsp;如果存在序列相关性且严格的外生性失败（例如存在滞后的dep.var），则应使用序列相关性稳健误差


<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

