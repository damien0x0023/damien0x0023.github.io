layout: post
title: Mathematical Finance - Unit 1 Elementary Market Model
subtitle: 金融数学（一）初级市场模型
category: money
tags: [ECON5020]
---

# Unit 1 Elementary Market Model

Uploaded by eva  

# General approach in these lectures  

- We want to learn how to price financial derivatives, say European Call Option. (Indeed, why not to start with something simple?)
- Financial derivatives are written on the price of underlying asset: if its price satisfies certain condition at certain time we exercise So we need to do two things
  - Describe the price process of the underlying asset. Also, we may need to say something about other existing assets - i.e. describe the market.
  - Specify the contract we want to price (derivative)
- Then we need to price the derivative. Our approach to pricing will be based on arbitrage considerations.
- So in these lectures we will discuss, step by step, what is the fair price (so no arbitrage possible) and how to compute it.    

# Single Period Market Models  

- Only one period is considered.
  - The beginning of the period is usually set as t = 0.  
  - The end of the period is usually set as t = 1 (or T = 1).  
- At t = 0, the prices of all assets are known and the investor can
choose the investment.  
- At t = 1, the prices of all assets are observed and the investor obtains a payoff corresponding to the current portfolio value.  
- Single period market models are not realistic, but allow us to illustrate important economic principles without su¤ering from (or enjoying) sophisticated mathematics.
- Single period market models are the atoms of the modern Mathematical Finance. A full understanding of their features (also drawbacks) is thus necessary for further developments.  


# Elementary Market Model: Informal Explanation
- Two points in time (one period)
- Two assets: the underlying asset and the riskless asset (bank account with known rate of return)
  - The riskless asset must always exist in these models - we need a benchmark. We we always compare to what would happen if we invested everything into the riskless asset.
- Two states of nature: the price of underlying asset can only go up or down with given probability
- The derivative security will be the European Call option: we will compute the fair price at time t = 0 of a contract to buy the underlying asset at time t = 1 and pay particular price K for a share.
- Let's start with all formal definitions  

# Elementary Market Model  

!["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM1.png "FIG.1")  

- The investor has initial wealth x at t = 0 and is allowed to invest in a riskless asset B (bank account) and a risky asset S (stock). He purchases \\(\phi\\) shares of the stock and invest the remaining funds in his bank account (or borrows cash).
- Notation:
  - Sample space: \\(\Omega = \\{\omega 1 , \omega 2\\}\\).
  - Probability measure: \\(P(omega 1) = p > 0 \\) and \\(P(\omega 2) = 1-p > 0\\).
  - A deterministic interest rate \\(r > -1\\).
  - The price of a risky asset at time t is denoted by \\(S_t\\) .
  - We assume that \\(S_0 > 0\\) and we set \\(u = \frac {S_1 (\omega 1 )}{S_0}\\) and \\(d = \frac {S_1 (\omega_2)} {S_0}\\)
  - M= (B, S) will be used to denote the model
- We suppose that 0 < d < u, so that there are two distinct values of the future stock price: \\(S_1(\omega_1) > S_1(\omega_2)\\).  
- We do **not** assume that d < 1 or u > 1 (although d stands for 'down'and u stands for 'up').  

# Why the Elementary Market Model?
- Stock price movements are more complicated than indicated by the elementary market model. Hence it cannot be claimed that the elementary model gives a realistic picture of the stock price fluctuations.
- Nevertheless, even in this simplistic framework the random character of the stock price is already visible and thus the problem of options pricing is non-trivial.
- There are two important reasons why we consider this model:
  - First, the concept of arbitrage-free pricing of derivative securities can be clearly explained.
  - Second, the binomial asset pricing model can be seen as an extension of elementary market models.

**Outline**
We will examine the following issues:
1Trading Strategies and Arbitrage-Free Models
2 Replication of Contingent Claims
3 Risk-Neutral Probability Measure
4 Put-Call Parity Relationship
5 Summary of the Elementary Market Model
6 Generalisation of the Elementary Market Model


# Trading Strategy and Wealth Process  

- For arbitrary real numbers x and \\(\phi\\), where x is the initial endowment and \\(\phi\\) is the number of shares of stock purchased or sold, the pair (x, \\(\phi\\)) is called the **trading strategy**.  
- The initial value (or wealth) equals  
!["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM2.png "FIG.2")  

- For any trading strategy \\((x, \phi)\\), the investor obtains at time 1 the random payoff \\(V_1(x, \phi)\\), which equals for i = 1, 2  

!["FIG.3"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM3.png "FIG.3") 

# Arbitrage
An essential feature of an e¢ cient market is that for any trading strategy which can turn nothing into something, the investor who adopts it must also face the risk of loss.  
The following definition is thus a crucial step in the arbitrage pricing methodology.  

!["FIG.4"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM4.png "FIG.4")  

# Arbitrage-Free Model
Note that, under A.2., the condition A.3. is equivalent to A.3'. There exists an wi such that \\(V_1(x, \phi)(\omega_i ) > 0 \\).  

- Real markets sometimes exhibit arbitrage, but it is necessarily lasts for a very short time. The forces of supply and demand take actions to remove it as soon as someone discovers it.
- A market model which admits arbitrage cannot be used for our purposes.  

!["FIG.5"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM5.png "FIG.5")  

Proof.
[Proof of Proposition 3.1 (\\(\Rightarrow)\\))] To prove the 'only if'part, we argue by contradiction:
Assume first that \\(d \ge 1 + r\\) :
- At t = 0, the investor borrows the amount \\(S_0\\) of cash on the money market and buys one share of the stock.
- At t = 1, the investor sells the stock and thus receives either \\(uS_0\\) or \\(dS_0\\). He also pays back \\((1 + r )S_0 \\).
Let us now assume that \\(u \le 1 + r\\) :
- At t = 0, the investor borrows one share of the stock from the stock market and sells it immediately. He then invests S0 in the money market.
- At t = 1, the investor obtains \\((1 + r )S_0\\) from the bank account. He spends either \\(uS_0\\) or \\(dS_0\\) to buy one share of the stock and returns it to the original owner.
- This completes the proof of the 'only if'part.  

!["FIG.6"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM6.png "FIG.6")  

# European Options  

Definition (European Call and Put Options)
A **European call (put) option** is a contract which gives the buyer the right to buy (sell) an asset at a future time T for a price K. The underlying asset, the maturity time T and the strike price K are specified in the contract.  
- How to compute the 'fair price' of a European call (put) option?
- Payoff of European call option:
  - If the stock price \\(S_1\\) at T = 1 is above K then the holder obtains the
payoff \\(S_1 - K > 0\\) from exercising the contract.
  - If the stock price \\(S_1\\) at T = 1 is below K then the holder does not exercise the contract and this leads to the null payoff.
  - Hence the payo¤ of a European call option at time T = 1 is  

  $$
\\\\ C_T= h(S_1)=max\\{0,S_1-K\\}=({S_1-K})^+
  $$  


- Payoff of European put option:
  - If the stock price \\(S_1\\) at T = 1 is above K then the holder does not exercise the contract; hence the payoff equals 0.
  - If the stock price \\(S_1\\) at T = 1 is below K then the holder exercises the option and obtains the payoff \\(K - S_1 > 0\\).
  - Hence the payoff of a European put option at time T = 1 equals  
$$
\\\\ P_T= h(S_1)=max\\{0,K-S_1\\}=({K-S_1})^+
$$  

- European calls and puts are examples of contingent claims. Their payoffs \\(C_T\\) and \\(P_T\\) at expiry date T are random, but they only depend on the stock price \\(S_1\\) and strike K.    

We will now address the following general question:
- How to select an initial investment, x, and a trading strategy, \\((x, \phi)\\),in order to obtain the same wealth \\(V_1(x, \phi)\\) at time 1 as the payoff of a given **contingent claim** \\(X = h(S_1)\\)?  

## Example
- \\(S_0 = 25, K = 35, r = 0 \\)
- two states of nature: 'price up to 40'and 'price down to 20'.  
- Investor expects \\(S_{1}^u= 40\\) with \\(p_u = 0.5\\) and \\(S_{1}^d=20\\) with \\(p_d = 0.5)  
- How much to pay for the call option?
- The seller knows that at time 1 she needs \\((S_1 - K)^+ = (S_1 - 35)^+\\)  
- The idea is to make initial investment to generate this money to meet
the claim
- She can create a portfolio \\((x - \phi S_0)\\)into saving account and \\((\phi S_0)\\) into shares
- She will get\\( (x - \phi S_0) (1 + 0) + 40  \phi \\) or \\((x - \phi S_0) (1 + 0) + 20 \phi \\)  
  - \\((x -\phi S_0) (1 + 0) + 40 \phi = 5 \\)then she can use these 5 + 35 from investor to deliver the share to the investor.  
  - \\((x -\phi S_0) (1 + 0) + 20 \phi = 0 \\) as the investor will not come  

- So we need to solve the system of 2 equations with 2 unknowns  


  - \\((x - \phi S_0) (1 + 0) + 40 \phi = 5\\)
  - \\((x - \phi S_0) (1 + 0) + 20 \phi = 0 \\)


- The solution (2 equations, 2 unknowns) at \\((x - \phi S_0) = -5\\) and
\\(\phi = \frac {1}{4}\\).
- The cost of building the portfolio at time zero  
$$
(x -\phi S_0) + \phi S_0 = -5 + \frac {1}{4} * 25 =\frac {5}{4}=1.25
$$  

- So \\(C_0 = 1.25\\) is the price
- Subjective probabilities are irrelevant!
- Solving portfiolion is not always convinient, it is convenient to represent \\(C_0\) as 'expectation'of some payoff.
  - to define an expectation, we need to define appropriate probability
measure.  

# Replication of a Contingent Claim  

!["FIG.8"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM8.png "FIG.8")  

# Hedging of a Contingent Claim

Computation of the hedge and (unique) arbitrage price x of a contingent
claim X = h(S1):
- By subtracting (2) from (1), we find the hedge ratio  

!["FIG.9"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM9.png "FIG.9")  

- Equality (3) is called the **delta hedging formula**.
- One can substitute (3) into (1) or (2) in order to compute x.
- To derive a convenient representation for x, we introduce the notation  

!["FIG.10"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM10.png "FIG.10")  

# Pricing of a Contingent Claim  

!["FIG.11"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM11.png "FIG.11") 

# Market Completeness
- In view of (5), the term with f vanishes. Therefore, equation (8) yields the following convenient representation for the price x  

!["FIG.12"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM12.png "FIG.12") 

- It can be seen from (9) that the price x depends on \\(\widetilde p\\) and \\(1 - \widetilde p\\), but it is independent of the probabilities p and 1 - p.
- Note that equalities (3) and (9) hold for an arbitrary payoff function \\(h(S_1)\\). Hence for any contingent claim X we have found the unique replicating strategy and arbitrage price.
Definition (Completeness)
Since all contingent claims (that is, all derivative securities) in the elementary market model have replicating strategies, the market described by this model is called **complete**.

# Risk-Neutral Probability Measure  

Definition (Risk-Neutral Probability Measure)
A probability measure Q on the sample space \\(\Omega = \\{\omega_1,\omega_2\\}\\) is called a **risk-neutral probability measure** (or an **equivalent martingale measure**) for the market model M= (B, S) if Q is equivalent to P and the following equality holds  

$$
\\\\ E_Q(\frac{S_1}{1+r})=S_0
$$

Proposition (3.2)
The risk-neutral probability measure for the market model M= (B, S) is unique and it satisfies \\(Q = \widetilde p\\) if and only if d < 1 + r < u.
If \\(1 + r \le d \\) or \\(u \le 1 + r \\) then no risk-neutral probability exists.  

!["FIG.13"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM13.png "FIG.13")   


# Expected Rates of Return
- Assume that u < 1 + r < d. Then the risk-neutral probability measure \\(\widetilde p\\) exists and is unique.
- The expected rate of return on the savings account B equals  
  
!["FIG.14"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM14.png "FIG.14") 


- The expected rate of return on the stock under \\(\widetilde p\\) equals r . This follows from the equality   

!["FIG.15"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM15.png "FIG.15")   

- The probability measure eP is the unique probability measure Q under which the equality \\(EQ(r_B ) = EQ(r_S )\\) holds.  

# Risk-Neutral Valuation Formula
Proposition (3.3)
For any claim X = h(S1), the arbitrage price of X at time 0 in the arbitrage-free elementary market model M= (B, S) satisfies  

!["FIG.16"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM16.png "FIG.16")   

Proof.
[Proof of Proposition 3.3] We know (see (9)) that the price x satisfies  

!["FIG.17"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM17.png "FIG.17")

Formula (11) now follows immediately.
We will now give another proof for (11).  

Proof.
[Another Proof of Proposition 3.3] It is assumed that u < 1 + r < d. Let \\((x, \phi)\\) be any trading strategy. From the equality  

$$
\frac {V_1(x,\phi)}{1+r} = x + \phi (\frac {S_1} {1+r}-S_0)
$$
and formula (5), we deduce that investing is a 'fair game' under P meaning that: for any strategy (x, f) we have  

$$  
E_\widetilde p (\frac {V_1(x,\phi)}{1+r})=x
$$

In particular, if (x, f) replicates X then \\(V_1 (x, \phi) = X\\) and thus we obtain the **risk-neutral valuation formula** (11)  

## Example: Call and Put Options
- Consider the elementary market model M= (B, S) with parameters   
$$ 
r = \frac {1}{3} ,S_0 = 1, u = 2, d = \frac {1}{2}, p = \frac{3}{5} and  T = 1.  
$$
- Recall that the risk-neutral probability measure \\(\widetilde p\\) is given as  
$$
\widetilde p (\omega_1) = \widetilde p  \ and \  \widetilde p(\omega_2) = 1 - \widetilde p 
$$  
where  
$$
\widetilde p := \frac {1+r-d}{u-d}  
$$  

- Hence the risk-neutral probability measure \\(\widetilde p\\) equals  


$$  
\widetilde P(\omega_1) = \widetilde p = \frac{1+\frac{1}{3}-\frac{1}{2}}{2-\frac{1}{2}}=\frac{5}{9}
$$  
and  

$$  
 \widetilde P(\omega_2) = 1-\widetilde p =\frac{4}{9}  
$$  


# Example: Call and Put Options  

!["FIG.19"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM19.png "FIG.19")  

!["FIG.20"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM20.png "FIG.20")  

# Put-Call Parity
- The arbitrage prices at time 0 computed in Example (3.1) satisfy  

$$  
C_0-P_0=\frac{1}{4}= 1-\frac {3}{4} =S_0-\frac {1}{1+r} K   \ \ \ \ (12)
$$  

- Equality (12) is a special case of the **put-call parity**.  

!["FIG.21"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM21.png "FIG.21")  

- Recall that we have already checked that \\(C_T - P_T = S_T - K\\) where T is the expiration date.
- Equality (13) is an easy consequence of Proposition (3.3).  

# Summary: Properties
Let us summarise the properties of the elementary market model:
1. The two-state single-period market model M= (B, S) is arbitrage-free if and only if d < 1 + r < u.
2. The arbitrage-free property of the model M= (B, S) does not depend on the actual probability measure P.
3. An arbitrary contingent claim X can be replicated by means of a unique trading strategy (hence the model is complete).
4. The initial endowment of a replicating strategy for X is called the arbitrage price for X and is denoted as \\(\pi_0(X)\\).
5. The risk-neutral probability measure eP exists and is unique if and only if d < 1 + r < u (that is, whenever the model M is arbitrage-free). By definition, \\(\widetilde p\\) is equivalent to P.
6. The arbitrage price \\(\pi_0(X)\\) of any claim X can be computed from the risk-neutral valuation formula.  

# Summary: Theorem  

!["FIG.22"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM22.png "FIG.22")  

# Generalisation of the Elementary Market Model
We generalise the elementary market model by postulating that:
1. We still deal with two primary traded assets: B and S.
2. The sample space \\(\\{\Omega = \omega_1,\omega_2, . . . ,\omega_k\\}\\) g where \\(k \ge 3\\).
3. Hence \\(S_1 = (S_1(\omega_1), . . . , S_1(\omega_k ))\\) where, without loss of generality, we may assume that  
$$
S_1(\omega_k ) < S1(\omega k_1) < ... < S_1(\omega_2) < S1(\omega_1).  
$$
4. It can be checked directly that this model is arbitrage-free if and only if \\(S_1(\omega_k ) < S_0(1 + r ) < S_1(\omega_1)\\).
5. The risk-neutral probability measure Q exists if and only if \\(S_1(\omega_k ) < S_0(1 + r ) < S_1(\omega_1)\\), but it is not unique if \\(k \ge 3\\).
6. The market is incomplete when \\(k \ge 3\\): for some contingent claims \\(X = (X(\omega_1), . . . ,X(\omega_k )) \\)no replicating strategy exists.
7. We will not examine this model in detail, since it can be seen as a special case of a general single-period market model.  

!["FIG.23"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/ElementaryMarketModel/EM23.png "FIG.23") 














<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>