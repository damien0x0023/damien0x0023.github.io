---
layout: post
title: Investment, Finance and Asset Prices - Unit 6 Investment Fixed Costs and Irreversibility
subtitle: 投资，金融与资产定价之（六）投资固定成本与不可逆性
category: money
tags: [ECON5068]
---

# Unit 6 Investment Fixed Costs and Irreversibility

translated by damien from sildes of Sisi Ramanan

## 1. Non-Convex Cost and Investment

The key assumption in the Investment-Q model is that adjustment costs are convex. 
For example, \\(AC_t=\frac {φ}{2}I ^2 _t\\) , a quadratic function is a common assumption.
This assumption implies that the investment rule is *continuous* and *smooth*.
- Since the adjustment function is convex, firms want to avoid large changes in investment as the cost rises at an increasingrate.

Is this the only cost faced by firms when investing?

Think about investment at a factory or plant, expanding capacity. In addition to the standard convex cost, firms/plants face:
1. Disruption costs from replacing existing capital.
2. Costly learning as the structure of production might have changed.
3. Delivery lags and time to build delays.
4. Irreversibility of projects due to lack of secondary market for capital goods.  

Microeconomic evidence from plant level data indicate investment is lumpy. 
**Lumpy** \\(\implies\\) Investment inaction followed by investment bursts.
This evidence suggests convex adjustment costs may not be the whole story in terms of capital adjustment.

![]({{site.url}}/assets/images/2020/business/InvestmentRateDistribution.png "Investment Rate Distribution")

![]({{site.url}}/assets/images/2020/business/sumStat.png "TABLE1. Summary statistics")

Longitudinal Research Database

7000 large manufacturing plants that were continually in operation betweeen 1972 and 1988.
This is the highest level of disaggregation, since a firm is a collection of plants.

First, notice the shape of the distribution: not symmetric, rather skewed to the right
- If these data were generated from a model with convex adjustment cost \\(\implies\\) distribution would be symmetric (bellshaped).

Second, there are periods of investment inaction, 8% of observations, plants do nothing.
Again, with convex adjustment costs only there will be no periods of inaction
- Plant will be doing a little bit of investment in all periods.

Third, there is asymmetry: 80% of observations entail positive investment rate, while only 10% of observations entail negative investment rate
- Suggests firms really dislike selling capital.

The message from this data is that firms likely face more than just convex adjustment costs.
Fixed costs of adjustment (in combination with convex adjustment costs) can explain these patterns of adjustment much better than convex costs alone.
In addition to fixed costs, firms may face irreversibiility.

## 2. Irreversibility and Investment

**Irreversibiility**: The purchase price of capital is significantly higher than the resell price.
This is very likely to be the case if capital goods are firm or industry specific.
We combine fixed costs and irreversibility under the general concept of non-convex adjustment costs.

Cooper and Haltiwanger consider a dynamic programming problem specified at the plant level as:

$$
V(A,K,p) = \max \{ V ^i (A,K,p), V ^a(A，K，p) \} \text{ for all } (A,K,p)
$$

&emsp;where \\(V ^a\\) is the value of the firm when it invests actively and \\(V ^i\\) is the value of inactivity (no investments).

The optimal value of the firm is the maximum of these two **options**. These options in turn are defined by:

$$
V ^i(A,K,p) = \pi (A,K) + \beta E _{A', p'|A,p} V(A',K(1-\delta),p')
$$

and

$$
V ^a(A,K,p) = \max _{K ^{'}} [\pi (A,K)λ − FK − p(K ^′−(1−\delta)K) + \beta E_{A', p'|A,p} V(A ^′,K ^′,p′)]
$$

Here there are two costs of adjustment that are independent of the level of investment activity.

The **first** is a loss of profit \\(= (1−\lambda)\\).
This is intended to capture an opportunity cost of investment in which the plant must be shut down during a period of investment activity.

The **second** non-convex cost is \\(FK\\).
The inclusion of \\(K\\) here is intended to capture the idea that these fixed costs, while independent of the current level of investment activity, may have some scale aspects to them.
The relative price of capital \\(p\\) is also allowed to vary.

How does the policy function for investment looks in this case? How does it compare relative to the function obtained under a convex cost only?

The key feature of the investment functionis that it will entail jumps. 
How?
Invest when it is important (low \\(K\\)), invest in bursts to avoid paying the fixed cost more than once.

![]({{site.url}}/assets/images/2020/business/optimalFirmValue.png "Optimal Value of the Firm")

![]({{site.url}}/assets/images/2020/business/InvestmentCashflow.png "Investment and Cashflow")

We have not distinguished between buying and selling price of capital.
There are several frictions present in the market for used capital that makes them imperfectly suitable for uses at other production sites.
To allow for this **partial irreversibility**, we alter our optimization problem to distinguish the buying and selling prices of capital.

The value function now becomes,

$$
V(A,K) = \max \{V ^b (A,K), V ^s (A,K), V ^i (A,K) \}
$$

&emsp;for all \\((A,K)\\) where the superscripts “b” refer to buying capital, “s” indicates that the firm is selling capital and “i” suggests inaction.

These options care then given by

$$
V ^b (A,K) = \max _{I} \pi (A,K) − I - \beta E_{A'|A} V(A^′,K^′(1-\delta)+I)
$$

$$
V ^s (A,K) = \max _{R} \pi (A,K) − p _s R - \beta E_{A'|A} V(A^′,K^′(1-\delta)-R)
$$

and

$$
V ^i (A,K) = \pi (A,K) − I - \beta E_{A'|A} V(A^′,K^′(1-\delta))
$$

Under the buy option, the plant obtains capital at a cost normalized to one.
Under the sell option, the plant retires \\(R\\) units of capital at a price \\(p_s\\).
The third option is inaction so that the capital stock depreciates at a rate of \\(δ\\).
Intuitively, the gap between the buying and selling price of capital will produce inaction.

Suppose that there is an adverse shock to the profitability of the plant.
If this shock was known to be temporary, then selling capital and repurchasing it in the near future.
...would not be profitable for the plant as long as \\(P_s<1\\).
Thus the manager of the plant does nothing, that is we observe inaction.
Under the convex cost case, (with \\(p_s= 1\\)) an adverse shock to profitability would imply downsizing (selling capital).

How important is investment irreversibility?

When capital goods are highly specialized on industry specific firms may find that reversing an investment decision is imposssible or costly (different between the purchase price and resale price of capital).
Irreversibility may generate a “reluctance to invest”.
Firm hesitates to invest today because of the possibility that it may wish to sell capital in the **uncertain** future but will recover little if any of the undepreciated asset value.


## 3. Further Reading

- Cooper and Haltiwanger (2006), On the Nature of Capital Adjustment Costs, Review of Economic Studies

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>