---
layout: post
title: Investment, Finance and Asset Prices Unit 2 Lagrange Optimization
subtitle: 投资，金融与资产定价之（二）拉格朗日优化 - 调整成本与托宾Q值
category: money
tags: [ECON5068]
---

# Unit 2 Lagrange Optimization - Adjustment Cost and Tobin's Q

translated by damien from sildes of Sisi Ramanan

## 1. Optimization by lagrange Multiplier

### 1.1. Lagrange Multiplier

A useful formulation for constrained optimization is the concept of Lagrangean function.
With the use of lagrangean multipliers, the Lagrangean incorporates all constraints in the objective function.
Any constrained optimization becomes unconstrained.
The multipliers also have an intuitive economic interpretation.
A general constrained maximization problem can be written as:  
&emsp;&emsp;拉格朗日函数的概念是约束的优化的一个有用的公式。
利用拉格朗日乘子，拉格朗日函数将所有约束条件纳入目标函数。
任何有约束的优化都会变成无约束的。
这个乘子也有一个直观的经济学解释。
一般的约束最大化问题可以写成：  
\\[ max f(x) \\]
subject to some constraints:  
&emsp;&emsp;受某些限制：  
\\[ g_i(x) = c_i \, \text{ for } i = 1,...m \\]

Here the function to be maximized \\(f(x) \\), called the objective function, is defined on a vector of decision variables:  
&emsp;&emsp;在这里，将要最大化的函数成为目标函数，定义在一个决策变量的向量上：
\\[ x = (x1, x2,...x_n)' \\]

Note: We could also have inequality constraints and m is usually less than n but not necessarily.  
&emsp;&emsp;注：我们也可以有不等式约束，m通常小于n，但不一定。

The Lagrangean function of this constrained maximization problem is written as:  
&emsp;&emsp;这个约束最大化问题的拉格朗日函数写为：

\\[ 
    \mathscr{L}(x, \lambda) = f(x)-\lambda_i(g_i(x) -c_i)
\\]
&emsp;\\( \lambda_i\\)'s are called Lagrange multiplier.  
&emsp;&emsp;\\( \lambda_i\\)'s被叫做拉格朗日乘子。

The necessary condition for maximum is then given by the first order conditions:  
&emsp;&emsp;最大值的必要条件由一阶条件（FOC）给出：

\\[
    \frac{\partial \mathscr{L}(x, \lambda)}{\partial x_i} = 0 \ , \text{for} \ i = 1, ...n 
\\]

&emsp;and  
&emsp;&emsp;和

\\[
    \frac{\partial \mathscr{L}(x, \lambda)}{\partial x_i} = 0 \ , \text{for} \ i = 1, ...m 
\\]

If the objective function is concave and the constraints are convex and differentiable, then the necessary conditions are also suffcient for a maximum.
All the models that we deal with in this course satisfy this criterion.  
&emsp;&emsp;如果目标函数是凹的，且约束是凸的和可微的，那么最大值的必要条件也是充分的。我们在本课程中处理的所有模型都满足这个标准。

The Lagrange multiplier can be interpreted as the rate of change in the maximal value of the objective function as the constraint is relaxed.  
&emsp;&emsp;拉格朗日乘子可以解释为目标函数的最大值随着约束的放松而变化的速率。

## 2. Adjustment Cost Model

This model assumes there are costs of quickly adjusting the capital stock. 
Adjustment costs can arise when new capital goods are installed, training workforce, learning by doing, shutting down plants.
We will focus on convex adjustment costs.
The model introduces a very useful concept, the Tobin's Q.  
&emsp;&emsp;该模型假设存在快速调整资本存量的成本。当新的资产财货被安置，培训劳动力，边干边学，关闭工厂时，就产生调整成本。我们将关注为凸函数的调整成本。这个模型引入了一个非常有用的概念，托宾Q。

Adjustment Costs can be internal or external.  
调整成本可以是内部的或者外部的。

**Internal** adjustment costs arise when firms face direct costs of changing their capital stocks.
Example: Installing new capital, training workforce to operate new machines etc.  
&emsp;&emsp;**内部**调整成本会在企业面临改变资本的直接成本时产生。例子：安置新资产，培训员工操作新机器等等。

**External** adjustment costs arise when the price of capital goods fluctuates depending on how much and how fast new capital is installed. Example: Any production that relies on external intermediaries to supply capital goods.  
&emsp;&emsp;**外部**调整成本在资本财货价格波动时产生，这取决于新资本的安装量和安装速度。例子：任何依赖外部中介机构提供资本资本货物的的生产。

We will focus on internal adjustment costs.  
&emsp;&emsp;我们将要关注内部调整成本。

The firm lives forever, time period is infinite.  
&emsp;&emsp;企业永存，时间无限。
The firm is assumed to maximize its value subject to an increasing and convex cost of adjusting capital.
The value of the firm is the expected present discounted sum of dividends (or equivalently net profits).
A constant interest rate is used for discounting time.  
&emsp;&emsp;假设企业在资本调整成本为凸函数且不断增加的情况下实现其价值最大化。公司的价值是股息（或相当于净利润）的预期现值折现总和。固定利率用于贴现时间。

The value of the firm at time t, Vt , is given by:  
&emsp;&emsp;公司在时间t时的价值，Vt，由以下公式得出：
\\[ 
    V_t = E_t \\left \lbrace
        \sum^\infty_{i=0} \\left (
            {1 \over 1+r} 
            \\right)^i D_{t+i} 
        \\right \rbrace   
    \tag{1} \label{firmValue}
\\]

We use the expectations operator \\(E[.]\\) since future dividends
are essentially unknown (random variables).  
&emsp;&emsp;我们使用期望算子\\(E[.]\\) ，因为未来股息基本上是未知的（随机变量）。

The problem of the firm is to maximize this value, given that current investments become productive with one period delay, the capital accumulation equation is given by:  
&emsp;&emsp;公司的问题是使该价值最大化，鉴于当前投资在一个时期的延迟后才具有生产性，资本积累方程由以下公式得出：

\\[ 
    K_{t+1} = (1-\delta)K_t+I_t 
    \tag{2} \label{capitalAccumulation}
\\]

Every unit of investments incurs quadratic adjustment cost \\( AC_t \\) of the form:  
&emsp;&emsp;每一个投资单位都会产生如下形式的二次调整成本：

\\[ 
    AC_t = \frac{\phi}{2} I^2_t
        \tag{3} \label{adjustmentCost}
\\]

&emsp;Note: When \\( \phi = 0 \\), we have no adjustment costs.  
注意：当\\(\phi = 0 \\)时，我们没有调整成本。


Dividends can be defined as profits net of investment expenditures and adjustment costs:  
股息可定义为扣除投资支出和调整成本后的利润：

\\[
    D_t = \pi (\theta_t, K_t) - I_t - AC_t
    \tag{4} \label{dividends}    
\\]

Here we have assumed that the price of capital is one.

Profits, \\( \pi (\theta_t, K_t) \\), is a function of capital at time \\( t \\)  and also productivity, \\(\theta_t\\) .
The variable \\(\theta_t\\)  measures the technological innovation in a firm.
More innovative firms can produce more output at the same
level of inputs.
The time variation in this variable is usually modelled as a
stochastic process (a sequence of random variables indexed
with time).

So we can finally write the complete firm's problem as follows:  

\\[
    max E_0 \sum^{\infty}_{t=0} \beta^t \left [ 
        \pi (\theta_t, K_t) - I_t - \frac{\phi}{2} I^2_t   
    \right]
\\]

&emsp;subject to the capital accumulation constraint in equation \eqref{capitalAccumulation} each period. Here \\( \beta = {1 \over 1+r}\\) is the **discount factor** and \\( {1 \over \beta} = 1+r \\) is the **discount rate**.  
**Note**: This constraint should hold for every period \\( t = 0, 1, 2,...\infty \\).

The Lagrangean can be written as:

$$
    \mathscr{L} = E_0 \sum^{\infty}_{t=0} \beta^t \left [    
        \pi(\theta_t, K)_t - I_t - \frac{\phi}{2} I^2_t - q_t(
            K_t - (1-\theta)K_t -I_t)
        \right ]
    \tag{5} \label{lagrange}
$$

&emsp; where \\(q_t \\) is the lagrange multiplier.  

The First Order Conditions (FOC) for the Lagrangean are given by:

\\[ 
    \frac{\partial \mathscr{L}}{\partial I_t} = 0 
    \implies 
    q_t = 1 + \phi I_t 
    \tag{6} \label{lagrangeFOC1} 
\\]

\\[
    \frac{\partial \mathscr{L}}{\partial K_{t+1}} = 0 
    \implies
    q_t = E_t \beta [ 
        \pi_K (\theta_{t+1} + K_{t+1} ) + 
        q_{t+1} (1-\delta) 
    ]
    \tag{7} \label{lagrangeFOC2}
\\]

&emsp;and

\\[
    \frac{\partial \mathscr{L}}{\partial q_t} = 0 
    \implies
    K_{t+1} = (1-\delta) K_t + I_t
    \tag{8} \label{lagrangeFOC3}   
\\]

Combining the first two FOC's, we have the condition for investment decision:

$$
    { \underbrace{ 1 + \phi I_t}_{ \text{Marginal Cost} } } 
    = 
    { \underbrace{E_t \beta [ 
        \pi_K (\theta_{t+1} + K_{t+1} ) + 
        q_{t+1} (1-\delta) 
    ]}_{\text{Expected discounted Marginal Benefit}} 
    }
    \tag{9} \label{combination}
$$

The left hand side is marginal cost of an additional unit of capital, the price of capital (1) plus the marginal adjustment cost ( \\( \phi I_t \\) ).
The right hand side is expected discounted value of marginal profitability and value of non-depreciated capital. 

The multiplier gives us the shadow value of capital.
The shadow value describes how much the value of the firm will rise if we were to have an additional unit of capital. Equivalently, the marginal profit net of adjustment cost that we can generate from an additional unit of capital.
The advantage of this model is that we have also defined the value of capital or the value of firm. 

## 3. Tobin's Q
&emsp; 托宾Q


Since the price of a new capital good is equal to one, the optimal investment rule says to keep investing in capital until the marginal value of this action given by \\(q_t \\)  equals its cost.

\\(q_t \\) is called **Marginal Q** or **Tobin's Q**, named after the economist James Tobin.

From the first order condition in eq. \eqref{lagrangeFOC1}, we have:

\\[ 
    q_t = 1 + \phi I_t 
\\]

&emsp;in terms of investments,
\\[ 
    I_t = {1 \over \phi} (q_t - 1) 
    \tag{10} \label{investment}
\\]

This says that net investments will be positive if and only if \\(q_t > 1 \\). The parameter \\(\phi \\) governs how sensitive investment is to \\(q_t \\). This equation also says that a firms' investment should only be a function of qt and parameters.

The investment rule clearly shows that investment depends on future expected profitability. Since capital is durable and capital boosts production and profits this makes sense.
\\(q_t \\)  or marginal Q is what we call in statistics a **suffcient statistic** for investment.
That is, knowing Q is sucient to understand all relevant information related to the investment decision, see eq. \eqref{investment}.

![tobin q and investment rate](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/usualMeasureofq.png "tobin q and investment rate")

The assumption of convex adjustment costs implies that the investment will be smooth as firms cannot tolerate very large changes in their capital stock.
This model thus, predicts that firms should **continuously** adjust their capital stock in response to changing conditions.
In other words, investment should always be small and continuous.
Unfortunately, this is not true in empirical data where investment is highly discontinuous and lumpy.
This is the main limitation of the convex adjustment cost model.

The value of the firm derived here is also a measure of its stock market value.
The model then implies that rises in future expected profitability will raise its firm value (stock market value).
It also predicts that investment is a positive function of future expected profits.
Combining these two statements, we get the prediction that investment and the stock market will move together.
Higher stock market valuation \\( \implies\\) higher investment. 

A historical example where this prediction is confirmed was during the technology boom of the 1990s in NASDAQ stock exchange.
Both stock prices (firm value) and corporate investment surged together.
We will have more on this relationship in a later lecture.

Further Reading:

Gregory Chow, Dynamic Economics: Optimization by the Lagrange Method.
Chapter 1: 1.1-1.3 and 1.8.


<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

