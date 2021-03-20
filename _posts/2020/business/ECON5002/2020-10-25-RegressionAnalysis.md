---
layout: post
title: Basic Econometrics - Unit 2 Regression Analysis Estimation
subtitle: 基础计量经济学（二）回归分析估计
category: money
tags: [ECON5002]
---


translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 2 Regression Analysis Estimation (Simple Regression)

# Video 1: Conditional Expectation and Prediction  
&emsp;视频1：条件期望与预测

##  The Distribution of Wages  
&emsp;工资分配

- Suppose that we are interested in wage rates in the U.S.  
&emsp;假设我们对美国的工资率感兴趣。

- We can view the *wage* of an individual worker as a random variable wage with distribution \\( F(z) = Pr (wage \le z) \\):  
&emsp;我们可以将单个工人的*wage*视为随机变量工资，其分布 \\( F(z) = Pr (wage \le z) \\):

- By saying that a person's wage is random mean that we do not know her wage before it is measured.  
&emsp;如果说一个人的工资是随机的，那就意味着我们在衡量之前不知道她的工资。

- The observed wage rates are treated as realizations from the same distribution \\( F(z)\\).  
&emsp;观察到的工资率被视为来自相同分布的实现\\( F(z)\\)。

![]({{site.url}}/assets/images/2020/ECON5002/wageDis.png "Figure 1.1: Wage Distribution and Densities. All Full-time U.S. Workers (Hansen (2000), Chapter 2).")

We will pretend the c.d.f and p.d.f.s refer to the **Population**!

###  Data

- Data: https://www.ssc.wisc.edu/~bhansen/econometrics/

- Description: https://www.ssc.wisc.edu/~bhansen/econometrics/cps09mar_description.pdf

- The distribution and the density are estimated from a sample of 50,742 full-time non-military wage-earners reported in the March 2009 Current Population Survey.  
&emsp;该分布和密度是根据2009年3月本次人口调查报告的50742名全职非军人工薪阶层样本估计的。

- The wage rate is constructed as annual individual wage and salary earning divided by hours worked.  
&emsp;工资率是指个人年工资和工资收入除以工作时间。

- The measures of central tendency describe some features of the distribution.  
&emsp;集中趋势的度量描述了分布的一些特征。

- The density is peaked around $15, and most of the probability mass lie between $10 and $40.  
&emsp;密度峰值在15美元左右，大部分概率质量在10美元到40美元之间。

- The median is $19.23, the mean is $23.90.  
&emsp;中位数是19.23美元，平均值是23.90美元。

- Right skewness and thick tails explain why Mean > Median (64% of workers earn less than $23.90).  
&emsp;右偏和厚尾解释了为什么均值>中位数（64%的工人收入低于23.90美元）。

- The expectation is not robust(1: The expectation is sensitive to perturbation in the tails of the distribution) but it is mathematically convenient.  
&emsp;期望不是鲁棒的（1：期望对分布尾部的扰动很敏感），但在数学上很方便。

- It is useful to transform the data: the density of ln(*wage*) is much less skewed and fat-tailed, and the mean is a much "better" measure of central tendency of the distribution.  
&emsp;转换数据是有用的：ln（*wage*）的密度不那么偏斜和厚尾，平均值是分布中心趋势的一个更好的度量。

### Conditional Expectation  
&emsp;条件期望

- Consider the density of ln(*wage*) saw in Fig 1.1(c).  
&emsp;考虑图1.1（c）所示的ln（*wage*）密度。

- Does the wage distribution vary across sub-populations?  
&emsp;工资分布在不同的亚人群中有差异吗？

- It is reasonable to expect that more educated people tend to earn more than less educated people.  
&emsp;我们有理由认为，受教育程度高的人往往比受教育程度低的人挣得多。

- This will not hold for each individual, but it is likely to be true on average.  
&emsp;这并不适用于每个人，但平均而言，这很可能是正确的。

- The conditional expectation is a measure of central tendency for the conditional distribution.  
&emsp;条件期望是条件分布中心趋势的度量。

![]({{site.url}}/assets/images/2020/ECON5002/CEF.png "Figure 1.2: Conditional Expectation Function (CEF)")

\\( E [ ln(wage) \| education ] \\) is a function of education.  
&emsp;上式是一个教育的函数。

Write *lwage* for ln(*wage*) and *educ* for *education*.  
&emsp;将*ln(wage)*写作*lwage*且将*education*写作*educ*。

A high school graduate has *education* = 12  
&emsp;一个高中毕业生的 *education* = 12.

$$
  E(lwage | educ = 12) = 2.71
$$

A professional degree (medical, law or PhD) has *education* = 20:  
&emsp;一个职业学位（医学，法律或者博士）的*education* = 20：

$$
  E [lwage | educ = 20] = 3.69
$$

![]({{site.url}}/assets/images/2020/ECON5002/condDens.png "Figure 1.3: Conditional densities")

$$
  f(lwage | educ = n), \ n = 12\text{ (dotted) and } n = 20 \text{solid}
$$

Remarks  
&emsp;备注

- Does education causes earnings to increase?  
&emsp;教育会导致收入增加吗？

- Even without answering this question, it seems that education predicts earnings.  
&emsp;即使不回答这个问题，教育似乎也能预测收入。

- We predict when we say in advance, foretell, what is the new or future observation.  
&emsp;当我们预先说，预言，什么是新的或未来的观察时，我们就预测。

- In Fig 1.2 we used the CEF(educ) to predict lwage.  
&emsp;在图1.2中，我们使用CEF（educ）预测lwage。

- Can we find a better predictor?  
&emsp;我们能找到更好的预测器吗？

### Best Predictor  
&emsp;最佳预测值

- Consider the problem of predicting a random variable *y* given a random variable *x*.  
&emsp;假设一个随机变量*x*，考虑预测一个随机变量*y*的问题。

- We can write any predictor as *h(x)*.  
&emsp;我们可以把任何预测器写成*h(x)*。

- The (ex-post) prediction error is *y-h(x)*.  
&emsp;（事后）预测误差为*y-h(x)*。

- A non-stochastic measure of the prediction error is  
&emsp;提出了预测误差的非随机测度

$$
  E [ y - h (x)] ^2 
  \tag{1.1} \label{predictionError}
$$

- We define the best predictor(2: in the mean square sense) as the function of x which minimizes \ref{predictionError}.  
&emsp;我们将最佳预测因子（2：均方意义上的）定义为x的函数，它使\ref{predictionError}最小化。

- It turns out that the best predictor is \\( E(y \| x) \\).  
&emsp;结果表明，最好的预测因子是\\( E(y \| x) \\)。

- If we set \\( m(x) = E(y \| x) \\) and define \\( u = y - m(x) \\), then, by construction  
&emsp;如果我们设置\\( m(x)=E(y \| x)\\) 并定义\\( u = y - m(x)\\)，那么，通过构造

$$
  y = m(x) + u \text{, with } E(u | x) = 0
  \tag{1.2} \label{}
$$

- An important special case is when the CEF is linear,  
&emsp;一个重要的特例是当CEF为线性时，

$$
  m(x) = \beta _0 + \beta _1 x
$$

The linear CEF model is often called **linear regression model**, or regression of *y* on *x*.  
&emsp;线性CEF模型经常被称作**线性回归模型**，或者*y*在*x*上的回归。

**Interpreting the CEF**  
&emsp;解析CEF


If \\( E(y \| x)\\) is linear, i.e. \\( m(x) = \beta _0 + \beta _1 x \\), then  
&emsp;如果上式成立，那么

$$
  \beta _0 = m(0).
$$


and \\( \beta _1\\) can be seen as marginal changes in \\( m(x) \\) implied by *a* change in *x*  
&emsp;而且\\( \beta _1\\)可以被看作是在\\( m(x) \\)上的边际变化值，由*a*在*x*上的改变可以推断出来

$$
  \Delta m(x) = m(x + \Delta x) - m(x) = \beta _1 \Delta x \implies \beta _1 = \frac{\Delta m(x)}{\Delta x}
$$

If x is continuous  
&emsp;如果x是连续的

$$
  \beta _1 = \lim _{\Delta x \to 0 } \frac{\Delta m(x)}{\Delta x} 
  = \frac{d m(x)}{d x} = m ' (x)
$$

**Best Linear Predictor**  
&emsp;最佳线性预测值

- While \\( m(x) = E(y \| x) \\) is the best predictor among all function of *x*, its functional form can be complicated.  
&emsp;虽然\\( m(x) = E(y \| x) \\)是*x*所有函数中最好的预测因子，但它的函数形式可能很复杂。

- We can restrict \\( h(x)\\) to be linear, i.e. \\( h(x) = b _0 + b _1 x\\).  
&emsp;我们可以将\\( h(x)\\)限制为线性，即\\( h(x) = b _0 + b _1 x\\)。

- The *best linear predictor* (BLP) of *y* given *x* is \\( \beta _0 + \beta _1 x \\), where  
&emsp;给定*x*的*y*的*best linear predictor*（BLP）是\\( \beta _0 + \beta _1 x \\)，其中

$$
  [\beta _0, \beta _1] = \mathop{\arg \max} \limits _{b _0, b _1} E[( y - b _0 - b _1 x) ^2]
  \tag{1.3} \label{blp}
$$

- If the moments exist and \\( Var(x) > 0 \\)  
&emsp;如果这个时刻存在而且\\( Var(x) > 0 \\)

$$
  \beta _0 = E(y) - \beta _1 E(x), \quad \beta _1 = \frac{Cov(x,y)}{Var(x)} 
  \tag{1.4} \label{blp2}
$$

![]({{site.url}}/assets/images/2020/ECON5002/CEFandBLP.png "Figure 1.4: CEF and BLP")


![]({{site.url}}/assets/images/2020/ECON5002/cumuDisFuncEduc.png "Figure 1.5: Cumulative Distribution function of education")


![]({{site.url}}/assets/images/2020/ECON5002/predLwageLinearEduc.png "Figure 1.6: Prediction lwage with a linear function of educ")

### The OLS estimator  
&emsp;最小二乘法的估计值

Given a data set \\( {(y _i, x _i), i = 1, \cdots, n} \\), the estimator of \\( [\beta _0, \beta _1] \\) is derived as the solution of the *sample* counterpart of \eqref{blp}, i.e.  
&emsp;给定上面的数据集，导出估计量\\( [\beta _0, \beta _1] \\)作为作为\eqref{blp}的*sample*对应项的解，即

$$
  [ \hat{\beta} _0, \hat{\beta} _1] \mathop{\arg \min} \limits _{b _0, b _1} \frac{1}{n} \sum _{i =1}^n u _i^2 (b _0 , b _1) 
  \tag{1.5} \label{ols}
$$

where \\( u _i (b _0, b _1) = y _i - b _0 - b _1 x _i \\)

The solution of \eqref{ols} is the OLS estimator  
&emsp;上面式\eqref{ols}的解便是最小二乘法的估计值

$$
  \begin{cases}
  \hat{\beta} _0  = \overline{y} - \hat{\beta} _1 \overline{x},
  \\\\
  \hat{\beta} _1 = \frac{\sum _{i=1}^n (x _i - \overline{x})(y _i - \overline{y})}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
  \end{cases}
$$

where \\( \overline{y} = n ^{-1} \sum _{i=1}^n y _i \text{ and } \overline{x} = n ^{-1} \sum _{i =1 }^n x _i \\). 

Note that  
&emsp;注意

$$
  \hat{\beta} _1 = \frac{ (n-1) ^{-1} \sum _{i=1}^n (x _i - \overline{x})(y _i - \overline{y})}{ (n-1) ^{-1} \sum _{i=1}^n (x _i - \overline{x}) ^2} 
  = \frac{\widehat{Cov} (x,y)}{\widehat{Var} (x)}
$$

Compare with \eqref{blp2}.  
&emsp;与\eqref{blp2}比较。

### Takeaway  
&emsp;课外

- The CEF is useful to model the relationship between *y* and *x*  
&emsp;条件期望方程CEF是有助于建模*y*与*x*之间的关系。

$$
  y = E(y | x) +u
$$

- The simple linear regression model  
&emsp;简单的线性回归模型

$$
  y = \beta _0 + \beta _1 + u
$$

has been derived as the solution of a liner prediction problem.  
&emsp;被导出作为一个线性预测问题的解。

- \\( [\beta _0, \beta _1] \\) is called OLS estimator because it solves a least square problem.  
&emsp;上面的解被称作最小二乘法OLS的估计值因为它解决了最小二乘问题。

## Video 2: Interpretation of the simple regression model  
&emsp;视频2：简单回归模型的解释

Consider the simple regression model:  
&emsp;考虑这个简单的回归模型：

$$ \tag{2.1} y =  \beta _0 + \beta _1 x + u  \label{simpleRegression1} $$

If the factors in \\( u \\) are held fixed when \\( x \\) changes by \\( \Delta x \\)  
&emsp;如果当\\( x \\) 随着\\( \Delta x \\)而改变时，\\( u \\)中的因子保持不变

$$ (y+\Delta y) = \beta _0 + \beta _1 (x + \Delta x) + u \tag{2.2} \label{simpleRegression2} $$

Substracting \eqref{simpleRegression1} from \eqref{simpleRegression2} we got  
&emsp;从\eqref{simpleRegression2}减去\eqref{simpleRegression1}，我们得到

$$ \Delta y = \beta _1 \Delta x \text{, if } \Delta u = 0 $$

Suppose  
&emsp;设想

$$ wage = -16.45 + 2.9 educ + u$$

An additional year of education increase the wage by $2.9, if \\( u \\) doesn't change when \\( educ \\) changes, i.e.  
&emsp;如果当\\( educ \\)改变时\\( u \\)不变，每增加一年的教育增加$2.9的工资。

$$ \Delta wage = 2.9 \Delta educ \text{, if } \Delta u = 0. $$

Suppose that  
&emsp;设想

$$ lwage = 1.44 + 0.11 educ + u $$

What is the effect on wage of an additional year of education?  
&emsp;增加一年的教育对工资的影响是什么？

$$
  \Delta ln{wage} 
  = ln(wage+\Delta wage) - ln(wage)
  = ln \left( \frac{wage+\Delta wage}{wage}\right)
$$

If \\(\epsilon = \Delta wage / wage \\) is small  
&emsp;如果\\(\epsilon = \Delta wage / wage \\) 是小的

$$
  \Delta ln(wage) = ln(1+\epsilon) \approx \epsilon
$$

If \\( \Delta ln (wage) = \beta _1\\), then,  
&emsp;如果\\( \Delta ln (wage) = \beta _1\\)，那么，

$$
  \beta _1 
  \approx \frac{\Delta wage} {wage} 
  \implies \\% \ \Delta wage 
  \approx 100 \beta _1
$$

Another year of education increases the predicted wage by 11%.  
&emsp;一年的教育增加了11%的预期工资。

### Remarks  
&emsp;备注：

- \\( \beta _1 \\) measures the effect of  \\(x\\) on  \\(y\\) holding the other factors in \\(u\\) fixed.  
&emsp;\\( \beta _1 \\) 测量x对y的影响保持u中的其他因素不变。

- How can we learn the ceteris paribus effect of  \\(x\\)  on \\(y\\), when we are ignoring all the other factors?  
&emsp;当我们忽视所有其他因素时，我们怎么能从x对y的相同条件中学习？

-  If we assume \\( E(u|x) = 0 \\), then \\( \beta _1 \Delta x\\)  tell us how the average value of \\(y\\) changes with  \\(x\\) .  
An additional year of education increases the predicted wage by 11% on average, not for every worker.  
&emsp;如果我们假设\\( E(u|x) = 0 \\)，那么\\( \beta _1 \Delta x\\)告诉我们y的平均值是如何随着x而改变的。增加一年的教育会平均增加11%的预期工资，而不是对于每个员工。

### Takeaway  
&emsp;课外

- If we assume that \\( E(u|x) = 0 \\), the slope \\( \beta _1 \\) can be interpreted as the average predicted change in y when x increases by one unit.  
It can be also interpreted as the predicted change in y, if we are ready to assume that  \\(u\\)  remains fixed when \\(x\\) changes.  
&emsp;如果我们假设\\( E(u|x) = 0\\)，斜率\\( \beta _1 \\)能被解释为当x增长一个单位时，y的平均预期变化量。

- The log transformation of the variables allow for constant (semi)-elasticity models.  
&emsp;变量的对数变换允许恒定的（半）弹性模型

## Video 3: Mechanics of Ordinary Least Squares  
&emsp;视频3：最小二乘法的机制

### Obtaining the OLS estimates  
&emsp;获取最小二乘法的估计值

Given that data set \\( \lbrace (lwage_i, educ_i); i = 1, \cdots, n \rbrace \\), suppose that we are interested in the relationship between wages and education.  
&emsp;考虑到数据集\\( \lbrace (lwage_i, educ_i); i = 1, \cdots, n \rbrace \\)，假设我们对工资和教育之间的关系感兴趣。

If we assume  
&emsp;如果我们假设

$$ lwage_i \approx b_0 + b_1 educ_i $$

then we are interested in b0 and b1. 
&emsp;那么我们对b0和b1感兴趣。

![]({{site.url}}/assets/images/2020/ECON5002/OLSestimates.png "Figure 3.1: How do we pick up the 'optimal' line?")

Given a data set \\( \lbrace (y _i, x _i) i = 1, \cdots, n \rbrace \\), for each observation, let  
&emsp;考虑到一个数据集\\( \lbrace (y _i, x _i) i = 1, \cdots, n \rbrace \\)，对每一个观测值，让

$$
  u _i (b _0, b _1) = y _i - (b _0 + b_1 x _i) 
  \tag{3.1} 
$$

and define the **ordinary least-square estimator** as  
&emsp;且定义**普通最小二乘估计量**为

$$
  [\hat{\beta} _0, \hat{\beta} _1] = \mathop{\arg\min}\limits _{b _0, b _1} \hat{S} (b _0, b _1)
  \tag{3.2} \label{OLSestimator}
$$

where  
&emsp;在这里

$$
  \hat{S} (b _0, b _1) \sum\limits _{i=1} ^{n} u ^2 _i (b _0, b _1)
  \tag{3.3}
$$

### The OLS estimator  
&emsp;最小二乘估计量

The solution of \eqref{OLSestimator} is  
&emsp;公式\eqref{OLSestimator}的解法是

$$
  \left \lbrace \begin{array}{l} 
  \hat{\beta} _0 = \overline{y} -\hat{\beta} _1 \overline{x}
  \\\\ \hat{\beta} _1 = \frac 
    {\sum _{i=1} ^n (x _i - \overline{x}) (y _i - \overline{y})}
    {\sum _{i=1} ^n (x _i - \overline{x})^2}
  \end{array} \right.
$$

assuming that \\( SST _x = \sum _{i=1} ^n (x _i - \overline{x})^2 > 0. \\)  
&emsp;假设以上公式

The fitted or predicted values, \\( \hat{y} _i \\), is defined by the **Sample Regression Function** (SRF)  
&emsp;拟合值或预测值\\( \hat{y} _i \\)由样本回归函数（SRF）定义

$$
  \hat{y} _i = \hat{\beta} _0 + \hat{\beta} _1 x _i
$$

The deviations from the SRF (or fitted regression line)  
&emsp;与SRF（或拟合回归线）的偏差

$$
  \hat{u} _i = y _i - \hat{y} _i, \  i = 1,\cdots, n
$$

are called **residuals**.  
&emsp;被叫做**残差**

Remark: We defined \\(   u _i (b _0, b _1) = y _i - (b _0 + b_1 x _i)  \\). Then, \\( \hat{u} _i =  u _i( \hat{\beta} _0, \hat{\beta} _1) \\).  
&emsp;备注：我们定义\\(   u _i (b _0, b _1) = y _i - (b _0 + b_1 x _i)  \\)，那么，\\( \hat{u} _i =  u _i( \hat{\beta} _0, \hat{\beta} _1) \\)。


![]({{site.url}}/assets/images/2020/ECON5002/OLSestimates2.png 'Figure 3.2: The sample regression function')

### Algebraic Properties of OLS statistics  
&emsp;最小二乘法统计量的代数性质

Recall equation \eqref{OLSestimator}  
&emsp;回忆等式\eqref{OLSestimator}


<!-- inline equation:
\\(
   f(x) =  \frac{1}{2} x^2 = \dfrac{1}{2} x^2 = \tfrac{1}{2} x^2
\\)

display equation:  
$$
  f(x) =  \frac{1}{2} x^2 = \dfrac{1}{2} x^2 = \tfrac{1}{2} x^2
$$ -->


<!-- $$
    \left.\frac{dy}{dx}\right|_{x=0}
$$ -->

$$
  [\hat{\beta} _0, \hat{\beta} _1] 
  = \mathop{\arg\min}\limits _{b _0, b _1} \hat{S} (b _0, b _1)
  = \mathop{\arg\min}\limits _{b _0, b _1} \sum _{i=1}^{n} u _i ^2 (b _0, b _1)
$$

First order conditions:  
&emsp;一阶条件：

$$
  \begin{array}{l}
    \left .\frac{\partial{\hat{S}(b _0, b _1)}}{\partial{b _0}} \right| 
      _{ \begin{array}{l} 
        b_0 = \hat{\beta} _0 
        \\\\ b_1 = \hat{\beta} _1 
        \end{array}}
    = \sum _{i=1}^n u _i \left(\hat{\beta} _0, \hat{\beta} _1 \right)
    = \sum _{i=1}^n \hat{u} _i 
    = 0
    \\\\
    \left .\frac{\partial{\hat{S}(b _0, b _1)}}{\partial{b _0}} \right| 
      _{ \begin{array}{l} 
        b_0 = \hat{\beta} _0 
        \\\\ b_1 = \hat{\beta} _1 
        \end{array}}
    = \sum _{i=1}^n u _i \left(\hat{\beta} _0, \hat{\beta} _1 \right) x _i
    = \sum _{i=1}^n \hat{u} _i x _i 
    = 0
  \end{array}
  \tag{3.4} \label{FOC}
$$

1. Deviations from regression line sum up to zero  
&emsp;一，与回归线的偏差总和为零

$$
  \sum _{i=1}^n \hat{u} _i = 0
  \tag{3.5}
$$

2. The sample correlation between deviations and regressors is zero  
&emsp;二，偏差和回归系数之间的样本相关性为零

$$
  \sum _{i=1}^n \hat{u} _i x _i = 0
  \tag{3.6}
$$

3. Sample averages of y and x lie on the regression line  
&emsp;三，y和x的样本平均值位于回归线上

$$
  \overline{y} = \hat{\beta} _0 + \hat{\beta} _1 \overline{x}
  \tag{3.7}
$$

4. Properties 1 and 2 imply  
&emsp;四，性质1和2意味着

$$
  \sum _{i=1}^n \hat{y} _i \hat{u} _i   = 0 
  \tag{3.8}
$$

5. Properties 1 implies  
&emsp;五，性质1意味着

$$
  \overline{y} 
  = \frac{1}{n} \sum _{i=1}^n y _i
  = \frac{1}{n} \sum _{i=1}^n \hat{y} _i .
  \tag{3.9}
$$

Measures of Variation  
&emsp;变化量

- Total Sum of Squares (total sample variation of the \\(y_i\\) )  
&emsp;总平方和（\\(y_i\\)的总样本变化量）

$$
  \text{SST} 
  = \sum _{i=1}^n ( y _i - \overline{y}) ^2
$$

- Explained Sum of Squares (total sample variation of the \\(\hat{y}_i\\) )  
&emsp;解释平方和（\\(\hat{y}_i\\)的总样本变化量）


$$
  \text{SSE} 
  = \sum _{i=1}^n ( \hat{y} _i - \overline{y}) ^2
  = \sum  _{i=1}^n \hat{\beta} ^2 (x _i - \overline{x}) ^2
$$

- Sum of Squared Residuals (total sample variation of the \\(\hat{u}_i\\))  
&emsp;残差平方和（\\(\hat{u}_i\\)的总样本变化量）

$$
  \text{SSR} 
  = \sum _{i=1}^n \hat{u}_i ^2.
$$

- Decomposition of total variation  
&emsp;总变差分解

$$
  \text{SST} = \text{SSE} +\text{SSR}
  \tag{3.10}
$$

i.e.

Total Variation = Explained Variation + Unexplained Variation  
&emsp;总偏差=解释偏差+为解释偏差

- Goodness offit measure(R-squared)  
&emsp;拟合优度（R平方）

$$
  R ^2 = \frac{SSE}{SST} = 1- \frac{SSR}{SST},\ 0 \le R ^2 \le 1
$$

The \\(R ^2\\) measure the fraction of the total variation explained by the regression.  
&emsp;\\(R ^2\\)度量回归解释的总变异的分数。

### Takeaway  
&emsp;课外

- The algebraic properties of OLS follow from the first order conditions in (4).  
&emsp;OLS的代数性质遵循（4）中的一阶条件。

- To compute the estimators, we only assumed variation in the \\(x _i, i = 1 \cdots n\\)  
&emsp;为了计算估计量，我们只假设\\(x _i, i = 1 \cdots n\\) 中的变量

- Learning how to handle OLS as a computational tool will be (hopefully) helpful with the usage and the interpretation of OLS as an estimator.  
&emsp;学习如何将OLS作为一种计算工具，将（希望）有助于OLS作为估计量的使用和解释。

## Video4: Expected Value and Variance of the OLS Estimators  
&emsp;视频4：最小二乘估计量的预期值与方差

### Unbiasedness of OLS  
&emsp;最小二乘法的无偏性

**Assumption SLR.2 (random sampling)**  
&emsp;**假设SLR.2（随机抽样）**

The random variables \\( \lbrace (y _1, x _1), \cdots , (y _i, x _i), \cdots , (y _n; x _n) \rbrace \\) are independent and identically distributed (i.i.d.)  
&emsp;随机变量\\( \lbrace (y _1, x _1), \cdots , (y _i, x _i), \cdots , (y _n; x _n) \rbrace \\)是独立的、同分布的（i.i.d.）

**Assumption SLR.1 (linearity in the parameters)**  
&emsp;**假设SLR.1（参数线性）**

The random variables \\( (y _i, x _i) \\) satisfy the linear regression equation  
&emsp;随机变量\\( (y _i, x _i) \\)满足线性回归方程

$$
  y _i = \beta _0 + \beta _1 x _i + u _i
  \tag{4.1}
$$

where \\(\beta _0\\) and \\(\beta _1\\) are the (unknown) population *intercept* and *slope* parameters.  
&emsp;其中\\(\beta _0\\) 和\\(\beta _1\\)是（未知）总体*截距*和*斜率*参数。

**Assumption SLR.3 (sample variation in x)**  
**假设SLR.3（x中的样本变化）**

(i) \\( 0 < Var(x _i) < 1 \\) .

(ii) The sample outcome \\( \lbrace x _1, \cdots , x _n \rbrace \\) are not all the same value.  
&emsp;示例结果\\( \lbrace x _1, \cdots , x _n \rbrace \\)的值不完全相同。

Recall that  
&emsp;回忆

$$
   \hat{\beta} _1 = \frac 
    {\sum _{i=1} ^n (x _i - \overline{x}) (y _i - \overline{y})}
    {\sum _{i=1} ^n (x _i - \overline{x})^2}
$$

![]({{site.url}}/assets/images/2020/ECON5002/constantRegressor.png 'Figure 4.1: Constant regressor.')

**Assumption SLR.4 (Zero Conditional Mean)**  
&emsp;**假设SLR.4（零条件平均值）**

$$
  E(u _i | x _i) = 0 
$$

- \\( E(U _i) = E[E(u _i \| x _i)] =0 \\).

- Assumption SLR.2 and SLR.4 imply that  
&emsp;假设SLR.2和SLR.4意味着

$$
  E(y _i | x _i, \cdots , x _n) = E(y _i | x _i) = \beta _0 + \beta _1 x _i 
$$

&emsp;&emsp;that is the **(Population) Regression Function** is linear.  
&emsp;即**（总体）回归函数**是线性的。

- If \\(y = log(wage)\\), \\(x = education\\) and \\(u = innate ability\\), assumption SLR.4 implies that the average level of innate ability does not depend on education.  
&emsp;如果\\(y = log(wage)\\)、\\(x = education\\) 和 \\(u = innate ability\\)，假设SLR.4意味着先天能力的平均水平不依赖于教育。

**Theorem 2.1. Unbiasedness of OLS**  
&emsp;**定理2.1. OLS的无偏性**

Under Assumption SLR.1-SLR.4  
&emsp;在假设SLR.1-SLR.4下

$$
  E(\hat{\beta} _0) =\beta _0, \text{ and }  E(\hat{\beta} _1) =\beta _1 . 
$$

### Variances of the OLS estimators  
&emsp;OLS估计量的方差

**Assumption SLR.5 (homoskedasticity)**  
&emsp;**假设SLR.5（同构性）**

$$
  Var(u _i | x _i) = \sigma ^2
$$

$$
  Var(u _i | x _i) = E(u _i^2  | x _i) - [E(u _i | x _i)] ^2 = E(u _i^2  | x _i)
$$

which means  
&emsp;也意味着

$$
  Var(u _i) = E(u _i^2) = E[E(u _i^2  | x _i)] = \sigma ^2 = Var(u _i | x _i).
$$

![]({{site.url}}/assets/images/2020/ECON5002/Homoskedasticity.png 'Figure 4.2: Homoskedasticity')

![]({{site.url}}/assets/images/2020/ECON5002/Heteroskedasticity.png 'Figure 4.3: Heteroskedasticity 1')

![]({{site.url}}/assets/images/2020/ECON5002/Heteroskedasticity2.png 'Figure 4.4: Heteroskedasticity 2')

**Theorem 2.2 (The sampling variance of the OLS estimators)**  
&emsp;**定理2.2（OLS估计量的抽样方差）**

Under Assumptions SLR.1-SLR.5  
&emsp;在假设SLR.1-SLR.5下

$$
  Var(\hat{\beta} _1 | x) 
  = \frac {\sigma ^2}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
  = \frac {\sigma ^2}{\text{SST} _x}
  \tag{4.2} \label{varianceEstimator1}
$$

and  
&emsp;和

$$
  Var(\hat{\beta} _0 | x) 
  = \frac {\sigma ^2 n ^{-1} \sum _{i=1}^n x _i^2}{\sum _{i=1}^n (x _i - \overline{x}) ^2}
  \tag{4.3} \label{varianceEstimator2}
$$

where \\( x = \lbrace x _1, \cdots, x _2 \rbrace \\) (sample values).  
&emsp;其中\\( x = \lbrace x _1, \cdots, x _2 \rbrace \\)（示例值）。

But \\( \sigma ^2\\) is unknown! And \\(u _i s\\) are not observable!  
&emsp;但是\\( \sigma ^2\\)是未知的！和\\(u _i s\\)是不可见的！

**Theorem 2.3 (The unbiased estimator of \\( \sigma ^2\\))**  
&emsp;**定理2.3（\\(\sigma^2\\)的无偏估计）**

$$
  E(\hat{\sigma} ^2) = \sigma ^2,
  \ \hat{\sigma} ^2 = \frac{\sum _{i=1}^n \hat{u} _i^2}{n-2}.
$$

Why (n - 2)? Recall the OLS first order conditions:  
&emsp;为什么是（n - 2）？回忆最小二乘法的一阶条件：

$$
  \sum _{i=1}^n \hat{u} _i = 0,
  \ \sum _{i=1}^n \hat{u} _i x _i = 0.
$$

- If \\( \hat{\sigma} ^2\\) is plugged in \eqref{varianceEstimator1} and \eqref{varianceEstimator2} we get an estimate of the variance.  
&emsp;如果\\( \hat{\sigma} ^2\\) 插入了公式\eqref{varianceEstimator1}和\eqref{varianceEstimator2}，我们就得到了方差的估计。

- Similarly, the **standard errors (se)** of \\(\hat{\beta} _0 \\) and \\(\hat{\beta} _1 \\).  
&emsp;类似地，\\(\hat{\beta} _0 \\)和\\(\hat{\beta} _1 \\)的**标准错误（se）**。

$$
  \begin{array}{m}
      se(\hat{\beta} _1) 
      = \hat{\sigma} 
        \sqrt{\frac{1}{\sum _{i=1}^n (x _i - \overline{x}) ^2}}
      \\\\ se(\hat{\beta} _0) 
      = \hat{\sigma} ^2 
        \sqrt{\frac{n ^{-1} \sum _{i=1}^n x _i^2}{\sum _{i=1}^n (x _i - \overline{x}) ^2}}
  \end{array}
$$

are estimates of the standard deviation of the estimators.  
&emsp;是估计量的标准差的估计。

![]({{site.url}}/assets/images/2020/ECON5002/estimatedDensity.png 'Figure 4.5: The estimated density.')

### Takeaway  
&emsp;课外

- Assumptions SLR.1-SLR.4 are sucient to show that \\(\hat{\beta} _0\\), \\(\hat{\beta} _0\\) are unbiased.  
&emsp;假设SLR.1-SLR.4有助于证明\\(\hat{\beta} _0\\)，\\(\hat{\beta} _0\\)是无偏的。

- SLR stands for Simple Linear Regression.  
&emsp;SLR代表简单线性回归。

- Because \\( E(y _i \| x _i) = \beta _0 + \beta _1 x _i \\) (SLR.4), estimating \\(\hat{\beta} _0\\) and \\(\hat{\beta} _1\\) mean estimating the CEF.  
&emsp;因为\\( E(y _i \| x _i) = \beta _0 + \beta _1 x _i \\) (SLR.4)，估计\\(\hat{\beta} _0\\)和\\(\hat{\beta} _1\\)意味着估计CEF。

- SLR.5 is added to obtain the variance of the OLS estimators.  
&emsp;加入SLR.5得到OLS估计量的方差。

- Mean and Variance refer to random variables! Here we considered the OLS estimators, not the estimates.  
&emsp;均值和方差指的是随机变量！这里我们考虑的是OLS估计，而不是估计。

## 5. Counterfactual Outcomes and Causality  
&emsp;五. 反事实结果和因果关系

### Causal Effects  
&emsp;因果关系

Let \\(x _i\\) a binary variable (either \\(x _i = 1 \text{ or } x _i = 0\\) ).  
&emsp;设\\(x _i\\)一个二进制变量（要么\\(x _i = 1 \text{ or } x _i = 0\\)。

- \\(x _i = 1 \\) indicates a treatment.  
&emsp;\\(x _i=1\\)表示治疗。

- \\(x _i = 0 \\) indicates a non-treatment.  
&emsp;\\(x _i=0\\)表示不治疗。

We are interested in the causal effect of \\(x _i\\)  on \\(y _i (x _i)\\). The difference between the two **potential** outcomes:  
&emsp;我们感兴趣的是\\(x _i\\)对\\(y _i (x _i)\\)的因果关系。两种**潜在**结果之间的差异：

$$
  \tau _i = y _i (1) - y _i (0)
$$

is called the **causal** (or **treatment**) effect.  
&emsp;被称为**因果**（或**治疗**）效应。

Example (the Perry Preschool Project):  
&emsp;例如（佩里幼儿园项目）：

- \\( y _i (1) \\) is the wage of the individual \\( i \\) if he/she entered the preschool program (\treatment group").  
&emsp;\\( y _i (1) \\) 是个人i的工资，如果他/她进入学前教育项目（\治疗组“）。

- \\( y _i (0) \\) is the wage of the individual \\( i \\) if he/she received no preschool education (\control group").  
&emsp;\\( y _i (0) \\)是未接受学前教育的个人i的工资（i\\)（\对照组）。

- For the individual \\( i \\) we only observe one the two potential outcomes.  
&emsp;对于个体i而言，我们只观察到两种潜在结果中的一种。

For each unit \\( i \\), the observed outcome \\( y _i \\) can be written as:  
&emsp;对于每个单位\\(i \\)，观察到的结果\\(y i \\)可以写出来:

$$
  y _i 
  = (1-x _i)y _i (0) + y _i (1) x _i 
  = y _i (0) + [y _i(1) + y _i (0)]x _i 
  \tag{5.1} \label{observedOutcome}
$$

Check that  
&emsp;检查

$$
  y _i =
  \begin{cases}
  y _i (1) \text{ if } x _i = 1,
  \\\\
  y _i (0) \text{ if } x _i = 0.
  \end{cases}
$$

Equation \eqref{observedOutcome} can be rewritten as  
&emsp;等式\eqref{observedOutcome}可以被重新为

$$
  y _i = y _i(0) + \tau _i x _i
  \tag{5.2}
$$

We cannot hope to estimated \\( \tau _i \\) for each unit \\( i \\).  
&emsp;我们希望为每一个单位i估计出\\( \tau _i \\)

Our aim will be to estimate the **average treatment (or causal) effect (ATE)**:  
&emsp;我们的目标是估计**平均治疗（或因果）效应（ATE）**：

$$
  \tau _{ate} = E(\tau _i) = E[y _i (1) - y _i (0)] = \alpha _1 - \alpha _0
$$

where  
&emsp;其中

$$
  \alpha _1 = E[y _i (1)] \text{, and } \alpha _0 = E[y _i (0)]
$$

Define  
&emsp;定义

$$
  y _i (1) = \alpha _1 + u _i (1) 
  \text{  and  } 
  y _i (0) = \alpha _0 + u _i (0)
$$

Then, equation  
&emsp;那么，等式

$$
  y _i = y _i (0) + \tau _i  x _i
  \tag{5.3}
$$

can be written as  
&emsp;可以被写作：

$$
  y _i = \alpha + \tau _{ate} \cdot x _i + u _i
  \tag{5.4}
$$

where \\( \tau _{ate} = \alpha _1 - \alpha _0\\), and  
&emsp;其中 \\( \tau _{ate} = \alpha _1 - \alpha _0\\)，而且

$$
  u _i = u _i(0) + [u _i(1) - u _i(0)] x _i
  \tag{5.5}
$$

If the treatment is randomly assigned  
&emsp;如果治疗被随机地指派

$$
  x _i \models [u _i(0) , u _i(1)]
  \tag{5.6}
$$

![]({{site.url}}/assets/images/2020/ECON5002/specialCharEq.png 'Equation 5.6: The estimated density.')

(post the clip here because the author has doubts of the character inside this equation)

Hence,  
&emsp;因此，

$$
  E[u _i (0) | x _i] = E[u _i (0)], \ E[u _i (1) | x _i] = E[u _i (1)]
  \tag{5.7}
$$

implying  
&emsp;意味着

$$
  E[u _i | x _i] 
  = E[u _i (0) | x _i] + E[u _i (1) - u _i (0) | x _i] x _i 
  = 0 
  \tag{5.8}
$$

The OLS estimators are unbiased for the \\(\alpha _0 \\) and \\( \tau _{ate} \\)!  
&emsp;OLS估计量对于 \\(\alpha _0 \\)和\\( \tau _{ate} \\)是无偏的！

### Takeaway  
&emsp;课外

- \\( \tau _{ate} \\) can be estimated by OLS.  
&emsp;\\( \tau _{ate} \\)可以用OLS估计。

- Random assignment implies that \\(E[u _i \| x _i]  = 0 \\). We conclude that \\( \hat{\tau} _{ate} \\) is unbiased.  
&emsp;随机赋值意味着\\(E[u _i \| x _i]  = 0 \\)。我们的结论是 \\( \hat{\tau} _{ate} \\)是无偏的。

## Video 6: Multiple regression analysis  
&emsp;视频6：多元回归分析

### Motivation  
&emsp;动机

Consider an extension of the regression of *lwage* on *educ*:  
&emsp;考虑*lwage*对*educ*回归的一个扩展：

$$
  lwage = \beta _0 + \beta _1 educ + \beta _2 IQ +u
$$

*IQ* is the Intelligence Quotient score (In population, the *IQ* score has mean 100 and standard deviation 15.)  
&emsp;*IQ*是智商得分（在人群中，*IQ*得分的平均值为100，标准差为15。）

Primarily interested in \\(\beta _1\\), but \\(\beta _2\\) is of some interest, too. Including *IQ* in the equation, it is taken out of the error term.  
If *IQ* is a good proxy for intelligence, this may lead to a more
persuasive estimate of the causal effect of schooling.  
&emsp;主要对\\(\beta _1\\)感兴趣，但\\\(\beta _2\\)也有兴趣。在方程中加上IQ，就从误差项中去掉了。
如果智商是智力的一个很好的代表，这可能会导致对学校教育因果关系的更具说服力的估计。

A model with two independent variables can be written as  
&emsp;有两个自变量的模型可以写成

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + u,
  \tag{6.1}
$$

- \\(\beta _0\\) is the intercept.  
&emsp;\\(\beta _0\\)是截距。

- \\(\beta _1\\) measures the change in y with respect to \\(x _1 \\), holding other factors fixed.  
&emsp;\\(\beta _1\\)测量y相对于\\(x _1\\)的变化，保持其他因素不变。

- \\(\beta _2\\) measures the change in y with respect to \\(x _2 \\), holding other factors fixed.  
&emsp;\\(\beta _2\\)测量y相对于\\(x _2\\)的变化，保持其他因素不变。

- *u* is the unobserved component (error).  
&emsp;*u*是未观测到的分量（误差）。

In the model with two explanatory variables, the key assumption about how u is related to \\(x _1 \\) and \\(x _2 \\) is  
&emsp;在有两个解释变量的模型中，关于u如何与\\(x _1 \\)和\\(x _2 \\)相关的关键假设是

$$
  E(u  | x _1, x _2)  = 0 .
  \tag{6.2}
$$

Then \\( E (y \| x _1, x _2 ) = \beta _0 + \beta _1 x _1 + \beta _2 x _2\\) and  
&emsp;那么\\( E (y \| x _1, x _2 ) = \beta _0 + \beta _1 x _1 + \beta _2 x _2\\)和

$$
  y = E (y | x _1, x _2 ) + u
$$

In the wage equation, the assumption is \\( E(u \| educ, IQ) = 0\\).  
&emsp;在工资公式中，假设为\\( E( u \| educ, IQ) = 0\\)。

Now *u* no longer contains intelligence (we hope), and so this assumption has a better chance of being true.  
&emsp;现在，*u*不再包含智力（我们希望如此），因此这个假设更有可能成为事实。

In the simple regression model, we had to assume *IQ* and *educ* were unrelated to justify \\( E(u \| educ) = 0\\)  (*IQ* was in *u*).  
&emsp;在简单回归模型中，我们必须假设*IQ*和*educ*与justify\\(E（u \| educ）=0\\)（*IQ*在*u*中）。

Other factors, such as workforce experience and @motivation," are part of u. Motivation is very dicult to measure. Measuring experience is easier:  
&emsp;其他因素，如工作经验和“激励”也是美国的一部分。激励很难衡量。测量体验更容易：

$$
  lwage = \beta _0 + \beta _1 educ + \beta _2 IQ + \beta _3 exper + u
$$

### The Model with k Explanatory Variables  
&emsp;k解释变量模型

The **multiple linear regression model** can be written in the population as  
&emsp;**多元线性回归模型**可以在总体中写成

$$
   y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \cdots +\beta _k x _k + u
$$

\\( \beta _0\\) is the **intercept**, \\( \beta _1\\) is the parameter associated with \\( x _1 \text{, } \beta _2\\) is the parameter associated with  \\( x _2\\), and so on.  
&emsp;\\( \beta _0\\)是**截距**，\\( \beta _1\\)是与\\( x _1 \text{, } \beta _2\\)相关的参数，依此类推。

Contains *k* + 1 (unknown) population parameters. We call \\( \beta _1, \cdots, \beta _k \\) the **slope parameters**.  
&emsp;包含*k*+1（未知）总体参数。我们称\\(\beta _1、\cdots、\beta _k\\)为**斜率参数**。

Multiple regressions allows more flexible functional forms.  
&emsp;多元回归允许更灵活的函数形式。

$$
  lwage = \beta _0 + \beta _1 educ + \beta _2 IQ + \beta _3 exper 
    + \beta _4 exper^2+ u 
$$

&emsp;so that exper is allowed to have a quadratic effect on *lwage*.  
这样exper就可以对*lwage*产生二次效应。

Let \\( x _1 = educ, x _2 = IQ, x _3 = exper, and x _4 = exper ^2 \\).  
&emsp;假设上述情况。

Note that \\(x _4\\) is a a nonlinear function of \\(x _3\\), but the model is still linear in the parameters!  
&emsp;注意，\\(x _4\\)是一个非线性函数，\\(x _3\\)，但是模型的参数仍然是线性的！

We already know that \\(100 \cdot \beta _1\\) is the ceteris paribus percentage change in *wage* when *educ* increases by one year.  
&emsp;我们已经知道，\\(100 \cdot \beta _1\\)是当教育费增加一年时，工资的其他同等百分比变化。

\\(100 \cdot \beta _2\\) has a similar interpretation (for \\(\Delta IQ = 1\\)).  
&emsp;\\(100 \cdot \beta _2\\)有类似的解释（对于\\(\Delta IQ = 1\\)）。

\\( \beta _3\\)  and \\( \beta _4\\) are harder to interpret. Using calculus,  
&emsp;\\( \beta _3\\)和\\( \beta _4\\)更难理解。用微积分，

$$
  \frac{\partial lwage} {\partial exper} 
  = \beta _3 + 2 \beta _4 exper
$$

&emsp; Multiply by 100 to get the percentage effect.  
&emsp;&emsp;乘以100得到百分比效果。

### Takeaway  
&emsp;课外

The multiple regression model allows us:  
&emsp;多元回归模型允许我们：

- to control for many other factors that simultaneously affect the dependent variables (ceteris paribus interpretation),  
&emsp;控制同时影响因变量的许多其他因素（其他因素同等解释），
 
- to model non-linear relationships (linearity is in the parameters!).  
&emsp;建立非线性关系模型（线性在参数中！）。

## Video 7: Mechanics and Interpretation of the Ordinary Least Squares  
&emsp;视频7：普通最小二乘法的力学和解释

### Interpreting the OLS Regression Line  
&emsp;解释OLS回归线

Consider the case *k* = 2:  
&emsp;考虑情况*k*=2：

$$
  \hat{y} = \hat{\beta} _0 + \hat{\beta} _1 x _1 + \hat{\beta} _2 x _2
  \tag{7.1}
$$

The intercept\\( \hat{\beta} _0 \\)is the predicted value of *y* when \\( x _1 = x _2 = 0 \\)  
&emsp;截距\\( \hat{\beta} _0 \\)是当\\( x _1 = x _2 = 0 \\)时*y*的预测值

The estimates \\( \hat{\beta} _1, \ \hat{\beta} _2\\) have **partial effects**, or **ceteris paribus** interpretations.  
&emsp;估计数\\( \hat{\beta} _1, \ \hat{\beta} _2 \\)具有**部分效应**，或**其他同等**解释。


If we "hold \\(x _2 \\) fixed"  
&emsp;如果我们“保持\\(x _2 \\)固定"


$$
  \Delta \hat{y}
  = \hat{\beta} _1 \Delta x _1 
  \text{ if } \Delta x _2 = 0
$$

\\( \beta _1\\) measures the predicted change in *y* due a one-unit increase in \\(x _1 \\), holding \\(x _2 \\) fixed.  
&emsp;\\( \beta _1\\) 衡量由于\\(x _1 \\)增加一个单位，持有\\(x _2 \\)固定不变而导致的*y*的预测变化。

Similarity,  
&emsp;相似的，

$$
  \hat{\beta} _2 = \frac{\Delta \hat{y}}{\Delta x _2} 
  \text{ if } \Delta x _1 = 0
$$

**Example**  
&emsp;例子

Dataset1 WAGE2.DTA(Wooldridge, online resources):

$$
  \begin{array}{m}
    \widehat{lwage} = 1.142 + .099 educ
    \\\\n = 759
  \end{array}
$$

and  
&emsp;和

$$
  \begin{array}{m}
    \widehat{lwage} = .728 + .073 educ + .0076IQ
    \\\\n = 759
  \end{array}
$$

The predicted return to a year of education falls from about 9:9% to about 7:3% when we control for differences in *IQ*.  
&emsp;如果我们控制智商的差异，预计一年的教育回报率从9:9%下降到7:3%。

- The simple regression does not allow us to compare people with the same *IQ* score.  
&emsp;简单的回归不允许我们比较那些智商相同的人。

- The larger estimated return from simple regression is because we are attributing part of the *IQ* effect to education.  
&emsp;简单回归得到的更大的估计回报是因为我们把部分智商效应归因于教育。

- Not surprisingly, \\( Corr(educ, IQ) = :573 \\).  
&emsp;毫不奇怪，\\( Corr(educ, IQ) = :573 \\)。

### Comparing Simple and Multiple Regression Estimates  
&emsp;比较简单和多元回归估计

Consider the simple and multiple OLS regression functions:  
&emsp;考虑简单和多重OLS回归函数：

$$
  \widetilde{y} _i = \widetilde{\beta} _0 + \widetilde{\beta} _1 x _{1i}
  \tag{7.2}
$$

$$
  \hat{y} _i = \hat{\beta} _0 + \hat{\beta} _1 x _{1i} + \hat{\beta} _2 x _{2i}
  \tag{7.3} 
$$

using the same *n* observations.  
&emsp;使用相同的*n*观测值。

Question: Is there a relationship between \\( \beta _1\\) (which does not control for \\( x _2\\) ) and \\( \beta _1\\) (which does)?  
&emsp;问题：\\(\beta _1\\)（不控制\\(x _2\\)）和\\(\beta _1\\)（控制x _2\\)之间有关系吗？

Yes, but we need to define another simple regression.  
&emsp;是的，但是我们需要定义另一个简单的回归。

Regressing \\( x _2\\) on \\( x _1\\) and a constant we obtain  
&emsp;在\\(x _1\\)上回归\\(x _2\\)，得到一个常数

$$
  x _{2i} = \widetilde{\delta} _0 + \widetilde{\delta} _1 x _{1i} + \widetilde{r} _i
  \tag{7.4}
$$

Then,  
&emsp;那么，

$$
  \begin{align}
    \hat{y} _i & = \hat{\beta} _0 + \hat{\beta} _1 x _{1i} + \hat{\beta} _2 x _{2i} \tag{7.5}
    \\\\ & = \left( \hat{\beta} _0 + \hat{\beta} _1 \widetilde{\delta} _0 \right)
    + \left( \hat{\beta} _1 + \hat{\beta} _2 \widetilde{\delta} _1 \right) x _{1i} + \hat{\beta} _2 \widetilde{r} _i \tag{7.6}
  \end{align}
$$

&emsp;where \\( \sum _{i=1}^n x _1 \widetilde{r} _i =0 \\) by construction.  
&emsp;&emsp;其中\\( \sum _{i=1}^n x _1 \widetilde{r} _i =0 \\)由构造。

Regressing y on \\( x _1\\) and a constant only or on \\([x _1, \widetilde{r}]\\) and a constant gives the same estimate of the coecient of \\( x _1\\).  
&emsp;将y在\\( x _1\\)上和一个常数或仅在\\([x _1, \widetilde{r}]\\)上和一个常数上回归得到\\( x _1\\)系数的相同估计。

For any sample  
&emsp;对于任何样本

$$
  \widetilde{\beta} _1 
  = \hat{\beta} _1 + \hat{\beta} _2 \widetilde{\delta} _1
  \tag{7.7}
$$

If the partial effect of \\( x _2\\) on *y* is positive, so \\( \widetilde{\beta} _2 > 0\\), and \\( x _1\\) and \\( x _2\\) are positive correlated in the sample, so \\( \widetilde{\delta} > 0 \\), then  
&emsp;如果\\( x _2\\)对*y*的部分效应是正的，那么\\( \widetilde{\beta} _2 > 0\\)和\\( x _1\\)和\\( x _2\\)在样本中是正相关的，所以\\( \widetilde{\delta} > 0 \\)，那么

$$
  \widetilde{\beta} _1 > \hat{\beta} _1
$$

**Example**  
&emsp;例子

![]({{site.url}}/assets/images/2020/ECON5002/example.png "lwage example")

### Takeaway  
&emsp;课外

- In the multiple regression model, the slopes measure the partial effects of the corresponding regressor on the dependent variable, holding all other regressors fixed.  
&emsp;在多元回归模型中，斜率测量了相应回归因子对因变量的部分影响，保持所有其他回归因子不变。

- Comparing the single and the bivariate model will be helpful to understand the omitted variable bias.  
&emsp;比较单变量模型和双变量模型有助于理解忽略的变量偏差。

## Video 8: Expected Value and Variance of the OLS estimators  
&emsp;视频8:OLS估计量的期望值和方差

### The Expected Value of the OLS Estimators  
&emsp;OLS估计量的期望值

As for the simple regression, we can specify a set of assumptions under which OLS is unbiased.  
&emsp;对于简单回归，我们可以指定一组假设，在这些假设下OLS是无偏的。

We will also explicitly consider the bias caused by omitting a variable that appears in the population model.  
&emsp;我们还将明确考虑由于忽略人口模型中出现的变量而导致的偏差。

The assumptions are labelled "MLR" (multiple linear regression).  
&emsp;这些假设被标记为“多元线性回归”。

**Assumption MLR.2 (Random Sampling)**  
&emsp;假设MLR.2（随机抽样）

We have a random sample of size n from the population, \\( \lbrace [x _{1i}, x _{2i}, \cdots, x _{ki}, y _i]: i = 1, \cdots,n \rbrace \\)  
&emsp;我们从人群中随机抽取了一个大小为n的样本，\\( \lbrace [x _{1i}, x _{2i}, \cdots, x _{ki}, y _i]: i = 1, \cdots,n \rbrace \\)

**Assumption MLR.1 (Linear in Parameters)**  
&emsp;假设MLR.1（参数线性）

For every unit "i", the model in the population can be written as  
&emsp;对于每个单位“i”，人口中的模型可以写成

$$
  y _i = \beta _0 + \beta _1 x _{1i} + \beta _2 x _{2i} + \cdots
    + \beta _k x _{ki} + u _i
$$

where the \\(\beta _k\\) are the population parameters and ui is the unobserved error.  
&emsp;其中，\\(\beta _k\\)是填充参数，ui是未观察到的错误。

**Assumption MLR.3 (No Perfect Collinearity)**  
&emsp;**假设MLR.3（无完全共线）**

In the sample (and in the population), none of the explanatory variables is constant, and there are no exact linear relationships among them.  
&emsp;在样本（和总体）中，没有一个解释变量是恒定的，它们之间也没有精确的线性关系。

We must rule out the case that one of the explanatory variables is an exact linear function of the others.  
&emsp;我们必须排除其中一个解释变量是其他变量的精确线性函数的情况。

Under perfect collinearity, there are no unique OLS estimators.  
&emsp;在完全共线性下，不存在唯一的OLS估计。

Usually perfect collinearity arises from a bad model specification.  
&emsp;通常，完美的共线性来自于糟糕的模型规格。

Perfect collinearity could also arise because of small sample size or bad luck in drawing. e.g. *educ/IQ *= constant.  
&emsp;由于样本量小或绘图运气不好，也可能出现完全共线。e、 g.*educ/IQ*=常数。

Assumption MLR.3 can only hold if \\( n > k + 1 \\).  
&emsp;假设MLR.3只能在\\(n>k+1\\)时成立。

**Assumption MLR.4 (Zero Conditional Mean)**  
&emsp;**假设MLR.4（零条件平均值）**

$$
  E(u _i | x _{1i}, x _{2i}, \cdots, x _{ki}) = 0
$$

**EXAMPLE: Effects of Class Size on Student Performance**  
&emsp;**例：班级规模对学生成绩的影响**

Suppose, for a standardized test score,  
&emsp;假设，对于标准化考试分数，

$$
  score = \beta _0 + \beta _1 classize + \beta _2 income + u
$$

Even at the same income level, families differ in their interest and concern about their children's education.  
&emsp;即使在相同的收入水平下，家庭对子女教育的兴趣和关注程度也不尽相同。

Family support and student motivation are in *u*.  
&emsp;家庭支持和学生动力在*u*中。

If the omitted factors are correlated with *classize* and *income*，**Assumption MLR.4 fails**.  
&emsp;如果省略的因素与*分类*和*收入*相关，**假设MLR.4失败**。 

**Theorem 2.1. Unbiasedness of OLS**  
&emsp;**定理2.1。OLS的无偏性**

Under Assumption MLR.1-MLR.4  
&emsp;假设MLR.1-MLR.4

$$
  E \left( \hat{\beta} _j \right) = \beta _j \text{, for } j = 0, 1, \cdots, k
$$

### Inclusion of Irrelevant Variables  
&emsp;包含无关变量

Suppose, then, that we specify the model  
&emsp;那么，假设我们指定了模型

$$
  lwage = \beta _0 + \beta _1 educ + \beta _2 exper 
    + \beta _3 mothexper + u 
$$

where MLR.1 through MLR.4 hold.  
&emsp;1号到4号传送器所在位置。

Suppose that \\( \beta _3 = 0 \\), but we do not know that. We estimate:  
&emsp;假设\\( \beta _3 = 0 \\)，但我们不知道。我们估计：

$$
  \widehat{lwage} = \hat{\beta} _0 + \hat{\beta} _1 educ + \hat{\beta} _2 exper + \hat{\beta} _3 motheDUC + u 
$$

We know from the unbiasedness result that  
&emsp;我们从无偏结果中可以得知

$$
  E \left ( \hat{\beta} _j \right) = \beta _j 
  \text{, } j = 0,1,2 \text{, and }
  E \left ( \hat{\beta} _3 \right) = 0
$$

### Omitted Variable Bias  
&emsp;省略变量偏差

Leaving a variable out when it should be including in multiple regression could lead to the **omitted variable bias**.  
&emsp;当一个变量应该包含在多元回归中时，将其忽略可能会导致**忽略变量偏差**。

Assume that the correct model has two explanatory variables:  
&emsp;假设正确的模型有两个解释变量：

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2  + u
$$

But suppose we leave out \\( x _2\\) and use simple regression of *y* on \\( x _1\\).  
&emsp;但是假设我们省略了\\(x _2 \\)，使用简单的回归*y*在\\(x _1 \\)上。

We should have estimated  
&emsp;我们应该估计

$$
 \hat{y} = \hat{\beta} _0 + \hat{\beta} _1 x _1 + \hat{\beta} _2 x _2
$$

but we estimate  
&emsp;但是我们估计

$$
  \widetilde{y} = \widetilde{\beta} _0 + \widetilde{\beta} _1 x _1
$$

Recall that  
&emsp;回顾

$$
  \widetilde{\beta} _1 = \hat{\beta} _1 + \hat{\beta} _2 \widetilde{\delta} _1
$$

where  
&emsp;其中

$$
  \hat{x} _2 = \widetilde{\delta} _0 + \widetilde{\delta} _1 x _1
$$

Conditional on the sample values of \\( x _1\\) and \\( x _2\\).  
&emsp;以样本值\\(x _1\\)和\\( x _2\\)为条件。

$$
  E \left( \widetilde{\beta} _1 | x \right ) 
  = E \left( \hat{\beta} _1 | x \right) 
    + \widetilde{\delta} _1 E \left( \hat{\beta} _2 | x \right) 
  = \beta _1 + \beta _2 \widetilde{   \delta} _1
$$

Bias \\( \left( \widetilde{\beta} _1 \| x \right) = E \left( \widetilde{\beta} _1 \| x \right) - \beta _1 = \beta _2 \widetilde{\delta} _1 \\)  
&emsp;上述偏差

The bias can be computed for any \\( \lbrace (x _{1i}, x _{2i}), i = 1, \cdots,n \rbrace \\), but if \\(i n \\rightarrow \infty \\) the bias will approach  
&emsp;可以为任何\\(\lbrace（x{1i}，x{2i}），i=1，\cdots，n\rbrace\\)计算偏差，但是如果\\(i n\\rightarrow\infty\\)，偏差将接近

$$
  \frac{Cov(x _{1i}, X _{2i})} {Var (x _{1i})} \beta _2
$$

The simple regression estimator is unbiased (for the given outcomes \\( \lbrace (x _{1i}, x _{2i}), i = 1, \cdots,n \rbrace \\) in two cases:  
&emsp;简单回归估计在两种情况下是无偏的（对于给定的结果\\(\lbrace（x{1i}，x{2i}），i=1，\cdots，n\rbrace\\)：

1. \\( \beta _2 = 0 \\) ( \\(x_2\\) does not appear in the population model),  
&emsp;\\(\beta _2=0\\)（\\(x _2\\)未出现在总体模型中），


2. \\( \widehat{Corr} (x _{1i}, x _{2i}) = 0 \\) (in the sample), entailing \\( \widetilde{\delta} _1 = 0 \\)  
&emsp;\\(\widehat{Corr}（x{1i}，x{2i}）=0\\)（在示例中），包含\\(\widetilde{\delta}u1=0\\)


### The Variance of the OLS Estimators  
&emsp;OLS估计量的方差

**Assumption MLR.5 (Homoskedasticity)**  
&emsp;**假设MLR.5（同构性）**

The conditional variance of the error, ui, does not change with any of \\( x _{1i}, x _{2i}, \cdots, x _{ki} \\) :  
&emsp;错误的条件方差ui不随\\(x{1i}，x{2i}，\cdots，x{ki}\\)中的任何一个而改变：

$$
  Var( u _i | x _{1i}, x _{2i}, \cdots, x _{ki}) = Var(u _i) = \sigma ^2
$$

Assumptions MLR.1 through MLR.5 are called the **Gauss Markov assumptions**.  
&emsp;假设MLR.1到MLR.5被称为**高斯-马尔可夫假设**。

**Theorem 3.2 (Sampling Variances of OLS Slope Estimators)**  
&emsp;**定理3.2（OLS斜率估计量的抽样方差）**

Under Assumptions MLR.1 to MLR.5, and condition on the values of the explanatory variables in the sample,  
&emsp;在假设MLR.1到MLR.5的情况下，以样本中解释变量的值为条件，

$$
  Var \left ( \hat{\beta} _ j | x \right)
  = \frac{\sigma ^2} {SST _j (1-R _j^2)}
  \text{, } j = 1, 2, \cdots, k.
$$

where  
&emsp;其中

- \\( SST _j = \sum _{i=1}^n (x _{ji} - \overline{x} _j) ^2\\)

- \\( R _j^2\\) is the \\(R ^2\\) of the regression

$$
  x _{ji} \text{ on } x _{1i}, x _{2i}, \cdots, x _{j-1,i}, x _{j+1,i},\cdots, x _{k,i}
$$

- Adding explanatory variables reduces \\( \sigma ^2 \\).  
&emsp;添加解释性变量会减少\\(\sigma^2\\)。

- It is easier to estimate how \\( x _j \\) affects *y* if we see more variation in \\( x _j \\) , and/or *n* is large.  
&emsp;如果我们看到\\(x _j\\)中有更多的变化，和/或*n*很大，则更容易估计\\(x _j\\)如何影响*y*。

- If \\( x _j \\) is unrelated to all other independent variables, it is easier to estimate its ceteris paribus effect on *y*.  
&emsp;如果\\(x _j \\)与所有其他自变量无关，则更容易估计它对*y*的其他同等影响。

- As \\( R _j^2 \\rightarrow 1\text{, } Var( \hat{\beta} _j) \\rightarrow 1 \\) (the estimate of \\(\beta _j \\) is not precise).  
&emsp;As\\(R _j^2\\rightarrow 1\text{，}Var（\hat{\beta} _j）\\rightarrow 1\\)（估计的\\(\beta _j\\)不精确）。

### Variances in Misspecified Models  
&emsp;错误指定模型中的方差

As for bias calculations, we can study the variances of the OLS estimators in misspecified models.  
&emsp;至于偏差计算，我们可以研究错误指定模型中OLS估计量的方差。

Assume that the model  
&emsp;假设模型

$$
  y = \beta _0 +\beta _1 x _1 + \beta _2 x _2 +u
$$

satisfies the Gauss-Markov assumptions.  
&emsp;满足Gauss-Markov假设。

We run the misspecified and the correctly specified regressions,  
&emsp;我们运行错误指定和正确指定的回归，

$$
  \begin{array}{m}
  \widetilde{y} = \widetilde{\beta} _0 + \widetilde{\beta} _1 x _1
  \\\\ \hat{y} = \hat{\beta} _0 + \hat{\beta} _1 x _1 + \hat{\beta} _2 x _2
  \end{array}  
$$

We know from the previous analysis that  
&emsp;根据前面的分析我们知道

$$
  Var \left ( \hat{\beta} _ j | x \right)
  = \frac{\sigma ^2} {SST _1 (1-R _1^2)}
$$

conditional on {\\( [x _{1i}, x _{2i}]: i = 1,\cdots, n \\)}.  
&emsp;条件为{\\([x{1i}，x{2i}）：i=1，\cdots，n\\)}。

What about the simple regression estimator? Can show  
&emsp;那么简单回归估计呢？可以显示

$$
  Var \left ( \widetilde{\beta} _ j | x \right)
  = \frac{\sigma ^2} {SST _1 }
$$

Whenever \\( x _{1i} \\) and \\( x _{2i} \\) are correlated, \\( R _1^2 > 0 \\), and  
&emsp;当\\( x _{1i} \\)和\\( x _{2i} \\)相关时，\\( R _1^2 > 0 \\)，和

$$
  Var \left ( \widetilde{\beta} _ j | x \right)
  = \frac{\sigma ^2} {SST _1 }
  < \frac{\sigma ^2} {SST _1 (1-R _1^2)}
  < Var( \hat{\beta} _1 | x)
$$

- So, by omitting \\(x _2\\), we can in fact get an estimator with a smaller variance, even though it is biased.  
&emsp;所以，通过省略\\(x _2 \\)，我们实际上可以得到一个方差较小的估计量，即使它是有偏的。

- When we look at bias and variance, we have a trade-off between simple and multiple regression.  
&emsp;当我们考虑偏差和方差时，我们在简单回归和多元回归之间进行了权衡。

- Conditioning on the same explanatory variables, we ignored the difference in the variance of the error term.  
&emsp;在相同的解释变量条件下，我们忽略了误差项方差的差异。

- \\(\sigma ^2\\) will be higher for the simple regression model (conditioning in \\( x _1\\) only)!  
&emsp;对于简单回归模型，\\(\sigma^2\\)将更高（仅在\\(x _1\\)中调节）！

### Estimating the Error Variance  
&emsp;估计误差方差

**Theorem: (Unbiased Estimation of \\( \sigma ^2 \\))**  
&emsp;**定理：（无偏估计\\(\sigma^2\\)**

Under the Gauss-Markov assumptions (MLR.1 through MLR.5)  
&emsp;在Gauss-Markov假设下（MLR.1到MLR.5）

$$
  \hat{\sigma} ^2 
  = (n - k - 1) ^{-1} \sum _{i=1}^n \hat{u} _i^2 
  = SSR/df 
$$

is an unbiased estimation of \\( \sigma ^2 \\)  
&emsp;是\\(\sigma^2\\)的无偏估计

- The square root of \\( \hat{\sigma} ^2, \hat{\sigma} \\), is reported by all regression packages (**standard error of the regression**, or **RMSE**).  
&emsp;\\(\hat{\sigma}^2，\hat{\sigma}\\)的平方根由所有回归包报告（**回归的标准误差**，或**RMSE**）。

- Note that *SSR* falls when a new explanatory variable is added, but *df* falls, too. So \\( \hat{\sigma} \\) can increase or decrease!  
&emsp;请注意，添加新的解释变量时，*SSR*会下降，但*df*也会下降。所以\\(\hat{\sigma}\\)可以增加或减少！

### Efficiency of OLS  
&emsp;OLS的效率

**THEOREM 3.4 (Gauss-Markov)**  
&emsp;**定理3.4（高斯-马尔可夫）**

Under Assumptions MLR.1 through MLR.5, the OLS estimators \\( \hat{\beta} _0, \hat{\beta} _1, \cdots, \hat{\beta} _k \\) are the **best linear unbiased estimators (BLUEs)**.  
&emsp;在假设MLR.1到MLR.5下，OLS估计量\\(\hat{\beta}u 0、\hat{\beta}u 1、\cdots、\hat{\beta}u k\\)是**最佳线性无偏估计量（blue）**。

- Best: smaller variance  
&emsp;最佳：方差较小

- Linear: can be expressed as a linear function of { \\(y _1, \cdots, y _n\\)},  
&emsp;线性：可以表示为{\\(y _1，\cdots，y _n\\)}的线性函数，

$$
  \hat{\beta} _j = \sum _{i=1}^n w _{ji} y _i
$$

where each \\( w _{ji} \\) is a function of the sample values of all independent variables. 
&emsp;其中每一个\\( w _{ji} \\)是所有独立变量（自变量？）的样本值的函数

### Takeaway  
&emsp;课外

- Under the Gauss-Markov Assumptions the OLS estimator are unbiased.  
&emsp;在Gauss-Markov假设下，OLS估计是无偏的。

- Omitting relevant variables causes OLS to be biased.  
&emsp;忽略相关变量会导致OLS有偏。

- Adding irrelevant variables generally increases the variance of the OLS estimators.  
&emsp;添加不相关的变量通常会增加OLS估计量的方差。

## Video 9: Potential Outcomes and Causal Effects  
&emsp;视频9：潜在结果和因果关系

### Causality  
&emsp;因果关系

- *Causality* has different means to different people.  
&emsp;因果关系对不同的人有不同的意义。

- Researchers working in different disciplines have found it useful to think of causal relationships in terms of potential outcomes.  
&emsp;从事不同学科的研究人员发现，从潜在结果的角度考虑因果关系是很有用的。

- The difference between these potential outcomes was said to be causal effect of the treatment.  
&emsp;这些潜在结果之间的差异被认为是治疗的因果效应。

- We saw that regression can be used to estimate the average treatment effect.  
&emsp;我们看到回归可以用来估计平均治疗效果。

- Suppose that there are two individuals, Amy and Ben, and both have the possibility of being high-school graduates or college graduates.  
&emsp;假设有两个人，艾米和本，都有可能是高中毕业生或大学毕业生。

- 2 possible states of the world: college and high-school graduation; 2 potential outcomes specific to each individual.  
&emsp;世界上有两种可能的状态：大学和高中毕业；每个人有两种可能的结果。

- Amy would have earned $20/hour as college graduated, $10/hour as high school graduate.  
&emsp;艾米大学毕业时每小时挣20美元，高中毕业时每小时挣10美元。

- Ben would have earned $12/hour as college graduated, $8/hour as high school graduate.  
&emsp;本大学毕业时每小时挣12美元，高中毕业时每小时挣8美元。

- Suppose we have a population of 32 individuals with equal numbers of Amies and Bens.  
&emsp;假设我们有一个32个人的群体，他们有相等数量的阿米和本。

- Suppose further that the individual type is unobservable.  
&emsp;进一步假设单个类型是不可观察的。

- The causal effect of going to college is $10 for Amy, $4 for Ben. The average causal effect is $7.  
&emsp;上大学的因果关系是艾米10美元，本4美元。平均因果效应为7美元。

- Is this what we learn from the regression analysis?  
&emsp;这是我们从回归分析中学到的吗？

Now suppose that while in high school all students take an aptitude test.  
&emsp;假设在高中时所有的学生都参加了能力倾向测试。

- If a student gets a high (*H*) score he/she goes to college with probability 3/4.  
&emsp;如果一个学生获得高分（*H*），他/她上大学的概率为3/4。

- If a student gets a low (*L*) score he/she goes to college with probability 1/4.  
&emsp;如果一个学生的分数很低，他/她上大学的概率是1/4。

- Suppose further that Amy gets an aptitude score of *H* with probability 3/4. Ben gets a score of *H* with probability 1/4.  
&emsp;进一步假设艾米的能力倾向得分为*H*，概率为3/4。本的得分是H，概率是1/4。

$$
  \begin{align}
    Pr(col | Amy) 
    & = Pr(col | H) Pr(H | Amy) + Pr(col | L) Pr(L | Amy)
    \\\\ & = (3/4) ^2 + (1/4) ^2 = 0.625
  \end{align}
$$

where *col* is the short for college. Similarly, \\( Pr(col \| Ben) = 0.375 \\).  
&emsp;*col*是大学的缩写。类似地，\\(Pr（col\| Ben）=0.375\\)。

![]({{site.url}}/assets/images/2020/ECON5002/distributions.png "Figure 9.1: Distributions")

- Let *col* denote a binary variable taking value 1 for a college graduate, 0 otherwise. From Table 1 we get  
&emsp;让*col*表示一个二进制变量，对于大学毕业生取1，否则取0。从表1我们得到

$$
  E[wage | col] = 8.75 + 8.25 col
$$

- $8.25 overstates the average causal effect of $7.  
&emsp;8.25美元夸大了7美元的平均因果效应。

- $8.25 is not the *Average Causal Effect* (ACE) of attending college, but it is the observed difference in realized wages in population.  
&emsp;8.25美元不是上大学的*平均因果效应*（ACE），而是人口中实际工资的观察差异。

- The decision to attend college is not independent of the unobservable individual type (Amy or Ben).  
&emsp;上大学的决定并不独立于不可观察的个体类型（艾米或本）。

- Additional education is not randomly assigned!  
&emsp;附加教育不是随机分配的！

- To estimate the *Average Causal Effect* we need to condition on the appropriate variables.  
&emsp;为了估计*平均因果效应*我们需要在适当的变量上设置条件。

- The decision to attend the college is based on the aptitude test score, and not on the individual type.  
&emsp;上大学的决定是基于能力倾向测试分数，而不是个人类型。

- Thus education and type are independent once we condition on the test score.  
&emsp;因此，教育和类型是独立的，一旦我们对考试成绩的条件。

- Let *hscore* be a binary variable taking value 1 if the student receives a hight test score (*H*), 0 otherwise.  
&emsp;如果学生获得高分（*H*），则将*hscore*设为二进制变量，取值为1，否则为0。

- Denote \\( wage _i(1), wage _i(0) \\) the potential outputs for \\( col _i = 1 \text{ and } col _i = 0 \\), respectively.  
&emsp;分别表示\ \\(wage _i（1），wage _i（0）\\)为\\(col _i=1 \text{和} col _i=0\\)的潜在输出。

- **Conditional Independence Assumption (CIA)**  
&emsp;**条件独立假设（CIA）**

$$
  [wage _i(1), wage _i(0)] \models col _i | hscore _i
$$

- Among the students with a hight test score, 3/4 are Amies and 1/4 are Bens.  
&emsp;在考试成绩高的学生中，有3/4的学生成绩差，1/4的学生成绩差。

- Thus, the ACE for students with score *H* is  
&emsp;因此，得分为*H*的学生的得分为

$$
  (3/4) \times (20 - 10) + (1/4) \times (12 - 8) = $8.5.
$$

- Among the students with a low test score, 1/4 are Amies and 3/4 are Bens.  
&emsp;在考试成绩低的学生中，1/4的学生是“阿美”，3/4的学生是“本”。

- Thus, the ACE for students with score L is  
&emsp;因此，得分为L的学生的得分是

$$
  (3/4) \times (20 - 10) + (3/4) \times (12 - 8) = $5.5.
$$

  - Would we be able to learn the ACE from a regression analysis?  
  &emsp;我们能从回归分析中学习ACE吗？

![]({{site.url}}/assets/images/2020/ECON5002/jointDistribution.png "Figure 9.2: Joint Distributions")

From the table above we compute  
&emsp;从上表我们可以计算

$$
  E[wage | col, hscore]
  = 8.50 + 1.00 hscore + 5.50 col + 3.00 (hscore \times col)
$$

The ACE for students with low test scores is indeed  
&emsp;考试分数低的学生的平均因果效应确实如此

$$
  E[wage(1) | hscore = 0] - E[wage(0) | hscore = 0] = $5.50
$$

Next we consider  
&emsp;接下来我们考虑

$$
  E[wage(1) | hscore = 1] - E[wage(0) | hscore = 1] = $8.50
$$

Since half of the students achieve a high score test, and half a low score test  
&emsp;因为一半的学生达到了高分测试，而一半的学生达到了低分测试

$$
  (5.50 + 8.50) \times 1/2 = $7,
$$

that is average causal effect in the population.  
&emsp;这是人口中的平均因果效应。

Similarly, we could consider the regression model  
&emsp;同样，我们可以考虑回归模型

$$
  wage(col, hscore, u) = 8.50 + 1.00 hscore + 5.50 col + 3.00 ( hscore \times col) + u
$$

If *u* and *hscore* remain fixed when *col* changes, then the causal effect of *col* on *wage* can be computed as  
&emsp;如果*col*改变时*u*和*hscore*保持不变，*col*对*wage*的因果关系可以计算为

$$
  wage(1, hscore, u) - wage(0, hscore, u) 
  = \begin{cases}
    $8.50 & \text{if  } hscore = 1,
    \\\\ $5.50 & \text{if } hscore = 0.
  \end{cases}
$$

Let  
&emsp;让

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2
    = \ell ( x _1, x _2, u)
$$

The causal effect of x1 on y is sometimes defined as  
&emsp;x1对y的因果关系有时被定义为

$$
  \nabla \ell ( x _1, x _2, u),
$$

the change in *y* due a change in \\(x _1\\), holding \\(x _2\\) and *u* constant, where  
&emsp;由于 \\(x _1\\)、保持\\(x _2\\)和*u*常数的变化而引起的*y*的变化，其中

$$
  \nabla \ell ( x _1, x _2, u) =
  \begin{cases}
    \ell ( 1, x _2, u) - \ell ( 0, x _2, u) & \text{x binary}
    \\\\ \ell ( x _1 +1, x _2, u) - \ell ( x _1, x _2, u) & \text{x discrete}
    \\\\ \frac{\partial{\ell ( x _1, x _2, u) }}{\partial{x _1}} & \text{x continous}
  \end{cases}
$$

### Takeaway  
&emsp;课外

- If the CIA holds, we can use the regression to estimate causal effects.  
&emsp;如果条件独立的假设成立，可以使用回归来估计因果关系。

- Conditioning on the aptitude test score, education can be treated as randomly assigned.  
&emsp;根据能力倾向测试分数，教育可以被视为随机分配。

## Video 10: Multiple Regression Analysis: Further Issues  
&emsp;视频10：多元回归分析：进一步的问题

### Models with Quadratics  
&emsp;二次模型

- Assume we have estimated the model  
&emsp;假设我们已经估计了模型

$$
  \begin{array}{m}
    \widehat{lwage} = \underbrace{-.192} _{(.291)} + \underbrace{.136} _{(.011)} educ + \underbrace{.123} _{(.037)} exper - \underbrace{.0038} _{(.0017)} exper ^2
    \\\\n = 759 \text{, } R ^2 = .196
  \end{array}
$$

- The estimated return to education is 13.6%. The model assumes this is the same for all years of experience and education.  
&emsp;教育回报率估计为13.6%。该模型假设这对于所有年的经验和教育都是相同的。

- On average, an additional year of education increases the wage by 13.6%, regardless present level of education.  
&emsp;不管目前的教育水平如何，平均来说，多受一年教育会使工资增加13.6%。

- By contrast, each year of experience is worth less than the preceding year.  
&emsp;相比之下，每一年的经验都不如前一年。

- Taking the partial derivative with respect to exper, we find  
&emsp;对于exper的偏导数，我们发现

$$
  \frac{\Delta \widehat{lwage}}{\Delta exper}
  \approx .123 - 2(.0038) exper 
  = .123 - .0076 exper 
  \tag{10.1}
$$

- We can think of 12:3% as approximately the return to the first year of experience { essentially starting off in the workforce.  
&emsp;我们可以把12:3%看作是对第一年工作经验的大致回报{基本上是从劳动力开始的。

- The return in going from 10 to 11 is about  
&emsp;从10点到11点的回报大约是

$$
  .123 - .0076(10) = .0.47
$$

or 4.7%  
&emsp;或者4.7%

- We could be more precise. Holding educ fixed  
&emsp;我们可以更加精确一些，保证educ不变

$$
  \begin{array}{l}
    \quad lwage(exp =1) -lwage(exp =10) \tag{10.2}
    \\\\ = [.123(11) - .0038(11) ^2] - [.123(10) - .0038(10)^2] = .043
  \end{array}
$$

or 4.3%, which is reasonably close.  
&emsp;或者4.3%， 相当接近。

- The quadratic function  
&emsp;二次函数

$$
  .123 exper - 0.0038 exper ^2 \tag{10.3}
$$

turns at about  
&emsp;大约转化为

$$
  exper ^* = .123/[2 \cdot (.0038)] \approx 16.2 \tag{10.4}
$$

- But fewer than 2% of the observations have exper > 16, so not much worry.  
&emsp;但只有不到2%的观察结果显示exper>16，所以不用太担心。

![]({{site.url}}/assets/images/2020/ECON5002/quadraticRelationship.png "Figure 10.1: Quadratic relationship between lwage and experience.")

### Models with Interaction Terms  
&emsp;具有交互项的模型

- Suppose we have two explanatory variables and start with the usual model:  
&emsp;假设我们有两个解释变量，从通常的模型开始：

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + u
$$

- The partial effect (PE) of \\(x _1\\) on y is \\(\beta _1\\) and the PE of \\(x _2\\) on y is \\(\beta _2\\).  
&emsp;\\(x _1\\)对y的部分效应（PE）为\\(\beta _1\\)，而\\(x _2\\)对y的部分效应（PE）为\\(\beta _2\\)。

- Sometimes it is natural to think the partial effect of one variable, say education, could depend on the level of another variable, say intelligence.  
&emsp;有时，人们很自然地认为，一个变量（比如教育）的部分影响可能取决于另一个变量（比如智力）的水平。

- We add an **interaction term**, \\(x _1 x _2\\), to the usual model:  
&emsp;我们在通常的模型中添加了一个**交互项**，\\(x _1 x _2\\)：

$$
  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \beta _3 x _1 x _2 + u
$$

- Holding \\(x _2\\)  (and *u*) fixed, the partial effect of \\(x _1\\)  on *y* is now  
&emsp;保持\\(x _2\\) （和*u*）固定，\\(x _1\\)对*y*的部分影响现在是

$$
  \frac{\Delta y}{\Delta x _1}
  \approx \beta _1 + \beta _3 x _2
$$

so that effect of \\(x _1\\) depends on \\(x _2\\) unless \\(\beta _3 = 0\\)  
&emsp;所以\\(x _1\\)的效应取决于\\(x _2\\)，除非\\(\beta _3=0\\)

- Similarly,  
&emsp;同样地，

$$
  \frac{\Delta y}{\Delta x _2}
  = \beta _2 + \beta _3 x _1
$$

**Example**  
&emsp;**示例**

- Do education and IQ have an interactive effect in the ln(*wage*) equation?  
&emsp;教育和智商在ln（*wage*）等式中有交互作用吗？

$$
  \widehat{lwage} = -.762 + .195 educ + .022 IQ - . 001(educ \cdot IQ) \tag{10.6}
$$

- According to these estimates, schooling is worth more for those with lower intelligence.  
&emsp;根据这些估计，对那些智力较低的人来说，上学更有价值。

$$
  \frac{\Delta \widehat{lwage}}{\Delta educ}
  \approx .195 - .001 IQ
$$

- The interpretation of the parameters on the original variables can be tricky.  
&emsp;原始变量的参数解释可能很棘手。

- \\(\beta _1\\) would be interpreted as the effect of an additional year of education for those with *IQ* = 0.  
&emsp;\\(\beta _ 1\\)将被解释为对那些智商为0的人额外接受一年教育的影响。

- This effect is not of much practical interest!  
&emsp;这种效果没有多大实际意义！

### Goodness-of-Fit  
&emsp;拟合优度

- Using the same set of data and the same dependent variable, the \\(R ^2\\) can never fall when another independent variable is added to the regression.  
&emsp;使用相同的数据集和相同的因变量，当另一个自变量加入回归时，\\(R^2\\)永远不会下降。

- This means that, if we focus on \\(R ^2\\), we might include silly variables among the \\(x _j\\) .  
&emsp;这意味着，如果我们关注\\(R^2 \\)，我们可能会在\\(x _j \\)中包含愚蠢的变量。

- Adding another *x* cannot make *SSR* increase. The *SSR* falls unless the coecient on the new variable is identically zero.  
&emsp;再加一个*x*不能使*SSR*增加。除非新变量的系数相同为零，*SSR*下降。

- Adding regressors, decreases the number of degrees of freedom.  
&emsp;添加回归，减少自由度的数量。

### Adjusted R-Squared  
&emsp;调整R平方

- Sometimes we want to compare models for the same dependent variable.  
&emsp;有时我们要比较同一因变量的模型。

- Comparing non-nested models using the \\(R ^2\\) can be unfair if the number of regressors is different.  
&emsp;如果回归数不同，使用\\(R^2\\)比较非嵌套模型可能不公平。

- The adjusted \\(R ^2\\) can be helpful in these cases.  
&emsp;在这些情况下，调整后的\\(R^2\\)可能会有所帮助。

- As usual, start with  
&emsp;像往常一样，从

$$
  y = \beta _0 + \beta _1 x _1 + \cdots +\beta _k x _k + u \tag{10.7}
$$

- The formula for the \\(R ^2\\) can be written as  
&emsp;\\(R ^2\\)的公式可以被写作

$$
  R ^2 = 1- \frac{SSR}{SST} = 1 - \frac{SSR/n}{SST/n} \tag{10.8}
$$

- We think of \\(R ^2\\) as using *SSR/n* to estimate *Var(u)* and *SST/n* to estimate *Var(y)*.  
&emsp;我们认为\\(R^2\\)是使用*SSR/n*来估计*Var（u）*，*SST/n*来估计*Var（y）*。

- These estimators are consistent, i.e.  
&emsp;这些估计是一致的，即。

$$
  \frac{SSR}{n} \xrightarrow p Var(u), 
  \ \frac{SST}{n} \xrightarrow p Var(y),
$$

but biased.  
&emsp;但有偏见。

- Instead, use  
&emsp;相反，使用

$$
  \frac{SSR}{n-k-1} \text{  and  } \frac{SST}{n-1}
$$

as the unbiased estimators.  
&emsp;作为无偏估计量。

The **adjusted R-squared** is defined as  
&emsp;**调整后的R平方**定义为

$$
  \begin{align}
    \overline{R} ^2 
    & = 1 - \frac{[SSR / (n-k-1)]}{[SST / (n-1)]} \tag{10.9} 
    \\\\ & = 1 - \frac{\hat{\sigma} ^2}{\hat{\sigma} _y^2} \tag{10.10}
  \end{align}
$$

where \\( \hat{\sigma} ^2\\) is the usual variance parameter estimator of \\( Var(u _i) \\).  
&emsp;其中\\(\hat{\sigma}^2\\)是\\(Var（u _i）\\)的常用方差参数估计量。

- When more regressors are added, *SSR* falls, but so does \\( df = n - k -1. \ \overline{R} ^2\\) can increase or decrease.  
&emsp;当加入更多的回归变量时，*SSR*下降，但\\(df=n-k-1）也下降。\\overline{R}^2\\)可以增加或减少。


- For \\( k > 1, \overline{R} ^2 < R ^2 \\) (unless *SSR* = 0).  
&emsp;对于\\(k>1，{R}^2<R^2\\)（除非*SSR*=0）。


- It is possible that \\( \overline{R} ^2 < 0 \\), especially if \\(df\\) is small.  
&emsp;有可能是\\(\overline{R}^2<0\\)，特别是如果\\(df\\)很小。


- \\( R ^2 > 0 \\) always.  
&emsp;上式始终成立。

### Takeaway  
&emsp;课外

- Quadratic and interaction terms make the regression function more fexible but the interpretation of the parameters can be tricky.  
&emsp;二次项和交互项使回归函数更灵活，但参数的解释可能很棘手。

- The adjusted R-squared penalizes for adding regressors with little explanatory power.  
&emsp;调整后的R-平方惩罚增加回归几乎没有解释力。

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

