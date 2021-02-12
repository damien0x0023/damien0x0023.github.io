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

## Normal distribution in a nutshell

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

## Simulations

![]({{site.url}}/assets/images/2020/ECON5002/simulations.png "Simulations")

- **Discussion of the normality assumption (cont.)**

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

### T-distribution

![]({{site.url}}/assets/images/2020/ECON5002/NDc.png "t-Distribution cruves")

- **t-statistic (or t-ratio)**

![]({{site.url}}/assets/images/2020/ECON5002/tStatistic.png "T Statistic")

- **Distribution of the t-statistic <u>if the null hypothesis is true</u>** 

$$
    t _{\hat{\beta} _j} = \hat{\beta} _j / se( \hat{\beta} _j )
    = ( \hat{\beta} _j - \beta _j) / se( \hat{\beta} _j )
    \sim t _{n - k -1}
$$

- **<u>Goal</u>: Define a rejection rule so that, if it is true, H0is rejected only with a small probability (= significance level, e.g. 5%)**

### An Example: The sample average

![]({{site.url}}/assets/images/2020/ECON5002/sampleAverage.png "The sample average")

- **Testing against one-sided alternatives (greater than zero)**

![]({{site.url}}/assets/images/2020/ECON5002/oneSidedAlternatives.png "The sample average")

- Specifying

$$
    H _1 : \beta _j > 0
$$

&emsp;&emsp;Means the null is effectively

$$
    H _0: \beta _j \le 0
$$

- If we reject \\( \beta _j = 0\\), then we reject any \\( \beta _j < 0\\)

- We usually just state \\(H _0: \beta _j = 0 \\) and act like we don't care about negative values.

- If \\(\hat{\beta} _j \le 0\\), it provides no evidence against \\(H _0 \\)

- If \\(\hat{\beta} _j > 0\\), how bid does \\(t _{\hat{\beta} _j}\\) have to be before we conclude that \\(H _0\\) is unlikely?

- <u>Traditional approach to hypothesis testing</u>:

1. Choose a null hypothesis, e.g. \\( H _0 : \beta _j = 0 \\)

2. Choose an alternative hypothesis, e.g. \\( H _0: \beta _j > 0 \\)

3. Choose a significance level \\(\alpha \\)(level, size) for the test and compute the critical value \\( c _\alpha (Pr(t>c _\alpha) = \alpha)\\), so that the refection rule

$$
    Reject \ \ if \ \  t _{\hat{\beta} _j}>c _\alpha
$$

&emsp;&emsp;leads to a\\( (\alpha \cdot 100) \\)% significance level.

- The significance level \\(\alpha\\) is the probability of rejecting the null hypothesis when it is in fact true(Type I error)

- The probabilities of Type I and Type II errors cannot be minimized simultaneously.

- The classic approach is to keep \\(\alpha \\) at a fairly low level(10%, 5%, 1%)

![]({{site.url}}/assets/images/2020/ECON5002/statisticiansCorner.png "Type I and II errors")

![]({{site.url}}/assets/images/2020/ECON5002/criticalValues.png "Critical Values of the t-Distribution")

- **Example: Wage equation**

    -   Test whether, after controlling for education and tenure, higher work experience leads to higher hourly wages

![]({{site.url}}/assets/images/2020/ECON5002/wageEqu.png "Wage equation")

![]({{site.url}}/assets/images/2020/ECON5002/wageEqu2.png "Wage equation(cont.)")

<u>"The effect of experience on hourly wage is statistically greater than zero at the 5% (and even at the 1%) significance level."</u>

- **Testing against one-sided alternatives (**less **than zero)**

![]({{site.url}}/assets/images/2020/ECON5002/testOneSided.png "Testing against one-sided alternatives")

- **Example: Student performance and school size**

    -   Test whether smaller school size leads to better student performance

![]({{site.url}}/assets/images/2020/ECON5002/schoolSizeStudentPerformance.png "smaller school size leads to better student performance?")

![]({{site.url}}/assets/images/2020/ECON5002/schoolSizeStudentPerformance2.png "Student performance and school size (cont.)")

<u>One cannot reject the hypothesis that there is no effect of school size on student performance (not even for a large significance level of 15%). \\( \hat{\beta} _{enroll} \\) is <font color=red>statistically insignificant</font> at 15% significance level.</u>

-   Alternative specification of functional form:

![]({{site.url}}/assets/images/2020/ECON5002/alternativeForm.png "Alternative specification of functional form")

![]({{site.url}}/assets/images/2020/ECON5002/tStaCritVal.png "t-statistic and Critical value for 5% significance level")

<u>The hypothesis that there is no effect of school size on student performance can be rejected in favor of the hypothesis that the effect is negative.</u>

![]({{site.url}}/assets/images/2020/ECON5002/effect.png "How large is the effect?")

- **Testing against two-sided alternatives**

![]({{site.url}}/assets/images/2020/ECON5002/testTwoSided.png "Testing against Two-sided alternatives")

- Example: Determinants of college GPA

![]({{site.url}}/assets/images/2020/ECON5002/GPADeterminants.png "Determinants of colleage GPA")

- **"Statistically significant“ variables in a regression**

    -   If a regression coefficient is different from zero in a two-sided test, the corresponding variable is said to be "statistically significant"

    -   If the number of degrees of freedom is large enough so that the normal approximation applies, the following rules of thumb apply:

    $$
        \begin{array}{l}
        |t-ratio| > 1.645 & \to \text{ "statistically significant at 10% level"}
        \\\\ |t-ratio| > 1.96 & \to \text{ "statistically significant at 5% level"}
        \\\\ |t-ratio| > 2.576 & \to \text{ "statistically significant at 1% level"}
        \end{array}
    $$

<u>Remarks:</u>

- Our hypothesis involve the unknown \\(\beta _j, \ j = 1, \cdots, k \\)

- Assume that \\(\hat{\beta} _j = 2.75 \\). We don't write the null hypothesis as

$$
    H _0 : 2.75 =0
$$

- Nor do we write 

$$
    H _0 : \hat{\beta} _j = 0
$$

We are testing if 2.75 is likely to be a realization of a normally distribution random variable centred in \\(\beta _j \\) with variance \\(Var(\hat{\beta} _j)\\).


- **Practical versus Statistical Significance**
    -   t-testing is purely about <u>statistical significance</u>
    -   <u>*Practical(Economic) significance*</u> depends on the size and sign of \\(\hat{\beta} _j \\)
    -   It is possible to estimate large(meaningful) economic effects but have the estimates so imprecise that they are statistically insignificant(small dataset, multicollinearity).
    -   It is possible to get estimates that are statistically significant(small p-values) but are not practically large.
    - Do not just fixate on *t statistics*! Interpreting the \\(\hat{\beta} _j \\) is just as important.

-   <u>Testing more general hypotheses about a regression coefficient</u>

![]({{site.url}}/assets/images/2020/ECON5002/HypoCoefficient.png "Null hypothesis and t-statistic")

-   <u>**The test works exactly as before, except that the hypothesized value is substracted from the estimate when forming the statistic**</u>

- **Example: Campus crime and enrollment**

    -   An interesting hypothesis is whether crime increases by one percent if enrollment is increased by one percent

![]({{site.url}}/assets/images/2020/ECON5002/crimeEnrollment.png "Campus crime and enrollment")

&emsp;Language:\\(\hat{\beta} _{log(enroll)}\\) is statistically different from 1 at 5% level.

- <u>**Computing p-values for t-tests**</u>
    -   If the significance level is made smaller and smaller, there will be a point where the null hypothesis cannot be rejected anymore
    -   Lowering the significance level reduces Pr(Type I err)
    -   <font color=red><u>Definition</u></font>:The smallest significance level at which the null hypothesis is still rejected, is called the p-valueof the hypothesis test
    -   A small p-value is evidence against the null hypothesis because one would reject the null hypothesis even at small significance levels
    -   A large p-value is evidence in favor of the null hypothesis 
    -   P-values are more informative than tests at fixed significance levels

- **How the p-value is computed (here: two-sided test)**

![]({{site.url}}/assets/images/2020/ECON5002/twoSidedTest.png "How the p-value is computed in two-sided test")

- Given a *p-value*, we can carry out a test at any significance level 

- If \\(\alpha \\) is the chosen level, then

$$
    \text{Reject} H _0 \text{  if  } p-value < \alpha \text{,    Do not reject } H _0 \text{  if  } p-value > \alpha
$$

- Example: Student performance and sccol size(one sided, n=408)

$$
    \begin{array}{m}
        t _{log(enroll)} = -1.29/.69 \approx -1.87
        \\\\ Pr(t \le -1.87) = Pr(t \ge 1.87) = 0.0307
    \end{array}
$$

&emsp;The null is rejected at 5%, it is not rejected at 1%

- Eviews reports two sided *p-value*. Divide by two to obtain one-sided *p-value*.

![]({{site.url}}/assets/images/2020/ECON5002/criticalValues.png "Critical Values of the t-Distribution 2")

<u>**Confidence Intervals**</u>

-   The CI (also know as interval estimate) is supposed to give a “likely” range of values for the population parameters.

-   The \\(\alpha % \\) confidence interval for \\(\beta _j \\) , is of the form

$$
    \hat{\beta} _j \pm c _\alpha \cdot se(\hat{\beta} _j)
$$

-   For 95% CI, \\(c _\alpha \\) comes from the 97.5 percentile in the \\( t _{df}\\) distribution.

-   The width of the CI depends on precision of the estimates and confidence level.

-   Let \\(\alpha = 5%\\),

![]({{site.url}}/assets/images/2020/ECON5002/CIcalc.png "Confidence Level Calculation")

-   **Interpretation of the confidence interval**
    -   The bounds of the interval are random
    -   In repeated samples, the interval that is constructed in the above way will cover the population regression coefficient in 95% of the casess

-   Confidence intervals for typical confidence levels

![]({{site.url}}/assets/images/2020/ECON5002/typicalCI.png "CI for typical confidence levels")

-   Relationship between confidence intervals and hypotheses tests

$$
    \alpha \notin interval \Rightarrow \text{reject} H _0: \beta _j = a _j \text{ in favor of } H _1 : \beta _j \neq a _j
$$

![]({{site.url}}/assets/images/2020/ECON5002/betaVal.png "values of beta")

- **Example: Model of firms‘ R&D expenditures**

![]({{site.url}}/assets/images/2020/ECON5002/RandDExpenditures.png "Firm's R&D expenditures")

-   One often sees statements such as “there is a 95%” chance that \\(\beta _{log(sales)} \\) is in the interval [0.961,1.21]

-   This is incorrect. \\(\beta _{log(sales)} \\)  is a fixed (unknown)value, and it either is or is not in the interval.

-   For a particular sample, we don’t know whether \\(\beta _{log(sales)} \\)  is in the interval

-   <u>**Testing Single Linear Restrictions**</u>

-   **Example: Return to education at 2 year vs. at 4 year colleges**

![]({{site.url}}/assets/images/2020/ECON5002/2or4yearsEdu.png "education at 2 years vs. at 4 years colleages")

-   **Impossible to compute with standard regression output because**

![]({{site.url}}/assets/images/2020/ECON5002/imposCompu.png "not available in regression output")

-   **Alternative method**

![]({{site.url}}/assets/images/2020/ECON5002/alterMethod.png "Alternative method")

-   **Estimation results**

![]({{site.url}}/assets/images/2020/ECON5002/estRes.png "Estimation Results")

-   **This method works
<u>always</u> for single linear hypotheses**

-   <u>**Testing multiple linear restrictions: The F-test**</u>

-   **Testing exclusion restrictions**

![]({{site.url}}/assets/images/2020/ECON5002/exclusionRestrictions.png "Testing exclusion restrictions")

-   **Estimation of the unrestricted model**

![]({{site.url}}/assets/images/2020/ECON5002/unrestrictedEst.png "Estimation of the unrestricted model")

![]({{site.url}}/assets/images/2020/ECON5002/unrestrictedEst2.png "Test Statistic")

-   **Test statistic**

![]({{site.url}}/assets/images/2020/ECON5002/testStatistic.png "Estimation of the unrestricted model")

-   **Rejection rule(Figure)**

![]({{site.url}}/assets/images/2020/ECON5002/rejectionRule.png "Figure 4.7")

![]({{site.url}}/assets/images/2020/ECON5002/criticalValuesFDis.png "5% Critical values of the F Distribution")

![]({{site.url}}/assets/images/2020/ECON5002/FDis.png "F Distribution")

-   **Test decision in the example**

![]({{site.url}}/assets/images/2020/ECON5002/testDesicion.png "Test decision in the example")

-   **Discussion**

    -   The three variables are "jointly significant"
    -   They were not significant when tested individually. Should we conclude that none of *bavg*, *hyrunsyr*, and *rbisyr* affects baseball player salaries? NO. This could be a mistake.
    -   The likely reason is multicollinearity between them (STANDARD ERRORS!)
    -   Corr(*hyrunsyr*,*rbisyr* )=0.89. One cannot hit a home run without getting at least one run batted in.

-   We want to see how the fit deteriorates as we remove a subset of variables **(joint hypotheses test)**.
-   \\(SSR _r \ge SSR _{ur} \\)(algebraic fact).
-   The F-test essentially ask: does the SSR increase proportionally by enough to conclude the restrictions under \\(H _0\\) are false?
-   The F-statistic use a degree of freedom adjustment.
-   If the null is rejected, the test will not tell us which parameter is different from zero.

-   <u>**Test of overall significance of a regression**</u>

![]({{site.url}}/assets/images/2020/ECON5002/overallSignificance.png "Test of overall significance of a regression")

-   **The test of overall significance is reported in most regression
packages; the null hypothesis is usually overwhelmingly rejected**

-   <u>**Testing general linear restrictions with the F-test**</u>

-   Example: Test whether house price assessments are rational

![]({{site.url}}/assets/images/2020/ECON5002/rationalHousePrice.png "Test whether house price assessments are rational")

-   Regression output for the unrestricted regression

![]({{site.url}}/assets/images/2020/ECON5002/unrestrictedRegOut.png "Regression output for the unrestricted regression")

-   Square sum restricted resduals

$$
    \begin{array}{l}
    x _i = log(price _i) - log(assess _i) \text{,  }
    SSR _r = \sum _{i=1}^n (x _i - \overline{x}) ^2 = 1.880
    \\\\ F = \frac{(SSR _r -SSR _{ur})/q}{SSR _{ur}/(n - k -1)} = \frac{(1.880 - 1.822)/4}{1.822/(88 - 4 -1)} \approx .661
    \\\\ F \sim F _{4,83} \Rightarrow c _0.05 = 2.50 \Rightarrow H _0 \text{  cannot be rejected}
    \end{array}
$$

-   The F-test works for general multiple linear hypotheses

-   For all tests and confidence intervals, validity of assumptions MLR.1 –MLR.6 has been assumed. Tests may be invalid otherwise.

-   <u>**F- and t-statistics**</u>

    -   If \\( q=1, F = t ^2\\)

    -   The *t-test* is more transparent and allows one-sided alternatives

-   **\\(\underline{R ^2 \text{ form of the } F-statistic}\\)**
    -   Assume that the same dependent variable is used in two regressions
    -   \\( SSR _r = (1-R _r^2)SST \text{,   } SSR _{ur} = (1 - R _{ur}^2) SST\\)

$$
    F = \frac{(R _{ur}^2 - R _r^2)/q}{(1-R _{ur}^2)/(n - k -1)}
$$

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
