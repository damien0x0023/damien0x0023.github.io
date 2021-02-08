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

## 3 Examples of Market Models  
### Example 4.1: Arbitrage-Free Market Model  
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

- Recall that  
$$  
\hat G_1(x,\phi^1,\phi^2) = \phi^1 \Delta \hat S_1^1 + \phi^2 \Delta \hat S_1^2
$$  

- Hence, the equation for hyperplane  

!["FIG.21"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP21.png "FIG.21")  

- Let us take \\(\phi^1 = 3 \\) and \\(\phi^2 = 1\\). Then we obtain the vector\\((0, 0, 39)^T\\) , which means we have an arbitrage opportunity.  

- Still, we can solve the system for the 'orthogonal vector':  

- but must have \\(Q(omega) > 0 \\) for all \\(\omega \in \Omega\\).
- Hence the FTAP confirms that the market model is not arbitrage-free.    


## 4 Risk-Neutral Valuation of Contingent Claims  

### 4.1 Contingent Claims  

- Since we now know how to check whether a given model is arbitrage-free, the following question arises:
- What should be the 'fair' price of a European call or put option in a general single-period market model?
- In a general single-period market model, the idea of pricing European options can be extended to any contingent claim.  

!["FIG.22"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP22.png "FIG.22")  

- Derivatives nowadays are usually quite complicated and thus it makes sense to analyse valuation and hedging of a general contingent claim, and not only European call and put options.

### 4.2 No-Arbitrage Principle  

!["FIG.23"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP23.png "FIG.23")  

#### Example 4.3: Stochastic Volatility Model
- In the elementary market model, a replicating strategy for any contingent claim always exists. However, in a general single-period market model, a replicating strategy may fail to exist for some claims.
- For instance, when there are more sources of randomness than there are stocks available for investment then replicating strategies do not exist for some claims.
- Consider a market model consisting of bond B, stock S, and a random variable v called the **volatility**.
- The volatility determines whether the stock price can make either a big or a small jump.
- This is a simple example of a **stochastic volatility model**.  
- The sample space is given by  
$$
\Omega = \\{\omega_1,\omega_2,\omega_3,\omega_4\\}
$$
and the volatility is defined as  

$$
  v (\omega_i)= \left
  \lbrace \begin{array}{l} 
  h,\text{for}\ i = 1,4,
  \\\\ l,\text{for}\ i = 2,3.
  \end{array} \right.
$$  

- We furthermore assume that \\(0 <  < h < 1\\). The stock price \\(S_1\\) is given by  

$$
  S_1 (\omega_i)= \left
  \lbrace \begin{array}{l} 
  (1+v(\omega_i)S_0),\text{for}\ i = 1,2,
  \\\\ (1-v(\omega_i)S_0),\text{for}\ i = 3,4.
  \end{array} \right.
$$

- Unlike in examples we considered earlier, the amount by which the stock price in this market model jumps is random.
- It is easy to check that the model is arbitrage-free whenever \\(1 - h < 1 + r < 1 + h\\).
- We claim that for some contingent claims a replicating strategy does not exist. In that case, we say that a claim is not **attainable**.
- To justify this claim, we consider the **digital call option** X with the payoff  

$$
  X= \left
  \lbrace \begin{array}{l} 
  1 \ \text{if}\ S_1 \gt K,
  \\\\ 0 \ otherwise.
  \end{array} \right.
$$  

where K > 0 is the strike price.  

- We assume that \\((1 + l )S_0 < K < (1 + h)S_0\\), so that  
$$  
(1 - h)S_0 < (1 - l )S_0 < (1 + l )S_0 < K < (1 + h)S_0
$$
and thus  
$$
  X(\omega_i)= \left
  \lbrace \begin{array}{l} 
  1 \ \text{for}\ i=1,
  \\\\ 0 \ otherwise.
  \end{array} \right.
$$  

Suppose that \\((x, \phi) \\)is a replicating strategy for X. Equality\\(V_1(x, \phi) = X\\) becomes  

!["FIG.24"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP24.png "FIG.24")  

- two unknowns, four equations  

!["FIG.24"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP24.png "FIG.24") 

- It is easy to see that the above system of equations has no solution and thus a digital call is not an attainable contingent claim within the framework of the stochastic volatility model.
- The heuristic explanation is that the randomness generated by the volatility cannot be replicated, we do not have anough traded assets to replicate volatility, since the volatility itself is not a traded asset in this model.  

### 4.3 Valuation of Attainable Contingent Claim  

We first recall the definition of attainability of a contingent claim. 

!["FIG.25"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP25.png "FIG.25")  

Let us summarise the known properties of attainable claims:
- It is clear how to price attainable contingent claims by the replicating principle.
- There might be more than one replicating strategy, but no arbitrage principle leads the initial wealth x (and therefore, price) to be unique.
- In the two-state single-period market model, one can use the risk-neutral probability measure to price contingent claims.  


### 4.4 Risk-Neutral Valuation Formula  

Our next goal is to extend the **risk-neutral valuation formula** to any attainable contingent claim within the framework of a general single-period market model.  

!["FIG.26"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP26.png "FIG.26")   

!["FIG.27"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP27.png "FIG.27")  


#### Example 4.3: Stochastic Volatility Model  

- Proposition 4.2 shows that risk-neutral probability measures can be used to price attainable contingent claims.
- Consider the market model introduced in Example 4.3 with the interest rate r = 0.
- Recall that in this case the model is arbitrage-free since \\(1 - h < 1 + r = 1 < 1 + h\\).
- The increments of the discounted stock price bS are represented in the following table  

!["FIG.28"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP28.png "FIG.28")  

- The equation for 'hyperplane'  

!["FIG.29"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP29.png "FIG.29")  

so it is not a hyperplane which must be the plane of maximim dimension.
- The orthogonal complement of W is thus the three-dimensional subspace of \\(R^4\\) given by  

!["FIG.30"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP30.png "FIG.30")   

- Recall that a vector \\((q_1, q_2, q_3, q_4)^T \\)must satisfy \\(\Sigma_{i=1}^4\\)=1 holds and \\(q_i > 0 \\) for i = 1, 2, 3, 4.
- Specifically,  

!["FIG.31"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP31.png "FIG.31")  

- The class M of all risk-neutral probability measures in our stochastic volatility model is therefore given by  

!["FIG.32"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP32.png "FIG.32")

- This set appears to be non-empty and thus we conclude that our stochastic volatility model is arbitrage-free.
- Recall that we have already shown that the digital call option is not attainable if  
$$  
(1+l)S_0 \lt K \lt (1+h)S_0  
$$ 

- It is not di¢ cult to check that for every \\(0 < q_1 < \frac{1}{2}\\) there exists a probability measure \\(Q \in M\\) such that Q(w1) = q1.
- Indeed, it su¢ ces to take \\(q_1 \in (0, \frac{1}{2})\\) and to set  
$$  
q_4 = q_1, q_2 = q_3 = \frac{1}{2} - q_1
$$  

- We apply the risk-neutral valuation formula to the digital call \\(X = (1, 0, 0, 0)^T\\). For \\(Q = (q_1, q_2, q_3, q_4)^T \in M \\), we obtain

$$  
E_Q(X) = q_1 \cdot 1 + q_2 \cdot 0 + q_3 \cdot 0 + q_4 \cdot 0 = q_1.  
$$  
- Since q_1 is any number from (0, 12), we see that every value from the open interval \\((0, \frac{1}{2})\\) can be achieved.  

### 4.5 Extended Market Model and No-Arbitrage Principle  

We no longer assume that a contingent claim X is attainable.  

!["FIG.33"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP33.png "FIG.33")  

- The interpretation of Definition 4.1 is as follows:  
- We assume that the market model \\(M= (B, S^1, . . . , S^n)\\) is arbitrage-free.
- We regard the additional asset as a tradable risky asset in the extended market model \\(\widetilde M= (B, S^1, . . . , S^{n+1})\\).  
- We postulate its price at time 0 should be selected in such a way that the extended market model \\(\widetilde M \\) is still arbitrage-free.  

### 4.6 Valuation of Non-Attainable Claims  

- We already know that the risk-neutral valuation formula returns the arbitrage price for any attainable claim.
- The next result shows that it also yields a price consistent with the no-arbitrage principle when it is applied to any non-attainable claim.
- The price obtained in this way is not unique, however.  

!["FIG.34"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP34.png "FIG.34")  

!["FIG.35"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP35.png "FIG.35")  


## 5 Completeness of Market Models  

### 5.1 Models of Complete and Incomplete Markets   

We categorise market models into two classes: **complete** and **incomplete** market models.  

!["FIG.36"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP36.png "FIG.36")  

- Given an arbitrage-free and complete markets, the issue of pricing contingent claims is completed solved.
- How can we recognize whether a given market is complete?  

### 5.2 Algebraic Criterion for Market Completeness  

!["FIG.37"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP37.png "FIG.37")  

!["FIG.38"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP38.png "FIG.38")  

#### Example 4.3: Incomplete Market  

- Consider the stochastic volatility model from Example 4.3.
- We already know that this market is incomplete, since the digital call is not an attainable claim.
- The matrix A is given by  

!["FIG.39"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP39.png "FIG.39")  

- The rank of A is 2, and thus it is not equal to k = 4.
- In view of Proposition 4.4, this confirms that this market model is incomplete.  

### 5.3 Probabilistic Criterion for Attainability
- Proposition 4.4 yields a method for determining whether a market model is complete.
- Given an incomplete model, how to recognize an attainable contingent claim?
- Recall that if a model M is arbitrage-free then the class \\(\mathbb{M}\\) is non-empty.  

!["FIG.40"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP40.png "FIG.40")  

### 5.4 Probabilistic Criterion for Market Completeness  

!["FIG.41"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP41.png "FIG.41")  


!["FIG.42"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP42.png "FIG.42")  

## 6 Summary
Let us summarise the properties of single-period market models:
- A single-period market model is arbitrage-free if and only if it admits at least one risk-neutral probability measure.  

- An arbitrage-free single-period market model is complete if and only if the risk-neutral probability measure is unique.  

- Under the assumption that the model is arbitrage-free:  

  - An arbitrary attainable contingent claim X (that is, a claim that can be replicated by means of some trading strategy) has the unique arbitrage price \\(\pi_0(X)\\).
  - The arbitrage price \\(\pi_0(X)\\) of any attainable claim X can be computed from the risk-neutral valuation formula using any risk-neutral probability measure \\(\mathbb{Q}\\).
  - If a claim X is not attainable then we may define a price of X consistent with the no-arbitrage principle. It can be computed using the risk-neutral valuation formula, but it depends on the choice of a risk-neutral probability measure \\(\mathbb{Q}\\).  


### 6.1 Proof of FTAP  

!["FIG.43"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP43.png "FIG.43")  

### 6.2 Geometric Interpretations  

- The proof of the implication \\((\Rightarrow)\\) in the FTAP needs some preparation, since it is based on geometric arguments.
- Any random variable on \\(\Omega\\) can be identified with a vector in  \\(R^k\\) ,specifically,  

$$  
X= (X(\omega_1), . . . ,X(\omega_k))^T = (x_1, . . . , x_k )^T \in R^k .
$$  

- An arbitrary probability measure Q on W can also be interpreted as a vector in \\(R^k\\)  

$$
Q = (Q(\omega_1), . . . ,Q(\omega_k )) = (q_1, . . . , q_k ) \in R^k .  
$$

- We note that  

$$  
E_Q (X) = \Sigma {i=1}{k} X(\omega_i) Q(\omega_i) = \Sigma_{i=1}^{k}x_i q_i = \langle X,Q \rangle
$$  

where \\(\langle \cdot,\cdot \rangle\\) denotes the inner product of two vectors in \\(R^k\\) .  

### 6.3 Axiliary Subsets  

- We define the following classes:  

!["FIG.44"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP44.png "FIG.44")  

- The set W is the image of the map \\(\hat V_1(0,\cdot, . . . , \cdot) : R^n \to R^k \\).
- We note that W represents all discounted values at t = 1 of trading strategies with null initial endowment.
- The set \\(W^\bot\\) is the set of all vectors in \\(R^k\\) orthogonal to W.
- We introduce the following sets of k-dimensional vectors:  

!["FIG.45"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP45.png "FIG.45")  

### 6.4 Vector Spaces  

!["FIG.46"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP46.png "FIG.46")   

### 6.5 Risk-Neutral Probability Measures  

!["FIG.47"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP47.png "FIG.47")   

!["FIG.48"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP48.png "FIG.48")   

!["FIG.49"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP49.png "FIG.49")  

!["FIG.50"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP50.png "FIG.50")  

From Lemmas 4.1 and 4.2, we get the following purely geometric reformulation of the FTAP:  

$$
\mathbb{W}\ \cap \mathbb{A} = \varnothing \leftrightarrow \mathbb{W}^\bot  \cap  \mathbb{P}^+ \ne \varnothing .  
$$

### 6.6 Separating Hyperplane Theorem: Statement  

!["FIG.51"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP51.png "FIG.51")  


### 6.7 Separating Hyperplane Theorem: Interpretation  

- Let the vectors \\(a, y \in R^k\\) be as in the statement of the Separating Hyperplane Theorem
- It is clear that \\(y \in R^k\\) is never a zero vector.
- We define the (k - 1)-dimensional **hyperplane** \\(H - R^k \\)by setting  

$$  
H= a +\\{x \in R^k | \langle x,y \rangle = 0\\} = a + \\{y\\}^\bot  
$$

- Then we say that the hyperplane H **strictly separates** the convex sets B and C.
- Intuitively, the sets B and C lie on di¤erent sides of the hyperplane H and thus they can be seen as geometrically separated by H.
- Note that the compactness of at least one of the sets is a necessary condition for the **strict** separation of B and C.  

### 6.8 Separating Hyperplane Theorem: Corollary  

- The following corollary is a consequence of the separating hyperplane theorem.
- It is more suitable for our purposes: it will be later applied to B =W and \\(C = A^+ := \\{X \in A | \langle X,P \rangle =1\\} \subset A\\).  

!["FIG.52"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP52.png "FIG.52")   

!["FIG.53"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP53.png "FIG.53")   

!["FIG.54"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP54.png "FIG.54")  

We now are ready to establish the implication \\((\Rightarrow)\\) in the Fundamental Theorem of Asset Pricing, that is,  

$$
\mathbb{W}\ \cap \mathbb{A} = \varnothing \leftrightarrow \mathbb{W}^\bot  \cap  \mathbb{P}^+ \ne \varnothing .  
$$  

!["FIG.55"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP55.png "FIG.55")  

!["FIG.56"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP56.png "FIG.56")  

!["FIG.57"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP57.png "FIG.57")  

!["FIG.58"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP58.png "FIG.58")  

!["FIG.59"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP59.png "FIG.59")  

!["FIG.60"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP60.png "FIG.60")  

!["FIG.61"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP61.png "FIG.61")   

!["FIG.62"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP62.png "FIG.62")  

!["FIG.63"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP63.png "FIG.63")  

!["FIG.64"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP64.png "FIG.64")  

!["FIG.65"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP65.png "FIG.65")  

!["FIG.66"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/SinglePeriodMarketModel/SP66.png "FIG.66")






























\\(\Omega = \\{\omega_1,\omega_2,\omega_3\\}\\)
























2 Fundamental Theorem of Asset Pricing
3 Examples of Market Models
4 Risk-Neutral Valuation of Contingent Claims
5 Completeness of Market Models







<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>  






