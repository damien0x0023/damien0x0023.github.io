---
layout: post
title: Mathematical Finance - Unit 0 Probability Review
subtitle: 金融数学（零）概率论回顾
category: money
tags: [ECON5020]
---

# Unit 0 Probability Review

Uploaded by eva 

fig


<font color="#dd0000">浅红色文字：</font><br/> 


!["FIG.111"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR_20210127152938.png "FIG.1")

**Outline**




## 1. Discrete Random Variables  

**1.1 Sample Space** 样本空间

- We collect the possible states of the world and denote the set by \\( \Omega \\).
The states are called **samples** or **elementary events**.
- The sample space \\( \Omega \\) is either **countable** or **uncountable**.  
&emsp;&emsp;我们收集世界的可能状态，并用Ω表示该状态。这些状态称为样本或基本事件。样本空间Ω是可数的或不可数的。


    - A toss of a coin: \\( \Omega = \\lbrace Head, Tail \\rbrace = \\lbrace H, T \\rbrace.  \\) 
    - The number of successes in a sequence of *n* identical and independent trials: \\( \Omega = \\lbrace 0, 1, . . . , n \\rbrace \\).  
    n个相同且独立的试验序列中的成功次数：
    - The moment of occurrence of the first success in an infinite sequence of identical and independent trials: \\( \Omega = \\lbrace 1, 2. . . \\rbrace \\).  
    相同且独立试验的连续序列中首次成功的时刻：
    - The lifetime of a light bulb: \\( \Omega = \\lbrace x \\in R || x \\geq 0  \\rbrace \\).  
    一个灯泡的寿命：

- The choice of a sample space is arbitrary and thus any set can be taken as a sample space. However, practical considerations justify the choice of the most convenient sample space for the problem at hand.  **Discrete** (finite or infinite, but countable) sample spaces are easier to handle than general sample spaces.  
&emsp;&emsp;样本空间的选择是任意的，因此任何集合都可以作为样本空间。然而，出于实际考虑，我们需要为手头的问题选择最方便的样本空间。
离散（有限或无限，但可数）样本空间比一般样本空间更容易处理。

**1.2 Discrete Random Variables**

- Examples of random variables: 随机变量示例
  - Prices of stocks. 股票价格
  - Exchange rates. 汇率
  - Payoffs corresponding to portfolios. 与投资组合相应的收益

  !["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR4.png "FIG.1")
  离散随机变量

  &emsp;&emsp;实值函数 X 的定义域 \\( \Omega \\)取值在实数R一个离散样本空间\\( \Omega = \omega _k\\)中，其中 *I* 是可数的。这个X 称为离散随机变量。
  !["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR4-1.png "FIG.2")
  概率

  &emsp;&emsp;映射P：定义域\\( \Omega \\)的取值在[0,1]之间，被称为离散样本空间\\( \Omega \\)上的概率。


**1.3 Probability Measure**

Let F = \\( 2^\Omega \\) stand for the class of all subsets of the sample space \\( \Omega \\).  
&emsp;&emsp;F代表样本空间Ω的所有子集的个数。Ω为元素个数。  
The set \\( 2^\Omega \\) is called the **power set** of \\( \Omega \\).  
&emsp;&emsp;\\( 2^\Omega \\) 是\\( 2^\Omega \\)的幂集。  
Note that the **empty set** \\(\emptyset\\) also belongs to any power set.  
&emsp;&emsp;空集属于任何幂集。
  !["FIG.3"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR5.png "FIG.3")
一个映射P的定义域F的取值在[0,1]之间，称为在（\\( \Omega \\)，F）上的概率测度。  
对于任何Ai 真包含于F，i=1，2，... 
Any set A \\(\in\\)F is called an **event**.
For any A \\in F the equality \\( P(\Omega  \ A) = 1 - P(A) \\) holds.

**Probability Measure on a Discrete Sample Space**
- Note a probability P :\\(\Omega \mapsto \\)  [0, 1] on a discrete sample space \\( \Omega \\)  uniquely specifies probabilities of all events \\( A_k = \\{\omega_k\\} \\).
- It is common to write P(fwk g) = P(wk ) = pk .
- The theorem shows that any probability on a discrete sample space W generates a unique probability measure on (W,F).  
!["FIG.4"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR6.png "FIG.4")  
- The proof of the theorem presents no di¢ culties, since W is assumed to be discrete.

**Example: Coin Flipping**
- Let X be the number of heads appearing when a fair coin is tossed twice. We choose the sample space W to be
W = f0, 1, 2g 
where a number k 2 W represents the number of times "head" has occurred.
- The probability measure P on W is dened as
P(k) =
1/4
, if k = 0, 2,
1/2
, otherwise.
- We recognise here the binomial distribution with n = 2 and p = 1/2. A single flip of a coin is a **Bernoulli trial**.

- We now suppose that the coin is not a fair one.
- Let the probability of "head"be p for some p 6= 1/2 .
Then the probability measure P is given by
P(k) =
8<
:
q2, if k = 0,
2pq, if k = 1,
p2, if k = 2,
- where q := 1-p is the probability of "tail" appearing.
- We deal here with the binomial distribution with n = 2 and 0 < p < 1.

## 2 Expectation of a Random Variable  
### 2.1 Expectation
!["FIG.5"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR9.png "FIG.5")

- Note that the expectation of a random variable can be seen as the weighted average.

- Since it is impossible to know the exact event in the future, expectation could help one to make decisions.
### 2.2 Expectation Operator
- Any random variable defined on a finite set W admits the expectation.
When the set W is countable (but infinite), we say that X is P-integrable whenever E_P (|X|) = åw2W jX(w)jP(w) < ¥. Then
the expectation EP (X) is well dened (and nite).
!["FIG.6"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR10.png "FIG.6")  

!["FIG.7"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR11.png "FIG.7")  

### 2.3 Expectation: Coin Flipping
- A fair coin is tossed three times. The player receives one dollar each time "head" appears and loses one dollar when "tail" occurs.
- Let the random variable X represent the player's payoff.
- The sample space W is dened as W = f0, 1, 2, 3g where k 2 W
represents the number of times head occurs.
- The probability measure is given by
P(k) =8<
:
18
, if k = 0, 3,
38
, if k = 1, 2.
- This is the binomial distribution with n = 3 and p = 1,2 .
- The random variable X is dened as
X(k) =
8>>< >>:
􀀀3, if k = 0,
􀀀1, if k = 1,
1, if k = 2,
3, if k = 3.
- Hence the players expected payo¤ equals
EP (X) =
3
= 0.
### 2.3 Expectation of a Function of a Random Variable
- Let X be a random variable and P be a probability measure on a discrete sample space W. We dene Y = f (X) where f : R ! R is an arbitrary function.
- Then Y is also a random variable on the sample space W endowed with the same probability measure P. Moreover,
EP(Y ) = EP(f (X)) = w2W f (X(w))P(w)
- If a random variable X is deterministic then EP(X) = X and EP(f (X)) = f (X).
## 3 Equivalence of Probability Measures  
&emsp;&emsp;概率测度测量
Let P and Q be two probability measures on a discrete sample space W.
!["FIG.8"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR15.png "FIG.8")   

The random variable L : W ! R+ given as
L(w) =
Q(w)
P(w)
is called the Radon-Nikodym density of Q with respect to P. Note that
EQ (X) = å
w2W
X(w)Q(w) = å
w2W
X(w)L(w)P(w) = EP (LX) .
### 3.1 Example: Equivalent Probability Measures
- The sample space W is defined as W = f1, 2, 3, 4g.
Let the two probability measures P and Q be given by

- It is clear that P and Q are equivalent, that is, P and Q. Moreover, the Radon-Nikodym density L of Q with respect to P can be represented as follows

- Check that for any random variable X: EQ (X) = EP (LX) .

### 3.2 Risky Investments
- When deciding whether to invest in a given portfolio, an agent may be concerned with the risk" of his investment.
!["FIG.9"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR17.png "FIG.9") 

## 4 Variance of a Random Variable  
&emsp;&emsp;随机变量的方差
### 4.1 Variance  
 !["FIG.10"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR18.png "FIG.10") 
- Variance is a measure of the spread of a random variable about its mean and also a measure of uncertainty.
- In financial applications, it is common to identify variance of the price of a security with its degree of "risk".
- Note that Var (X) = s2 \lt 0. It equals 0 if and only if X is deterministic.
### 4.2 Independence of a Random Variable

!["FIG.11"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR19.png "FIG.11")  
!["FIG.12"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR20.png "FIG.12")  

!["FIG.13"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR21.png "FIG.13")  
!["FIG.14"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR22.png "FIG.14") 

## 5 Continuous Random Variables  
!["FIG.15"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR23.png "FIG.15") 

Assume that X is a continuous random variable.
- Note that a probability density function need not satisfy the constraint f (x) \le 1.
A function F (x) is called a **continuous random variable*
(cdf) 
F (x) = P(X \le x) =

The relationship between the pdf f and cdf F
F (x) =

f (y )dy , f (x) =

The expectation and variance of a continuous random variable X are
defined as follows:
!["FIG.16"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR25.png "FIG.16")   

The properties of expectations of discrete random variables carry over to continuous random variables, with probability measures being replaced by pdfs and sums by integrals.

## 6 Examples of Probability Distributions  
&emsp;&emsp;概率测度的示例
### 6.1 Discrete Probability Distributions

!["FIG.17"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR26.png "FIG.17")  
!["FIG.18"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR27.png "FIG.18")  
!["FIG.19"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR28.png "FIG.19")   

### 6.2 Continuous Probability Distributions
!["FIG.20"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR29.png "FIG.20")   

!["FIG.21"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR30.png "FIG.21")  

!["FIG.22"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR31.png "FIG.22")  

!["FIG.23"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR32.png "FIG.23")  

### 6. LLN and CLT
!["FIG.24"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR33.png "FIG.24")  

## 7 Correlation of Random Variables  
&emsp;&emsp;随机变量的相关性
### 7.1 Covariance of Random Variables  
- In the real world, agents can invest in several securities and typically would like to benefit from diversification.
- The price of one security may a¤ect the prices of other assets. For example, the stock index falling may lead the price of gold to rise.
- To quantify this e¤ect, it is convenient to introduce the notion of covariance.

!["FIG.25"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR34.png "FIG.25")  

### 7.2 Correlated and Uncorrelated Random Variables
- The covariance of two random variables is a measure of the degree of variation of one variable with respect to the other. 
- Unlike the variance of a random variable, covariance of two random variables may take negative values. 
  - s12 > 0: An increase in one variable tends to coincide with an increase in the other.
  - s12 < 0: An increase in one variable tends to coincide with a decrease in the other.
  - s12 = 0: Then the random variables X1 and X2 are said to be uncorrelated. If s12 6= 0 then X1 and X2 are correlated.

!["FIG.26"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR35.png "FIG.26")  


### 7.3 Properties of the Covariance
!["FIG.27"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR36.png "FIG.27")  
### 7.4 Correlation Coefficient
- We can normalise the covariance measure. We obtain in this way the so-called correlation coe¢ cient.
- Note that the correlation coe¢ cient is only dened when s1 > 0 and s2 > 0, that is, none of the two random variables is deterministic.
!["FIG.28"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR37.png "FIG.28")  
### 7.5 Properties of Correlation Coe¢ cient
!["FIG.29"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR38.png "FIG.29")  
- r = 1: If one variable increases, the other will also increase.
- 0 < r < 1: If one increases, the other will tend to increase.
- -r = 0: The two random variables are uncorrelated.
- -1 < r < 0: If one increases, the other will tend to decrease.
- r = -1: If one increases, the other will decrease.
### 7.6 Linear Regression in Basic Statistics
- If we observe the time series of prices of two securities the following question arises: how are they related to each other?
- Consider two random variables X and Y on the sample space W = fw1,w2, . . . ,wng. Denote X(wi ) = xi and Y (wi ) = yi .
- A linear t is a relation of the following form, for a, b2 R,
yi = a + bxi + ei .
- The number ei is called the residual of the ith observation.
- In Statistics, the best linear t to observed data is obtained through the method of least-squares: minimise Sni
=1e2i. The line y = a + bx is called the least-squares linear regression.
- We denote by e the random variable such that e(wi ) = ei . This means that we set e := Y - a - bX.
### 7.7 Linear Regression in Probability Theory
- In Probability Theory, if a and b are chosen to minimise
EP
n􀀀
Y 􀀀 a 􀀀 bX
2
o
= EP
􀀀
e2
= Sni
=1e2(wi )P(wi )
then the random variable `Y jX := a + bX is called the linear regression of Y on X.
- The next result is valid for both discrete and continuous random variables.
!["FIG.30"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR40.png "FIG.30") 
### 7.8 Covariance Matrix
Recall that the covariance of random variables Xi and Xj equals
Cov (Xi ,Xj ) = sij := EP
n
(Xi 􀀀 μi )

Xj 􀀀 μj
o
where μi = EP (Xi ) and μj = EP (Xj ).
!["FIG.31"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR41.png "FIG.31") 
!["FIG.32"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR42.png "FIG.32") 

### 7.9 Linear Combinations of Random Variables
!["FIG.33"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR43.png "FIG.33") 

## 8 Conditional Distributions and Expectations
&emsp;&emsp;条件分布和期望  

For two random variables X1 and X2 and an arbitrary set A such that
P(X2 2 A) 6= 0, we dene the conditional probability
P(X1 2 A1 j X2 2 A2) :=
P(X1 2 A1,X2 2 A2)
P(X2 2 A2)
and the conditional expectation
EP(X1 j X2 2 A) :=
EP(X11fX22Ag)
P(X2 2 A)
where 1fX22Ag : W ! f0, 1g is the indicator function of fX2 2 Ag, that
is,
1fX22Ag(w) =

1, if X2(w) 2 A,
0, otherwise.
### 8.1 Discrete Case
- Assume that X and Y are discrete random variables
pi = P(X = xi ) > 0 for i = 1, 2, . . . and
¥å
i=1
pi = 1,
bpj = P(Y = yj ) > 0 for j = 1, 2, . . . and
¥å
j=1
bpj = 1.
!["FIG.34"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR45.png "FIG.34") 

- It is easy to check that
pi = P(X = xi ) = å¥
j=1 P(X = xi j Y = yj )P(Y = yj )
= å¥
j=1 pX jY (xi j yj ) bpj .
- The expected value EP(X) satises
EP(X) =
¥å
j=1
EP(X j Y = yj )P(Y = yj ).
!["FIG.35"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR46.png "FIG.35") 

### 8.2 Continuous Case
- Assume that the continuous random variables X and Y have the joint pdf fX ,Y (x, y ).
!["FIG.36"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR47.png "FIG.36") 

!["FIG.37"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR48.png "FIG.37") 

- An important property of conditional expectation is that
EP(Y ) = EP(EP(Y j X)) =
Z ¥
􀀀¥
EP(Y j X = x)fX (x) dx.
- Hence the expected value EP(Y ) can be determined by rst conditioning on X (in order to compute EP(Y jX)) and then integrating with respect to the pdf of X.
<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>