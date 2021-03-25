---
layout: post
title: Mathematical Finance - Unit 7 The Black-Scholes Model
subtitle: 金融数学（七）布莱克-舒尔斯模型
category: money
tags: [ECON5020]
---

# Unit 7 The Black-Scholes Model

Uploaded by eva 


**Outline**     

We will examine the following issues:  
1 Wiener Process and its Properties  
2 The Black-Scholes Market Model  
3 The Black-Scholes Call Option Pricing Formula  
4 The Black-Scholes Partial Di¤erential Equation  


Wiener Process  
- The **Brownian motion** is a mathematical model used to describe the random movements of particles. It was named after Scottish botanist Robert Brown (1773-1858).  
- The Brownian motion is also known as the **Wiener process** in honour of American mathematician Norbert Wiener (1894-1964). The Wiener process  
is widely used to model uncertainty in engineering, economics and finance.  
- It is known that almost all sample paths of the Wiener process are continuous functions of the time parameter, but they are non-differentiable everywhere.  


Wiener Process: Definition  

Definition (Wiener Process: Equivalent Definition)  
A stochastic process \\(W = (W_t , t \in \mathbb R_+)\\) on \\(\Omega\\) is called the **Wiener process** if the following conditions hold:  
1 W(0) = 0.  
2 Sample paths of W are continuous functions.  
3 For any \\(0 \leq s < t, W(t) -W(s) \sim N (0, t - s)\\) where \\(N(μ, \sigma^2)\\) denotes the normal distribution with expected value μ and variance \\(\sigma^2\\).
4 The process \\(W_t\\) has independent increments, i.e. for any \\(0 \leq t_1 < t_2 < ... < t_n\\),  
$$
W(t_1),W(t_2) -W(t_1), . . . ,W(t_n) -W(t_{n-1})  
$$
are mutually independent.  


Existence of the Wiener Process  
- The Brownian motion was used in Physics to describe the diffusion movements of particles (in particular, by Einstein in his famous paper published in 1905).  
- The existence of a process satisfying the definition of a Wiener process is not obvious, however.
- The following theorem was first rigorously established by Norbert Wiener in the paper published in 1923.  

Theorem (Wiener's Theorem)  

There exists a probability space \\((\Omega,\cal F,\mathbb P)\\) and a process W defined on this space, such that conditions (1)-(4) of the definition of the Wiener process are met.  

Wiener Process: Sample Paths  

!["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/1.png "FIG.1")   

Figure: Three paths of a Wiener process with \\(\Delta t = 0.005\\)  


Distribution of the Wiener Process  

Let \\(N(μ, \sigma^2)\\) denote the normal distribution with mean μ and variance \\(\sigma^2\\). Probability distribution function (pdf) or a normally distributed variable is  

!["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/2.png "FIG.2")

The random variable Wt has the pdf p(x, t) given by  

!["FIG.3"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/3.png "FIG.3")

Hence for any real numbers \\(a \leq b\\)  

!["FIG.4"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/4.png "FIG.4")

where N is the standard normal cumulative distribution function (cdf), that is, 

!["FIG.5"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/5.png "FIG.5")   

Markov Property  
Proposition (8.1)  
The Wiener process W is a Markov process in the following sense: for every \\(n \geq 1\\), any sequence of times \\(0 < t_1 < . . . < t_n < t\\) and any collection \\(x_1, . . . , x_n\\) of real numbers, the following holds:  

!["FIG.7"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/7.png "FIG.7") 


for all \\(x \in \mathbb R\\). Moreover,  

!["FIG.6"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/6.png "FIG.6") 

is the transition probability density function of the Wiener process.  

Martingale Property  

Proposition (8.2)  

Let (W,F,P) be a probability space and W be the Wiener process. Then the process W is a martingale with respect to its natural filtration 
\\(\cal F_t = \cal F_t^W\\), that is, the filtration generated by W.  

Proof.
[Proof of Proposition 8.2] For all \\(0 \leq s < t\\), using the independence of increments of W, we obtain   

!["FIG.8"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/8.png "FIG.8")  

We conclude that W is a martingale with respect to its natural filtration.  


Stochastic differential equations  

Recall that differential equation  

$$  
x(t)=f(t,x(t))
$$

can be written alternatively as  

$$  
dx(t)=f(t,x(t)) dt
$$

or approximative as  

$$  
\Delta x(t)=f(t,x(t)) \Delta t
$$

with \\(\Delta x(t)= x(t+\Delta t)- x(t) \\)and \\(\Delta t\\) a small time increment.    
The increment of the function x(.) over the small time interval \\(\Delta t\\) is given by \\(f(t,x(t)) \Delta t\\) (all deterministic)  

Stochastic differential equations
1. Now, imagine that the dynamics of x(t) is a¤ected by little random shocks \\(\Delta W\\) generated by the increments of Brownian motion
2. More precisely, assume that (in approximation) the increment of the state variable x(.) over the time interval \\(\Delta t\\) is given by  

!["FIG.9"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/9.png "FIG.9")   

3. In differential notation we write equation (3) as   

!["FIG.10"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/10.png "FIG.10")  

and call the latter a stochastic differential equation.  

The Itô formula
Assume we have a process which is the solution of the stochastic differential equation  

!["FIG.11"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/11.png "FIG.11")  

and that we are interested in the values or more generally in the dynamic and the stochastic properties of an expression such as \\(g(t) = G(t, x(t)) with G : [0,\infty) × \mathbb R \to \mathbb R\\).    

1. the Itô formula provides a tool, how to compute the dynamic of the transformed process g(.) with g(t) = G(t, x(t)) in terms of the dynamic of x(.)
2. it presents in a way a generalization of the chain rule of classical calculus
3. this shows to be extremely helpful when solving stochastic differential equations and is necessary to derive pricing PDEs for option pricing problems  

The Itô formula
Theorem (Itô formula)
Suppose that x(.) solves the stochastic differential equation  

!["FIG.12"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/12.png "FIG.12")  

and that \\( G : [0,\infty) × \mathbb R \to \mathbb R\\) is a function with continuous partial derivatives \\(G_t,G_x\\) and \\(G_{xx} \\). Then the stochastic process g(.) defined by g(t) = G(t, x(t)) has the following dynamics  

!["FIG.13"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/13.png "FIG.13")  

The Itô formula  

Knowing the chain-rule of classical calculus, only the middle term
\\(\frac{1}{2} \sigma^2(t, x(t))G_{xx} (t, x(t))\sigma^2(t, x(t))dt\\) is somehow unexpected. The reason for its occurrence is the following:
1. a second order term in dW produces a first order dt, often written as
\\((dW(t))^2 = dt\\)
2. the Itô formula can then be derived from second order Taylor approximation, taking the above rule into account, and neglecting all dt terms which are of order strictly higher than first order.
3. there is also a multi-dimensional version of the Itô formula
4. in our applications x(t) will denote the stock price and G(t, x(t)) the price of an option  

Stock Price Process  

- We note that the values of the Wiener process W can be negative and thus it cannot be used to directly model the movements of the stock price.
- Following Black and Scholes (1973), we postulate that the stock price
process S can be described under the risk-neutral probability measure
\\(\mathbb P\\) by the following **stochastic differential equation** 

!["FIG.14"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/14.png "FIG.14") 

with a constant initial value \\(S_0 > 0\\).  
- The term \\(\sigma S_t dW_t\\) is aimed to give a reasonable description of the uncertainty in the market.  

- The **volatility** parameter \\(\sigma > 0\\) is used to control the size of random fluctuations of the stock price.  

Stock Price Process  
- It turns out that stochastic di¤erential equation (1) can be solved
explicitly yielding   

!["FIG.15"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/15.png "FIG.15")  

The process S is called the geometric Brownian motion.
- Note that St has the lognormal distribution for every t > 0.
- It can be shown that S is a Markov process. Note, however, that S is
not a process of independent increments.
- We assume that the continuously compounded interest rate r is
constant. Hence the savings account equals   

!["FIG.16"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/16.png "FIG.16")  

Sample Paths of Stock Price  

!["FIG.17"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/17.png "FIG.17")

Random Walk Approximation  
- Our final goal is to examine an approximation of the Black-Scholes
model by a sequence of CRR models.  
- The following result is an easy consequence of the Central Limit
Theorem.  

Theorem (8.2)   
be a random walk starting at 0 with increments  

!["FIG.18"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/18.png "FIG.18")

and the limit exists in the sense of probability distribution.  


Random Walk Approximation
!["FIG.19"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/19.png "FIG.19")  


Approximation of the Stock Price  

- Recall that the JR parameterisation for the CRR binomial model
postulates that   

!["FIG.20"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/20.png "FIG.20") 

- We will show that it corresponds to a particular approximation of the
stock price process S  

- Suppose that \\(S_s\\) is known. Recall (formula (5) in this set of slides) that for all \\(s \leq t\\)   

!["FIG.21"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/TheBlack-ScholesModel/21.png "FIG.21") 



<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>