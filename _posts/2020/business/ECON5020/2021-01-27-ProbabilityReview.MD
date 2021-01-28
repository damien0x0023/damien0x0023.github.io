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
The set \\( 2^\Omega \\) is called the **power set** of \\( \Omega \\).
Note that the **empty set** \\emptyset also belongs to any power set.

!["FIG.3"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/PR5.png "FIG.3")

Any set A 2 F is called an event.
For any A 2 F the equality P(W n A) = 1 􀀀 P(A) holds.
**Probability Measure on a Discrete Sample Space**


**Example: Coin Flipping**



## 2 Expectation of a Random Variable  

- Note that the expectation of a random variable can be seen as the weighted average.

- Since it is impossible to know the exact event in the future,
expectation could help one to make decisions.




## 3 Equivalence of Probability Measures  
&emsp;&emsp;概率测度测量
## 4 Variance of a Random Variable  
&emsp;&emsp;随机变量的方差
## 5 Continuous Random Variables  
## 6 Examples of Probability Distributions  
&emsp;&emsp;概率测度的示例
## 7 Correlation of Random Variables  
&emsp;&emsp;随机变量的相关性
## 8 Conditional Distributions and Expectations
&emsp;&emsp;条件分布和期望



<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>