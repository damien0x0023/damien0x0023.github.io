---
layout: post
title: Investment, Finance and Asset Prices - Unit 5 Stock Market Bubbles and Investment
subtitle: 投资，金融与资产定价之（四）股票市场的泡沫与投资
category: money
tags: [ECON5068]
---

# Unit 5 Stock Market Bubbles and Investment

translated by damien from sildes of Sisi Ramanan

## Lecture Overview

1. Stock Market Bubbles and Investment

2. Campello and Graham empirical study

3. Further Reading:
- Campello and Graham 2007, ”DO STOCK PRICES INFLUENCE CORPORATE DECISIONS? EVIDENCE FROM THE TECHNOLOGY BUBBLE”, NBER.

## Asset Return: Facts

- High average stock returns, high volatility of stock returns.

- Low averge return on bonds (T-bills), low volatility of return on bonds

- Based on 1947-2008 real (after-tax) U.S. Data:
    1. The expected return on stocks is 8% while for bonds is 1%.  
    2. The standard deviation of stock returns is 17% while for bonds is 2%.

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/marketValueOf1Dollar1960.png "Market Value of 1$ invested in Tbills, Tbonds or Stocks in 1960")

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/marketValueOf1Dollar1995.png "Market Value of 1$ invested in Tbills, Tbonds or Stocks in 1995")

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/stockMarketEmployment.png "Stock marked and Employment")

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/stockMarketIP.png "Stock marked and IP")

**Investment and Q**

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/NonresFixedIdivKandQ.png "Nonres. Fixed I/K and Q")

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/Correlation.png "Correlation (Investment, Earnings Growth Forecast)")

Stock market seems to forecast quite well
1. Employment

2. Industrial Production

3. **Investment**

Is all the movement in stock prices due to fundamentals? 
If not, why does investment respond to non-fundamental movements?

What do we mean by non-fundamental movements in stock prices. 
Value of firm, V measures the expected discounted sum of dividends. 
A stock is a claim on the value (equivalently assets) of the firm, thus stock price is simply,
$$
    p = V/N = \text{Value of firm}/\text{Number of stocks}
$$
Thus, in theory all the movement in the stock market is fundamental:
$$
    V = p ∗ N
$$
Does this equality hold in practice?

## Stock Market Bubbles

Can all of the movements be accounted by fundamentals? 
Robert Shiller argues **NO**. 
Shiller’s argument is that stock prices contain bubbles. 
Consider a stock that pays dividends, dt every period. The fundamental price is then given by:
$$
    P_t = E_t \left [ \sum ^{\infty} _{s=t+1} m_s d_s \right]
$$

Thus, stock prices should vary closely with dividends. 
Shiller in a series of papers published in the early 1980’s finds that stock prices move too much to be justified by changes in dividends. 
Dividends were observed to be very stable while stock prices were not. 
In general, stock prices were found to deviate from fundamentals.
$$
    P_t = E_0 \left [ \sum ^{\infty} _{s=0} \beta^t d_t \right] + Bubble_t
$$

Bubbles can arise from a variety of reasons. 
Example: Bias in investor’s beliefs, some investors are optimistic while some others pessimistic.
The question we are interested in is:

*“Do stock market bubbles affect corporate investment? ”*

## How can bubbles impact investment?

If some firms are financially constrained, a bubble provides an opportunity to issue shares at inflated prices. 
New issues of shares at high prices provides additional income. 
This new income can be utilitized for investments.
Bubbles can thus relax financial constraints.

A clever analysis by Campello and Graham (2007) shows that bubbles affect corporate investment.
The question posed is: *When is mispricing most likely to affect firm policies and which firms are most likely to respond to mis-pricing*

Campello and Graham (2007) focus their empirical analysis in the 1990s.
The 1990s was viewed as a period of technological revolution.
Innovations in computer software, telecoms, Dot-Com startups such as Google, and in general advancements in data processing and storage.

**First**, there was the so called, “DotCom Bubble”: stock prices in the Nasdaq index rose significantly.

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/dotcomBubbleNASDAQ.png "The DotCom Bubble in NASDAQ")

Second, most stock prices (non-tech sectors) indices (notably Dow Jones) rose as well significantly during the decade. 
But firms in the Dow-Jones index did not belong in the tech sectors of the economy where the revolution was taking place. 
A possibility is that investor’s became overoptimistic about equity investments both in the new and old economy stocks.

Campello and Graham focus on firms in the non-tech sectors of the economy: **There is no reason to expect that they have experienced changes in their fundamentals.**

The empirical strategy is to regress firm investment on
1. A standard proxy for firm market value (\\(Q ^{Mkt} \\))
2. The projection of firm market value on firm and industry fundamentals such as past profitability and sales growth (\\(FundQ\\)).
3. Look at subsets of financially unconstrained and constrained firms.

The basic idea is that once one expunges publicly-available information about capital productivity (\\(FundQ\\) from market prices (\\(Q ^{Mkt} \\)), the remainder should have no explanatory power over firm investment, unless misvaluation affects firm decisions.

**Main Result**

While the non-fundamental component of prices has no effect on the investment of unconstrained non-tech manufacturers, the effect of mis-pricing on the investment of constrained non-tech manufacturers is positive and strong during the tech bubble.

The result is consistent with the hypothesis we articulated earlier: stock market bubbles shift investment spending towards financially constrained firms.

**Data and Analysis**

Identify non-tech/ non-bubble sectors: energy, steel, mining,
chemicals, paper, food and tobacco.

Non-bubble Sectors: Industrial sectors whose business
fundamentals were likely not directly aected by the advances
in telecommunications and data processing of the late 1990s.

Look at historical data of price-earnings ratio and rm level q
(1970 onwards). The series show that during the 1990s
valuations deviate from the historical average.

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/nonBubbleFirmMarketValuation.png "\"Non-Bubble\" Firms' Market Valuation")

Now look at business fundamentals. 
Industry and firm-level data on employment, prices, sales and profitability over the last three decades to check whether these fundamental indicators change around the 1990s tech bubble. 
No evidence that fundamental was significantly changing during the bubble period.

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/nonBubbleFirmFundamentals.png "\"Non-Bubble\" Firms' Fundamentals")

Classify firms in a way that identifies samples of financially constrained vs. unconstrained. 
Several classifications: dividends, size, bond rating.

The baseline regression is of the form:  
$$
    Investment _{it} = a_1 Q ^{Mkt} _{it} + a_2 FundQ _{it} + a_3 CashFlow _{it} + firm_i + year_t + \epsilon _{it}
    \tag{1} \label{baseline}
$$  
Dummy variables \\(firm_i\\) and \\(year_t\\) to capture idiosyncratic variations at the firm level and time variations, respectively.

They first estimate this regression model on a panel dataset of firm variables observed over 30 years.

Result: **Fundamentals drive investment.**

This result is consistent with the Investment-Q theory. 
They find no evidence that mis-pricing affects investment.

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/InvestmentFundamentals1.png "Investment and Fundamentals eq.(I)")

They then estimate a second regression of the form:

$$
    Investment _{it} = a_1 Q ^{Mkt} _{it} + a_2 FundQ _{it} + a_3 CashFlow _{it} + a_4Bubble _t + a_5 (Q ^{Mkt} \times Bubble _t) + firm_i + \epsilon _{it}
    \tag{2} \label{second}   
$$

&emsp; \\(Bubble_t\\) is an indicator variable that takes value 1 during
periods when there is a bubble and 0 when there is no bubble.

This regression focuses on the 1990s when the DotCom
bubble was observed.

The idea behind regression equation \eqref{second} is that . . . 
if manufacturers respond to Bubbles, the estimated coefficient \\( \hat{a _5} \\) should be positive and statistically significant. 
This is exactly what they find.

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/business/InvestmentFundamentals2.png "Investment and Fundamentals eq.(II)")

The estimates imply that the impact of mispricing on the investment of constrained firms was quite pronounced during the Bubble period but not outside of that period. 
For constrained firms, \\( \hat{a _5} \\) is positive and statistically significant. 
The impact of market valuation, given by \\( \hat{a _1} + \hat{a _5} \\) is positive and statistically significant at better than the 5% test level across all constrained partitions.

Sharp contrast with the financially unconstrained firms, the bubble has no impact on the relation between valuation and investment for unconstrained firms. 
Similar findings are also reported by Gilchrist, Himmelberg and Huberman (2005).


<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

