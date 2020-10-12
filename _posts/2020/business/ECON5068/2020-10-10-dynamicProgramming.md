---
layout: post
title: Investment, Finance and Asset Prices - Unit 3 Dynamic Programming
subtitle: 投资，金融与资产定价之（三）动态规划
category: money
tags: [ECON5068]
---

# Unit 3 Dynamic Programming

<!-- translated by damien from sildes of Sisi Ramanan -->

## 1. Dynamic Programming


In the last lecture, we used Lagrange multipliers to solve the optimization problem of the firm.
Dynamic Programming is an alternate method that can be used to solve optimization problems.
The approach is different yet gives an identical solution.

Dynamic Programming is popular since it is easy to implement numerically in the computer.
We will learn dynamic programming using an example.

## 2. Example: Cake-Eating


Suppose you have a cake of size \\( W_1 \\). You have T periods to consume this cake.
Every period \\( t=1,2...T \\) you consume some of the cake and save the rest.
The initial size of the cake at \\( t=1 \\) is \\( W_1 \\). 

Assume that the cake cannot melt (depreciate) or grow.
Let  \\( c_t \\) represent the consumption of cake at time t and \\( u(c_t) \\) the flow of utility (satisfaction) from this consumption.

Assume \\( u(.) \\) is real-valued, continuous, differentiable and concave and consumption should always be non-negative.
The life-time utility from consuming the cake is given by the discounted sum of all current and future utility of consumption: 

$$
    u(c_1) + \beta u(c_2) +\beta^2 u(c_3) + ... +\beta^{T-1} u(c_T)
$$

That is,

$$
    \sum^T_{t=1} \beta^{t-1} u(c_t)
$$

&emsp; where \\( 0 \leq \beta \leq 1 \\) is the discount factor.

The evolution of cake size every period is given by: 

\\[ W_{t+1} = W_t - c_t  \ ,\  \text{for} \ t=1,2,... T. \\]

**Problem**: \\( \text{How would you find the optimal path of consumption} \ \left \\{ c^*_t \right \\}^T _{t=1} \\)?

In other words, what is the level of consumption every period that maximizes your lifetime utility.

### 2.1 Lagrangean Approach

One approach is to use the method of Lagrange multipliers.
This is then a constrained optimization problem where:

$$
    \max_{c_t,W_{t+1}} \left [ \sum^T_{t=1} \beta^{t-1} u(c_t) \right ]
$$

&emsp; subject to the constraint:

$$
    W_{t+1} = W_t - c_t
$$

&emsp; for all \\( t = 1,2, ... T. \\)

The Lagrangean function can be written as:

$$
    \mathscr{L} = \sum^T_{t=1} \beta^{t-1} \left [    
        u(c_t) - \lambda_t(W_{t+1} - W_t -c_t)    
    \right ]
$$

&emsp; Note: This is a dynamic optimization problem, we have an objective function and a constraint at every period \\( t \\). All future values need to be discounted.

The necessary condition for maximizing this lagrangean function is given by the three FOC's:


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

\\[
    u'(c_t) = \beta u'(c_{t+1})
    \tag{4} \\label{eulerEquation}
\\]

This equation is so common that it has a special name in economics - **Euler Equation**.

The left hand side represents the marginal loss in utility when you sacrifice 1 unit of consumption and the right hand side is the discounted marginal gain in utility from this extra unit of consumption next period.

For optimal consumption, this Euler equation should be satisfied.

The second condition is simply the cake size constraint:

$$
    W_{t+1} = W_t -c_t
    \tag{5} \label{cakeSizeConstraint}
$$

These two conditions are not enough for an optimal solution. 
Since this is a finite time horizon problem, we need to have a terminal condition.

For maximum utility, there should not be any cake left over at the end of the last period. That is,

\\[
    W_{T+1} = 0
    \tag{6} \label{maximumUtility}
\\]

This terminal condition naturally implies that the sum of consumption across all periods should equal the total size of the cake:

$$
    \sum^T_{t=1} c_t = W_1
    \tag{7} \label{totalSize}
$$

Using the value of W1 and eq.'s \eqref{eulerEquation} and \eqref{totalSize}, we can find the optimal path of consumption \\( \left \\{ c^*_t \right \\}^T _{t=1} \\) that maximizes utility.

### 2.2 Dynamic Programming Approch

The solution to this T period cake eating problem is found by substituting the optimal path of consumption in the lifetime utility function. We will denote this maximum as \\( V_t(W_1)\\): 

$$
    V_t(W_1) = \max \left [ \sum^T_{t=1} \beta^{t-1} u(c_t) \right ] = \sum^T_{t=1} \beta^{t-1} u(c^*_t) 
$$

\\( V(W_1) \\) is called as a **value function** and here it represents the maximum \\( T \\) period utility of consumption given an initial level of wealth \\( W_1 \\).

Suppose we change this cake eating problem by adding a period 0 and giving an initial cake size of \\( W_0 \\). 
We can again solve this by formulating a new lagrangean for the \\( T + 1 \\) period problem.
However, a better way would be to somehow make use of the \\( T \\)  period solution that we found.

Dynamic Programming (DP) provides means for doing this.
DP essentially converts a general \\( T \\)  period problem into a 2 period one.
DP breaks down the optimal path into two parts, what is optimal today and the optimal continuation path.
Given  \\( W_0 \\), the optimization problem can be written as: 

$$
    \max_{c_0} [ u(c_0) + \beta V_T(W_1)]
$$

&emsp; where
\\[  W_1 = W_0 - c_0 \\]

**So instead of choosing the entire path** of \\( c_t\\) , we are just choosing \\( c_0 \\). 
The rest of the path is optimally determined by the value function, \\( V_T (W_1) \\). 
Once \\( c_0 \\) and hence \\( W_1 \\) is determined, the value function summarizes the rest of the problem. 

This is the **principle of optimality** due to Richard Bellman: we can represent the full dynamic problem as a sequence of **recursive** 2 period problems.

The first order condition of this value function problem is given by:

\\[ 
    u'(c_0) = \beta V'_T (W_1)    
\\]

so that the marginal gain from reducing consumption a little in period 0 is summarized by the derivative of the value function. 
Also,

\\[ 
    V'_T (W_1) = \beta^t u' (c _{t+1})
\\]

&emsp; for \\( t = 1,2, ... T-1 \\). Using these two conditions together yields

\\[
    u' (c_t) = \beta u' (c _{t+1})
\\]

which is the same as the Lagrange solution.

Suppose that we consider the above problem and allow the horizon to go to infinity. As before, one can consider solving the infinite horizon sequence problem given by:

$$
    \max_{ \\{c_t \\} ^\infty_1 ,\ \\{ W_{t+1} \\} ^\infty_2 } \left [ \sum^T_{t=1} \beta^{t} u(c_t) \right ]
$$

&emsp; along with the transition equation of

$$
    W_{t+1} = W_t - c_t
$$

for \\( t = 1, 2, ... \infty \\).

We can write this as a dynamic programming problem as:

$$
    V(W) = \max_{c, W'} u(c) + \beta V(W')
    \tag{8} \label{DP}
$$

for all W where \\( W' = W - c \\) is the transition equation. 

\\( V(W) \\) is the value of the infinite horizon cake eating problem or the maximal utility from this consumption. 
\\( W' = W - c \\) is the state transition equation or equivalently the evolution of cake size.

Variables with prime denote future values, not to be confused with the derivative.

In general, we use primes to denote future values when we are looking for a stationary solution to an infinite horizon problem.
The value function here is stationary, that is:

$$
    V_t(W) = V_{t+k} (W) = V(W) \ \ \text{for any } k > 0
$$

Stationarity means **time-invariant**, that is the value function or policy functions are optimal and do not change with time.

Remember these functions denote a path or a rule, so stationarity here means that this path is constant (not the actual variable).
The two policy functions maps the state varables to controls.

In this problem, the two policy functions are:

$$
    W'(W) \text{ and } c(W)
$$

next period cake size and consumption.

What are the **state** and **control** (choice) variables?

The state variable is the size of the cake (W) that is given at the start of any period. The cake size completely summarizes all information from the past that is needed for the forward looking optimization problem.

The control variable is the variable that is being chosen. In this case, it is the level of consumption in the current period, \\( c \\) and next period cake size \\( W' \\).

The transition (or the constraint) desribes the dependence of the state tomorrow on the state today and the control today:

$$
    W' = W - c
$$

Alternatively, we can write the DP, in \eqref{DP}, as:

$$
    V(W) = \max_{W'} u(W' - w) + \beta V(W')
$$

&emsp; where we have substituted the constraint so that we have to choose only tomorrow's cake size.

Either specification will yield the same result. This expression is a functional equation and is often called a Bellman equation after Richard Bellman, the originator of dynamic programming.

Note that the unknown in the Bellman equation is the value function itself: the idea is to find a function V(W) that satisfies this condition for all W.

## 3. Investment

We will apply Dynamic Programming to the adjustment cost model.
The firm's optimization problem is as follows:

$$
    \max_{K_{t+1}} E_0 \sum^{\infty}_{t=0} \beta^t \left [    
            \pi(\theta_t, K)_t 
            - p(K _{t+1} - (1-\delta) K _t)
            - C(K _{t+1}, K _t)
        \right ]
$$

where \\( C(.) \\) is the convex adjustment cost function, \\( p \\) is the price of capital (investments) and we have substituted the capital acccumulation constraint for investments \\( I_t \\).

This is the generalized version of the **adjustment cost model** where \\( p \\), \\( \theta \\) is time-varying and the adjustment cost could be any function that is convex and increasing.

The Bellman equation or the DP for this problem can be written as follows:

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

\\[
    \theta' = \rho  \theta + \epsilon , \text{ where } \epsilon \sim N(0,1)
\\]

Here the next period value, \\(\theta '\\), depends on its previous period
value, \\(\theta \\), and a **random** error normally distributed with mean
zero and variance 1.
This is one way to model the unpredictable (random) evolution of technological productivity/innovation.

The firm manager solves the DP in eq. \eqref{bellmanEqu} by choosing the next period level of capital \\( K' \\). The solution is given by the FOC with reference to (w.r.t)  \\( K' \\):

$$
        \frac{\partial V(\theta, K)}{\partial K'}  = 0
$$

$$
       \implies - C_{K'}(K',K) - p + \beta E[V _{K'} (A',K') ] = 0
$$

Thus, the optimal investment decision is based on the following condition:

$$
    \underbrace{ C_{K'}(K',K)+p} _{\text{Marginal Cost} } 
    = \underbrace { \beta E[V _{K'} (A',K')]} _{ \text{Expected discounted marginal benefit } }
    \tag{9} \label{optimalInvestment}
$$

The left side of this condition is the marginal cost of capital acccumulation and includes the direct cost of buying capital and the marginal adjustment cost.

The right side indicates the expected and discounted marginal gains given by the derivative (change) in the value of the firm.

The expected discounted marginal value of the firm is also the **Marginal Q** \\( = \beta E[V _{K'} (A',K')] \\) .

Also,

$$
    \begin{split} 
        \frac{\partial V(\theta, K)}{\partial K'} &= V _{K'} (A',K') \\\\
        & =  [ \pi _{K'} (\theta', K') +p' (1-\delta) - C _{K'} (K'',K')]
    \end{split}
$$

Substuting this in the investment decision condition, \\[  C _{K'} (K'',K') + p = \beta E[\pi _{K'} (\theta', K') +p' (1-\delta) - C _{K'} (K'',K')] \\]

&emsp;where subscripts denote partial derivatives and primes denote
next period values.

Assuming price is 1 and constant, and A quadratic adjustment cost \\( C(K',K) = C(I) = \frac{\phi}{2} I^2_t \\) ,  
Then

$$
    \begin{split} 
        1+ \phi I 
        & = \beta E[ \pi _{K'} (\theta', K') + (1-\delta) + (1-\delta) (\phi I')] \\\\
        & = \beta E[ \pi _{K'} (\theta', K') + (1-\delta) (1 + \phi I')]
    \end{split}
$$

Since marginal Q, \\( q = 1 + \phi I \\),

$$
    1+\phi I = \beta E[ \pi _{K'} (\theta', K') - (1 - \delta) q ]
$$

Marginal Cost today equals expected discounted additional profits tomorrow and the value of non-depreciated capital priced at \\( q' \\).
See why  \\( q \\) can also be interpreted as the "shadow price".
Note that both Dynamic Programming and Lagrange multiplier thus gives us the same solution.

The manager needs to take into account productivity shocks, \\(\theta \\), when deciding how much to invest, and they become an argument of the value function.
The way we take this into account in our problem is via the conditional expectation.
The manager thus weighs different possible scenarios in the future using their associated probabilities and takes an average value of these.
The implication here is that its not just current productivity shocks that impact firm value but also future uncertainty.

## 4. Essential Reading

- Gregory, Chow: Dynamic Economics: Optimization by the Lagrange Method - Chapter 2.

- Adda and Cooper: Dynamic Economics: Quantitative Methods and Applications - Chapter 1.





<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
 