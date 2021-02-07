---
layout: post
title: Mathematical Finance - Unit 3 Single Period Market Model
subtitle: 金融数学（三）单期市场模型
category: money
tags: [ECON5020]
---

# Unit 3 Single Period Market Model
Uploaded by eva 

## General Single-Period Market Model
- The main di¤erences between the elementary and general single-period market models are:  

 - The investor is allowed to invest in several risky securities instead of only one.  

 - The sample set is bigger, that is, there are more possible states of the world at time t = 1.  

- The sample space is \\(\Omega = \\{\omega_1,\omega_2, . . . ,\omega_k\\}\\) with \\(F = 2^{\Omega}\\).  

- An investor's personal beliefs about the future behaviour of stock prices are represented by the probability measure \\(P( \omega_i ) = p_i > 0 \\) for i = 1, 2, . . . , k.  

- The savings account B equals \\(B_0 = 1\\) and \\(B_1 = 1 + r\\) for some constant r > -1.  

- The price of the jth stock at t = 1 is a random variable on \\(\Omega\\). It is denoted by \\(S_t^{j}\\) t for t = 0, 1 and j = 1, . . . , n.  

- A contingent claim \\(X = (X(\omega_1), . . . ,X(\omega_k)\\)) is a random variable on the probability space \\((\Omega,F,P)\\).  

Questions
1.Under which conditions a general single-period market model \\(M= (B, S^1, . . . , S^n)\\) is arbitrage-free?  

2.How to define a risk-neutral probability measure for a model?  

3.How to use a risk-neutral probability measure to analyse a general single-period market model?  

4.Under which conditions a general single-period market model is complete?  

5.Is completeness of a market model related to risk-neutral probability measures?  

6 How to define an arbitrage price of an attainable claim?  

7 Can we still apply the risk-neutral valuation formula to compute the
price of an attainable claim?  

8 How to deal with contingent claims that are not attainable?  

9 How to use the class of risk-neutral probability measures to value non-attainable claims?  

Outline
We will examine the following issues:  

## 1 Trading Strategies and Arbitrage-Free Models  

!["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP1.png "FIG.1")  

If an investor adopts the trading strategy \\((x, \phi^1, . . . , \phi^n) \\)at time t= 0 then the cash value of his portfolio at time t = 1 equals  

$$
V_1(x, \phi^1, . . . , \phi^n) :=(x-\Sigma_{j=1}^{n} \phi^j S_{0}^j)(1+r)+\Sigma_{j=1}^{n} \phi^j S_{1}^j
$$  

### 1.1 Wealth Process of a Trading Strategy  

!["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP2.png "FIG.2")  

### 1.2 Gains (Profits and Losses) Process
- Obviously, the proits or losses an investor obtains from the investment can be calculated by subtracting \\(V_0(\cdot) \\)from \\(V_1(\cdot)\\).This is called the (undiscounted) gains process.  

- The 'gain' can be negative; hence it may also represent a loss.  

!["FIG.3"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP3.png "FIG.3")   

### 1.3 Discounted Stock Price and Wealth Process  
- To understand whether the jth stock appreciates in real terms, we consider the **discounted stock prices** of the jth stock  

$$  
\hat S_{0}^j :=  S_{0}^j =\frac {S_{0}^j}{B_0}, \hat S_{1}^j :=\frac {S_{1}^j}{1+r} =\frac {S_{1}^j}{B_1}
$$  

- Similarly, we define the **discounted wealth process** as 
$$  
\hat V_0(x,\phi^1,...,\phi^n) := x,\hat V_1 (x,\phi^1,...,\phi^n) :=\frac {V_1 (x,\phi^1,...,\phi^n)}{B_1}
$$

- It is easy to see that  

$$  
\hat V_1(x,\phi^1,...,\phi^n)=(x-\Sigma_{j=1}^{n} \phi^j \hat S_1^j )
=x+\Sigma_{j=1}^{n} \phi^j (\hat S_1^j-\hat S_0^j)
$$  

### 1.4 Discounted Gains Process  

!["FIG.4"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP4.png "FIG.4")  

### 1.5 Arbitrage: Definition  

The concept of an arbitrage in a general single-period market model is essentially the same as in the elementary market model. It is worth noting that P can be replaced here by any equivalent probability measure Q.  

!["FIG.5"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP5.png "FIG.5")  

### 1.6 Arbitrage: Equivalent Conditions  

The following condition is equivalent to A.3.   

- A.3'. There exists w 2 W such that V1(x, f1, . . . , fn)(w) > 0.  
The definition of arbitrage can be formulated using the discounted value and gains processes. This is sometimes very helpful.  

!["FIG.6"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP6.png "FIG.6")  

!["FIG.7"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP7.png "FIG.7")  

!["FIG.8"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP8.png "FIG.8")   


### 1.7 Verification of the Arbitrage-Free Property
- It can be sometimes hard to check directly whether arbitrage opportunities exist in a given market model, especially when dealing
with several risky assets or in the multi-period setup.  

- We have introduced the risk-neutral probability measure in the elementary market model and we noticed that it can be used to compute the arbitrage price of any contingent claim.  

- We will show that the concept of a risk-neutral probability measure is also a convenient tool for checking whether a general single-period market model is arbitrage-free or not.  

- In addition, we will argue that a risk-neutral probability measure can also be used for the purpose of valuation of a contingent claim (either attainable or not).   

### 1.8 Risk-Neutral Probability Measure  

!["FIG.9"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP9.png "FIG.9")  

- Condition R.1 means that Q and P are equivalent probability measures. A risk-neutral probability measure is also known as an **equivalent martingale measure**.
- Note that condition R.2 is equivalent to \\(E_Q (\hat S_1^j)= \hat S_0^j\\)or, more explicitly,  

$$  
E_Q (S_1^j)= (1+r) S_0^j
$$  

for j=1,2,...,n.  

### 1.9 Example
#### Example 4.1: Stock Prices
- We consider the following model featuring two stocks \\(S^1\\) and \\(S^2\\) on the sample space \\(\Omega) = \\{\omega_1,\omega_2,\omega_3\\}\\).  

- The interest rate \\(r = \frac{1}{10}\\) so that \\(B_0 = 1 \\) and \\(B_1 = 1 + \frac{1}{10} \\).  

- We deal here with the market model \\(M= (B, S^1, S^2)\\).  

- The stock prices at t = 0 are given by \\(S_0^1 = 2 \\)and \\(S_0^2 = 3\\).  

- The stock prices at t = 1 are represented in the table:   
 
|  |\\(\omega_1\\)|\\(\omega_2\\)|\\(\omega_3\\)|  
:---|--------|--------|--------|  
|\\(S_1^1\\)  |1|5|3|  
|\\(S_1^2\\)  |3|1|6|    
 
#### Example 4.1: Wealth Process  

- For any trading strategy \\((x, \phi^1, \phi^2) \in R^3\\), we have  

!["FIG.10"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP10.png "FIG.10")   

#### Example 4.1: Gains Process  

!["FIG.11"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP11.png "FIG.11")  

#### Example 4.1: Discounted Stock Prices  

- Out next goal is to compute the discounted wealth process bV (x, f1, f2) and the discounted gains process bG1(x, f1, f2).
- To this end, we first compute the discounted stock prices. 
- Of course, \\(\hat S_0^j = S_0^j \\) for j = 1, 2.
- The following table represents the discounted stock prices \\(\hat S_1^j\\) for j = 1, 2 at time t = 1   

||\\(\omega_1\\)|\\(\omega_2\\)|\\(\omega_3\\)|  
:---|--------|--------|--------|  
|\\(S_1^1\\)|\\(\frac {10}{11}\\)|\\(\frac {50}{11}\\)|\\(\frac {30}{11}\\)|  
|\\(S_1^2\\)|\\(\frac {30}{11}\\)|\\(\frac {10}{11}\\)|\\(\frac {60}{11}\\)|  

#### Example 4.1: Discounted Wealth Process  
The discounted wealth process \\(\hat V (x, \phi^1, \phi^2)\\) is thus given by  
$$  
\hat V_0(x, \phi^1, \phi^2) = V_0(x, \phi^1, \phi^2) = x
$$  

and   

$$  
\hat V_1(x, \phi^1, \phi^2)(\omega_1) = \phi^0+ \frac{10}{11} \phi^1+\frac{30}{11}  \phi^2 
$$  
$$  
\hat V_1(x, \phi^1, \phi^2)(\omega_2) = \phi^0+ \frac{50}{11} \phi^1+\frac{10}{11}  \phi^2 
$$   
$$  
\hat V_1(x, \phi^1, \phi^2)(\omega_3) = \phi^0+ \frac{30}{11} \phi^1+\frac{60}{11}  \phi^2 
$$   

where \\(\phi^0 = x - 2\phi^1 - 3\phi^2\\) is the amount of cash invested in B at time 0(as opposed to the initial wealth given by x).  

#### Example 4.1: Discounted Gains Process  

- The increments of the discounted stock prices equal  
!["FIG.12"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP12.png "FIG.12")  

#### Example 4.1: Arbitrage-Free Property
- The condition \\(\hat G_1(x, \phi^1, \phi^2) \ge 0\\) is equivalent to 
$$
-12\phi^1 - 3\phi^2 \ge 0  
$$  
$$
28\phi^1 - 23\phi^2 \ge 0  
$$
$$
8\phi^1 + 27\phi^2 \ge 0  
$$  

-Can we find \\((\phi^1, \phi^2) \in R^2\\) such that all inequalities are valid and at least one of them is strict?
- It appears that the answer is negative, since the unique vector satisfying all inequalities above is \\((\phi^1, \phi^2) = (0, 0)\\).
- Therefore, the single-period market model \\(M= (B, S^1, S^2)\\) is arbitrage-free.  

#### Example 4.1: Risk-Neutral Probability Measure
- We will now show that this market model admits a unique risk-neutral probability measure on \\(\Omega) = \\{\omega_1,\omega_2,\omega_3\\}\\).
- Let us denote \\(Q(\omega_i ) = q_i\\) for i = 1, 2, 3. From the definition of a risk-neutral probability measure, we obtain the following
linear system  

!["FIG.13"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP13.png "FIG.13")   


- The unique solution equals \\(Q = (q_1, q_2, q_3) = (\frac{47}{80},\frac{15}{80},\frac{18}{80})\\)  



## 2 Fundamental Theorem of Asset Pricing  

### 2.1 Fundamental Theorem of Asset Pricing (FTAP)   
- In Example 4.1, we have checked directly that the market model
\\(M= (B, S^1, S^2)\\) is arbitrage-free.
- In addition, we have shown that the unique risk-neutral probability measure exists in this model.
- Is there any relation between no arbitrage property of a market model and the existence of a risk-neutral probability measure?  

- The following important result, known as the FTAP, gives a complete answer to this question within the present setup.
- The FTAP was first established by Harrison and Pliska (1981) and it was later extended to continuous-time market models.  

!["FIG.14"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP14.png "FIG.14")   

!["FIG.15"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP15.png "FIG.15")  

#### Example 4.1: Arbitrage-Free Market Model  
- We consider the market model \\(M= (B, S^1, S^2) \\)introduced in Example 4.1.
- The interest rate \\(r = \frac{1}{10}\\) so that \\(B_0 = 1\\) and \\(B_1 = 1 + \frac {1}{10}\\).  
- The stock prices at t = 0 are given by \\(S_0^1 = 2\\) and \\(S_0^2= 3\\).
- We have shown that the increments of the discounted stock prices \\(\hat S^1\\) and \\(\hat S^2\\) equal  

!["FIG.16"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP16.png "FIG.16")  

- How to find RNP measure?  

!["FIG.17"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP17.png "FIG.17")   

- The gain expressions  
!["FIG.18"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP18.png "FIG.18")  

determines a hyperplane in \\(R^3: \phi^1 Z_1 + \phi^2 Z_2, \phi^1, \phi^2 \in R \\)
- So, vector \\(q : \langle q,Z_j \rangle = 0 \\)must be orthogonal to the hyperplane. 
- And \\(\Sigma_i^K q_i =1, q_i \gt 0\\)  
- If such vector exists then it defines RNP measure. 
- For our example there is the unique risk-neutral probability measure.
- The FTAP confirms that the market model is arbitrage-free.  

- We consider the following model featuring two stocks \\(S^1\\) and \\(S^2\\) on the sample space \\(\Omega = \\{\omega_1,\omega_2,\omega_3\\}\\).
- The interest rate \\(r = \frac{1}{10} \\)so that \\(B_0 = 1 \\)and \\(B_1 = 1 + \frac {1}{10} \\).
- The stock prices at t = 0 are given by \\(S_0^1 = 1\\) and \\(S_0^2 = 2\\) and the stock prices at t = 1 are represented in the table:  

!["FIG.19"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP19.png "FIG.19")  

- Does this market model admit an arbitrage opportunity?  
- The increments of discounted stock prices are represented in the following table  
!["FIG.20"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP20.png "FIG.20")  

- To tell whether a model is arbitrage-free it su¢ ces to know the increments of discounted stock prices.









\\(\Omega = \\{\omega_1,\omega_2,\omega_3\\}\\)
























2 Fundamental Theorem of Asset Pricing
3 Examples of Market Models
4 Risk-Neutral Valuation of Contingent Claims
5 Completeness of Market Models







<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>  






