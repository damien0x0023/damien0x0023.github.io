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
&emsp;**回归模型中的统计推断**

    - Hypothesis tests about population parameters.  
    &emsp;关于总体参数的假设检验。

    - Construction of confidence intervals.  
    &emsp;置信区间的构造。

- **Sampling distributions of the OLS estimators**  
&emsp;**OLS估计量的抽样分布**

    - The OLS estimators are <u><font color=red>random variables</font></u>.  
    &emsp;OLS估计量是随机变量。

    - We already know their expected values and their variances.  
    &emsp;我们已经知道了它们的期望值和方差。

    - However, for hypothesis tests we need to know their <u><font color=red>distributions</font></u>.  
    &emsp;然而，对于假设检验，我们需要知道它们的分布。

    - In order to derive their distributions we need additional assumptions.  
    &emsp;为了得到它们的分布，我们需要额外的假设。

## Normal distribution in a nutshell  
&emsp;简言之(?)，正态分布

![]({{site.url}}/assets/images/2020/ECON5002/normalDis.png "Normal Distribution 1")

![]({{site.url}}/assets/images/2020/ECON5002/normalDis2.png "Normal Distribution 2")

- If \\( X \sim N(\mu, \sigma ^2) \\), then  
&emsp;如果上式成立，那么

$$
    Z = \frac{X - \mu}{\sigma} \sim N(0,1)
$$

- Let \\( X _1, \cdots, X _n\\) be mutually independent random variable with \\( X _i \sim N(\mu _i, \sigma _i^2) \\).  Let \\( a _1, \cdots, a _n \\) and \\( b _1, \cdots, b _n \\) be fixed constants. Then,  
&emsp;设\\( X _1, \cdots, X _n\\) 与\\( X _i \sim N(\mu _i, \sigma _i^2) \\)是相互独立的随机变量。让\\( a _1, \cdots, a _n \\)与\\( b _1, \cdots, b _n \\)为固定常数。那么，

$$
    Y = \sum _{i=1}^n (a _i X _i + b _i ) 
    \sim N \left( \sum _{i=1}^n (a _i \mu _i + b _i ), \sum _{i=1}^n a _i^2 \sigma _i^2 \right)
$$

- \\(𝑋_1,𝑋_2 \\) are jointly normal, then they are independent **IFF** \\(𝐶ov(𝑋 _1,𝑋 _2) = 0 \\)  
&emsp;\\(𝑋_1,𝑋_2 \\) 是联合正态，那么他们是独立的**IFF**

- **Assumption MLR.6 (Normality of error terms)**  
&emsp;**假设MLR.6（误差项的正态性）**

$$
    u _i \sim N(0, \sigma ^2), \  u_i
    \text{ independent of } x _{i1}, x _{i2}, \cdots, x _{ik}
$$

![]({{site.url}}/assets/images/2020/ECON5002/mlr5.png "assumptionMLR6")

![]({{site.url}}/assets/images/2020/ECON5002/yMean.png "y Mean")

- **Discussion of the normality assumption**  
&emsp; **关于正态性假设的讨论**

    - The error term is the sum of *many* different unobserved factors.  
    &emsp;误差项是*许多*不同的未观察因素的总和。

    - Number large enough? Possibly very heterogenuous distributions of individual factors. How independent are the different factors?  
    &emsp;数字够大吗？个体因素的分布可能很不均匀。不同的因素有多独立？

    - The normality of the error term is an empirical question  
    &emsp;误差项的正态性是一个经验问题

    - At least the error distribution should be closeto normal  
    &emsp;至少误差分布应该接近正态分布

    - In many cases, normality is questionable or impossible by definition Dependent variables are positive (wages), integer (# muders)....  
    &emsp;在许多情况下，正态性是有问题的或不可能的定义因变量是正的（工资），整数（#muders）。。。。

    - Normality might be achieved trough transformation.  
    &emsp;正态性可以通过变换来实现。

**Simulations**  
&emsp;**模拟**

![]({{site.url}}/assets/images/2020/ECON5002/simulations.png "Simulations")

- **Discussion of the normality assumption (cont.)**  
&emsp;**关于正态性假设的讨论（续）**

    - Ultimately, normality is maintained for convenience.  
    &emsp;归根结底，为了方便而保持常态。

    - It allows to perform <u>exact</u> statistical inference.  
    &emsp;它允许执行精确的统计推断。

    - <u>Important:</u> The assumption of normality can be replaced by a large sample size.  
    &emsp;<u>重要提示</u>:正态性假设可以用大样本代替。

### Example  
&emsp;示例

- **the simple regression** \\( 𝒚=𝜷 _𝟎 + 𝜷 _𝟏 𝒙 + 𝒖 \\)  
&emsp;**简单回归**

$$
    \hat{\beta} _1 = \sum _{i=1}^n c _i y _i, 
    \to c _i = \frac{(x _i - \overline{x})}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
$$

Note that  
&emsp;注意

$$
    \hat{\beta} _1 = \sum _{i=1}^n c _i (\beta _0 + \beta _1 x _i + u _i)
    = \sum _{i=1}^n c _i u _i
$$

because  
&emsp;因为

$$
    \sum _{i=1}^n c _i = 0, \text{ and }
    \sum _{i=1^n} c _i x _i =1
$$

If \\( u _i \sim N (0, \sigma ^2) \\), then  
&emsp;如果上式成立，那么

$$
    \hat{\beta} _1 | X \sim N \left (\beta _1, \frac{\sigma ^2}{\sum _{i=1}^n(x _i - \overline{x}) ^2} \right )
$$

- **Terminology**  
&emsp;**术语**

$$
    \underbrace{MLR.1 - MLR.5} _{\text{"Gauss-Markov assumptions"}} \quad
    \underbrace{MLR.1 - MLR.6} _{\text{"Classical Linear Regression Model (CLRM) assumptions"}}
$$

- **Theorem 4.1 (Normal sampling distributions)**  
&emsp;**定理4.1（正态抽样分布）**

Under assumptions MLR.1 –MLR.6:  
&emsp;在MLR.1-6的假设下

![]({{site.url}}/assets/images/2020/ECON5002/underAssumptions1to6.png "Under assumptions MLR.1 - MLR.6")

![]({{site.url}}/assets/images/2020/ECON5002/NDcruves.png "Normal Distribution cruves")

- <u> **Testing hypotheses about a single population parameter** </u>  
&emsp;<u> **测试关于单个总体参数的假设**</u>

- **Theorem 4.1 (t-distribution for standardized estimators)**  
&emsp;**定理4.1（标准化估计的t分布）**

Under assumptions MLR.1 –MLR.6:  
&emsp;在MLR.1-6的假设下

![]({{site.url}}/assets/images/2020/ECON5002/underAssumptions1to6_2.png "Theorem 4.1")

- **Null hypothesis (Standard in Econometric Softwares)**  
&emsp;**零假设（计量经济软件中的标准）**

![]({{site.url}}/assets/images/2020/ECON5002/nullHypothesis.png "Null hypothesis")

## *T*-Distribution  
&emsp;*T*分布

![]({{site.url}}/assets/images/2020/ECON5002/NDc.png "t-Distribution cruves")

- **t-statistic (or t-ratio)**  
&emsp;**t统计（或者t-比率）**

![]({{site.url}}/assets/images/2020/ECON5002/tStatistic.png "T Statistic")

- **Distribution of the t-statistic <u>if the null hypothesis is true</u>**  
&emsp;**<u>如果零假设为真，t统计量的分布</u>**

$$
    t _{\hat{\beta} _j} = \hat{\beta} _j / se( \hat{\beta} _j )
    = ( \hat{\beta} _j - \beta _j) / se( \hat{\beta} _j )
    \sim t _{n - k -1}
$$

- **Goal: Define a rejection rule so that, if it is true, H0is rejected only with a small probability (= significance level, e.g. 5%)** 
&emsp;**目标：定义一个拒绝规则，这样，如果是真的，h0被拒绝的概率很小（=显著性水平，例如5%）**

### Examples  
&emsp;示例

-   **Example: The sample average**  
&emsp;**例子：样本平均**

![]({{site.url}}/assets/images/2020/ECON5002/sampleAverage.png "The sample average")

- **Testing against one-sided alternatives (greater than zero)**  
&emsp;**针对单向选项（大于零）进行测试**

![]({{site.url}}/assets/images/2020/ECON5002/oneSidedAlternatives.png "The sample average")

- Specifying  
&emsp;指定

$$
    H _1 : \beta _j > 0
$$

&emsp;&emsp;Means the null is effectively  
&emsp;表示空值是有效的

$$
    H _0: \beta _j \le 0
$$

- If we reject \\( \beta _j = 0\\), then we reject any \\( \beta _j < 0\\)  
&emsp;如果我们拒绝相等假设，那么我们拒绝任何负值假设。

- We usually just state \\(H _0: \beta _j = 0 \\) and act like we don't care about negative values.  
&emsp;我们通常做出如上声明，就像我们不关心负值。

- If \\(\hat{\beta} _j \le 0\\), it provides no evidence against \\(H _0 \\)  
&emsp;如果该值小于等于0，它提供不了证据对抗零假设。

- If \\(\hat{\beta} _j > 0\\), how bid does \\(t _{\hat{\beta} _j}\\) have to be before we conclude that \\(H _0\\) is unlikely?  
&emsp;如果该值大于0，在我们得出零假设不太可能之前，\\(t _{\hat{\beta} _j}\\)的出价应该是多少？

- <u>Traditional approach to hypothesis testing</u>:  
&emsp;<u> 传统的假设检验方法</u>:

1. Choose a null hypothesis, e.g. \\( H _0 : \beta _j = 0 \\)  
&emsp;选择一个无效假设，例如上述零假设。

2. Choose an alternative hypothesis, e.g. \\( H _0: \beta _j > 0 \\)  
&emsp;选择另一种假设，例如为正值。

3. Choose a significance level \\(\alpha \\)(level, size) for the test and compute the critical value \\( c _\alpha (Pr(t>c _\alpha) = \alpha)\\), so that the refection rule  
&emsp;为测试选择显著性水平\\(\alpha \\)（水平，大小）并计算临界值\\( c _\alpha (Pr(t>c _\alpha) = \alpha)\\)，以便反射规则

$$
    Reject \ \ if \ \  t _{\hat{\beta} _j}>c _\alpha
$$

&emsp;&emsp;leads to a \\( (\alpha \cdot 100) \\)% significance level.  
&emsp;&emsp;&emsp;导致\\( (\alpha \cdot 100) \\)%%显著性水平。 

- The significance level \\(\alpha\\) is the probability of rejecting the null hypothesis when it is in fact true(Type I error)  
&emsp;显著性水平\\(\alpha\\)是在事实上为真时拒绝无效假设的概率（I型错误）

- The probabilities of Type I and Type II errors cannot be minimized simultaneously.  
&emsp;类型I和类型II错误的概率不能同时最小化。

- The classic approach is to keep \\(\alpha \\) at a fairly low level(10%, 5%, 1%)  
&emsp;经典的方法是将\\(\alpha \\)保持在一个相当低的水平（10%，5%，1%）

![]({{site.url}}/assets/images/2020/ECON5002/statisticiansCorner.png "Type I and II errors")

![]({{site.url}}/assets/images/2020/ECON5002/criticalValues.png "Critical Values of the t-Distribution")

- **Example: Wage equation**  
&emsp;**示例：工资公式**

    -   Test whether, after controlling for education and tenure, higher work experience leads to higher hourly wages  
    &emsp;测试在控制了教育和任期后，更高的工作经验是否会导致更高的小时工资

![]({{site.url}}/assets/images/2020/ECON5002/wageEqu.png "Wage equation")

![]({{site.url}}/assets/images/2020/ECON5002/wageEqu2.png "Wage equation(cont.)")

<u>"The effect of experience on hourly wage is statistically greater than zero at the 5% (and even at the 1%) significance level."</u>  
&emsp;<u> “在5%（甚至1%）显著性水平上，经验对小时工资的影响在统计学上大于零。”</u>
 
- **Testing against one-sided alternatives (**less **than zero)**  
**针对单侧备选方案进行测试（**小于**小于零）**

![]({{site.url}}/assets/images/2020/ECON5002/testOneSided.png "Testing against one-sided alternatives")

- **Example: Student performance and school size**  
&emsp;**例如：学生表现和学校规模**

    -   Test whether smaller school size leads to better student performance  
    &emsp;测试较小的学校规模是否能提高学生的学习成绩

![]({{site.url}}/assets/images/2020/ECON5002/schoolSizeStudentPerformance.png "smaller school size leads to better student performance?")

![]({{site.url}}/assets/images/2020/ECON5002/schoolSizeStudentPerformance2.png "Student performance and school size (cont.)")

<u>One cannot reject the hypothesis that there is no effect of school size on student performance (not even for a large significance level of 15%). \\( \hat{\beta} _{enroll} \\) is <font color=red>statistically insignificant</font> at 15% significance level.</u>  
&emsp;<u>我们不能否认学校规模对学生成绩没有影响的假设（即使是15%的显著性水平也没有影响）。\\( \hat{\beta} _{enroll} \\)在15%显著性水平上无统计学意义。</u>

-   Alternative specification of functional form:  
&emsp;函数形式的替代规范：

![]({{site.url}}/assets/images/2020/ECON5002/alternativeForm.png "Alternative specification of functional form")

![]({{site.url}}/assets/images/2020/ECON5002/tStaCritVal.png "t-statistic and Critical value for 5% significance level")

<u>The hypothesis that there is no effect of school size on student performance can be rejected in favor of the hypothesis that the effect is negative.</u>  
&emsp;<u> 学校规模对学生成绩没有影响的假设可能会被否定，而支持消极影响的假设。</u>

![]({{site.url}}/assets/images/2020/ECON5002/effect.png "How large is the effect?")

- **Testing against two-sided alternatives**  
&emsp;**测试双面替代品**

![]({{site.url}}/assets/images/2020/ECON5002/testTwoSided.png "Testing against Two-sided alternatives")

- Example: Determinants of college GPA  
&emsp;例如：大学平均绩点的决定因素

![]({{site.url}}/assets/images/2020/ECON5002/GPADeterminants.png "Determinants of colleage GPA")

- **"Statistically significant“ variables in a regression**  
&emsp;**回归中的“统计显著”变量**

    -   If a regression coefficient is different from zero in a two-sided test, the corresponding variable is said to be "statistically significant"  
    &emsp;如果在双边检验中回归系数不同于零，则相应变量称为“统计显著性”

    -   If the number of degrees of freedom is large enough so that the normal approximation applies, the following rules of thumb apply:  
    &emsp;如果自由度的数目足够大，以致于法向近似适用，则以下经验法则适用：

    $$
        \begin{array}{l}
        |t-ratio| > 1.645 & \to \text{ "statistically significant at 10% level"}
        \\\\ |t-ratio| > 1.96 & \to \text{ "statistically significant at 5% level"}
        \\\\ |t-ratio| > 2.576 & \to \text{ "statistically significant at 1% level"}
        \end{array}
    $$

<u>Remarks:</u>  
&emsp;备注：

- Our hypothesis involve the unknown \\(\beta _j, \ j = 1, \cdots, k \\)  
&emsp;我们的假设涉及未知的\\(\beta _j, \ j = 1, \cdots, k \\)

- Assume that \\(\hat{\beta} _j = 2.75 \\). We don't write the null hypothesis as  
&emsp;假设\\(\hat{\beta} _j = 2.75 \\)。我们不把零假设写成

$$
    H _0 : 2.75 =0
$$

- Nor do we write  
&emsp;我们也不写

$$
    H _0 : \hat{\beta} _j = 0
$$

We are testing if 2.75 is likely to be a realization of a normally distribution random variable centred in \\(\beta _j \\) with variance \\(Var(\hat{\beta} _j)\\).  
&emsp;我们正在测试2.75是否可能是一个正态分布随机变量的实现，其中心为\\(\beta _j \\)，方差为\\(Var(\hat{\beta} _j)\\)。


- **Practical versus Statistical Significance**  
&emsp;**实际意义与统计意义**

    -   t-testing is purely about <u>statistical significance</u>  
    &emsp;t检验纯粹是关于统计显著性

    -   <u>*Practical(Economic) significance*</u> depends on the size and sign of \\(\hat{\beta} _j \\)  
    &emsp;实际（经济）意义取决于\\(\hat{\beta} _j \\)的大小和符号

    -   It is possible to estimate large(meaningful) economic effects but have the estimates so imprecise that they are statistically insignificant(small dataset, multicollinearity).  
    &emsp;有可能估计出大的（有意义的）经济影响，但由于估计太不精确，所以在统计上不重要（小数据集，多重共线性）。

    -   It is possible to get estimates that are statistically significant(small p-values) but are not practically large.  
    &emsp;可以得到具有统计意义（小p值）但实际上并不大的估计值。

    - Do not just fixate on *t statistics*! Interpreting the \\(\hat{\beta} _j \\) is just as important.  
    &emsp;不要只专注于*t统计数据*！解释\\(\hat{\beta} _j \\)同样重要。

-   <u>Testing more general hypotheses about a regression coefficient</u>  
&emsp;检验关于回归系数的更一般的假设

![]({{site.url}}/assets/images/2020/ECON5002/HypoCoefficient.png "Null hypothesis and t-statistic")

-   <u>**The test works exactly as before, except that the hypothesized value is substracted from the estimate when forming the statistic**</u>  
&emsp;<u>**除了在形成统计数据时从估计值中减去假设值外，测试的工作原理与之前完全相同**</u>

- **Example: Campus crime and enrollment**  
&emsp;**例如：校园犯罪和招生**

    -   An interesting hypothesis is whether crime increases by one percent if enrollment is increased by one percent  
    &emsp;一个有趣的假设是，如果入学人数增加1%，犯罪率是否会增加1%

![]({{site.url}}/assets/images/2020/ECON5002/crimeEnrollment.png "Campus crime and enrollment")

&emsp;Language:\\(\hat{\beta} _{log(enroll)}\\) is statistically different from 1 at 5% level.  
&emsp;&emsp;语言：\\(\hat{\beta} _{log(enroll)}\\) 与1在5%水平上有统计学差异。

- <u>**Computing p-values for t-tests**</u>  
&emsp;<u>**计算t检验的p值**</u>

    -   If the significance level is made smaller and smaller, there will be a point where the null hypothesis cannot be rejected anymore  
    &emsp;如果显著性水平越来越小，就会出现一个不能再拒绝无效假设的点

    -   Lowering the significance level reduces Pr(Type I err)  
    &emsp;降低显著性水平降低Pr（I型错误）

    -   <font color=red><u>Definition</u></font>:The smallest significance level at which the null hypothesis is still rejected, is called the p-valueof the hypothesis test  
    &emsp;<font color=red><u>定义</u></font>：无效假设仍被拒绝的最小显著性水平，称为假设检验的p值

    -   A small p-value is evidence against the null hypothesis because one would reject the null hypothesis even at small significance levels  
    &emsp;一个小的p值是反对无效假设的证据，因为即使在很小的显著性水平上，人们也会拒绝无效假设

    -   A large p-value is evidence in favor of the null hypothesis  
    &emsp;一个大的p值是支持无效假设的证据

    -   P-values are more informative than tests at fixed significance levels  
    &emsp;P值比固定显著性水平下的检验更具信息性

- **How the p-value is computed (here: two-sided test)**  
&emsp;**如何计算p值（此处：双边试验）**

![]({{site.url}}/assets/images/2020/ECON5002/twoSidedTest.png "How the p-value is computed in two-sided test")

- Given a *p-value*, we can carry out a test at any significance level  
&emsp;给定一个p值，我们可以在任何显著性水平上进行检验

- If \\(\alpha \\) is the chosen level, then  
&emsp;如果\\（\alpha\\）是所选级别，则

$$
    \text{Reject} H _0 \text{  if  } p-value < \alpha \text{,    Do not reject } H _0 \text{  if  } p-value > \alpha
$$

- Example: Student performance and sccol size(one sided, n=408)  
&emsp;示例：学生表现和sccol大小（单侧，n=408）

$$
    \begin{array}{m}
        t _{log(enroll)} = -1.29/.69 \approx -1.87
        \\\\ Pr(t \le -1.87) = Pr(t \ge 1.87) = 0.0307
    \end{array}
$$

&emsp;The null is rejected at 5%, it is not rejected at 1%  
&emsp;空假设在5%时被拒绝，在1%时不被拒绝

- Eviews reports two sided *p-value*. Divide by two to obtain one-sided *p-value*.  
&emsp;Eviews报告双面*p值*。除以二得到单面的*p值*。

![]({{site.url}}/assets/images/2020/ECON5002/criticalValues.png "Critical Values of the t-Distribution 2")

<u>**Confidence Intervals**</u>  
&emsp;<u> **置信区间**</u>

-   The CI (also know as interval estimate) is supposed to give a “likely” range of values for the population parameters.  
&emsp;CI（也称为区间估计）应该给出总体参数的“可能”值范围。

-   The \\(\alpha % \\) confidence interval for \\(\beta _j \\) , is of the form  
&emsp;\\（\beta\u j\\）的\\（\alpha%\\）置信区间的形式如下

$$
    \hat{\beta} _j \pm c _\alpha \cdot se(\hat{\beta} _j)
$$

-   For 95% CI, \\(c _\alpha \\) comes from the 97.5 percentile in the \\( t _{df}\\) distribution.  
&emsp;对于95%置信区间，\\（c \\ alpha\\）来自于\\（t{df}\\）分布的97.5个百分位数。

-   The width of the CI depends on precision of the estimates and confidence level.  
&emsp;置信区间的宽度取决于估计的精度和置信水平。

## F-Distribution  
&emsp;##F分布

-   Let \\(\alpha = 5%\\),  
&emsp;设\\(\alpha = 5%\\)，

![]({{site.url}}/assets/images/2020/ECON5002/CIcalc.png "Confidence Level Calculation")

-   **Interpretation of the confidence interval**  
&emsp;**置信区间的解释**

    -   The bounds of the interval are random  
    &emsp;区间的界限是随机的

    -   In repeated samples, the interval that is constructed in the above way will cover the population regression coefficient in 95% of the casess  
    &emsp;在重复样本中，用上述方法构造的区间将覆盖95%的样本的总体回归系数

-   Confidence intervals for typical confidence levels  
&emsp;典型置信水平的置信区间

![]({{site.url}}/assets/images/2020/ECON5002/typicalCI.png "CI for typical confidence levels")

-   Relationship between confidence intervals and hypotheses tests  
&emsp;置信区间与假设检验的关系

$$
    \alpha \notin interval \Rightarrow \text{reject} H _0: \beta _j = a _j \text{ in favor of } H _1 : \beta _j \neq a _j
$$

![]({{site.url}}/assets/images/2020/ECON5002/betaVal.png "values of beta")

- **Example: Model of firms‘ R&D expenditures**  
&emsp;*示例：企业研发支出模型**

![]({{site.url}}/assets/images/2020/ECON5002/RandDExpenditures.png "Firm's R&D expenditures")

-   One often sees statements such as “there is a 95%” chance that \\(\beta _{log(sales)} \\) is in the interval [0.961,1.21]  
&emsp;人们经常会看到这样的语句：“有95%的可能性，\\(\beta _{log(sales)} \\)在区间[0.961,1.21]

-   This is incorrect. \\(\beta _{log(sales)} \\)  is a fixed (unknown)value, and it either is or is not in the interval.  
&emsp;这是不正确的。\\(\beta _{log(sales)} \\)是一个固定的（未知）值，它要么在区间内，要么不在区间内。

-   For a particular sample, we don’t know whether \\(\beta _{log(sales)} \\)  is in the interval  
&emsp;对于一个特定的示例，我们不知道\\(\beta _{log(sales)} \\)是否在间隔内

-   <u>**Testing Single Linear Restrictions**</u>  
&emsp;<u>**测试单一线性限制**</u>

### Example  
&emsp;示例

-   **Return to education at 2 year vs. at 4 year colleges**  
&emsp;**2年制大学与4年制大学的回归教育**

![]({{site.url}}/assets/images/2020/ECON5002/2or4yearsEdu.png "education at 2 years vs. at 4 years colleages")

-   **Impossible to compute with standard regression output because**  
&emsp;**无法使用标准回归输出进行计算，因为**

![]({{site.url}}/assets/images/2020/ECON5002/imposCompu.png "not available in regression output")

-   **Alternative method**  
&emsp;**替代方法**

![]({{site.url}}/assets/images/2020/ECON5002/alterMethod.png "Alternative method")

-   **Estimation results**  
&emsp;**估算结果**

![]({{site.url}}/assets/images/2020/ECON5002/estRes.png "Estimation Results")

-   **This method works <u>always</u> for single linear hypotheses**  
&emsp;**这种方法对单个线性假设总是有效的**

-   <u>**Testing multiple linear restrictions: The F-test**</u>  
&emsp;<u> **测试多重线性限制：F测试**</u>  

-   **Testing exclusion restrictions**  
&emsp;**测试排除限制**

![]({{site.url}}/assets/images/2020/ECON5002/exclusionRestrictions.png "Testing exclusion restrictions")

-   **Estimation of the unrestricted model**  
&emsp;**非限制模型的预测**

![]({{site.url}}/assets/images/2020/ECON5002/unrestrictedEst.png "Estimation of the unrestricted model")

![]({{site.url}}/assets/images/2020/ECON5002/unrestrictedEst2.png "Test Statistic")

-   **Test statistic**
&emsp;**测试统计**

![]({{site.url}}/assets/images/2020/ECON5002/testStatistic.png "Estimation of the unrestricted model")

-   **Rejection rule(Figure)**  
&emsp;**拒绝规则（图）**

![]({{site.url}}/assets/images/2020/ECON5002/rejectionRule.png "Figure 4.7")

![]({{site.url}}/assets/images/2020/ECON5002/criticalValuesFDis.png "5% Critical values of the F Distribution")

![]({{site.url}}/assets/images/2020/ECON5002/FDis.png "F Distribution")

-   **Test decision in the example**  
**示例中的测试决策**

![]({{site.url}}/assets/images/2020/ECON5002/testDesicion.png "Test decision in the example")

-   **Discussion**  
&emsp;**讨论**

    -   The three variables are "jointly significant"  
    &emsp;这三个变量“共同显著”。

    -   They were not significant when tested individually. Should we conclude that none of *bavg*, *hyrunsyr*, and *rbisyr* affects baseball player salaries? NO. This could be a mistake.  
    &emsp;单独测试时，它们并不显著。我们是否应该得出这样的结论：bavg*、*hyrunsyr*和*rbisyr*都不会影响棒球运动员的工资？不，这可能是个错误。

    -   The likely reason is multicollinearity between them (STANDARD ERRORS!)  
    &emsp;可能的原因是它们之间的多重共线性（标准误差！）

    -   Corr(*hyrunsyr*,*rbisyr* )=0.89. One cannot hit a home run without getting at least one run batted in.  
    &emsp;Corr（*hyrunsyr*，*rbisyr*）=0.89。一个人不可能打出一个本垒打而不得到至少一次击球。


##  Joint Hypotheses Test  
&emsp;联合假设检验

-   We want to see how the fit deteriorates as we remove a subset of variables **(joint hypotheses test)**.  
&emsp;我们想看看当我们去掉一部分变量**（联合假设检验）**时，拟合度是如何恶化的。

-   \\(SSR _r \ge SSR _{ur} \\)(algebraic fact).  
\\(SSR _r \ge SSR _{ur} \\)（代数事实）。

-   The F-test essentially ask: does the SSR increase proportionally by enough to conclude the restrictions under \\(H _0\\) are false?  
&emsp;F检验本质上是在问：SSR是否按比例增加到足以得出结论，在\\(H _0\\)下的限制是错误的？

-   The F-statistic use a degree of freedom adjustment.  
&emsp;F统计量使用自由度调整。

-   If the null is rejected, the test will not tell us which parameter is different from zero.  
&emsp;如果null被拒绝，测试将不会告诉我们哪个参数不同于零。

-   <u>**Test of overall significance of a regression**</u>  
&emsp;<u>**回归总体显著性检验**</u>

![]({{site.url}}/assets/images/2020/ECON5002/overallSignificance.png "Test of overall significance of a regression")

-   **The test of overall significance is reported in most regression packages; the null hypothesis is usually overwhelmingly rejected**  
&emsp;*在大多数回归包中报告了总体显著性检验；无效假设通常被压倒性地拒绝**

-   <u>**Testing general linear restrictions with the F-test**</u>  
&emsp;<u>**用F-检验法检验一般线性限制条件**</u>

### Example  
&emsp;示例

-   **Test whether house price assessments are rational**  
&emsp;**检验房价评估是否合理**

![]({{site.url}}/assets/images/2020/ECON5002/rationalHousePrice.png "Test whether house price assessments are rational")

-   Regression output for the unrestricted regression  
&emsp;无限制回归的回归输出

![]({{site.url}}/assets/images/2020/ECON5002/unrestrictedRegOut.png "Regression output for the unrestricted regression")

-   Square sum restricted resduals  
&emsp;平方和限制重数

$$
    \begin{array}{l}
    x _i = log(price _i) - log(assess _i) \text{,  }
    SSR _r = \sum _{i=1}^n (x _i - \overline{x}) ^2 = 1.880
    \\\\ F = \frac{(SSR _r -SSR _{ur})/q}{SSR _{ur}/(n - k -1)} = \frac{(1.880 - 1.822)/4}{1.822/(88 - 4 -1)} \approx .661
    \\\\ F \sim F _{4,83} \Rightarrow c _0.05 = 2.50 \Rightarrow H _0 \text{  cannot be rejected}
    \end{array}
$$

-   The F-test works for general multiple linear hypotheses  
&emsp;F检验适用于一般多重线性假设

-   For all tests and confidence intervals, validity of assumptions MLR.1 –MLR.6 has been assumed. Tests may be invalid otherwise.  
&emsp;对于所有测试和置信区间，假设MLR.1–MLR.6的有效性已被假定。否则测试可能无效。

-   <u>**F- and t-statistics**</u>  
&emsp;<u>**F-和t-统计**</u>

    -   If \\( q=1, F = t ^2\\)

    -   The *t-test* is more transparent and allows one-sided alternatives  
    &emsp;t检验更为透明，允许单边选择

-   **\\(\underline{R ^2 \text{ form of the } F-statistic}\\)**

    -   Assume that the same dependent variable is used in two regressions  
    &emsp;假设在两个回归中使用相同的因变量

    -   \\( SSR _r = (1-R _r^2)SST \text{,   } SSR _{ur} = (1 - R _{ur}^2) SST\\)

$$
    F = \frac{(R _{ur}^2 - R _r^2)/q}{(1-R _{ur}^2)/(n - k -1)}
$$

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
