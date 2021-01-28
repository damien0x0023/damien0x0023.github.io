---
layout: post
title: Investment, Finance and Asset Prices - Unit 6a Investment Fixed Costs and Irreversibility
subtitle: 投资，金融与资产定价之（六a）投资固定成本与不可逆性
category: money
tags: [ECON5068]
---

translated by damien from sildes of Sisi Ramanan

# Unit 6a Investment Fixed Costs and Irreversibility

## 1. Non-Convex Cost and Investment

非凸成本与投资

The key assumption in the Investment-Q model is that adjustment costs are convex. 
For example, \\(AC_t=\frac {φ}{2}I ^2 _t\\) , a quadratic function is a common assumption.
This assumption implies that the investment rule is *continuous* and *smooth*.  
&emsp;&emsp;投资Q模型的关键假设是调整成本是凸的。
例如，\\(AC_t=\frac {φ}{2}I ^2 _t\\)，二次函数是常见的假设。
这个假设意味着投资规则是连续且光滑的。
- Since the adjustment function is convex, firms want to avoid large changes in investment as the cost rises at an increasingrate.  
&emsp;&emsp;由于调整函数是凸函数，企业希望避免随着成本的增加而导致投资的巨大变化。

Is this the only cost faced by firms when investing?  
&emsp;&emsp;这是公司在投资时面临的唯一成本吗？

Think about investment at a factory or plant, expanding capacity. In addition to the standard convex cost, firms/plants face:  
&emsp;&emsp;想想在工厂或工厂投资，扩大产能。除了标准凸成本外，公司/工厂还面临：
1. Disruption costs from replacing existing capital.  
&emsp;&emsp;替换现有资本的中断成本。
2. Costly learning as the structure of production might have changed.  
&emsp;&emsp;随着生产结构的改变，代价高昂的学习。
3. Delivery lags and time to build delays.  
&emsp;&emsp;交付延迟和构建延迟的时间。
4. Irreversibility of projects due to lack of secondary market for capital goods.  
&emsp;&emsp;由于缺乏资本货物二级市场，项目的不可逆转性。  

Microeconomic evidence from plant level data indicate investment is lumpy. 
**Lumpy** \\(\implies\\) Investment inaction followed by investment bursts.
This evidence suggests convex adjustment costs may not be the whole story in terms of capital adjustment.  
&emsp;&emsp;来自工厂层面数据的微观经济证据表明，投资是不稳定的。
**不稳定的** \\(\implies\\) 投资不活跃，接着是投资爆发。
这一证据表明，就资本调整而言，凸形调整成本可能并非全部。

![]({{site.url}}/assets/images/2020/business/InvestmentRateDistribution.png "Investment Rate Distribution")

![]({{site.url}}/assets/images/2020/business/sumStat.png "TABLE1. Summary statistics")

Longitudinal Research Database  
&emsp;&emsp;纵向研究数据库

7000 large manufacturing plants that were continually in operation betweeen 1972 and 1988.
This is the highest level of disaggregation, since a firm is a collection of plants.  
&emsp;&emsp;在1972年至1988年间，7000家大型制造厂一直在运营。这是最高层次的分解，因为企业是工厂的集合。

First, notice the shape of the distribution: not symmetric, rather skewed to the right  
&emsp;&emsp;首先，注意分布的形状：不是对称的，而是向右倾斜的
- If these data were generated from a model with convex adjustment cost \\(\implies\\) distribution would be symmetric (bellshaped).  
&emsp;&emsp;如果这些数据来自凸调整模型，则成本分布将是对称的（钟形）。

Second, there are periods of investment inaction, 8% of observations, plants do nothing.
Again, with convex adjustment costs only there will be no periods of inaction  
&emsp;&emsp;第二，有一段时间投资不活跃，8%的观察，电厂无所作为。同样，只有凸形调整成本，才不会有无所作为的时期
- Plant will be doing a little bit of investment in all periods.  
&emsp;&emsp;这家工厂将在所有时期进行少量投资。

Third, there is asymmetry: 80% of observations entail positive investment rate, while only 10% of observations entail negative investment rate.  
&emsp;&emsp;第三，存在非对称性：80%的观测值需要正的投资率，而只有10%的观测值具有负的投资率。 
- Suggests firms really dislike selling capital.  
&emsp;&emsp;这表明公司确实不喜欢出售资本。

The message from this data is that firms likely face more than just convex adjustment costs.
Fixed costs of adjustment (in combination with convex adjustment costs) can explain these patterns of adjustment much better than convex costs alone.
In addition to fixed costs, firms may face irreversibiility.  
&emsp;&emsp;这一数据传递出的信息是，企业可能面临的不仅仅是凸形调整成本。固定调整成本（与凸调整成本相结合）可以比单独的凸成本更好地解释这些调整模式。除了固定成本外，企业还可能面临不可逆性。

## 2. Irreversibility and Investment

不可逆转性与投资

**Irreversibiility**: The purchase price of capital is significantly higher than the resell price.
This is very likely to be the case if capital goods are firm or industry specific.
We combine fixed costs and irreversibility under the general concept of non-convex adjustment costs.  
&emsp;&emsp;**不可逆性**：资本的购买价格明显高于转售价格。如果资本货物是特定于公司或行业的，这种情况很可能发生。在非凸调整成本的一般概念下，我们将固定成本和不可逆性结合起来。

Cooper and Haltiwanger consider a dynamic programming problem specified at the plant level as:  
&emsp;&emsp;Cooper和Haltiwanger考虑在工厂级指定的动态规划问题为：

$$
V(A,K,p) = \max \{ V ^i (A,K,p), V ^a(A，K，p) \} \text{ for all } (A,K,p)
$$

&emsp;where \\(V ^a\\) is the value of the firm when it invests actively and \\(V ^i\\) is the value of inactivity (no investments).  
其中\\(V ^a\\)是公司积极投资时的价值，\\(V ^i\\)是不活跃（无投资）的价值。

The optimal value of the firm is the maximum of these two **options**. These options in turn are defined by:  
&emsp;&emsp;企业的最优价值是这两种期权的最大值。这些期权依次由以下定义：

$$
V ^i(A,K,p) = \pi (A,K) + \beta E _{A', p'|A,p} V(A',K(1-\delta),p')
$$

and  
&emsp;&emsp;和

$$
V ^a(A,K,p) = \max _{K ^{'}} [\pi (A,K)λ − FK − p(K ^′−(1−\delta)K) + \beta E_{A', p'|A,p} V(A ^′,K ^′,p′)]
$$

Here there are two costs of adjustment that are independent of the level of investment activity.  
&emsp;&emsp;这里有两个独立于投资活动水平的调整成本。

The **first** is a loss of profit \\(= (1−\lambda)\\).
This is intended to capture an opportunity cost of investment in which the plant must be shut down during a period of investment activity.  
&emsp;&emsp;首先是利润损失\\(= (1−\lambda)\\)。这是为了捕捉投资机会成本，在投资活动期间，工厂必须关闭。

The **second** non-convex cost is \\(FK\\).
The inclusion of \\(K\\) here is intended to capture the idea that these fixed costs, while independent of the current level of investment activity, may have some scale aspects to them.
The relative price of capital \\(p\\) is also allowed to vary.  
&emsp;&emsp;第二个非凸成本是\\(FK\\)。这里所包含的这些固定成本\\(K\\)，虽然与当前的投资活动水平无关，但可能有一定的规模因素。资本的相对价格\\(p\\)也允许变动。

How does the policy function for investment looks in this case? How does it compare relative to the function obtained under a convex cost only?  
&emsp;&emsp;在这种情况下，投资政策的作用如何？它与仅在凸代价下得到的函数相比如何？

The key feature of the investment functionis that it will entail jumps. 
How?
Invest when it is important (low \\(K\\)), invest in bursts to avoid paying the fixed cost more than once.  
&emsp;&emsp;投资功能的主要特点是，它将带来跳跃。怎样？避免一次性投资比一次性投资更重要（低\\(K\\)）。

![]({{site.url}}/assets/images/2020/business/optimalFirmValue.png "Optimal Value of the Firm")

![]({{site.url}}/assets/images/2020/business/InvestmentCashflow.png "Investment and Cashflow")

We have not distinguished between buying and selling price of capital.
There are several frictions present in the market for used capital that makes them imperfectly suitable for uses at other production sites.
To allow for this **partial irreversibility**, we alter our optimization problem to distinguish the buying and selling prices of capital.  
&emsp;&emsp;我们没有区分资本的买入价和卖出价。在二手资本市场上存在着一些摩擦，使得它们不完全适合用于其他生产场所。为了考虑到这种**部分不可逆性**，我们改变了我们的优化问题来区分资本的买入价和卖出价。

The value function now becomes,  
&emsp;&emsp;值函数现在变成

$$
V(A,K) = \max \{V ^b (A,K), V ^s (A,K), V ^i (A,K) \}
$$

&emsp;for all \\((A,K)\\) where the superscripts “b” refer to buying capital, “s” indicates that the firm is selling capital and “i” suggests inaction.  
&emsp;&emsp;对于所有的\((A,K)\\)，上标“b”表示买入资本，“s”表示公司在出售资本，“i”表示无所作为。

These options care then given by  
&emsp;&emsp;这些期权由

$$
V ^b (A,K) = \max _{I} \pi (A,K) − I - \beta E_{A'|A} V(A^′,K^′(1-\delta)+I)
$$

$$
V ^s (A,K) = \max _{R} \pi (A,K) − p _s R - \beta E_{A'|A} V(A^′,K^′(1-\delta)-R)
$$

and  
&emsp;&emsp;和

$$
V ^i (A,K) = \pi (A,K) − I - \beta E_{A'|A} V(A^′,K^′(1-\delta))
$$

Under the buy option, the plant obtains capital at a cost normalized to one.
Under the sell option, the plant retires \\(R\\) units of capital at a price \\(p_s\\).
The third option is inaction so that the capital stock depreciates at a rate of \\(δ\\).
Intuitively, the gap between the buying and selling price of capital will produce inaction.  
&emsp;&emsp;在购买期权下，工厂以标准化为1的成本获得资本。在出售期权下，工厂以一定的价格\\(p_s\\)收回\\(R\\) 单位的资本。第三种选择是不采取行动，使股本以\\(δ\\)的比率贬值。直观地说，资金的买卖价格差距会产生不作为。

Suppose that there is an adverse shock to the profitability of the plant.
If this shock was known to be temporary, then selling capital and repurchasing it in the near future.
...would not be profitable for the plant as long as \\(P_s<1\\).
Thus the manager of the plant does nothing, that is we observe inaction.
Under the convex cost case (with \\(p_s= 1\\)), an adverse shock to profitability would imply downsizing (selling capital).  
&emsp;&emsp;假设工厂的盈利能力受到不利冲击。如果这种冲击被认为是暂时的，那么在不久的将来抛售资本并回购。。。如果 \\(P_s<1\\)，工厂就不会盈利了。所以厂长什么也不做，就是我们观察不作为。在凸成本情况下(伴随着 \\(p_s= 1\\))，对盈利能力的不利冲击意味着缩减规模（出售资本）。

How important is investment irreversibility?  
&emsp;&emsp;投资不可逆转有多重要？  
  
When capital goods are highly specialized on industry specific firms may find that reversing an investment decision is imposssible or costly (different between the purchase price and resale price of capital).
Irreversibility may generate a “reluctance to invest”.
Firm hesitates to invest today because of the possibility that it may wish to sell capital in the **uncertain** future but will recover little if any of the undepreciated asset value.  
&emsp;&emsp;当资本货物高度专业化于特定行业时，企业可能会发现，逆转投资决策是不可能的或代价高昂的（资本的购买价格和转售价格不同）。不可逆转性可能导致“不愿投资”。这家公司今天不愿投资，因为它可能希望在**不确定的**未来出售资本，但如果有任何未折旧的资产价值，它几乎不会收回。


## 3. Further Reading

- Cooper and Haltiwanger (2006), On the Nature of Capital Adjustment Costs, Review of Economic Studies

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>