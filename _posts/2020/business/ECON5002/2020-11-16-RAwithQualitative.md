---
layout: post
title: Basic Econometrics - Unit 4 Multiple Regression Analysis with Qualitative Information
subtitle: 基础计量经济学（四）
category: money
tags: [ECON5002]
---


translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 4 Multiple Regression Analysis with Qualitative Information  
&emsp;计量经济学基础第4单元定性信息多元回归分析

- **<u>Qualitative Information</u>**  
&emsp;**定性信息**

    -   Examples: gender, race, industry, region, rating grade, …  
    &emsp;例如：性别，种族，行业，地区，等级…

    -   A person is either male or female, a worker belongs to a union or not...  
    &emsp;一个人不是男性就是女性，一个工人是否属于工会...

    -   Qualitative variables may appear as the dependent or as independent variables  
    &emsp;定性变量可以作为因变量或自变量出现

##   <u>A single dummy independent variable</u>  
&emsp;<u>单个虚拟自变量</u>

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
&emsp;**图示**

![]({{site.url}}/assets/images/2020/ECON5002/graIllustration.png "Graphical Illustration")

-   **Dummy variable trap**  
&emsp;*虚拟变量陷阱**

![]({{site.url}}/assets/images/2020/ECON5002/dummyTrap.png "Dummy Variable Trap")

-   **Estimated wage equation with intercept shift**  
&emsp;**带截距偏移的估计工资方程**

![]({{site.url}}/assets/images/2020/ECON5002/estWageEqu.png "Estimated wage equation")

-   **Does that mean that women are discriminated against?**  
&emsp;**这是否意味着妇女受到歧视？**

    -   Not necessarily. Being female may be correlated with other produc-tivity characteristics that have not been controlled for.  
    不一定。女性可能与其他尚未控制的生产特征有关。

###   Using dummy explanatory variables in equations for log(y)  
&emsp;在对数（y）方程中使用虚拟解释变量

![]({{site.url}}/assets/images/2020/ECON5002/dummyVarInEqu.png "dummy explanatory variables in equations")

###   <u>Using dummy variables for multiple categories</u>  
&emsp;对多个类别使用虚拟变量

1.  Define membership in each category by a dummy variable  
&emsp;通过虚拟变量定义每个类别中的成员身份

2.  Leave out one category (which becomes the base category)  
&emsp;省略一个类别（成为基本类别）

![]({{site.url}}/assets/images/2020/ECON5002/dummyVarMul.png "dummy variables for multiple categories")

-   This *marriage premium* for men has long been noted by labour economists.  
&emsp;长期以来，劳工经济学家一直注意到男性的这种“婚姻溢价”。

    -   Does marriage make men more productive?  
    &emsp;婚姻能让男人更有效率吗？

    -   Is being married a signal to employers (say, of stability and reliability)?  
    &emsp;结婚是雇主的信号吗（比如说，稳定和可靠）？

    -   Is there a selection issue in that more productive men are likely to be married, on average?  
    &emsp;平均而言，生产力更高的男性很可能已婚，这是否存在选择问题？

    -   The regression cannot tell us which explanation is correct.  
    &emsp;回归不能告诉我们哪种解释是正确的。

-   A married woman, at given levels of the other variables, earns about 19.8% *less* than a single man.  
&emsp;在给定的其他变量水平下，已婚女性的收入比单身男性低19.8%。

-   A single woman earns about 11.0% less than a comparable single man. (*p-value* 0.048.)  
&emsp;单身女性的收入比同等单身男性低11.0%。（*p-value*0.048。）

-   What if we want to compare married women and single women?  
&emsp;如果我们想比较已婚女性和单身女性呢？

    -   slope for married women =. 321 −. 198  
    &emsp;已婚妇女的坡度 =. 321 −. 198

    -   slope for single women =. 321 −. 110  
    &emsp;单身女性的坡度 =. 321 −. 110    

    -   difference = −. 198 − (−. 110) = −. 088  
    &emsp;差异 = −. 198 − (−. 110) = −. 088

-   so married women earn about 8.8% less than single women (controlling for other factors).  
&emsp;因此，已婚女性的收入比单身女性低8.8%（控制其他因素）。

-   We cannot tell from the previous output whether this difference is statistically significant.  
&emsp;我们无法从先前的结果判断这种差异是否具有统计学意义。

-   Choose *marrfem* as the base group, re-estimate the model (including the other thee categories)  
&emsp;选择*marrfem*作为基组，重新估计模型（包括其他类别）

![]({{site.url}}/assets/images/2020/ECON5002/lwage.jpg "lwage and its variables")

###   <u>Using Dummy Variables to Incorporate Ordinal Information</u>  
&emsp;使用虚拟变量合并顺序信息

-   The data set BEAUTY.DTA includes a ranking of physical attractiveness of each man or woman, on a scale of 1 to 5, with 5 being “strikingly beautiful or handsome.”  
&emsp;数据集BEAUTY.DTA包括每个男人或女人的外表吸引力排名，从1到5分，其中5分为“惊人的美丽或英俊”

-   As we move up the scale from 1 to 5, why should a one-unit increase mean the same amount of “beauty”?  
&emsp;当我们从1上升到5时，为什么一个单位的增加意味着同样多的“美”？

-   The “looks” variable is what we call an ordinal variable: we know that the order of outcomes conveys information (5 is better than 4, and 2 is better than 1) but we do not know that the difference between 5 and 4 is the same as 2 and 1.  
&emsp;“looks”变量就是我们所说的序数变量：我们知道结果的顺序传递信息（5比4好，2比1好），但我们不知道5和4之间的差别与2和1是一样的。

-   Very few people are at the extreme values 1 and 5 (less than 1% each).  
&emsp;很少有人处于极端值1和5（每个都小于1%）。

-   It makes sense to combine into three categories: *belavg*, *avg*, *abvavg*.  
&emsp;将其分为三类是有意义的：*belavg*、*avg*、*abvavg*。

![]({{site.url}}/assets/images/2020/ECON5002/fewPeople.jpg "Very few people are at the extreme beautiful or handsome")

-   *avg* is the base group:  
&emsp;*avg*是基础组：

![]({{site.url}}/assets/images/2020/ECON5002/baseGroupAvg.jpg "Average looking people are the base group")

###   <u>Incorporating ordinal information using dummy variables</u>  
&emsp;使用虚拟变量合并顺序信息

-   **Example: City credit ratings and municipal bond interest rates**  
&emsp;**例如：城市信用评级和市政债券利率**

![]({{site.url}}/assets/images/2020/ECON5002/cityCredit.png "City credit ratings and municipal bond interest rates")

###   <u>Interactions involving dummy variables</u>  
&emsp;涉及虚拟变量的交互作用

-   Allowing for different slopes  
&emsp;考虑到不同的坡度

![]({{site.url}}/assets/images/2020/ECON5002/diffSlopes.png "Allowing for different slopes")

-   Interesting hypotheses  
&emsp;有趣的假设

![]({{site.url}}/assets/images/2020/ECON5002/interestingHypo.png "Interesting hypotheses")

-   **Graphical Illustration**  
&emsp;**图示**

![]({{site.url}}/assets/images/2020/ECON5002/graIllustration2.png "Graphical Illustration 2")

-   **Estimated wage equation with interaction term**  
&emsp;**带交互项的估计工资方程**

![]({{site.url}}/assets/images/2020/ECON5002/estWageEqu2.png "Estimated wage equation 2")

![]({{site.url}}/assets/images/2020/ECON5002/lwage2.jpg "log wage calculation")


F-statistic for  
&emsp;F统计是为了

$$
    H _0: \beta _{female} = \beta _{female \cdot educ} = 0
$$

Is equal to \\( 34.33 ( df =2,518), \ p-value=0.0000 \\)

###   <u>Testing for differences in regression functions across groups</u>  
&emsp;测试各组回归函数的差异

-   **Unrestricted model (contains full set of interactions)**  
&emsp;**无限制模型（包含全套交互）**

![]({{site.url}}/assets/images/2020/ECON5002/unrestrictedModel.png "Unrestricted model (contains full set of interactions)")

-   **Restricted model (same regression for both groups)**  
&emsp;**限制模型（两组回归相同）**

$$
    cumgpa = \beta _0 + \beta _1 sat + \beta _2 hsperc + \beta _3 tothrs + u
$$

-   **Null hypothesis**  
&emsp;**空假设**

![]({{site.url}}/assets/images/2020/ECON5002/nullHyp2.png "Null hypothesis of Unrestricted model (contains full set of interactions)")

-   **Estimation of the unrestricted model**  
&emsp;**非限制模型的预测**

![]({{site.url}}/assets/images/2020/ECON5002/estUnresModel.png "Estimation of Unrestricted model (contains full set of interactions)")

-   **Joint test with F-statistic**  
&emsp;**F统计的联合测试**

![]({{site.url}}/assets/images/2020/ECON5002/jointTest.png "Joint test with F-statistic")

Many regressors: adding all the interaction effects might be cumbersome  
&emsp;许多回归因素：添加所有交互效应可能会很麻烦

###   Alternative way to compute the F-statistic (<u>Chow test</u>)  
&emsp;计算F统计量的另一种方法（<u>Chow检验</u>）

-   Run separate regressions for the groups (e.g. men and for women); the unrestricted SSR is given by the sum of the SSR of these two regressions.  
&emsp;对各组（例如男性和女性）分别进行回归分析；无限制SSR由这两个回归的SSR之和得出。

-   We necessarily get the same estimated intercepts and slopes as if we include female dummy and a full set of interaction.  
&emsp;我们必须得到相同的估计截距和斜率，如果我们包括女性假人和一整套互动。

-   Run regression for the restricted (pooled) model and store SSR.  
&emsp;对受限（合并）模型运行回归并存储SSR。

-   <font color=red>Null: equality of regression functions across two groups.</font>  
&emsp;<font color=red>Null：两组回归函数相等。</font>

-   <u>Important</u>: Test assumes a constant error variance accross groups.  
&emsp;<u>重要</u>：测试假设各组间的误差方差恒定。

$$
    F = \frac{[SSR - (SSR _1 + SSR _2)]}{SSR _1 + SSR _2} 
        \cdot \frac{[n - 2(k+1)]}{k+1}
$$

![]({{site.url}}/assets/images/2020/ECON5002/equs.jpg "F-statistic I")

![]({{site.url}}/assets/images/2020/ECON5002/equs2.jpg "F-statistic II")

We can allow for an intercept difference between the groups, and then test for slope difference.  
&emsp;我们可以考虑组之间的截距差，然后测试斜率差。

Replace \\( SSR _p \\) in Chow F-stat with the residuals from a regression with a dummy.  
&emsp;将Chow F-stat中的\\( SSR _p \\)替换为虚拟回归的残差。

![]({{site.url}}/assets/images/2020/ECON5002/chowFstatDummy.jpg "F-statistic III")

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
