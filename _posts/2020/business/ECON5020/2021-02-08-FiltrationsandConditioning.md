---
layout: post
title: Mathematical Finance - Unit 4 Filtrations and Conditioning
subtitle: 金融数学（三）单期市场模型
category: money
tags: [ECON5020]
---
  
# Unit 4 Filtrations and Conditioning
Uploaded by eva 



## 1 New Features  
- Two important new features of multi-period market models:
  - Investors can trade in assets at any specific time \\(t \in \\{0,1,2,...,T\\}\\) where T is the horizon date.
  - Investors can gather information over time, since the fluctuations of asset prices can be observed.
- We have to determine how the level of information evolves over time.
- The latter aspect leads to the probabilistic concepts of \\(\sigma\\)-fields and filtrations.  


## Example  

- In one-period model we have the set of possible events (states of nature) \\(\Omega = \\{\omega_1,\omega_2\\}\\) at time t = 0, and at time t = 1 we know which state of nature realised. \\(\\{\omega_1,\omega_2\\} = \\{'up', 'down'\\}\\)
- In multi-period model the structure of information is more comlex
  - We start with W = A0 = fw1, ...,wk , ...g the set of all possible states of nature.  

  $$  
  (A_0 = \\{'up \  \text{at}\  \  t=1','down \ \text{at}\ \ t=1','up \ \ \  \text{at}\ \ t=2',,'down \  \text{at}\ \ t=2',...\\} 
  $$  
  - at each next period t > 0 we know that some events will never realise,\\(A_t \subseteq A_{t-1} \subseteq  ... \subseteq A_1 \subseteq A_0 \\).  

  $$  
  (A_1 = \\{'down \ \text{at}\ \ t=1','up \ \ \  \text{at}\ \ t=2',,'down \  \text{at}\ \ t=2',...\\} \subseteq A_0 )
  $$
So we may denote complement set \\(A_t^c = \Omega \ A_t\\) which containes all states of nature which are ruled out at time t.  


!["FIG.1"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC1.png "FIG.1")  

!["FIG.2"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC2.png "FIG.2")   

### Example 5.4: Stock Price Model  

!["FIG.3"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC3.png "FIG.3")  

### Example: Stock Price Model  

!["FIG.4"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC4.png "FIG.4")  

!["FIG.5"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC5.png "FIG.5")  

!["FIG.6"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC6.png "FIG.6")  


## 1.Partitions and \\(\sigma\\)-Fields  

### 1.1 \\(\sigma\\)-Fields  

- The model of information structure can be described using sequence of partitons, where each partition becomes finer. Or it can be described using trees.  

- The concept of a \\(\sigma\\)- field can be used to describe the amount of information available at a given moment.  

- Let \\(N = \\{1, 2, ...\\}\\) be the set of all natural numbers.  
- It follows that the empty set belongs to \\(F:\varnothing  = \Omega^c \in F\\)  

- So, we have defined algebra: zero element is there, the inverse element is there, and an operation is defined.  

- Moreover, it is a field as two operations (sum=union and multiplication=intersection) are defined, existence of inverse operation. Most of the literature uses \\('\sigma-algebra'\\)rather than \\(\sigma\\)-field.  

### 1.2 Interpretation of a \\(\sigma\\)-Fields  

- Many different \\(\sigma\\)-Fields can be defined on one set W.  
- The set of information has to contain all possible states, so that we postulate that W belongs to each \\(\sigma\\)-Fields.  
- Any set \\(A \in F\\) is interpreted as an observed event.  
- If an event \\(A \in F\\) is given, that is, some collection of states is given, then the remaining states can also be identified and thus the complement \\(A^c\\) is also an event.  
- The idea of a \\(\sigma\\)-Fields is to model a certain level of information.  
- We will later introduce a concept of an increasing flow of information, formally represented by an ordered family of \\(\sigma\\)-Fields.  

### 1.3 Probability Measure  

!["FIG.7"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC7.png "FIG.7")  

- Note that \\(P(\varnothing) = 0 \\) due to the definition of probability measure.
- By convention, the probability of all possibilities is 1.
- Probability should satisfy \\(\sigma\\)-\additivity.  

### 1.4 Example: \\(\sigma\\)-Fields  

!["FIG.7"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC7.png "FIG.7")  

### 1.5 Example: Probability Measure  

!["FIG.8"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC8.png "FIG.8")  


### 1.6 Partitions  

!["FIG.10"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC10.png "FIG.10")   


### Partition Associated with a \\(\sigma\\)-Field   

!["FIG.11"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC11.png "FIG.11")  

Further properties of partitions:
- If W is **countable** then for any \\(\sigma\\)-Fields F there exists a unique partition P of \\(\Omega\\) associated with F. It is also clear that this partition generates F, so that \\(F = \sigma(P)\\)
- The sets \\(A_i\\) in a partition must be smallest, specifically, if \\(F = \sigma(P)\\) and \\(A \in F\\) is such that \\(A  A_i \\)then \\(A = A_i\\) .
- The probability of any \\(A \in F\\) equals the sum of probabilities of \\(A_{iS}\\) in the partition generating F, specifically,  

$$  
A = \bigcup_ {i \in j} A_i \Rightarrow P(A)= \Sigma_{i \in J} P (A_i)  
$$  

### Example: Partition Associated with a \\(\sigma\\)-Field  

!["FIG.12"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC12.png "FIG.12")  


### Random Variable and Measurability  

Let F be an arbitrary \\(\sigma\\)-Field of subsets of W. In the next definition, we do not assume that the sample space is discrete.

!["FIG.13"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC13.png "FIG.13")












\\(\Omega = \\{\omega_1,\omega_2, . . . ,\omega_k\\}\\)














Outline
We will examine the following issues:
1.Partitions and \\(\sigma\\)-Fields
2.Filtrations and Adapted Stochastic Processes
3.Conditional Expectations
4.Change of a Probability Measure


  










<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>