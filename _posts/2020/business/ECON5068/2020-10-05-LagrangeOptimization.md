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

\\[ 
    \mathscr{L}(x, \lambda) = f(x)-\lambda_i(g_i(x) -c_i)
    \tag{} \label{}
\\]
&emsp;&emsp;\\( \lambda_i\\)'s are called Lagrange multiplier.  

The necessary condition for maximum is then given by the first order conditions:  

\\[
    \frac{\partial \mathscr{L}(x, \lambda)}{\partial x_i} = 0 \ , \text{for} \ i = 1, ...n 
\\]

&emsp;&emsp;and  

\\[
    \frac{\partial \mathscr{L}(x, \lambda)}{\partial x_i} = 0 \ , \text{for} \ i = 1, ...m 
\\]

If the objective function is concave and the constraints are convex and dierentiable, then the necessary conditions are also suffcient for a maximum.

All the models that we deal with in this course satisfy this criterion.

The Lagrange multiplier can be interpreted as the rate of change in the maximal value of the objective function as the constraint is relaxed.

## 2. Adjustment Cost Model

This model assumes there are costs of quickly adjusting the capital stock. 
Adjustment costs can arise when new capital goods are installed, training workforce, learning by doing, shutting down plants.
We will focus on convex adjustment costs.
The model introduces a very useful concept, the Tobin's Q.

Adjustment Costs can be internal or external.

**Internal** adjustment costs arise when firms face direct costs of changing their capital stocks.Example: Installing new capital, training workforce to operate new machines etc.

**External** adjustment costs arise when the price of capital goods 
fluctuates depending on how much and how fast new capital is installed. Example: Any production that relies on external intermediaries to supply capital goods.

We will focus on internal adjustment costs.

The firm lives forever, time period is infinite.

The firm is assumed to maximize its value subject to an increasing and convex cost of adjusting capital.
The value of the firm is the expected present discounted sum of dividends (or equivalently net profits).
A constant interest rate is used for discounting time.

The value of the firm at time t, Vt , is given by:
\\[ 
    V_t = E_t \\left \\{ 
        \sum^\infty_{i=0} \\left (
            {1 \over 1+r} 
            \\right)^i D_{t+i} 
        \\right \\}    
    \tag{1} \label{firmValue}
\\]

We use the expectations operator \\(E[.]\\) since future dividends
are essentially unknown (random variables).

## 3. Tobin's Q



<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

