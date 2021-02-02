---
layout: post
title: Mathematical Finance - Unit 1 Introduction
subtitle: 金融数学 (一) 介绍
category: money
tags: [ECON5020]
---

# Unit 1 Introduction

Uploaded by eva 



## Goals of the Course
- Our main aim is to compute the fair price of a derivative security
- Of course, we will need to dene a concept of fair price
- We will need to learn how to model various features, for example how to model the randomness inherent in securities prices
- We will introduce and use a lot of new concepts, for example
  - arbitrage
  - trading strategies and hedging strategies
  - risk-neutral probability measure
  - attainable claims
  - complete markets
- We first start working with the simplest possible model, and introduce all notions, which the model can explain.
- We then enrich the model with some more realistic features and go again over the key results, to see whether they change. 
- Gradually, we start working with 'proper' discrete-time models and then with continuous time models.

## We Will Cover
- Discrete-Time Models
- Continuous-Time Models

## Discrete and Continuous Time Finance
- In the paper The Pricing of Options and Corporate Liabilities by Fischer Black and Myron Scholes published in 1973, the authors developed ideas, which are nowadays widely used by practitioners to price derivative securities.
- The full theory of security markets requires some knowledge of stochastic calculus and numerical methods for partial diffierential equations (PDEs).  
- We therefore start with discrete-time nancial models and get a good grasp of fundamental ideas of arbitrage pricing before doing continuous-time models.
- In practice, discrete time models are used to price derivatives.Continuous-time models have to be solved numerically, and it is always discretisation, i.e. approximation by discrete-time models.

## We Will Cover
- European Type Options
- American Type Options  

## The structure of the course
- Elementary Market Model (one period, two assets, two states of nature)
- Single-period market model (one period, many assets, many states of nature)
- Modelling uncertainty (filtration and conditioning)
- Generalisation of all results in Multi-period market model
- Binomial model as a special case of Multi-period market model
- Applications: European and American type of options in binomial models
- Continuous time models: Black-Scholes formula
- Extensions

## Long and Short Positions
- A financial security (or asset) is a contract which records some entitlement or obligation and which can be traded at financial markets.  
- Some examples of financial securities: stocks, bonds, options, swaps, and futures.
- An agent takes a so-called long (short) position in the asset if the agent owns (owes) it.
- At modern financial markets, it may not be necessary to own an asset to sell. The strategy of selling a borrowed asset is called short-selling.
  - One can borrow a number of stocks and sells them to undertake other investments The agent buys them back and returns to the original owner at a predetermined time.

## Short Selling Explained
- Short Selling is NOT allowed
Investor has money M at time 0 and can invest into shares and bonds at
time 1.  

!["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/Intorduction/I1.png "FIG.1")  

!["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/Intorduction/I2.png "FIG.2")  

- Short Selling is allowed  
Investor has shares and bonds and can sell any of them at time 0.  


\\(\left. \begin{array} \ share 1\\\\bond\end{array} \right\\}\to \\) sell bond at time 0 and buy more shares 1 at time 1  
\\(\left. \begin{array} \ share 1\\\\bond\end{array} \right\\}\to \\) sell shares at time 0 and buy more bonds at time 1  
As we are selling, coefficients ai which describe proportion of money invested into assets will be negative (compare with the case when no short selling is allowed).

## Exchanges and OTC Markets  

- If a large number of traders short sell a certain stock, it is very likely that the stock price will fall. This has drawn some criticism in the last couple of years and restrictions on short-selling were introduced in some countries.
- Two types of financial markets:
  - Exchanges (stock exchange, options exchange, futures exchange, etc.)
  - Over-the-counter (OTC) markets.  
- A securities exchange provides an organised forum for trading securities whose contracts are standardized. Buyers and sellers do not directly contact each other and all trades are done by the market makers. Prices of securities traded on exchanges are widely disseminated.  

## Exchanges
- Some examples of exchanges and securities traded on them:  
  - Equity markets: stocks and shares.  
  -  Bond market: zero-coupon bonds (ZCBs), government bonds and corporate bonds.  
  - Futures market: futures contracts.  
  - Foreign exchange (FX) market: foreign currencies, options on foreign currencies.  
  - Options market: equity options and interest rate options.  
  - Commodity market: oil and metals futures.  

## OTC Markets
- OTC markets are less organised and two institutions such as a bank and an investment company may be simply involved.  
- Prices of OTC traded securities are generally hard to obtain.  
- Some examples of OTC markets and most typical securities traded on
them:  
  - Interest rate market (mostly OTC): caps, floors, swaps and swaptions.  
  - Exotic options market: barrier options, lookback options, compound options.  
  - Credit market (mostly OTC): credit derivatives such as CDSs and CDOs.  

## Reasons of Trading in Securities
- Profit
  - A trader believing that the price of a security will rise may follow the idea of buying low and selling high. If he believes that the price of a security will decline then short-selling is the right strategy.
- Protection
  - For example, a company dependent on imports may prefer to fix the exchange rate in advance and apply it to a trade later. To this end, one can purchase a futures contract on the exchange rate. It is also possible to enter an OTC forward contract on the exchange rate.
- Hedging
  - To reduce the risk that a trader's portfolio is exposed to, by holding a certain position in related securities.
- Diversification
  - Risks a¤ecting specific securities behave in diffierent manner and thus they may cancel out.  

## Bear and Bull Markets
- Market prices of traded securities are driven by the forces of **supply** and **demand** (that is, the willingness to sell and buy, respectively).  
- In over-supply or under-demand, security prices will generally fall. This is referred to as the **bear market**.  
- In under-supply or over-demand, security prices will generally rise. This is called the **bull market**.    
- Some factors, such as: market information, rumour mill and human psychology, cause **random fluctuations** in supply and demand and hence the market price as well.
- Prices that satisfy supply and demand are called to be in **equilibrium** (at least, in the academic literature).

## Perfect Markets  

- Assumption 1. Markets are frictionless, i.e., no transaction costs, no taxes or other costs and there are no penalties for short selling.
- Assumption 2. Infinitely divisible security prices. It is possible to buy or sell any (also non-integer) quantity of any security.
- Assumption 3. All traders have access to the same information. The Efficient Market Hypothesis (EMH) holds:
  - Weak-form: Current security prices reflect all past market prices and data. Technical analysis is of no benefit.
  - Semi-strong form: Current security prices reect all publicly available information. Fundamental analysis is of no benefit.
  - Strong form: Current security prices reect all available information. Inside information is of no benefit.  

## Arbitrage-free Markets  

- Assumption 4. Markets are assumed to be arbitrage-free:  
  - **Arbitrage** is the guarantee of certain future profit without any current investment. Much of the modern financial theory holds under the assumption that efficient financial markets should forbid such an arbitrage opportunity.  
  - It follows from the **no-arbitrage principle** that if two financial securities have the same pattern of future cash-flows, they should have the same price today. This property is commonly known as the **law of one price**.   
- Standing assumptions 1. to 4. provide a framework in which we can develop mathematical models for **primary securities** and propose pricing methods for **derivative securities**.   
- Assumptions 1. to 3. will be implicitly taken into account when describing **trading**. We will thus mainly focus on the no-arbitrage principle when dealing with **valuation**.  

## European Call Option
Definition. A **European call option** is a financial security, which gives its buyer the right (but not the obligation) to buy an asset at a future time T > 0 for a price K > 0, which is known as the strike price.
- The underlying asset, the **expiration** (or maturity) date T and the **strike** (or exercise) price K are specified in the contract.  
- We assume that the underlying asset is one share of the stock with price \\(S_T\\) at time t.  

At expiry T, a rational holder of a European call option should proceed as follows:  
- If the stock price \\(S_T > K\\), he should buy the stock at time T for the price K from the seller of the option (an option is exercised) and immediately sell it on the market for the market price \\(S_T\\) , leading to a positive payoff of \\(S_T-K\\).  

## Call Option Payoff
If \\(S_T \le K\\), then it does not make sense to buy the stock for the price K from the seller since it can be bought for a lower price on the market. In that case, the holder should waive his right to buy (an option is abandoned) and this leads to a payoff of 0.  
These arguments show that a European call option is formally equivalent to the following random payoff C_T at time T  
$$
C_T := max(S_T- K, 0) = (S_T- K )^+  
$$  
where we denote \\(x^+ = max(x, 0)\\) for any real number x. Note that the payoff \\(C_T\\) is path-independent, meaning that it only depends on the stock price at expiry date T, and not on the whole sample path \\(St , t \in [0,T]\\) of the stock price.  

## European Put Option
Definition. A European put option is a financial security, which gives its buyer the right (but not the obligation) to sell an asset at a future time T > 0 for a price , which is known as the strike price.  
One can show that a European put option on the stock S is formally equivalent to the following random payo¤ PT at time T:  
$$
P_T := max(K - S_T , 0) = (K-S_T )^+  
$$  

It is also easy to see that \\(C_T - P_T = S_T - K \\)  
- European call and put options are actively traded on organised exchanges.
- A pertinent theoretical question thus arises:
  - What should be the 'fair' prices \\(C_t\\) and \\(P_t\\) of European call and put options prior to the expiry date T ?    
  
## Interest Rates and Zero-Coupon Bonds  

- All participants of financial markets have access to **riskless cash** through borrowing and lending from the money market.
- An investor who borrows cash must pay the loan back to the lender with interest at some time in the future. An investor who lends cash will receive from the borrower the nominal value and the **interest** on the loan at some time in the future.
- We assume throughout that the **borrowing rate** is equal to the **lending rate**.  
Definition (*Zero-Coupon Bond*) The unit zero-coupon bond maturing at T is a financial security returning to its holder one unit of cash at time T.  
We denote by B(t,T) the bond price at time \\(t \in [0,T]\\). Hence B(T,T) = 1.  

## Discretely Compounded Interest
- The set of dates is \\(\\{0, 1, 2, ...\\}\\). Let a real number r > -1 represent the simple interest rate over each period [t, t + 1] for t = 0, 1, 2, ....  
One unit of cash invested at time 0 in the money market account yields the following amount at time t = 0, 1, 2, ...  
$$
B_t = (1 + r )^t  
$$  

- From the law of one price, it follows that  
$$
B(t,T) = \frac {B_t} {B_T} = (1+r)^{-(T-t)}
$$

- In general, if \\(r (t) > -1 \\) is the deterministic simple interest rate over the time period [t, t + 1] then we obtain, for every t = 0, 1, 2, ...,  
$$
B_t = \prod_{u=0}^{t-1} (1+r(u)), B(t,T)=\prod_{u=t}^{T-1} (1+r(u))^{-1}
$$



<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

$$ \begin{cases}可到性\\\\极值\end{cases}$$