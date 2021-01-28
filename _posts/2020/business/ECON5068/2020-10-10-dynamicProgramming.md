---
layout: post
title: Investment, Finance and Asset Prices - Unit 3 Dynamic Programming
subtitle: 投资，金融与资产定价之（三）动态规划
category: money
tags: [ECON5068]
---

translated by damien from sildes of Sisi Ramanan

# Unit 3 Dynamic Programming

## 1. Dynamic Programming


In the last lecture, we used Lagrange multipliers to solve the optimization problem of the firm.
Dynamic Programming is an alternate method that can be used to solve optimization problems.
The approach is different yet gives an identical solution.  
&emsp;&emsp;在上节课中，我们使用拉格朗日乘数来解决企业的优化问题。
动态规划是一种可以用来解决优化问题的替代方法。
方法不同，但给出了相同的解决方案。

Dynamic Programming is popular since it is easy to implement numerically in the computer.
We will learn dynamic programming using an example.  
&emsp;&emsp;动态规划因其易于在计算机中用数值实现而广受欢迎。
我们将用一个例子来学习动态编程。

## 2. Example: Cake-Eating


Suppose you have a cake of size \\( W_1 \\). You have T periods to consume this cake.
Every period \\( t=1,2...T \\) you consume some of the cake and save the rest.  
&emsp;&emsp;假设你有一个尺寸为\\( W_1 \\)的蛋糕。
你有T个周期来吃这个蛋糕。
每一个周期 \\( t=1,2...T \\) 你吃一点蛋糕，剩下的就存起来。

The initial size of the cake at \\( t=1 \\) is \\( W_1 \\).
Assume that the cake cannot melt (depreciate) or grow.
Let \\( c_t \\) represent the consumption of cake at time t and \\( u(c_t) \\) the flow of utility (satisfaction) from this consumption.  
&emsp;&emsp;蛋糕在 \\( t=1 \\) 的初始尺寸为 \\( W_1 \\)。
假设蛋糕不能融化（贬值）或生长。
让 \\( c_t \\) 代表时间t对蛋糕的消费，并且\\( u(c_t) \\) 表示消费的效用流（满意度）。

Assume \\( u(.) \\) is real-valued, continuous, differentiable and concave and consumption should always be non-negative.
The life-time utility from consuming the cake is given by the discounted sum of all current and future utility of consumption:  
&emsp;&emsp;假设 \\( u(.) \\) 是实数值的，连续的，可微的和凹的，消费应该总是非负的。
消费蛋糕的终生效用由所有当前和未来消费效用的折现总和得出：

$$
    u(c_1) + \beta u(c_2) +\beta^2 u(c_3) + ... +\beta^{T-1} u(c_T)
$$

That is,  
&emsp;&emsp;那就是，

$$
    \sum^T_{t=1} \beta^{t-1} u(c_t)
$$

&emsp;where \\( 0 \leq \beta \leq 1 \\) is the discount factor.  
&emsp;&emsp;在这里 \\( 0 \leq \beta \leq 1 \\) 是折现系数。

The evolution of cake size every period is given by:  
&emsp;&emsp;每个时期蛋糕大小的演变由以下公式给出：

\\[ W_{t+1} = W_t - c_t  \ ,\  \text{for} \ t=1,2,... T. \\]

**Problem**: How would you find the optimal path of consumption  \\( \left \\{ c^* _t \right \\}^T _{t=1} \\)  ?  
&emsp;&emsp; **问题**：你如何找到最佳的消费路径  \\( \left \\{ c^* _t \right \\}^T _{t=1} \\) ？

In other words, what is the level of consumption every period that maximizes your lifetime utility.  
&emsp;&emsp;换言之，每个时期的消费水平是多少，使你的一生效的用最大化。

### 2.1 Lagrangean Approach

One approach is to use the method of Lagrange multipliers.
This is then a constrained optimization problem where:  
&emsp;&emsp;一种方法是使用拉格朗日乘子的方法。这是一个约束优化问题，其中：

$$
    \max_{c_t,W_{t+1}} \left [ \sum^T_{t=1} \beta^{t-1} u(c_t) \right ]
$$

&emsp; subject to the constraint:  
&emsp;&emsp; 受约束：

$$
    W_{t+1} = W_t - c_t
$$

&emsp; for all \\( t = 1,2, ... T. \\)  
&emsp;&emsp;对所有\\( t = 1,2, ... T. \\)

The Lagrangean function can be written as:  
&emsp;&emsp;拉格朗日函数可以被写作：

$$
    \mathscr{L} = \sum^T_{t=1} \beta^{t-1} \left [    
        u(c_t) - \lambda_t(W_{t+1} - W_t -c_t)    
    \right ]
$$

&emsp;Note: This is a dynamic optimization problem, we have an objective function and a constraint at every period \\( t \\). All future values need to be discounted.  
&emsp;&emsp;注：这是一个动态优化问题，我们在每个周期都有一个目标函数和一个约束。所有未来价值都需要折现。

The necessary condition for maximizing this lagrangean function is given by the three FOC's:  
&emsp;&emsp;最大化拉格朗日函数的必要条件由三个FOC给出：


\\[ 
    \frac{\partial \mathscr{L}}{\partial c_t} = 0 
    \implies 
    u'(c_t) = \lambda_t
    \tag{1} \label{lagrangeFOC1} 
\\]

\\[
    \frac{\partial \mathscr{L}}{\partial W_{t+1}} = 0 
    \implies
    \lambda_t = \beta \lambda_{t+1}
    \tag{2} \label{lagrangeFOC2}
\\]

&emsp;and  
&emsp;&emsp;和

\\[
    \frac{\partial \mathscr{L}}{\partial \lambda_t} = 0 
    \implies
    W_{t+1} = W_t - c_t
    \tag{3} \label{lagrangeFOC3}   
\\]

From eq.'s \eqref{lagrangeFOC1} and \eqref{lagrangeFOC2},  
&emsp;&emsp;从等式\eqref{lagrangeFOC1} 和 \eqref{lagrangeFOC2},

\\[
    u'(c_t) = \beta u'(c_{t+1})
    \tag{4} \\label{eulerEquation}
\\]

This equation is so common that it has a special name in economics - **Euler Equation**.  
&emsp;&emsp;这个方程非常普遍，在经济学中有一个特殊的名字——欧拉方程。

The left hand side represents the marginal loss in utility when you sacrifice 1 unit of consumption and the right hand side is the discounted marginal gain in utility from this extra unit of consumption next period.
For optimal consumption, this Euler equation should be satisfied.  
&emsp;&emsp;左边表示当你牺牲1个单位的消费时效用的边际损失，右边是从下一个时期这个额外的消费单位得到的效用边际收益的折现值。为了达到最佳消费，这个欧拉方程应该被满足。

The second condition is simply the cake size constraint:  
&emsp;&emsp;第二个条件就是蛋糕大小的限制：

$$
    W_{t+1} = W_t -c_t
    \tag{5} \label{cakeSizeConstraint}
$$

These two conditions are not enough for an optimal solution. 
Since this is a finite time horizon problem, we need to have a terminal condition.  
&emsp;&emsp;这两个条件不足以得到最优解。
由于这是一个有限时间范围问题，我们需要有一个最终条件。

For maximum utility, there should not be any cake left over at the end of the last period. That is,  
&emsp;&emsp;为了最大限度地发挥效用，在最后一个时期结束时，不应留下任何蛋糕。也就是说，

\\[
    W_{T+1} = 0
    \tag{6} \label{maximumUtility}
\\]

This terminal condition naturally implies that the sum of consumption across all periods should equal the total size of the cake:  
&emsp;&emsp;这种最终条件自然意味着所有时期的消费总额应等于蛋糕的总尺寸：

$$
    \sum^T_{t=1} c_t = W_1
    \tag{7} \label{totalSize}
$$

Using the value of \\( W_1 \\) and eq.'s \eqref{eulerEquation} and \eqref{totalSize}, we can find the optimal path of consumption \\( \\{ c^* _t \\}^T _{t=1}  \\) that maximizes utility.  
&emsp;&emsp;使用 \\( W_1 \\) 的值和等式 \eqref{eulerEquation} and \eqref{totalSize}，我们可以找到使效用最大化的最佳消费路径  \\( \left \\{ c^* _t \right \\}^T _{t=1} \\) 。

### 2.2 Dynamic Programming Approch

The solution to this T period cake eating problem is found by substituting the optimal path of consumption in the lifetime utility function. We will denote this maximum as \\( V_t(W_1)\\):  
&emsp;&emsp;通过在寿命效用函数中代入最优消费路径，得到了T期吃蛋糕问题的解。我们将此最大值表示为 \\( V_t(W_1)\\)：

$$
    V_t(W_1) = \max \left [ \sum^T_{t=1} \beta^{t-1} u(c_t) \right ] = \sum^T_{t=1} \beta^{t-1} u(c^*_t) 
$$

\\( V(W_1) \\) is called as a **value function** and here it represents the maximum \\( T \\) period utility of consumption given an initial level of wealth \\( W_1 \\).  
&emsp;&emsp; \\( V(W_1) \\) 被称为一个价值函数，这里它代表了给定初始财富水平的消费的最大周期效用。

Suppose we change this cake eating problem by adding a period 0 and giving an initial cake size of \\( W_0 \\). 
We can again solve this by formulating a new lagrangean for the \\( T + 1 \\) period problem.
However, a better way would be to somehow make use of the \\( T \\)  period solution that we found.  
&emsp;&emsp; 假设我们通过添加一个阶段0并给出初始大小为 \\( W_0 \\) 的蛋糕来改变这个吃蛋糕的问题。我们可以通过为周期问题建立一个新的拉格朗日方程来解决这个问题。然而，一个更好的方法是利用我们发现的周期解。

Dynamic Programming (DP) provides means for doing this.
DP essentially converts a general \\( T \\)  period problem into a 2 period one.
DP breaks down the optimal path into two parts, what is optimal today and the optimal continuation path.
Given  \\( W_0 \\), the optimization problem can be written as:  
&emsp;&emsp; 动态规划（DP）提供了实现这一点的方法。DP本质上是将一般周期问题转化为2周期问题。DP将最优路径分为两部分，即当前最优路径和最优连续路径。给定优化问题可以写成：

$$
    \max_{c_0} [ u(c_0) + \beta V_T(W_1)]
$$

&emsp; where  
&emsp;&emsp;在这里
\\[  W_1 = W_0 - c_0 \\]

**So instead of choosing the entire path** of \\( c_t\\) , we are just choosing \\( c_0 \\). 
The rest of the path is optimally determined by the value function, \\( V_T (W_1) \\). 
Once \\( c_0 \\) and hence \\( W_1 \\) is determined, the value function summarizes the rest of the problem.  
&emsp;&emsp; **所以，我们不是选择\\( c_t\\) 的整个路径**，而是选择  \\( c_0 \\) 。路径的其余部分由值函数 \\( V_T (W_1) \\) 优化确定。一旦确定了 \\( c_0 \\) 和 \\( c_t \\)，价值函数将总结问题的其余部分。

This is the **principle of optimality** due to Richard Bellman: we can represent the full dynamic problem as a sequence of **recursive** 2 period problems. 
The first order condition of this value function problem is given by:  
&emsp;&emsp;这是Richard Bellman提出的**最优性原则**：我们可以将整个动态问题表示为一系列**递归的**2周期问题。
这个值函数问题的一阶条件由下式给出：


\\[ 
    u'(c_0) = \beta V'_T (W_1)    
\\]

so that the marginal gain from reducing consumption a little in period 0 is summarized by the derivative of the value function. 
Also,  
&emsp;&emsp;因此，在第0阶段，通过对价值函数的导数，可以总结出减少消费的边际收益。也就是，

\\[ 
    V'_T (W_1) = \beta^t u' (c _{t+1})
\\]

&emsp; for \\( t = 1,2, ... T-1 \\). Using these two conditions together yields  
&emsp;&emsp;对 \\( t = 1,2, ... T-1 \\)。同时使用这两个条件可以得到



\\[
    u' (c_t) = \beta u' (c _{t+1})
\\]

&emsp;which is the same as the Lagrange solution.  
&emsp;&emsp;这是和拉格朗日的解法是一样的。

Suppose that we consider the above problem and allow the horizon to go to infinity. As before, one can consider solving the infinite horizon sequence problem given by:  
&emsp;&emsp;假设我们考虑上述问题，允许视界无限远。如前所述，我们可以考虑解决无限水平序列问题：

$$
    \max_{ \\{c_t \\} ^\infty_1 ,\ \\{ W_{t+1} \\} ^\infty_2 } \left [ \sum^T_{t=1} \beta^{t} u(c_t) \right ]
$$

&emsp; along with the transition equation of  
&emsp;&emsp;伴随着跃迁方程

$$
    W_{t+1} = W_t - c_t
$$

&emsp; for \\( t = 1, 2, ... \infty \\).  
&emsp;&emsp;对 \\( t = 1, 2, ... \infty \\)。

We can write this as a dynamic programming problem as:  
&emsp;&emsp;我们能将它写成一个动态规划问题：

$$
    V(W) = \max_{c, W'} u(c) + \beta V(W')
    \tag{8} \label{DP}
$$

&emsp; for all W where \\( W' = W - c \\) is the transition equation.  
&emsp;&emsp; 对过渡方程\\( W' = W - c \\)中所有的W。

\\( V(W) \\) is the value of the infinite horizon cake eating problem or the maximal utility from this consumption. 
\\( W' = W - c \\) is the state transition equation or equivalently the evolution of cake size.
Variables with prime denote future values, not to be confused with the derivative.  
&emsp;&emsp; \\( V(W) \\) 是无限地平线的吃蛋糕问题的价值或从这个消费的最大效用。\\( W' = W - c \\) 是状态转移方程，或等价于蛋糕尺寸的演化。
带有上标的变量\\( W' \\)表示未来值，不要与导数混淆。

In general, we use primes to denote future values when we are looking for a stationary solution to an infinite horizon problem.
The value function here is stationary, that is:  
&emsp;&emsp; 一般来说，当我们在寻找一个无限地平线问题的均衡解时，我们用上标来表示未来的值。这里的值函数是平稳的，即：

$$
    V_t(W) = V_{t+k} (W) = V(W) \ \ \text{for any } k > 0
$$

Stationarity means **time-invariant**, that is the value function or policy functions are optimal and do not change with time.  
&emsp;&emsp;平稳性是指**时间不变的**，即价值函数或策略函数是最优的且不随时间变化。

Remember these functions denote a path or a rule, so stationarity here means that this path is constant (not the actual variable).
The two policy functions maps the state varables to controls.
In this problem, the two policy functions are:  
&emsp;&emsp;记住，这些函数表示一条路径或一条规则，所以这里的平稳性意味着这个路径是常量（不是实际变量）。这两个策略函数将状态变量映射到控制变量。在这个问题中，两个策略函数是：

$$
    W'(W) \text{ and } c(W)
$$

next period cake size and consumption.  
&emsp;&emsp;下一阶段蛋糕的大小和消费量。

What are the **state** and **control** (choice) variables?  
&emsp;&emsp;什么是**状态**和**控制**（选择） 变量？

The state variable is the size of the cake (W) that is given at the start of any period. The cake size completely summarizes all information from the past that is needed for the forward looking optimization problem.  
&emsp;&emsp;**状态**变量是在任何时期开始时给定的蛋糕（W）的大小。蛋糕大小完全总结了前瞻性优化问题所需的所有过去的信息。

The control variable is the variable that is being chosen. In this case, it is the level of consumption in the current period, \\( c \\) and next period cake size \\( W' \\).  
&emsp;&emsp;**控制**变量是正在选择的变量。在这种情况下，就是本期消费水平，以及下一期蛋糕的大小。

The transition (or the constraint) desribes the dependence of the state tomorrow on the state today and the control today:  
&emsp;&emsp;过渡（或约束）描述了明天的状态对今天的状态和今天的控制的依赖：

$$
    W' = W - c
$$

Alternatively, we can write the DP, in \eqref{DP}, as:  
&emsp;&emsp;或者，我们可以将\eqref{DP}中的DP写成如下所示：

$$
    V(W) = \max_{W'} u(w - W') + \beta V(W')
$$

&emsp; where we have substituted the constraint so that we have to choose only tomorrow\'s cake size.  
&emsp;&emsp;在这里我们已经替换了约束，所以我们只能选择明天的蛋糕大小。

Either specification will yield the same result. This expression is a functional equation and is often called a Bellman equation after Richard Bellman, the originator of dynamic programming.  
&emsp;&emsp;任何一种规格都会产生相同的结果。这个表达式是一个函数方程，通常以动态规划的创始人Richard Bellman的名字称为Bellman方程。

Note that the unknown in the Bellman equation is the value function itself: the idea is to find a function V(W) that satisfies this condition for all W.  
&emsp;&emsp;注意，在Bellman方程中未知的是值函数本身：其思想是找到一个函数V（W），它满足所有W的这个条件。

## 3. Investment

We will apply Dynamic Programming to the adjustment cost model.
The firm's optimization problem is as follows:  
&emsp;&emsp;我们将动态规划应用于调整成本模型。公司的优化问题如下：

$$
    \max_{K_{t+1}} E_0 \sum^{\infty}_{t=0} \beta^t \left [    
            \pi(\theta_t, K)_t 
            - p(K _{t+1} - (1-\delta) K _t)
            - C(K _{t+1}, K _t)
        \right ]
$$

&emsp;where \\( C(.) \\) is the convex adjustment cost function, \\( p \\) is the price of capital (investments) and we have substituted the capital acccumulation constraint for investments \\( I_t \\).  
&emsp;&emsp;其中\\( C(.) \\) 是调整成本的凸函数，\\( p \\)是资本（投资）的价格，我们用资本累积约束代替了投资\\( I_t \\)。

This is the generalized version of the **adjustment cost model** where \\( p \\), \\( \theta \\) is time-varying and the adjustment cost could be any function that is convex and increasing.
The Bellman equation or the DP for this problem can be written as follows:  
&emsp;&emsp;这是**调整成本模型**的广义版本，其中，是时变的，调整成本可以是任何凸的和递增的函数。该问题的贝尔曼方程或DP可以写成：

$$
    V(\theta, K) = \max_{K'} \left [    
            \pi(\theta_t, K)_t 
            - p(K' - (1-\delta) K )
            - C(K', K)
            + \beta E[ V(\theta',K')]
        \right ]
    \tag{9} \label{bellmanEqu}
$$

Policy functions is \\( K'(\theta, K) \\) and \\( I(\theta, K) \\) .
Expectation here is conditional on current state is \\( E[ . ] = E_{\theta', K' \| \theta, K} \\).
The variable \\(\theta \\) is actually a time varying stochastic process, even though we do not state it explicitly.
For example, \\(\theta \\)  could follow an autoregressive process of order one AR(1):  
&emsp;&emsp;策略函数是 \\( K'(\theta, K) \\) 和\\( I(\theta, K) \\)。
这里的期望值是以当前状态 \\( E[ . ] = E_{\theta', K' \| \theta, K} \\)为条件的。
这个变量实际上是一个时变的随机过程，即使我们没有明确地说明它。例如，可以遵循一阶AR（1）的自回归过程：

\\[
    \theta' = \rho  \theta + \epsilon , \text{ where } \epsilon \sim N(0,1)
\\]

Here the next period value, \\(\theta '\\), depends on its previous period
value, \\(\theta \\), and a **random** error normally distributed with mean
zero and variance 1.
This is one way to model the unpredictable (random) evolution of technological productivity/innovation.  
&emsp;&emsp;这里的下一个周期值\\(\theta '\\)，取决于它的前一个周期值 \\(\theta \\)，以及一个正态分布的**随机**误差，其均值为零，方差为1。这是模拟技术生产力/创新不可预测（随机）演变的一种方法。

The firm manager solves the DP in eq. \eqref{bellmanEqu} by choosing the next period level of capital \\( K' \\). The solution is given by the FOC with reference to (w.r.t)  \\( K' \\):  
&emsp;&emsp;企业经理通过选择下一个时期的资本水平来解决等式中的DP。解决方案由FOC参考（w.r.t）给出：

$$
        \frac{\partial V(\theta, K)}{\partial K'}  = 0
$$

$$
       \implies - C_{K'}(K',K) - p + \beta E[V _{K'} (A',K') ] = 0
$$

Thus, the optimal investment decision is based on the following condition:  
&emsp;&emsp;因此，最优投资决策基于以下条件：

$$
    \underbrace{ C_{K'}(K',K)+p} _{\text{Marginal Cost} } 
    = \underbrace { \beta E[V _{K'} (A',K')]} _{ \text{Expected discounted marginal benefit } }
    \tag{9} \label{optimalInvestment}
$$

The left side of this condition is the marginal cost of capital acccumulation and includes the direct cost of buying capital and the marginal adjustment cost.  
&emsp;&emsp;这个条件的左边是资本积累的边际成本，包括购买资本的直接成本和边际调整成本。

The right side indicates the expected and discounted marginal gains given by the derivative (change) in the value of the firm.  
&emsp;&emsp;右边表示公司价值的衍生工具（变化）给出的预期和贴现边际收益。

The expected discounted marginal value of the firm is also the **Marginal Q** \\( = \beta E[V _{K'} (A',K')] \\) .
Also,  
&emsp;&emsp;企业的预期折现边际价值也是边际Q\\( = \beta E[V _{K'} (A',K')] \\)。
也就是，

$$
    \begin{split} 
        \frac{\partial V(\theta, K)}{\partial K'} &= V _{K'} (A',K') \\\\
        & =  [ \pi _{K'} (\theta', K') +p' (1-\delta) - C _{K'} (K'',K')]
    \end{split}
$$

Substuting this in the investment decision condition,  
&emsp;&emsp;将此代入投资决策条件中，


\\[  C _{K'} (K'',K') + p = \beta E[\pi _{K'} (\theta', K') +p' (1-\delta) - C _{K'} (K'',K')] \\]

&emsp;where subscripts denote partial derivatives and primes denote next period values.  
&emsp;&emsp;其中下标表示偏导数，上标表示下一个周期值。

Assuming price is 1 and constant, and A quadratic adjustment cost \\( C(K',K) = C(I) = \frac{\phi}{2} I^2_t \\) ,  
Then  
&emsp;&emsp;假设价格为1且为常数，且为二次调整成本 \\( C(K',K) = C(I) = \frac{\phi}{2} I^2_t \\)，那么

$$
    \begin{split} 
        1+ \phi I 
        & = \beta E[ \pi _{K'} (\theta', K') + (1-\delta) + (1-\delta) (\phi I')] \\\\
        & = \beta E[ \pi _{K'} (\theta', K') + (1-\delta) (1 + \phi I')]
    \end{split}
$$

Since marginal Q, \\( q = 1 + \phi I \\),  
&emsp;&emsp;因为边际Q，\\( q = 1 + \phi I \\),所以

$$
    1+\phi I = \beta E[ \pi _{K'} (\theta', K') - (1 - \delta) q ]
$$

Marginal Cost today equals expected discounted additional profits tomorrow and the value of non-depreciated capital priced at \\( q' \\).
See why  \\( q \\) can also be interpreted as the "shadow price".
Note that both Dynamic Programming and Lagrange multiplier thus gives us the same solution.  
&emsp;&emsp;今天的边际成本等于明天的预期贴现额外利润和在\\( q' \\)阶段时定价的未折旧资本的价值。也可以理解为什么\\( q \\) 为“影子价格”。注意，动态规划和拉格朗日乘数都给出了相同的解。

The manager needs to take into account productivity shocks, \\(\theta \\), when deciding how much to invest, and they become an argument of the value function.
The way we take this into account in our problem is via the conditional expectation.
The manager thus weighs different possible scenarios in the future using their associated probabilities and takes an average value of these.
The implication here is that its not just current productivity shocks that impact firm value but also future uncertainty.  
&emsp;&emsp;管理者在决定投资多少时，需要考虑生产力（率）的冲击，\\(\theta \\)，它们就成了价值函数的一个论据。我们在问题中考虑这一点的方法是通过条件期望。因此，管理者使用相关的概率来衡量未来可能出现的不同情况，并取其平均值。这意味着，影响企业价值的不仅仅是当前的生产率冲击，还有未来的不确定性。

## 4. Essential Reading

- Gregory, Chow: Dynamic Economics: Optimization by the Lagrange Method - Chapter 2.

- Adda and Cooper: Dynamic Economics: Quantitative Methods and Applications - Chapter 1.





<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
 