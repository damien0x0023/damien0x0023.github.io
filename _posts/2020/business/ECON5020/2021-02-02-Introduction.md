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
  我们的主要目的是计算衍生证券的公平价格
- Of course, we will need to define a concept of fair price  
  当然，我们需要定义一个公平价格的概念
- We will need to learn how to model various features, for example how to model the randomness inherent in securities prices  
我们将需要学习如何建模各种特征，例如如何建模证券价格固有的随机性
- We will introduce and use a lot of new concepts, for example  
例如，我们将引入和使用许多新概念
  - arbitrage  
  套利
  - trading strategies and hedging strategies  
  交易策略和对冲策略
  - risk-neutral probability measure  
  风险中性概率测度
  - attainable claims  
  可实现的债权
  - complete markets  
  完整的市场
- We first start working with the simplest possible model, and introduce all notions, which the model can explain.  
我们首先从最简单的模型开始，介绍模型能够解释的所有概念。
- We then enrich the model with some more realistic features and go again over the key results, to see whether they change.  
然后，我们用一些更真实的特征来丰富模型，并再次检查关键结果，看看它们是否发生了变化。 
- Gradually, we start working with 'proper' discrete-time models and then with continuous time models.  
渐渐地，我们开始使用“适当的”离散时间模型，然后使用连续时间模型。

## We Will Cover  
我们将涵盖
- Discrete-Time Models  
离散时间模型
- Continuous-Time Models  
连续时间模型

## Discrete and Continuous Time Finance  
离散与连续时间金融
- In the paper The Pricing of Options and Corporate Liabilities by Fischer Black and Myron Scholes published in 1973, the authors developed ideas, which are nowadays widely used by practitioners to price derivative securities.  
在Fischer-Black和Myron-Scholes于1973年发表的论文《期权与公司负债定价》中，作者提出了一些想法，这些想法目前被从业者广泛用于衍生证券的定价。
- The full theory of security markets requires some knowledge of stochastic calculus and numerical methods for partial diffierential equations (PDEs).  
完整的证券市场理论需要一定的随机演算知识和偏微分方程的数值方法。  
- We therefore start with discrete-time nancial models and get a good grasp of fundamental ideas of arbitrage pricing before doing continuous-time models.  
因此，我们先从离散时间金融模型入手，在建立连续时间模型之前，先掌握套利定价的基本思想。
- In practice, discrete time models are used to price derivatives.Continuous-time models have to be solved numerically, and it is always discretisation, i.e. approximation by discrete-time models.  
在实践中，离散时间模型用于定价导数。连续-时间模型必须用数值方法求解，而且总是离散化的，即用离散时间模型逼近。

## We Will Cover
- European Type Options  
欧式期权
- American Type Options  
美式期权  

## The structure of the course
- Elementary Market Model (one period, two assets, two states of nature)  
基本市场模型（一个周期，两种资产，两种自然状态）
- Single-period market model (one period, many assets, many states of nature)  
单周期市场模型（一个周期，多个资产，多个自然状态）
- Modelling uncertainty (filtration and conditioning)  
建模不确定性（过滤和调节）
- Generalisation of all results in Multi-period market model  
多期市场模型所有结果的推广
- Binomial model as a special case of Multi-period market model  
二项式模型作为多期市场模型的特例
- Applications: European and American type of options in binomial models  
应用：二项式模型中的欧式和美式期权
- Continuous time models: Black-Scholes formula  
连续时间模型：Black-Scholes公式
- Extensions  
扩展

## Long and Short Positions  
多头和空头头寸
- A financial security (or asset) is a contract which records some entitlement or obligation and which can be traded at financial markets.  
金融证券（或资产）是一种记录某种权利或义务的合同，可以在金融市场上交易。  
- Some examples of financial securities: stocks, bonds, options, swaps, and futures.  
金融证券的一些例子：股票、债券、期权、掉期和期货
- An agent takes a so-called long (short) position in the asset if the agent owns (owes) it.  
如果代理拥有（欠）资产，则代理在资产中持有所谓的多头（空头）头寸。
- At modern financial markets, it may not be necessary to own an asset to sell. The strategy of selling a borrowed asset is called short-selling.  
在现代金融市场上，可能没有必要持有资产出售。出售借入资产的策略称为卖空
  - One can borrow a number of stocks and sells them to undertake other investments The agent buys them back and returns to the original owner at a predetermined time.  
  一个人可以借一些股票，然后卖掉它们进行其他投资——代理人买回这些股票，然后在预定的时间归还给原来的所有者。

## Short Selling Explained  
卖空解释
- Short Selling is NOT allowed  
不允许卖空  
Investor has money M at time 0 and can invest into shares and bonds at
time 1.  
投资者在时间0时拥有资金M，可以在时间0时投资股票和债券时间1。

!["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/Intorduction/I1.png "FIG.1")  

!["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/Intorduction/I2.png "FIG.2")  

- 允许卖空  
投资者拥有股票和债券，可以在0时出售其中任何一种。

- Short Selling is allowed  
 允许卖空  
 Investor has shares and bonds and can sell any of them at time 0.  
投资者拥有股票和债券，可以在0时出售其中任何一种。

\\(\left. \begin{array} \ share 1\\\\bond\end{array} \right\\}\to \\) sell bond at time 0 and buy more shares 1 at time 1  
在时间0卖出债券，在时间1买入更多股票  

\\(\left. \begin{array} \ share 1\\\\bond\end{array} \right\\}\to \\) sell shares at time 0 and buy more bonds at time 1  
在时间0卖出股票，在时间1买入更多债券  
As we are selling, coefficients \\(\alpha_ i\\) which describe proportion of money invested into assets will be negative (compare with the case when no short selling is allowed).  
当我们卖出时，描述投资资产的资金比例的系数\\(\alpha_ i\\)将为负（与不允许卖空的情况相比).

## Exchanges and OTC Markets  
交易所和场外交易市场

- If a large number of traders short sell a certain stock, it is very likely that the stock price will fall. This has drawn some criticism in the last couple of years and restrictions on short-selling were introduced in some countries.  
如果大量交易员卖空某只股票，股价很可能下跌。这在过去几年中招致了一些批评，一些国家也出台了卖空限制措施。
- Two types of financial markets:  
两类金融市场：
  - Exchanges (stock exchange, options exchange, futures exchange, etc.)  
  交易所（证券交易所、期权交易所、期货交易所等）
  - Over-the-counter (OTC) markets.  
  场外交易市场  
- A securities exchange provides an organised forum for trading securities whose contracts are standardized. Buyers and sellers do not directly contact each other and all trades are done by the market makers. Prices of securities traded on exchanges are widely disseminated. 
证券交易所提供了一个组织化的论坛，用于交易合同标准化的证券。 买卖双方不直接联系，所有交易均由做市商完成。 在交易所买卖的证券价格被广泛传播。 

## Exchanges  
交易所
- Some examples of exchanges and securities traded on them:  
交易所和在其上交易的证券的一些例子： 
  - Equity markets: stocks and shares.  
  股票市场：股票和股票  
  -  Bond market: zero-coupon bonds (ZCBs), government bonds and corporate bonds.  
  债券市场：零息债券、政府债券和公司债券  
  - Futures market: futures contracts.  
  期货市场：期货合约  
  - Foreign exchange (FX) market: foreign currencies, options on foreign currencies.  
  外汇市场：外汇，外汇期权  
  - Options market: equity options and interest rate options.  
  期权市场：股票期权和利率期权  
  - Commodity market: oil and metals futures.  
  商品市场：石油和金属期货 

## OTC Markets  
场外交易市场
- OTC markets are less organised and two institutions such as a bank and an investment company may be simply involved.  
场外交易市场组织较少，银行和投资公司等两个机构可能只是简单地参与其中。 
- Prices of OTC traded securities are generally hard to obtain.   
场外交易证券的价格通常很难获得。  
- Some examples of OTC markets and most typical securities traded on them:  
场外交易市场和最典型的证券交易的一些例子：  
  - Interest rate market (mostly OTC): caps, floors, swaps and swaptions.  
  利率市场（主要是场外交易）：上限、下限、互换和互换期权。  
  - Exotic options market: barrier options, lookback options, compound options.  
  奇异期权市场：障碍期权、回望期权、复合期权。 
  - Credit market (mostly OTC): credit derivatives such as CDSs and CDOs.  
  信用市场（主要是场外交易市场）：信用衍生产品，如CDS和CDO 

## Reasons of Trading in Securities  
证券交易原因
- Profit  
利润
  - A trader believing that the price of a security will rise may follow the idea of buying low and selling high. If he believes that the price of a security will decline then short-selling is the right strategy.  
  相信证券价格会上涨的交易者可能会遵循低买高卖的想法。如果他相信证券价格会下跌，那么卖空就是正确的策略。  
  - Protection  
  保护  
  - For example, a company dependent on imports may prefer to fix the exchange rate in advance and apply it to a trade later. To this end, one can purchase a futures contract on the exchange rate. It is also possible to enter an OTC forward contract on the exchange rate.  
  例如，依赖进口的公司可能倾向于提前确定汇率，然后将其应用于贸易。为此，人们可以按汇率购买期货合约。也可以就汇率签订场外远期合约。  
  - Hedging  
  套期保值
  - To reduce the risk that a trader's portfolio is exposed to, by holding a certain position in related securities.  
  通过持有相关证券的特定头寸来降低交易者的投资组合所面临的风险  
  - Diversification   
  多样化
  - Risks a¤ecting specific securities behave in diffierent manner and thus they may cancel out.  
  特定证券的风险表现不同，因此它们可能会抵消。

## Bear and Bull Markets  
熊市和牛市
- Market prices of traded securities are driven by the forces of **supply** and **demand** (that is, the willingness to sell and buy, respectively).  
交易证券的市场价格是由**供给**和**需求**的力量驱动的（即分别是卖出和买入的意愿）  
- In over-supply or under-demand, security prices will generally fall. This is referred to as the **bear market**.  
在供过于求或供不应求的情况下，证券价格通常会下跌。这被称为**熊市**
- In under-supply or over-demand, security prices will generally rise. This is called the **bull market**.  
在供给不足或需求过剩的情况下，证券价格普遍会上涨。这就是所谓的**牛市**    
- Some factors, such as: market information, rumour mill and human psychology, cause **random fluctuations** in supply and demand and hence the market price as well.  
一些因素，如：市场信息、谣言工厂和人类心理，会导致供求的**随机波动**，从而导致市场价格
- Prices that satisfy supply and demand are called to be in **equilibrium** (at least, in the academic literature).  
满足供求关系的价格被称为处于**均衡**（至少在学术文献中是这样）

## Perfect Markets  
完美市场  

- Assumption 1. Markets are frictionless, i.e., no transaction costs, no taxes or other costs and there are no penalties for short selling.  
假设1。市场是无摩擦的，即没有交易成本，没有税收或其他成本，卖空也没有处罚
- Assumption 2. Infinitely divisible security prices. It is possible to buy or sell any (also non-integer) quantity of any security.  
无限可分证券价格。可以买卖任何数量的证券。
- Assumption 3. All traders have access to the same information. The Efficient Market Hypothesis (EMH) holds:  
所有交易者都可以获得相同的信息。有效市场假说（EMH）认为： 
  - Weak-form: Current security prices reflect all past market prices and data. Technical analysis is of no benefit.  
  弱形式：当前证券价格反映了所有过去的市场价格和数据。技术分析毫无益处
  - Semi-strong form: Current security prices reflect all publicly available information. Fundamental analysis is of no benefit.  
  半强形式：当前证券价格重新评估所有公开信息。基本分析毫无益处
  - Strong form: Current security prices reect all available information. Inside information is of no benefit.  
  强形式：当前证券价格重新评估所有可用信息。内幕消息毫无用处  

## Arbitrage-free Markets  
无套利市场  

- Assumption 4. Markets are assumed to be arbitrage-free:  
假设4。假设市场无套利 
  - **Arbitrage** is the guarantee of certain future profit without any current investment. Much of the modern financial theory holds under the assumption that efficient financial markets should forbid such an arbitrage opportunity.  
  **套利**是在没有任何流动投资的情况下，对未来一定利润的保证。许多现代金融理论都假设有效的金融市场应该禁止这种套利机会。  
  - It follows from the **no-arbitrage principle** that if two financial securities have the same pattern of future cash-flows, they should have the same price today. This property is commonly known as the **law of one price**.   
  根据**无套利原则**，如果两种金融证券的未来现金流模式相同，那么它们今天的价格应该相同。这个属性通常被称为**一价法则**  
- Standing assumptions 1. to 4. provide a framework in which we can develop mathematical models for **primary securities** and propose pricing methods for **derivative securities**.  
长期假设1。到4。提供一个框架，在此框架中我们可以开发**初级证券**的数学模型，并提出**衍生证券**的定价方法。   
- Assumptions 1. to 3. will be implicitly taken into account when describing **trading**. We will thus mainly focus on the no-arbitrage principle when dealing with **valuation**.   
假设1。到3。在描述**交易**时将隐含考虑在内。因此，在处理**估值**时，我们将主要关注无套利原则。 

## European Call Option  
欧式看涨期权
Definition. A **European call option** is a financial security, which gives its buyer the right (but not the obligation) to buy an asset at a future time T > 0 for a price K > 0, which is known as the strike price.  
定义。**European看涨期权**是一种金融证券，它赋予买方在未来时间 T>0 以 K>0 的价格购买资产的权利（而不是义务），这就是所谓的执行价。
- The underlying asset, the **expiration** (or maturity) date T and the **strike** (or exercise) price K are specified in the contract.  
标的资产,**到期日**（或到期日）T和**行权日**（或行权日）K在合同中规定  
- We assume that the underlying asset is one share of the stock with price \\(S_T\\) at time t.  
我们假设标的资产是时间T时价格为\（S \ \ \ \）的股票的一部分。

At expiry T, a rational holder of a European call option should proceed as follows:  
- If the stock price \\(S_T > K\\), he should buy the stock at time T for the price K from the seller of the option (an option is exercised) and immediately sell it on the market for the market price \\(S_T\\) , leading to a positive payoff of \\(S_T-K\\).  
到期日T时，欧式看涨期权的理性持有人应按以下步骤进行：

-如果股票价格\\(S_T > K\\)，他应该在时间T以K的价格从期权卖方（行使期权）处购买股票，并立即以市场价格\\(S_T\\)在市场上出售，从而获得\\(S_T-K\\)的正收益。  

## Call Option Payoff  
买入期权收益  

If \\(S_T \le K\\), then it does not make sense to buy the stock for the price K from the seller since it can be bought for a lower price on the market. In that case, the holder should waive his right to buy (an option is abandoned) and this leads to a payoff of 0.  
These arguments show that a European call option is formally equivalent to the following random payoff C_T at time T  
如果\（S\u T\le K \），那么从卖方以K的价格购买股票是没有意义的，因为它可以在市场上以较低的价格购买。在这种情况下，持有人应放弃购买权（放弃期权），这将导致0的回报。

这些论据表明，欧式看涨期权在形式上等价于时间T的随机报酬 
$$
C_T := max(S_T- K, 0) = (S_T- K )^+  
$$  
where we denote \\(x^+ = max(x, 0)\\) for any real number x. Note that the payoff \\(C_T\\) is path-independent, meaning that it only depends on the stock price at expiry date T, and not on the whole sample path \\(St , t \in [0,T]\\) of the stock price.  
其中，我们表示任意实数x的\\(x^+ = max(x, 0)\\)。注意，收益\\(C_T\\)是路径独立的，这意味着它只取决于到期日T的股票价格，而不取决于股票价格的整个样本路径\\(St , t \in [0,T]\\)。  

## European Put Option  
欧式看跌期权  

Definition. A European put option is a financial security, which gives its buyer the right (but not the obligation) to sell an asset at a future time T > 0 for a price , which is known as the strike price.  
定义。欧式看跌期权是一种金融证券，买方有权（但没有义务）在未来时间 T>0 以一个称为执行价的价格出售资产。  
One can show that a European put option on the stock S is formally equivalent to the following random payo¤ PT at time T:  
我们可以证明，股票S的欧式看跌期权在形式上等价于时间T的下列随机支付：  

$$
P_T := max(K - S_T , 0) = (K-S_T )^+  
$$  

It is also easy to see that \\(C_T - P_T = S_T - K \\)  
也很容易看出\\(C_T - P_T = S_T - K \\)  
- European call and put options are actively traded on organised exchanges.  
欧洲看涨期权和看跌期权在有组织的交易所交易活跃。
- A pertinent theoretical question thus arises:  
因此产生了一个相关的理论问题：
  - What should be the 'fair' prices \\(C_t\\) and \\(P_t\\) of European call and put options prior to the expiry date T ?   
  在到期日 t 之前，欧洲看涨期权和看跌期权的“公平”价格应该是多少？   
  
## Interest Rates and Zero-Coupon Bonds  
  利率和零息债券

- All participants of financial markets have access to **riskless cash** through borrowing and lending from the money market.  
金融市场的所有参与者都可以通过从货币市场借贷获得**无风险现金** 
- An investor who borrows cash must pay the loan back to the lender with interest at some time in the future. An investor who lends cash will receive from the borrower the nominal value and the **interest** on the loan at some time in the future.  
借入现金的投资者必须在将来某个时候将贷款连同利息一起偿还给贷款人。借出现金的投资者将在未来某个时候从借款人处获得贷款的票面价值和**利息**
- We assume throughout that the **borrowing rate** is equal to the **lending rate**.  
我们始终假设**借款利率**等于**贷款利率**。 
Definition (*Zero-Coupon Bond*) The unit zero-coupon bond maturing at T is a financial security returning to its holder one unit of cash at time T.  
定义（*零息债券*）在T到期的单位零息债券是指在T时向持有人返还一单位现金的金融证券。  
We denote by B(t,T) the bond price at time \\(t \in [0,T]\\). Hence B(T,T) = 1.  
我们用B（t，t）表示时间\\(t \in [0,T]\\) 的债券价格。因此B（T，T）= 1  

## Discretely Compounded Interest  
利率和零息债券  

- The set of dates is \\(\\{0, 1, 2, ...\\}\\). Let a real number r > -1 represent the simple interest rate over each period [t, t + 1] for t = 0, 1, 2, ....  
  日期集合是\\(\\{0, 1, 2, ...\\}\\) . 设一个实数 r>-1 表示 t=0，1，2，…，每个期间的单利 [t, t + 1] for t = 0, 1, 2, .... 
One unit of cash invested at time 0 in the money market account yields the following amount at time t = 0, 1, 2, ...  
在时间0投资于货币市场账户的一单位现金在时间t=0，1，2...

$$
B_t = (1 + r )^t  
$$  

- From the law of one price, it follows that  
根据一价定律，可以得出  
$$
B(t,T) = \frac {B_t} {B_T} = (1+r)^{-(T-t)}
$$

- In general, if \\(r (t) > -1 \\) is the deterministic simple interest rate over the time period [t, t + 1] then we obtain, for every t = 0, 1, 2, ...,  
一般来说，如果\\(r (t) > -1 \\)是一段时间内确定的简单利率[t，t+1]，那么我们得到，对于每t=0，1，2,..  
  
$$
B_t = \prod_{u=0}^{t-1} (1+r(u)), B(t,T)=\prod_{u=t}^{T-1} (1+r(u))^{-1}
$$



<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

$$ \begin{cases}可到性\\\\极值\end{cases}$$