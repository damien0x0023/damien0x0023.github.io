---
layout: post
title: Mathematical Finance - Unit 6 Binomial Asset Pricing Model
subtitle: 金融数学（六）二项式资产定价模型
category: money
tags: [ECON5020]
---

# Unit 6 Binomial Asset Pricing Model

Uploaded by eva 


**Outline**   

We will examine the following issues:
1 The Cox-Ross-Rubinstein Market Model
2 The CRR Call Option Pricing Formula
3 Call and Put Options of American Style
4 Dynamic Programming Approach to American Claims  
美国索赔的动态规划方法
5 Examples: American Call and Put Options  

# Introduction
- The Cox-Ross-Rubinstein market model (CRR model) is an example of a multi-period market model of the stock price.
- At each point in time, the stock price is assumed to either go 'up' by a fixed factor u or go 'down' by a fixed factor d.  
在每一个时间点，股票价格都被假定为以固定因子u“上升”或以固定因子d“下降”。
- Only three parameters are needed to specify the binomial asset pricing model: u > d > 0 and r > -1.  
二项资产定价模型只需要三个参数：u>d>0 和 r>-1。
- Note that we do not postulate that d < 1 < u.  
注意，我们没有假设

- The real-world probability of an 'up' movement is assumed to be the same 0 < p < 1 for each period and is assumed to be independent of all previous stock price movements.   
假设每个时期的实际“上涨”概率为0<p<1， 并且与之前的所有股价变动无关。


# Bernoulli Processes  

Definition (Bernoulli Process)  
定义（伯努利过程)  
A process \\(\pi(X)= (\pi_t (X))_{0 \leq t \leq T}\\) on a probability space \\((\Omega,\cal F,\mathbb P)\\) is called a **Bernoulli process** with parameter 0 < p < 1 if the random variables \\(\pi(X)= (\pi_t (X))_{0 \leq t \leq T}\\) are independent and have the following common probability distribution  
概率空间\\((\Omega,\cal F,\mathbb P)\\)上的过程\\(X = (X_t)_{\leq t \leq T}\\)称为参数为0<P<1的**伯努利过程**，如果随机变量\\(X_1,X_2, . . . ,X_T\\)是独立的，具有以下公共概率分布

$$
\mathbb p (X_t = 1) = 1 - P(X_t = 0) = \mathbb p.   
$$  

Definition (Bernoulli Counting Process)  

The **Bernoulli counting process**  \\(N = (N_t )_{\leq t \leq T} \\) is defined by setting \\(N_0 = 0\\) and, for every t = 1, . . . ,T and \\(\omega \in \Omega \\),   

伯努利计数过程
$$
N_t (\omega) := X_1(\omega) + X_2(\omega) + ... + X_t (\omega).   
$$ 

The process N is a special case of an **additive random walk**.  
过程N是**加性随机游走**的特例。


!["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/1.png "FIG.1")  

# Stock Price
Definition (Stock Price)
The stock price process in the CRR model is defined via an initial value \\(S_0 > 0\\) and, for \\(1 \leq t \leq T\\) and all \\(\omega \in \Omega\\),  

$$
S_t (\omega) := S_0 u^N_t (\omega)d^t-N_t (\omega).  
$$  


- The underlying Bernoulli process X governs the 'up' and 'down' movements of the stock. The stock price moves up at time t if \\(X_t (\omega) = 1\\) and moves down if \\(X_t (\omega) = 0\\).  

基本的伯努利过程X控制着股票的“上升”和“下降”运动。如果 \\(X_t (\omega) = 1\\)，股票价格在时间t上升，如果\\(X_t (\omega) = 0\\)，股票价格下降。
- The dynamics of the stock price can be seen as an example of a multiplicative random walk.    
股票价格的动态可以看作是乘性随机游走的一个例子。   

- The Bernoulli counting process N counts the up movements. Before and including time t, the stock price moves up \\(N_t\\) times and down \\(t - N_t \\) times.  

伯努利计数过程N计算上升运动。在时间t之前（包括时间t），股票价格向上移动\\(N_t\\)次，向下移动\\(t - N_t \\)次。

!["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/2.png "FIG.2")  

!["FIG.3"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/3.png "FIG.3")  

# Distribution of the Stock Price  
- For each t = 1, 2, . . . ,T, the random variable \\(N_t\\) follows a binomial distribution with parameters p and t.  
对于每个t=1，2。，T，随机变量\\(N_t\\)遵循参数p和T的二项分布。

- Specifically, for every t = 1, . . . ,T and k = 0, . . . , t we have that  
具体来说,

!["FIG.32"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/32.png "FIG.32")


- Hence the probability distribution of the stock price \\(S_t\\) at time t is given by  
因此，时间t时股票价格的概率分布\\(S_t\\)由下式给出

!["FIG.33"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/33.png "FIG.33") 

# Stock Price Lattice  

!["FIG.4"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/4.png "FIG.4")  

# Risk-Neutral Probability Measure  

Proposition (7.1)  

Assume that d < 1 + r < u. Then a probability measure \\(\mathbb {\widetilde P}\\) on \\((\\Omega,\cal F_T )\\) is a risk-neutral probability measure for the CRR model \\(\cal M= (B, S)\\) with parameters p, u, d, r and time horizon T if and only if:
1. \\(X_1,X_2,X_3, . . . ,X_T\\) are independent under the probability measure \\(\mathbb {\widetilde P}\\),
2. 0 < ˜p := \\( \mathbb {\widetilde P} (X_t = 1) < 1\\) for all t = 1, . . . ,T,
3. ˜pu + (1 - ˜p)d = (1 + r ),
where X is the Bernoulli process governing the stock price S.  

Proposition (7.2)  

If d < 1 + r < u then the CRR market model M= (B, S) is
arbitrage-free and complete.
Since the CRR model is complete, the unique arbitrage free price of any European contingent claim can be computed using the risk-neutral valuation formula  

!["FIG.5"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/5.png "FIG.5")   

# CRR Call Option Pricing Formula  

!["FIG.6"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/6.png "FIG.6")  

# Proof of Proposition 7.3  

!["FIG.7"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/7.png "FIG.7")   

[Proof of Proposition 7.3]
Recall we are interested in
􀀀
S0ukdT􀀀k 􀀀 K
+
Dene ˆk to be the smallest non-negative integer k such that
S0ukdT􀀀k > K. If ˆk > T then S0ukdT􀀀k  K and C0 = 0.
Otherwise we have a chance to get some money.
Note
k log
 u
d

> log

K
S0dT

,
 u
d
k
>
K
S0dT , S0uk dT􀀀k 􀀀 K > 0
so this is just a way to write condition for the rst occurence of
S0ukdT􀀀k 􀀀 K > 0.
We dene ˆk = ˆk (S0,T) as the smallest integer k such that the last
inequality is satised. If there are less than ˆk upward movements the
option will expire worthless.  


!["FIG.8"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/8.png "FIG.8")  


!["FIG.9"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/9.png "FIG.9")  

# Put-Call Parity  

!["FIG.10"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/10.png "FIG.10")   

We started with t = 0, but the same analysis is true for any t. It is
easy to demonstrate that   

!["FIG.11"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/11.png "FIG.11")

Similarly, for a put option    

!["FIG.12"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/12.png "FIG.12")  


Therefore, put-call parity holds at any date t = 0, 1, . . . ,T  

!["FIG.13"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/13.png "FIG.13")   

American Options
In contrast to a contingent claim of European style, a claim of
American style can by exercised by its holder at any date before its
expiration date T.  

Denition (American Call and Put Options)
An American call (put) option is a contract which gives the holder the
right to buy (sell) an asset at any time t  T of her/his choice at strike
price K.  

In the study of American options, we are concerned with the price
process and the optimalexercise policy by its holder.
If the holder of an American option exercises it at t 2 [0,T], t is
called the exercise time.  

American Call Option
Denition
By an arbitrage free price of the American call we mean a price process
Ca
t , t  T, such that the extended nancial market model that is, a
market with trading in riskless bonds, stocks and the American call option
remains arbitrage-free.
By denition, the arbitrage free price of American call option  

!["FIG.14"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/14.png "FIG.14")  


Proposition (7.4)
The price of an American call option in the CRR arbitrage-free market
model with r  0 coincides with the arbitrage price of a European call
option with the same expiry date and strike price.  


Proof of Proposition 7.4
Proof.
[Proof of Proposition 7.4] For simplicity, we assume r > 0. Obviously  

!["FIG.15"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/15.png "FIG.15")   


!["FIG.16"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/16.png "FIG.16")   

The result only holds for non-dividend-paying stock.
The proof requires r > 0. It means that the similar proof for a put
option might require r < 0, which is not realisic. In fact, we see a
number of examples further in the course when it is optimal to
exercise put option early.  


American Put Option
Recall that the American put is an option to sell a specied number
of shares, which may be exercised at any time before or at the expiry
date T.
By denition, the arbitrage free price Pa
t of an American put option equals  

!["FIG.17"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/17.png "FIG.17")  


Dynamic Programming Recursion
The stopping time tt is called the rational exercise time
of an American put option that is assumed to be still alive
at time t.
By an application of the classic Bellman principle (1952), one
reduces the optimal stopping problem in Proposition 7.5 to an explicit
recursive procedure for the value process.
We now show how to arrive to the dynamic programming recursion
for the value of an American put option. The American call option
can be treated similarly.
Note that this is an extension of the backward induction approach to
the valuation of European contingent claims.  


Dynamic Programming Recursion
Corollary (Bellman Principle)  
Let the non-negative adapted process U be dened recursively by setting  
!["FIG.18"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/18.png "FIG.18")

Then the arbitrage free price Pa
t of the American put option at time t
equals Ut and the rational exercise time after time t admits the following
representation  

!["FIG.19"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/19.png "FIG.19")  


Dynamic Programming Recursion
It is also possible to show directly that the price Pa
t satises the
recursive relationship, for t  T 􀀀 1,  
!["FIG.20"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/20.png "FIG.20") 

subject to the terminal condition PaT
= (K 􀀀 ST )+.
In the case of the CRR model, this formula reduces the valuation
problem to the simple single-period case.
To show this we shall argue by contradiction. Assume rst that (1)
fails to hold for t = T 􀀀 1. If this is the case, one may easily
construct at time T 􀀀 1 a portfolio which produces riskless prot at
time T. Hence, we conclude that necessarily  

!["FIG.21"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/21.png "FIG.21") 

This procedure may be repeated as many times as needed.  

American Put Option: Summary
To summarize:
In the CRR model, the arbitrage pricing of the American put option
reduces to the following recursive recipe, for t  T 􀀀 1,  
!["FIG.22"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/22.png "FIG.22")  

The quantities Pau
t+1 and Pad
t+1 represent the values of the American
put in the next step corresponding to the upward and downward
movements of the stock price starting from a given node on the CRR
lattice.  

American Call Option: Summary
To summarize:
In the CRR model, the arbitrage pricing of the American call option
reduces to the following recursive recipe, for t  T 􀀀 1,    

!["FIG.23"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/23.png "FIG.23")   


The quantities Cau
t+1 and Cad
t+1 represent the values of the American
call in the next step corresponding to the upward and downward
movements of the stock price starting from a given node on the CRR
lattice.  

Example: American Call Option  

Example (7.1)
We consider here the CRR binomial model with the horizon date
T = 2 and the risk-free rate r = 0.2.
The stock price S for t = 0 and t = 1 equals
S0 = 10, Su
1 = 13.2, Sd
1 = 10.8.
Let Xa be the American call option with maturity date T = 2 and
the following payo¤ process
g(St , t) = (St 􀀀 Kt )+.
The strike Kt is variable and satises
K0 = 9, K1 = 9.9, K2 = 12.  

Example: American Call Option
Example (7.1 Continued)
We will rst compute the arbitrage price pt (Xa) of this option at
times t = 0, 1, 2 and the rational exercise time t0.
Subsequently, we will compute the replicating strategy for Xa up to
the rational exercise time t0.
We start by noting that the unique risk-neutral probability measure eP
satises
ep =
1 + r 􀀀 d
u 􀀀 d
=
(1 + r )S0 􀀀 Sd
1
Su
1 􀀀 Sd
1
=
12 􀀀 10.8
13.2 􀀀 10.8
= 0.5
The second exhibit represents the price of the call option.  

!["FIG.24"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/24.png "FIG.24") 

!["FIG.25"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/25.png "FIG.25")  

Example: Replicating Strategy
Example (7.1 Continued)
Holder. The rational holder should exercise the American option at
time t = 1 if the stock price rises during the rst period. Otherwise,
the option should be held till time 2. Hence t0 : W ! f0, 1, 2g equals  


!["FIG.26"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/26.png "FIG.26")  

Issuer. We now take the position of the issuer of the option.
At t = 0, we need to solve  

!["FIG.27"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/27.png "FIG.27")    

Example: Replicating Strategy
Example (7.1 Continued)
If the stock price rises during the rst period, the option is exercised
and thus we do not need to compute the strategy at time 1 for
w 2 fw1,w2g.
If the stock price falls during the rst period, we solve  

!["FIG.28"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/28.png "FIG.28")  


Note that ef0
1 = 􀀀8.46 is the amount of cash borrowed at time 1,
rather than the number of units of the savings account B.
The replicating strategy f = (f0, f1) is dened at time 0 for all w
and it is dened at time 1 on the event fw3,w4g only.
Kirsanova (Glasgow) Mathematical Finance Semester  


!["FIG.29"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/29.png "FIG.29")  

Example: American Call Option vs. European Call Option
Example (7.1)
Consider the same setup but Kt = 12 and does not depend on time.
The same strike price is for the European Call option.
We start by noting that the unique risk-neutral probability measure eP
satises  

!["FIG.30"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/30.png "FIG.30") 

!["FIG.31"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/31.png "FIG.31")  

Derivation of u and d from r and s
the parameters r and S0 can be observed in real nancial markets,
but the parameters u and d are only a model idealization and can not
be directly determined by observation of real world data
people trading on stock markets study a di¤erent parameter, which
they call volatility and which reects a property of the corresponding
continuous time model, also known as the Black-Scholes model
From the market data for stock prices, one can estimate the stock
price volatility s per one time unit (typically, one year).
Note that until now we assumed that t = 0, 1, 2, . . . ,T, which means
that Dt = 1. In general, the length of each period can be any positive
number smaller than 1. We set n = T/Dt.



<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>