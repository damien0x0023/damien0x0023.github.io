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
- 对于任一序列Ai 真包含于F，i=1，2，... \\(A_i \cap A_j =\emptyset\\)

Any set A \\(\in\\) F is called an **event**.  
任何一组A \\(\in\\) F都成为事件。  

For any A \\(\in\\) F the equality \\( P(\Omega \setminus A) = 1 - P(A) \\) holds.  
任何A \\(\in\\) F等式\\( P(\Omega \setminus A) = 1 - P(A) \\)成立。  

### 1.4 Probability Measure on a Discrete Sample Space  
1.4 离散样本空间上的概率测度

- Note a probability P :\\(\Omega \mapsto \\)  [0, 1] on a discrete sample space \\( \Omega \\)  uniquely specifies probabilities of all events \\( A_k = \\{\omega_k\\} \\).  
注意，离散样本空间\\( \Omega \\)上的概率P :\\(\Omega \mapsto \\)[0，1]唯一地指定了所有事件的概率\\( A_k = \\{\omega_k\\} \\).

- It is common to write as  
&emsp;&emsp;通常写作:

$$
  P( \lbrace \omega _k \rbrace ) = P(\omega _k)=p _k
$$

- The theorem shows that any probability on a discrete sample space \\( \Omega \\) generates a unique probability measure on (\\( \Omega,F\\).  
该定理表明，离散样本空间\\(\Omega\\)上的任何概率在 \\(\Omega,F\\)上产生唯一的概率测度。  !["FIG.4"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR6.png "FIG.4")  

- The proof of the theorem presents no difficulties, since \\( \Omega \\) is assumed to be discrete.  
由于\\(\Omega\\)被假定为离散的，定理的证明没有什么困难。

### 1.5 Example: Coin Flipping 

- Let X be the number of "heads" appearing when a **fair** coin is tossed twice. We choose the sample space \\( \Omega \\) to be  
让X是一枚**公平**的硬币,被抛两次时出现的“头”数。我们选择样本空间\\( \Omega \\) 作为

$$
   \Omega = \\{ 0, 1, 2 \\}
$$

where a number \\(k \in \Omega \\) represents the number of times "head" has occurred.  
其中数字\\(k \in \Omega \\)表示“头”出现的次数。

- The probability measure P on \\( \Omega \\) is defined as  
\\( \Omega \\)上的概率测度 P 定义为

$$
  P(k)= \left
  \lbrace \begin{array}{l} 
  \frac {1} {4},\ \text{if}\ k = 0,2,
  \\\\ \frac {1} {2},\ otherwise.
  \end{array} \right.
$$

- We recognise here the binomial distribution with n = 2 and p = 1/2. A single flip of a coin is a **Bernoulli trial**. 
我们在这里认识到n=2且p=1/2的二项分布。一枚硬币的一次抛投就是伯努利实验。
- We now suppose that the coin is not a fair one.  
我们现在认为这枚硬币不公平。
- Let the probability of "head"be p for some \\(p \ne 1/2\\) .  
让“头”的概率为P
Then the probability measure P is given by  
然后概率测度P由下式给出

$$
 P(k)=  \begin{cases}
  q^2, &\text{if}\ k = 0,
  \\\\ 2pq, &\text{if}\ k = 1,
  \\\\ p^2, &\text{if}\ k = 2.
  \end{cases}
$$
- where q := 1-p is the probability of "tail" appearing.  
其中q:=1-p是出现“尾”的概率.
- We deal here with the binomial distribution with n = 2 and 0 < p < 1.  
这里我们讨论的是n=2，0<p<1的二项分布.

## 2 Expectation of a Random Variable  
### 2.1 Expectation
!["FIG.5"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR9.png "FIG.5")  
定义（期望）  
设X是离散样本空间\\( \Omega \\)上的随机变量，赋以概率测度P。X的期望值（期望值或平均值）定义为  

\\(E_p\\)称为概率P上的期望算子。
- Note that the expectation of a random variable can be seen as the weighted average.  
注意，随机变量的期望值可以看作加权平均值。
- Since it is impossible to know the exact event in the future, expectation could help one to make decisions.  
由于不可能知道未来的确切事件，期望可以帮助人们做出决定。

### 2.2 Expectation Operator  
期望算子
- Any random variable defined on a finite set \\( \Omega \\) admits the expectation.  
在有限集\\( \Omega \\)上定义的任何随机变量都有期望值。  
When the set\\( \Omega \\) is countable (but infinite), we say that X is **P-integrable** whenever \\(E_P (|X|) = \sum _{\omega\in\Omega} |X(\omega)|P(\omega) <\infty\\).Then the expectation \\(E_p (X) \\)is well defined (and finite).  
当集合\\( \Omega \\)可数（但无限）时，我们说X是**p-可积（加）的**当\\(E_P (|X|) = \sum _{\omega\in\Omega} |X(\omega)|P(\omega) <\infty\\)时，期望 \\(E_p (X) \\)被明确定义的（并且是有限的）。
!["FIG.6"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR10.png "FIG.6")   
设X和Y是两个P-可积随机变量，P是离散样本空间\\( \Omega \\)上的概率测度，那么对于所有  
因此概率空间的期望（定义域取值为实数）是P-可积空间X上的线性算子。  
!["FIG.7"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR11.png "FIG.7")  
期望算子的证明：  
因此随机变量aX+bY属于X。  
期望的线性可以很容易地从定义中推导出来：  
其中\\(\alpha\\)和\\(\beta\\)是任意实数。
### 2.3 Expectation: Coin Flipping
- A fair coin is tossed three times. The player receives one dollar each time "head" appears and loses one dollar when "tail" occurs.  
一枚硬币掷三次。玩家每次出现“头”时得到一美元，出现“尾”时损失一美元。
- Let the random variable X represent the player's payoff.  
让随机变量X代表玩家的收益。
- The sample space \\( \Omega \\) is dened as\\( \\{\Omega=0,1,2,3 \\}\\) where \\(k \in \Omega \\) represents the number of times "head" occurs.  
样本空间\\( \Omega \\)被定义为\\( \\{\Omega=0,1,2,3 \\}\\)，其中\\(k \in \Omega \\)表示“head”出现的次数。
- The probability measure is given by  
概率测度由下式给出

$$
 P(k)=  \begin{cases}
  \frac {1} {8}, &\text{if}\ k = 0,3,
  \\\\ \frac {3} {8}, &\text{if}\ k = 1,2.
  \end{cases}
$$

- This is the binomial distribution with n = 3 and p = 1\2 .  
这是二项分布，n=3，p=1\2。
- The random variable X is defined as  
随机变量X定义为
$$
 X(k)=  \begin{cases}
  -3, &\text{if}\ k = 0,
  \\\\ -1, &\text{if}\ k = 1,
  \\\\ 1, &\text{if}\ k = 2,
  \\\\ 3,&\text{if}\ k = 3.
  \end{cases}
$$

- Hence the player's expected payoff equals  
因此，玩家的预期收益等于
$$ 
E_P(X)=\sum_{k=0}^3 X(k)P(k)
$$
$$
=\frac {-3} {8}+(\frac {-3} {8})+\frac {3} {8}+\frac {3} {8}
= 0.
$$
### 2.4 Expectation of a Function of a Random Variable  
随机变量函数的期望
- Let X be a random variable and P be a probability measure on a discrete sample space \\( \Omega \\). We define Y = f (X) where \\(f : R \to R\\) is an arbitrary function.  
设X是一个随机变量，P是离散样本空间\\( \Omega \\)上的概率测度。我们定义Y=f（X），其中\\(f : R \to R\\)是一个任意函数。
- Then Y is also a random variable on the sample space \\( \Omega \\) endowed with the same probability measure P. Moreover,    
那么Y也是样本空间\\( \Omega \\)上具有相同概率测度P的随机变量。此外，
$$
E_p(Y) = E_p(f(X)) = \sum_{\omega \in \Omega}f(X(w))P(w).
$$
- If a random variable X is deterministic then \\(E_p(X) = X\\)and \\(E_p\(f(X)) = f (X)\\).  
如果一个随机变量X是确定性的，那么

## 3 Equivalence of Probability Measures  
&emsp;&emsp;概率测度的等价性  
Let P and Q be two probability measures on a discrete sample space \\( \Omega \\).  
设P和Q是离散样本空间\\( \Omega \\)上的两个概率测度。
!["FIG.8"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR15.png "FIG.8")   
定义（概率测度的等价性）  
我们说概率测度P和Q是等价的,我们记作P趋近于Q，无论何时所有的\\(\omega\in \Omega\\).

The random variable L : \\( \Omega \mapsto R_+\\)given as   
随机变量L的定义域\\(\Omega\\)的取值范围为正实数，表示为
$$
L(w) =
\frac {Q(\omega)} {P(\omega)}
$$
is called the **Radon-Nikodym** density of Q with respect to P. Note that  
这称为Q相对于P.的拉东-尼科迪姆定理。记作
$$
E_Q (X) = \sum_{\omega \in \Omega} X(\omega) Q(\omega)= \sum_{\omega \in \Omega} X(\omega) L(\omega) P(\omega) = E_P (LX)
$$
### 3.1 Example: Equivalent Probability Measures  
例子：等效概率度量
- The sample space \\( \Omega \\) is defined as \\( \Omega = \\{1, 2, 3, 4\\}\\)  
样本空间\\( \Omega \\)定义为\\( \Omega = \\{1, 2, 3, 4\\}\\)
- Let the two probability measures P and Q be given by  
设两个概率测度P和Q为
$$
(\frac {1}{8},\frac {3}{8},\frac {2}{8},\frac {2}{8}) \ and\ (\frac {4}{8},\frac {1}{8},\frac {2}{8},\frac {1}{8})
$$
- It is clear that P and Q are equivalent, that is, P and Q.   
很明显，P和Q是等价的，即P趋近于Q。
- Moreover, the Radon-Nikodym density L of Q with respect to P can be represented as follows  
此外，Q相对于P.的拉东-尼科迪姆L可以表示为
$$
(4,\frac {1}{3},1,\frac {1}{2})
$$
- Check that for any random variable \\(X: E_Q (X) = E_p (LX)\\) .  
检查任意随机变量

### 3.2 Risky Investments  
风险投资
- When deciding whether to invest in a given portfolio, an agent may be concerned with the "risk" of his investment.  
在决定是否投资某一特定投资组合时，代理人可能会考虑其投资的“风险”。
!["FIG.9"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR17.png "FIG.9")   
考虑一位投资者，他有机会在以下两种选择中进行选择：  
投资者得到或损失1000美元的概率相等。这个随机收益用\\(X_1\\)表示。 
投资者收到或损失1000000美元的概率相等。我们把这个随机收益表示为\\(X_2\\).  
因此，在这两种情况下，预期收益值等于\\(E_p（X_1）=E_p（X_2）=0\\)。  
下面的问题出现了：哪个选项更好？


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
- Consider two random variables X and Y on the sample space \\( \Omega \\) = fw1,w2, . . . ,wng. Denote X(wi ) = xi and Y (wi ) = yi .
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
where 1fX22Ag : \\( \Omega \\) ! f0, 1g is the indicator function of fX2 2 Ag, that
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