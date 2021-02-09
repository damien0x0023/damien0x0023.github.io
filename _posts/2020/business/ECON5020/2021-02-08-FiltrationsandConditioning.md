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


### 1.7 Partition Associated with a \\(\sigma\\)-Field   

!["FIG.11"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC11.png "FIG.11")  

Further properties of partitions:
- If W is **countable** then for any \\(\sigma\\)-Fields F there exists a unique partition P of \\(\Omega\\) associated with F. It is also clear that this partition generates F, so that \\(F = \sigma(P)\\)
- The sets \\(A_i\\) in a partition must be smallest, specifically, if \\(F = \sigma(P)\\) and \\(A \in F\\) is such that \\(A  A_i \\)then \\(A = A_i\\) .
- The probability of any \\(A \in F\\) equals the sum of probabilities of \\(A_{iS}\\) in the partition generating F, specifically,  

$$  
A = \bigcup_ {i \in j} A_i \Rightarrow P(A)= \Sigma_{i \in J} P (A_i)  
$$  

### 1.8 Example: Partition Associated with a \\(\sigma\\)-Field  

!["FIG.12"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC12.png "FIG.12")  


### 1.9 Random Variable and Measurability  

Let F be an arbitrary \\(\sigma\\)-Field of subsets of W. In the next definition, we do not assume that the sample space is discrete.

!["FIG.13"](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC13.png "FIG.13")  

#### Example  

!["FIG.14](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC14.png "FIG.14")   


!["FIG.15](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC15.png "FIG.15")  


### 1.10 Information Flow: Filtration
- In a typical application, the information about random events increases over time.  

- To model the information ow, we introduce the concept of a **filtration**.  

- The following definition covers the cases of the discrete and
continuous time.  

!["FIG.16](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC16.png "FIG.16")  

- We interpret the \\(\sigma\\)-Field \\(F_t\\) as the information available to an agent at time t. In particular, \\(F_0\\) represents the information available at time 0, that is, the initial information.
- We assume that the information accumulated over time can only grow, so that we never forget anything!  

## 2.Filtrations and Adapted Stochastic Processes
### 2.1 Stochastic Process  

!["FIG.17](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC17.png "FIG.17")   

#### Example 5.4: Stock Price Model

!["FIG.18](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC18.png "FIG.18")  


!["FIG.19](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC19.png "FIG.19")  


### 2.2 Filtration Generated by a Stochastic Process
- A filtration construced in previous example is said to be **generated** by the stochastic process.
- It is the coarsest one possible, i.e. the various algebras have the fewest possible subsets such that the stochastic process under discussion is adapted.  
- Notation: Let \\(X=(X_t)_{0 \le t \le T}\\) be a stochastic process on the probability space \\((\Omega,F,P)\\).  
\\(F^X = (F_t^X)\\) \\(0 \le t \le T\\)is the filtration **generated** by the process X.
- But there is another way to construct the securities market model, see the next slide.  

#### Example: Stock Price Model

!["FIG.20](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC20.png "FIG.20")  

## 3.Conditional Expectations

### 3.1 Conditional Expectation in Elementary Probability Theory
Sample space \\(\Omega\\) is finite.  


!["FIG.21](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC21.png "FIG.21")  


!["FIG.22](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC21.png "FIG.22")  


### 3.2 Conditional Expectations
- Let \\((\Omega,F,P)\\) be a finite (or countable) probability space.
- Let X be an arbitrary F-measurable random variable.
- Assume that G is a s-field which is contained in F.
- Let \\((A_i )_{i \in I}\\) be the unique partition associated with G.
- Our next goal is to define the **conditional expectation** \\(E_P(X | G)\\),that is, the conditional expectation of a random variable X with respect to a \\(\sigma\\)-Field G.  


We work with stochastic processes defined on a filtered probability space need to define \\(E_P(X| G)\\). It is convenient to use \\(E_P(X| G)\\) as a sum of all conditional expectations of the form \\(E_P(X| A)\\) as the event A runs through the algebra G.
We can see that  

$$  
E_p(X|G) 1_A = E_p (X|A) for \ all \  A \in P  
$$
where P is partition of \\(\Omega\\) that corresponds to G.  

!["FIG.23](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC23.png "FIG.23")  

This generalises the definition of conditional expectation to probability spaces when \\(\Omega\\) is not finite.  


- E_P(X | G) is G-measurable random variable
- E_P(X | G) is the best estimate of X given the information represented by the \\(\sigma\\)-Field G.  
- The following identity uniquely characterises the conditional expectation (in addition to G-measurability):  

!["FIG.24](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC24.png "FIG.24")   

!["FIG.25](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC25.png "FIG.25")  

#### Example 5.5: Conditional Expectation  

!["FIG.26](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC26.png "FIG.26")  

#### Example: Conditional Expectation  

!["FIG.27](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC27.png "FIG.27")   

!["FIG.28](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC28.png "FIG.28")  

!["FIG.29](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC29.png "FIG.29")  


## 4.Change of a Probability Measure

### 4.1 Change of a Probability Measure
- Let P and Q be equivalent probability measures on \\((\Omega,F)\\).
- Let the density of Q with respect to P be 

$$
\frac {d Q}{d P} (\omega) = L (\omega)
$$

meaning that L is F-measurable and, for every \\(A \in F\\),   

$$    
\int_{A} X dQ = \int_{A} XL\  dP
$$  

- If \\(\Omega\\) is finite then this equality becomes   

$$  
\Sigma_{\omega \in A} X(\omega) Q(\omega)= \Sigma_{\omega \in A} X(\omega) L(\omega) P(\omega)
$$  

- Random variable L is strictly positive and \\(E_P(L) = 1\\).
- Equality \\(E_Q(X) = E_P(XL)\\) holds for any Q-integrable random variable X (it suffices to take A = \\(\Omega\\)).  

### 4.2 Abstract Bayes formula

!["FIG.30](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC30.png "FIG.30")  

### 4.3 Martingales  

**Martingales** are stochastic processes representing **fair games**.  

!["FIG.31](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC31.png "FIG.31")  


!["FIG.32](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/ECON5020/FiltrationsandConditioning/FC32.png "FIG.32")









\\(\Omega = \\{\omega_1,\omega_2, . . . ,\omega_k\\}\\)



  










<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>