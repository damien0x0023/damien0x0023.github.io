---
layout: post
title: Basic Econometrics - Unit 5 Heteroskedasticity 
subtitle: 基础计量经济学（五）异方差性
category: money
tags: [ECON5002]
---

translated by damien from Marco Avarucci

#  Basic Econometrics - Unit 5 Heteroskedasticity  
&emsp;计量经济学基础第5单元异方差性

-   Heteroscedasticity:  
&emsp;异方差：

$$
    Var(u | x _1, x _2, \cdots, x _k) \neq Var(u)
$$

MLR.5 is violated.  
&emsp;违反了MLR.5。

-   **Example (Saving and Income):**  
&emsp;**示例（储蓄和收入）：**

when incomes grow, people have more discretionary income and hence more scope for choice about the disposition about their income.  
&emsp;当收入增长时，人们有更多的可自由支配收入，因此在收入分配上有更多的选择余地。

-   OLS is still unbiased and consistent under MLR.1-MLR.4.  
&emsp;OLS在MLR.1-MLR.4下仍然是无偏的和一致的。

-   MLR.5 was not used to obtain either of these properties.  
&emsp;MLR.5没有用于获得这些属性中的任何一个。

-   OLS can used to estimate the parameters of the linear model.  
&emsp;OLS可以用来估计线性模型的参数。

-   The \\(R ^2\\) (and \\(\overline{R} ^2\\)) remain consistent estimators of the population counterparts (\\(SSR/n \to \sigma _u^2\\) whether or not \\(Var(u) = Var(u || x) \\) )  
&emsp;无论\\(Var(u) = Var(u || x) \\)与否， \\(R ^2\\) (和 \\(\overline{R} ^2\\))保持种群对应物的一致估计(\\(SSR/n \to \sigma _u^2\\)

![]({{site.url}}/assets/images/2020/ECON5002/rSquare.png "R squared")

## <u>Consequences of heteroscedasticity for OLS (inference)</u>  
&emsp;异方差对OLS（推断）的影响

-   Heteroscedasticity invalidates variance formulas for OLS estimators  
&emsp;异方差性使OLS估计的方差公式失效

-   t-tests and confidence intervals cannot be trusted under heteroscedasticity (even in large samples!)  
&emsp;异方差下的t检验和置信区间不可信（即使在大样本中！）

-   Joint hypotheses tests using the usual *𝐹* are no longer valid in presence of heteroscedasticity (for any *𝑛*)  
&emsp;使用通常的*𝐹*的联合假设检验在存在异方差的情况下不再有效（对于任何*𝑛*）

-   Under heteroscedasticity, OLS is no longer the best linear unbiased estimator (BLUE); there may be more efficient linear estimators  
&emsp;在异方差条件下，OLS不再是最佳的线性无偏估计（BLUE），可能存在更有效的线性估计

-   Witout MLR.5, there are still good reasons to use OLS, but we need to modify the usual test statistics to make them valid in the presence of heteroskedasticity.  
&emsp;在没有MLR.5的情况下，仍然有充分的理由使用OLS，但是我们需要修改通常的检验统计量，使它们在异方差的存在下有效。

-   We are not talking about a new estimation method. It is still OLS estimation to obtain the β \\(\hat{\beta} _j \\), but we need to use **heteroskedasticity-robust inference** after OLS estimation.  
&emsp;我们不是在讨论一种新的估算方法。得到β\\（\hat{\beta}\uj\\）仍然是OLS估计，但是在OLS估计之后需要使用**异方差鲁棒推理**。

-   Fortunately, standard errors and all test statistics can be modified to be valid in the presence of **heteroskedasticity of unknown form**.  
&emsp;幸运的是，标准误差和所有检验统计量可以修改为在存在未知形式的**异方差**时有效。

-   This includes the possibility of homoskedasticity. So we can compute CIs and conduct statistical inference without worrying about whether MLR.5 holds.  
&emsp;这包括同骨骼的可能性。因此，我们可以计算CI并进行统计推断，而不必担心MLR.5是否成立。

-   Most regression packages include an option with OLS estimation that computes **heteroskedasticity-robust standard errors**, which then produces **h.r.** ***t*** **statistics** and **h.r. C.I.s**.  
&emsp;大多数回归包都包含一个OLS估计选项，该选项计算**异方差稳健标准误差**，然后生成**h.r.** ***t*** **统计量**和**h.r.C.I.s**。

-   The heteroskedasticity-robust test statistics and CIs only have asymptotic justification, even if the full set of CLM assumptions hold.  
&emsp;即使全套CLM假设成立，异方差稳健性检验统计量和CI也只有渐近正当性。

-   With smaller sample sizes, the heteroskedasticity-robust statistics might be more biased than the usual statistics.  
&emsp;在小样本情况下，异方差稳健统计量可能比通常的统计量更有偏差。

-   Example:  
&emsp;示例：


**Hourly wage equation**  
&emsp;**小时工资公式**

![]({{site.url}}/assets/images/2020/ECON5002/hourWage.png "hourly wage equation")

## <u>Testing for heteroscedasticity</u>  
&emsp;异方差检验

We start with the linear model  
&emsp;我们从线性模型开始

$$
    y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \cdots + \beta _k x _k + u
$$

and assume that MLR.1-MLR4 hold true.  
&emsp;并且预设MLR.1-MLR.4为正。

-   **Breusch-Pagan test for heteroscedasticity**  
&emsp;**异方差的Breusch-Pagan检验**

![]({{site.url}}/assets/images/2020/ECON5002/breuschPagan1.png "Breusch-Pagan Test I")

![]({{site.url}}/assets/images/2020/ECON5002/breuschPagan2.png "Breusch-Pagan Test II")

**Steps in Computing the Breusch-Pagan Test**  
&emsp;**计算Breusch-Pagan测试的步骤**

1.  Estimate the equation \\(  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \cdots + \beta _k x _k + u \\) by OLS, saving the OLS residuals, \\(\hat{u} _i \\). Compute the squared residuals, \\(\hat{u} _i^2 \\). (There is a squared residual for each of the *n* observations.)  
&emsp;通过OLS估计方程\\(  y = \beta _0 + \beta _1 x _1 + \beta _2 x _2 + \cdots + \beta _k x _k + u \\) ，保存OLS残差\\(\hat{u} _i \\)。计算平方残差，\\(\hat{u} _i^2 \\)。（每个*n*观测值都有一个平方残差。）

2.  Regress \\(\hat{u} _i^2 \\) on all explanatory variables and compute the usual *F* test of joint significance of the explanatory variables.  
&emsp;对所有解释变量进行回归\\(\hat{u} _i^2 \\)，并计算解释变量联合显著性的常用*F*检验。

3.  If the *p-value* of the test in step 2 is sufficiently small, reject the null of homoskedasticity and conclude Assumption MLR.5 fails.  
&emsp;如果步骤2中测试的*p-value*足够小，则拒绝同构性的空值，并得出假设MLR.5失败的结论。

-   Example:  
&emsp;示例：

**Heteroscedasticity in housing price equations**  
&emsp;**住房价格方程的异方差性**

![]({{site.url}}/assets/images/2020/ECON5002/heteroscedasticityHousingPrice.jpg "Heteroskedasticity in housing price equations")

### <u>White test for heteroscedasticity</u>  
&emsp;异方差White检验

![]({{site.url}}/assets/images/2020/ECON5002/whiteTest.png "White test")

- **Disadvantage of this form of the White test**  
&emsp;**这种形式的White测试的缺点**

  - Including all squares and interactions leads to a large number of esti-mated parameters (e.g. k=6 leads to 27 parameters to be estimated)  
  &emsp;包括所有的平方和相互作用导致大量的估计参数（例如k=6导致27个待估计参数）

- **Alternative form of the White test**  
&emsp;**White试验的替代形式**

![]({{site.url}}/assets/images/2020/ECON5002/alterWhiteTest.png "Alternative White test")

- **Example:**  
&emsp;**示例：**

**Heteroscedasticity in (log) housing price equations**  
&emsp;**（对数）房价方程的异方差性**

$$
  R _{\hat{u} ^2}^2 = .0392, LM = 88(.0392) 
  \approx 3.45, p-value _{LM} = .178
$$

### <u>Weighted least squares estimation</u>  
&emsp;加权最小二乘估计

- Heteroscedasticity is known up to a multiplicative constant  
&emsp;异方差已知到一个乘法常数

![]({{site.url}}/assets/images/2020/ECON5002/multiCons.png "multiplicative constant")

- **Example:**  
&emsp;**示例：**

**Savings and income**  
&emsp;**储蓄和收入**

![]({{site.url}}/assets/images/2020/ECON5002/savIncome.png "Savings and Income")

- **The transformed model is homoscedastic**  
&emsp;**变换后的模型是等腰的**

$$
  E(u _i^{*2} | X _i) = E \left [(\frac{u _i}{\sqrt{h _i}}) ^2 | X _i \right]
  = \frac{E(u _i^2 | X)}{h _i}
  = \frac{\sigma ^2 h _i}{h _i} = \sigma ^2 
$$


**If the other Gauss-Markov assumptions hold as well, <u>OLS applied to the transformed model</u> is the best linear unbiased estimator!**  
&emsp;**如果其他高斯-马尔可夫假设也成立，<u>应用于变换模型的OLS</u>是最佳的线性无偏估计量！**

- **OLS in the transformed model is weighted least squares (WLS)**  
&emsp;**转换模型中的OLS是加权最小二乘法（WLS）**

![]({{site.url}}/assets/images/2020/ECON5002/wls.png "Weighted least squares (WLS)")

- **Why is WLS more efficient than OLS in the original model?**  
&emsp;**为什么WLS比原始模型中的OLS更有效？**

  - Observations with a large variance are less informative than observa-tions with small variance and therefore should get less weight  
  &emsp;方差较大的观测值比方差较小的观测值信息量小，因此应获得较少的权重

- **WLS is a special case of generalized least squares (GLS)**  
&emsp;**WLS是广义最小二乘法（GLS）的特例**

- **Example:**  
&emsp;**示例：**

**Financial wealth equation**  
&emsp;**金融财富方程**

![]({{site.url}}/assets/images/2020/ECON5002/finWeaEqu.png "Financial wealth equation")

- **Important special case of heteroscedasticity**  
&emsp;**异方差的重要特例**

  - If the observations are reported as averages at the city/county/state/-country/firm level, they should be weighted by the size of the unit  
  &emsp;如果将观察值作为市/县/州/国家/公司级别的平均值进行报告，则应根据单位大小对其进行加权

![]({{site.url}}/assets/images/2020/ECON5002/specCase.png "Important special case of heteroscedasticity")

If errors are homoscedastic at the employee level, WLS with weights equal to firm size mi should be used. If the assumption of homoscedasticity at the employee level is not exactly right, one can calculate robust standard errors after WLS (i.e. for the transformed model).  
&emsp;如果误差在员工层面是同方差的，则应使用权重等于公司规模mi的WLS。如果员工层面上的一致性假设不完全正确，则可以在WLS之后计算鲁棒标准误差（即对于转换模型）。

- **Unknown heteroscedasticity function (feasible GLS)**  
&emsp;**未知异方差函数（可行GLS）**

![]({{site.url}}/assets/images/2020/ECON5002/feasiableGLS.png "Unknown heteroscedasticity function")

<u>Feasible GLS is consistent and asymptotically more efficient than OLS.</u>  
&emsp;<u>可行的GLS是一致的，并且渐近地比OLS更有效。</u>

- **Example:**  
&emsp;**示例：**

**Demand for cigarettes**  
&emsp;**对香烟的需求**

- **Estimation by OLS**  
&emsp;**OLS估算**

![]({{site.url}}/assets/images/2020/ECON5002/OLSest.png "Demand Estimation for cigarettes by OLS")

- **Estimation by FGLS**  
&emsp;**FGLS估算**

![]({{site.url}}/assets/images/2020/ECON5002/FGLSest.png "Demand Estimation for cigarettes by FGLS")

- **Discussion**  
&emsp;**讨论**

  - The income elasticity is now statistically significant; other coefficients are also more precisely estimated (without changing qualit. results)  
  &emsp;收入弹性现在在统计上是显著的；其他系数也被更精确地估计（在不改变质量的情况下。结果）

- <u>What if the assumed heteroscedasticity function is wrong?</u>  
&emsp;如果假设的异方差函数是错误的呢？

  - WLS is still consistent under MLR.1 – MLR.4  
  &emsp;WLS在MLR.1–MLR.4下仍然保持一致

  - Robust standard errors should be computed.  
  &emsp;应计算稳健的标准误差。

  - How can we adjust the standard error to heteroskedasticity of unknown form?  
  &emsp;如何将标准差调整为未知形式的异方差？

- Consider the bivariate model  
&emsp;考虑二元模型

$$
  y _i = \beta _0 + \beta _1 x _i + u _i, \quad \hat{\beta} _1 
    = \frac{\sum _{i=1}^n (y _i - \overline{y})(x _i - \overline{x})}  {\sum _{i=1}^n (x _i - \overline{x})^2}
$$

- We proved that  
&emsp;我们证明

$$
  \hat{\beta} _1 = \beta _1 + \frac{\sum _{i=1}^n (x _i - \overline{x}) u _i}{\sum _{i=1}^n (x _i - \overline{x})^2}
$$

and, conditional to *X*  
&emsp;还有，条件是*X*

$$
  Var(\hat{\beta} _1) = \frac {\sum _{i=1}^n (x _i - \overline{x})^2 E(u _i^2)} {\left [\sum _{i=1}^n (x _i - \overline{x})^2 \right]^2} 
$$

**White's Heteroscedasticity-robust standard variance**  

&emsp;**White异方差稳健标准方差**

$$
  \widehat{Var(\hat{\beta} _1) } _{HC} = \frac {\sum _{i=1}^n (x _i - \overline{x})^2 \hat{u} _i^2} {\left [\sum _{i=1}^n (x _i - \overline{x})^2 \right]^2} 
$$

  - HC stands for “Heteroscedasticity Consistent”.  
  &emsp;HC代表“异方差一致性”。

  - It is a valid estimator in the presence of heteroscedasticity of any form (including homoscedasticity).  
  &emsp;当存在任何形式的异方差（包括同方差）时，它是一个有效的估计量。
  
<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>