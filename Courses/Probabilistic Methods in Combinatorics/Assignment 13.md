#Definition #ProbabilisticMethods 

##### Problem 1
Let $\mathcal{S}$ denote the set of all non-trivial 3-term arithmetic progressions on $[n]:=\{ 0,1,\dots,n-1 \}$. Then, 
$$\left| \mathcal{S} \right| =\sum_{i=2}^{n-1}\sum_{j= i /2}^{i-1}1\leq\sum_{i=2}^{n-1} \frac{i}{2}= \frac{n-2}{4}(n+1)\leq \frac{n^2}{4}$$
Now let $s\in \mathcal{S}$, let $B_{s}$ denote the event that the three terms are in $A$. Let $X:=\sum_{s\in \mathcal{S}}^{}\mathbb{1}_{B_{s}}$. Then, 
1. $\mu=\left| \mathcal{S} \right|/ p^3\leq \frac{n^2}{4p^3}$.
2. Further, for distinct $s,t\in \mathcal{S}$ we have that $B_{s}\cap B_{t}$ if they share a term. Hence, $$\sum_{(s,t):s \sim t}^{}\mathbb{P}(B_{s}\cap B_{t})=\sum_{(s,t):s \sim t}^{}$$ 

---
##### Problem 2
Wlog assume that $6$ divides $n$. 
