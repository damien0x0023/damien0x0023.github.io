---
layout: post
title: Basic Econometrics - Unit 4 Multiple Regression Analysis with Qualitative Information
subtitle: 基础计量经济学（四）
category: money
tags: [ECON5002]
---


translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 4 Multiple Regression Analysis with Qualitative Information


- **<u>Qualitative Information</u>**

    -   Examples: gender, race, industry, region, rating grade, …

    -   A person is either male or female, a worker belongs to a union or not...

    -   Qualitative variables may appear as the dependent or as independent variables

##   <u>A single dummy independent variable</u>

![]({{site.url}}/assets/images/2020/ECON5002/sinIndepVari.png "A single dummy independent variable")

$$
    \begin{array}{c|lcr}
        \hline
        peson & wage & educ & exper & female & married &
        \\\\ \hline 1 & 3.10 & 11 & 2 & 1 & 0
        \\\\ \hline 2 & 3.24 & 12 & 22 & 1 & 1
        \\\\ \hline 3 & 3.00 & 11 & 2 & 0 & 0
        \\\\ \hline 4 & 6.00 & 8 & 44 & 0 & 1
        \\\\ \hline 5 & 5.30 & 12 & 7 & 0 & 1
        \\\\ \hline \vdots & \vdots & \vdots & \vdots & \vdots
        \\\\ \hline 525 & 11.56 & 16 & 5 & 0 & 1
        \\\\ \hline 526 & 3.50 &  14 & 5 & 1 & 0
    \end{array}
$$

-   **Graphical Illustration**

![]({{site.url}}/assets/images/2020/ECON5002/graIllustration.png "Graphical Illustration")

-   **Dummy variable trap**

![]({{site.url}}/assets/images/2020/ECON5002/dummyTrap.png "Dummy Variable Trap")

-   **Estimated wage equation with intercept shift**

![]({{site.url}}/assets/images/2020/ECON5002/estWageEqu.png "Estimated wage equation")

-   **Does that mean that women are discriminated against?**

    -   Not necessarily. Being female may be correlated with other produc-tivity characteristics that have not been controlled for.

###   Using dummy explanatory variables in equations for log(y)

![]({{site.url}}/assets/images/2020/ECON5002/dummyVarInEqu.png "dummy explanatory variables in equations")

###   <u>Using dummy variables for multiple categories</u>

1.  Define membership in each category by a dummy variable

2.  Leave out one category (which becomes the base category)

![]({{site.url}}/assets/images/2020/ECON5002/dummyVarMul.png "dummy variables for multiple categories")

-   This *marriage premium* for men has long been noted by labour economists.

    -   Does marriage make men more productive?

    -   Is being married a signal to employers (say, of stability and reliability)?

    -   Is there a selection issue in that more productive men are likely to be married, on average?

    -   The regression cannot tell us which explanation is correct.

-   A married woman, at given levels of the other variables, earns about 19.8% *less* than a single man.

-   A single woman earns about 11.0% less than a comparable single man. (*p-value* 0.048.)

-   What if we want to compare married women and single women?

    -   slope for married women =. 321 −. 198
    -   slope for single women =. 321 −. 110    
    -   difference = −. 198 − (−. 110) = −. 088

-   so married women earn about 8.8% less than single women (controlling for other factors).

-   We cannot tell from the previous output whether this difference is statistically significant.

-   Choose *marrfem* as the base group, re-estimate the model (including the other thee categories)

![]({{site.url}}/assets/images/2020/ECON5002/lwage.jpg "lwage and its variables")

###   <u>Using Dummy Variables to Incorporate Ordinal Information</u>

-   The data set BEAUTY.DTA includes a ranking of physical attractiveness of each man or woman, on a scale of 1 to 5, with 5 being “strikingly beautiful or handsome.”

-   As we move up the scale from 1 to 5, why should a one-unit increase mean the same amount of “beauty”?

-   The “looks” variable is what we call an ordinal variable: we know that the order of outcomes conveys information (5 is better than 4, and 2 is better than 1) but we do not know that the difference between 5 and 4 is the same as 2 and 1.

-   Very few people are at the extreme values 1 and 5 (less than 1% each).

-   It makes sense to combine into three categories: *belavg*, *avg*, *abvavg*.

![]({{site.url}}/assets/images/2020/ECON5002/fewPeople.jpg "Very few people are at the extreme beautiful or handsome")

-   *avg* is the base group:

![]({{site.url}}/assets/images/2020/ECON5002/baseGroupAvg.jpg "Average looking people are the base group")

###   <u>Incorporating ordinal information using dummy variables</u>

-   **Example: City credit ratings and municipal bond interest rates**

![]({{site.url}}/assets/images/2020/ECON5002/cityCredit.png "City credit ratings and municipal bond interest rates")

###   <u>Interactions involving dummy variables</u>

-   Allowing for different slopes

![]({{site.url}}/assets/images/2020/ECON5002/diffSlopes.png "Allowing for different slopes")

-   Interesting hypotheses

![]({{site.url}}/assets/images/2020/ECON5002/interestingHypo.png "Interesting hypotheses")

-   **Graphical Illustration**

![]({{site.url}}/assets/images/2020/ECON5002/graIllustration2.png "Graphical Illustration 2")

-   **Estimated wage equation with interaction term**

![]({{site.url}}/assets/images/2020/ECON5002/estWageEqu2.png "Estimated wage equation 2")

![]({{site.url}}/assets/images/2020/ECON5002/lwage2.jpg "log wage calculation")


F-statistic for 

$$
    H _0: \beta _{female} = \beta _{female \cdot educ} = 0
$$

Is equal to \\( 34.33 ( df =2,518), \ p-value=0.0000 \\)

###   <u>Testing for differences in regression functions across groups</u>

-   **Unrestricted model (contains full set of interactions)**

![]({{site.url}}/assets/images/2020/ECON5002/unrestrictedModel.png "Unrestricted model (contains full set of interactions)")

-   **Restricted model (same regression for both groups)**

$$
    cumgpa = \beta _0 + \beta _1 sat + \beta _2 hsperc + \beta _3 tothrs + u
$$

-   **Null hypothesis**

![]({{site.url}}/assets/images/2020/ECON5002/nullHyp2.png "Null hypothesis of Unrestricted model (contains full set of interactions)")

-   **Estimation of the unrestricted model**

![]({{site.url}}/assets/images/2020/ECON5002/estUnresModel.png "Estimation of Unrestricted model (contains full set of interactions)")

-   **Joint test with F-statistic**

![]({{site.url}}/assets/images/2020/ECON5002/jointTest.png "Joint test with F-statistic")

Many regressors: adding all the interaction effects might be cumbersome

###   Alternative way to compute the F-statistic (<u>Chow test</u>)

-   Run separate regressions for the groups (e.g. men and for women); the unrestricted SSR is given by the sum of the SSR of these two regressions.

-   We necessarily get the same estimated intercepts and slopes as if we include female dummy and a full set of interaction.

-   Run regression for the restricted (pooled) model and store SSR.

-   <font color=red>Null: equality of regression functions across two groups.</font>

-   <u>Important</u>: Test assumes a constant error variance accross groups.

$$
    F = \frac{[SSR - (SSR _1 + SSR _2)]}{SSR _1 + SSR _2} 
        \cdot \frac{[n - 2(k+1)]}{k+1}
$$

![]({{site.url}}/assets/images/2020/ECON5002/equs.jpg "F-statistic I")

![]({{site.url}}/assets/images/2020/ECON5002/equs2.jpg "F-statistic II")

We can allow for an intercept difference between the groups, and then test for slope difference. 

Replace \\( SSR _p \\) in Chow F-stat with the residuals from a regression with a dummy.

![]({{site.url}}/assets/images/2020/ECON5002/chowFstatDummy.jpg "F-statistic III")

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
