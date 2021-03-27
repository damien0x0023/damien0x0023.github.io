---
layout: post
title: Mathematical Finance - Unit 9 Revision Lecture
subtitle: 金融数学（九）回顾
category: money
tags: [ECON5020]
---  

# Unit 9 Revision Lecture

Uploaded by eva  

## Set 1: Security markets (covered in Lecture 1)  
- This was a brief introduction to the course: a promise to discuss arbitrage pricing, concentrate on discrete time models.  
- Intuitive discussion of what is arbitrage, what is a perfect market 
- Definitions of bonds, European call and put options, discrete time- and continuous time- interest
- Everything will be discussed again during the course, formally and with examples.  


## Set 2: Elementary Market Model (One period, Two assets, Two states of nature)  
- Key model for understanding the following material  
- As we now know all sophisticated models which we studied can be seen as a 'collection' of elementary market models  
- All relevant concepts can be introduced in this model, and all sophisticated concepts can be studied with the help of this model
- General concepts introduced here
  - Contingent claim
  - A probability measure
  - Trading strategies, replicating trading strategies
  - Arbitrage
  - Risk neutral probability measure vs. subjective probability measure
  - Complete markets
  - Risk-neutral valuation formula (note the role of discounting)
- Examples: European call&put option, call-put parity proved  

## Set 3: Single-Period Market Model (One period, Many assets, Many states of nature)  
- Possibly infinite number states of nature, while we always had them finite in the notation and all examples
- The same concepts, introduced for elementary model, are generalized here.
  - Wealth and Gains, discounted
  - Arbitrage-free markets: we considered geometric interpretation of this concept using examples
  - Risk-neutral probability measure
- One key difference is that we deal with the bigger set of states of nature, so pay attention to the notation used.  

- Fundamental Theorem of Asset Pricing
  - Proved \\(\Leftarrow\\)
  - no proof of \\(\Rightarrow\\) .
  - However, we discussed an algorithm how to check whether the market is arbitrage-free. Whether we do it using replication strategy and see if it has a unique solution and the risk-neutral probability vector has positive components, or we so essentially the same thing by exploiting axillary sets, it does not matter. This is the matter of your choice.  

- As the number of states of nature is not equal to the number of assets any more, it is clear that not all contingent claims can be priced.
- The notion of attainable claim is introduced
  - Example of stochastic volatility model and digital call option
- Algebraic Criterion of Market Completeness
- Probabilistic Criterion for Attainability (proved\\(\Rightarrow\\) , but not \\(\Leftarrow\\))
- Extended market model and valuation of non-attainable claims  

- FATP: Model M is arbitrage free \\(\Leftrightarrow\\) at least one RNPM exists.
  - Need a procedure to find RNPM. If we can construct a RNPM then
there is no arbitrage. We discussed the procedure.
  - If we have a replicating strategy then the contingent claim is attainable.  
- Complete market: all contingent claims are attainable.
- Need to have at least as many (different) securities (N + 1) as
(different) states of nature (K).
- So, we are naturally interested in working with complete markets.There is a unique RNPM there. And we learned how to construct a replicating portfolio and so we learned how to find an arbitrage price of a contingent claim.
- However, when markets are incomplete, then certain claims can still be attainable.  

## Set 4: Filtrations and Conditioning  
- Multi-period market model: Many periods, Many assets, many states of nature
- Need to understand how information is changing over time.
- Standard way to do model information as subsets of bigger set, and each period we learn some new subset.
- One of the challenges of this lecture is to learn new notation and formal approach
- Adapted processes
- Conditional expectation. When computing expectations at period t they are now conditional on 'information available at time t', not 'the
whole information'.
- Martingales are introduced  

## Set 5: Multi-period Market Model  
- Yet again, all main concepts are re-introduced
- Self-financing trading strategy
- Wealth and Gains, discounted
- Arbitrage
- Risk Neutral Probability measure
- Discounted wealth as a martingale
- Fundamental Theory of Asset Pricing (without a proof)
- Examples: Replication principle. Hedging strategy in case of digital call option  

We examined three pricing and hedging approaches:  
1. The method based on the idea of replication of a contingent claim. It can only be applied to attainable contingent claim in a complete or incomplete model and it yields the hedging strategy and arbitrage price process.
2. The method relying on the concept of a risk-neutral probability, which can be applied in either a complete or incomplete model. It furnishes the unique arbitrage price process for any attainable claim and a possible arbitrage price process for a non-attainable contingent claim. In the latter case, the price process depends on the choice of a risk-neutral probability.
3. The backward induction approach in which a multi-period market model is decomposed into a family of single-period models. Pricing is performed in a recursive way starting from the date T - 1 and moving step-by-step towards the initial date 0. Hedging strategy can also be computed provided that the claim is attainable.  

## Set 6: Examples: European and American options in CRR model  

- The previous lectures discussed very generally types of models 
- CRR model - binomial model, where factors 'up'nd 'down'are constant.
  - Introduced Bernoulli processes  
  - Derived CRR formula for European Call Option in CRR model  
- American option
  - Optimal stopping time
  - Price of American call option is equal to the price of European call option: it is optimal to wait
  - Not true for put options - early exercise may be optimal
- Examples of American Call and Put option pricing  


## Sets 7-8: Continuous Time Models  
- We approach the issue from two sides  
- First, we take multi-period model, and discretise time: take small increments. We used CRR model with JR or CRR parameterisation as an example, but we could take more general model and do the same.
- Second, we simply assume that there is a continuous price process, and the log of it follows Brownian motion. It turns out that at the limit we have the same process: CRR model with JR parameterisation gives log-normal distribution of asset price.
  - When doing this second approach we introduce a Wiener stochastic process and demonstrate that it is a martingale
  - We also defie discounted stock price, similar to what we did in discrete time models  


- So, we got the price is log-normally distributed. But we are interested in pricing a derivative. We only considered a European option.
- First, we demonstrated that the European Call option price satisfies Black-Scholes equation. We did it by formulating Feynman-Kac theorem for a Wiener process, which shows that such process satisfies a heat equation. We did simple algebra to formulate this 'heat' equation for a Brownian motion which has drift component.
- Second, we presented Ito formula (without proof) which shows how you should differentiate a function of stochastic process. We then considered a portfolio of a call option and a risky asset (the underlying asset), and derived conditions under which the return on such portfolio is the same as on bonds and so does not have stochastic component (riskless). This condition produces an equation for the price of call option the Black and Scholes equation.  


- The second way of deriving Black-Sholes equation is simple and intuitive. It can easily be generalised for a more general type of underlying asset: dividend-paying, foreign currency, commodity, futures.
- Note that Black-Scholes equation ( a PDE equation for price of financial derivative) is particularly simple for an European call option. It has an analytic solution. Very rarely we can have this. We have written it out.
- We also computed Greeks for the European Call option.  
- We discussed that the implied volatility for Black-Scholes equation is not constant, so Black Scholes equation is likely not to be very accurate description of realistic market price.  

## Computational Examples we studied  
- Single-period models. Arbitrage-free models and models with arbitrage. Pricing of a contingent claim in single-period models  
- Multi-period models, in particular CRR model. European or/and American type contingent claims. Early exercise.
- Continuous time models. Applications of Ito formula. In most cases we do not have a procedure to find an analytical solution to Black and Scholes equation. The most common way is 'guess and verify'.  




<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>