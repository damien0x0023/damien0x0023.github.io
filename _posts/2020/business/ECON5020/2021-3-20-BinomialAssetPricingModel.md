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
5 Examples: American Call and Put Options  

# Introduction
The Cox-Ross-Rubinstein market model (CRR model) is
an example of a multi-period market model of the stock price.
At each point in time, the stock price is assumed to either go upby
a xed factor u or go downby a xed factor d.
Only three parameters are needed to specify the binomial asset pricing
model: u > d > 0 and r > 􀀀1.
Note that we do not postulate that d < 1 < u.
The real-world probability of an upmovement is assumed to be the
same 0 < p < 1 for each period and is assumed to be independent of
all previous stock price movements.  

# Bernoulli Processes
Denition (Bernoulli Process)
A process X = (Xt )1tT on a probability space (W,F,P) is called a
Bernoulli process with parameter 0 < p < 1 if the random variables
X1,X2, . . . ,XT are independent and have the following common
probability distribution
P(Xt = 1) = 1 􀀀 P(Xt = 0) = p.
Denition (Bernoulli Counting Process)
The Bernoulli counting process N = (Nt )0tT is dened by setting
N0 = 0 and, for every t = 1, . . . ,T and w 2 W,
Nt (w) := X1(w) + X2(w) +    + Xt (w).
The process N is a special case of an additive random walk.  

!["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/1.png "FIG.1")  

# Stock Price
Definition (Stock Price)
The stock price process in the CRR model is dened via an initial value
S0 > 0 and, for 1  t  T and all w 2 W,
St (w) := S0uNt (w)d t􀀀Nt (w).
The underlying Bernoulli process X governs the upand down
movements of the stock. The stock price moves up at time t if
Xt (w) = 1 and moves down if Xt (w) = 0.
The dynamics of the stock price can be seen as an example of a
multiplicative random walk.
The Bernoulli counting process N counts the up movements. Before
and including time t, the stock price moves up Nt times and down
t 􀀀 Nt times.  

!["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/2.png "FIG.2")  

!["FIG.3"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/3.png "FIG.3")  

# Distribution of the Stock Price
For each t = 1, 2, . . . ,T, the random variable Nt follows a binomial
distribution with parameters p and t.
Specically, for every t = 1, . . . ,T and k = 0, . . . , t we have that
P(Nt = k) =

t
k

pk (1 􀀀 p)t􀀀k .
Hence the probability distribution of the stock price St at time t is
given by
P(St = S0ukdt􀀀k ) =

t
k

pk (1 􀀀 p)t􀀀k
for k = 0, 1, . . . , t.  

# Stock Price Lattice  

!["FIG.4"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/BinomialAssetPricingModel/4.png "FIG.4")  

# Risk-Neutral Probability Measure  

Proposition (7.1)
Assume that d < 1 + r < u. Then a probability measure ˜P on (W,FT ) is
a risk-neutral probability measure for the CRR model M= (B, S) with
parameters p, u, d, r and time horizon T if and only if:
1 X1,X2,X3, . . . ,XT are independent under the probability measure ˜P,
2 0 < ˜p := ˜P (Xt = 1) < 1 for all t = 1, . . . ,T,
3 ˜pu + (1 􀀀 ˜p)d = (1 + r ),
where X is the Bernoulli process governing the stock price S.  

Proposition (7.2)
If d < 1 + r < u then the CRR market model M= (B, S) is
arbitrage-free and complete.
Since the CRR model is complete, the unique arbitrage free price of
any European contingent claim can be computed using the
risk-neutral valuation formula  

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










<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>