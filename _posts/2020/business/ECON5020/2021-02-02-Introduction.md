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
share 1
bond  

\to sell bond at time 0 and buy more shares 1 at time 1
share 1
bond

! sell shares at time 0 and buy more bonds at time 1
As we are selling, coe¢ cients ai which describe proportion of money
invested into assets will be negative (compare with the case when no short
selling is allowed).




<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>