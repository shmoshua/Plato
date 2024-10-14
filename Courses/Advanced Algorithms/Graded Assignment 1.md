#Series #Algorithms 

##### 1. Covering Cliques
We define the following variables:
1. $z_{e}\in \{ 0,1 \}$ for $e\in E$ to denote whether $e\in F$.
2. $q_{e,i}\in \{ 0,1 \}$ for $e\in E$ and $i\in [\ell]$ to denote whether $e\in {V_{i} \choose 2}\cap F$.
3. $p\in \mathbb{Z}$ to denote the size $\left| F \right|$.

Then, $$\begin{align}\text{min}\quad &p\\\text{subject to}\quad&\sum_{e\in E}^{}z_{e}\leq p\\&\sum_{e\in E}q_{e,i}\geq s&&\forall i\in [\ell]\\&q_{e,i}-z_{e}=0&&\forall i\in[\ell], e\in {V_{i} \choose 2}\cap E\\&q_{e,i}=0&&\forall i\in[\ell],e\notin {V_{i} \choose 2}\\&q_{e,i}\in \{ 0,1 \}&&\forall i\in [\ell],e\in E\\&z_{e}\in \{ 0,1 \}&&\forall e\in E\end{align}$$
.
---
Consider the relaxed LP version of the problem, i.e. $q_{e,i},z_{e}\in[0,1]$ for all $e\in E$, $i\in [\ell]$ and $k\in \mathbb{R}$. 

##### Approach 1. 
Take $e\in F$ with probability $z_{e}$. Then, let $X_{i}:=\left| {V_{i}\choose 2}\cap F \right|$. We also define $n_{i}:= \left| {V_{i}\choose 2}\cap E \right|$. Then, We have that $$\mathbb{E}[X_{i}]=\sum_{e\in {V_{i} \choose 2}\cap E}^{}\mathbb{P}(e\in F)=\sum_{e\in {V_{i} \choose 2}\cap E}^{}z_{e}=\sum_{e\in {V_{i} \choose 2}\cap E}^{}q_{e,i}$$

 $$\mathbb{P}(X_{i}\leq s-1)=\mathbb{P}(n_{i}-X_{i}\geq n_{i}-s-1 )\leq\frac{n_{i}-\mathbb{E}[X_{i}]}{n_{i}-s-1}$$
 
 Therefore, $$\mathbb{P}(\exists i\in [\ell]:X_{i}<s)\leq \sum_{i=1}^{\ell}\frac{n_{i}-\mathbb{E}[X_{i}]}{n_{i}-s-1}$$

Therefore, $$\mathbb{P}(\exists i\in [\ell]:X_{i}<s)\leq \sum_{i=1}^{\ell}\frac{m-\mathbb{E}[X_{i}]}{m-s-1}=\frac{m-\sum_{i=1}^{\ell}\sum_{e\in{V_{i} \choose 2}\cap E }^{}q_{e,i}}{m-s-1}$$

$$\mathbb{E}[\left| F \right|]=k^{*}\cdot \mathbb{P}(\forall i\in [\ell]:X_{i}\geq s)+$$