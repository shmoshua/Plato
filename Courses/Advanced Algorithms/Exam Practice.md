##### Problem 3
We have that:
1. Firstly, we sort the weights and assume that $w_{i}\leq w_{i+1}$ for all $i$. Then, we will use a DP and rounding to solve the problem. Let $n=\left| V \right|$ and $m=\left| E \right|$. We first have the following assumption:
	1. **Assumption 1:** the algorithm knows $x$ s.t. $\text{OPT}(B)\leq x\leq 2\text{OPT}(B)$.
   
   Let $d:= \varepsilon x / m$ and let $w'_{j}:=d\left\lceil w_{j} / d\right\rceil$. Further, let $D:=\{ 0,d,2d, \dots,{\left\lceil 2x / d\right\rceil}d \}$. Now,  root the tree $G$ at the destination node $v^{*}$. For any $v\in V$, let $T_{v}$ denote the subtree rooted at $v$. For all $v\in V$, $c\in D$ and  $$\text{DP}[v,c,p]=\max_{r:\sum_{e\in E(T)}r_{e}\leq c}\sum_{j\in[p]}^{}t_{j}\cdot \mathbb{1}_{v_{j}\in T_{v}}\cdot \mathbb{1}_{\min_{e\in P_{v_{j}v}}r_{e}\geq w'_{j}}$$
   Let $\text{child}(v)=\{ w_{1},\dots,w_{\ell} \}$. Then, we compute $\text{DP}[v,c,p]$ using another DP table $\text{DP}_{2}$ where: $$\text{DP}_{2}[i,c,p]=\max_{r:\sum_{q\leq i}^{}\sum_{e\in E(T_{w_{q}})}r_{e}\leq c}\sum_{j\in[p]}^{}t_{j}\cdot \mathbb{1}_{v_{j}\in T_{v}}\cdot \mathbb{1}_{\min_{e\in P_{v_{j}v}}r_{e}\geq w'_{j}}$$ $$\text{DP}[i,c,p]=$$Notice that there are $O\left( \frac{nm}{\varepsilon} \right)$ states the compute in total and for each state, we need 

---


Let $p\geq \frac{c\log n}{\varepsilon^{2}n}$.

For $e\in{[n] \choose 2}$, let $X_{e}$ denote the indicator variable whether $e\in G$. Further, for any $S\subseteq V$ with $\left| S \right|=: k\leq n /2$, we denote $X_{S}:=\sum_{e\in E_{K_{n}}(S , V \backslash S)}^{}X_{e}$. 

We first see that as $\left| X \backslash S \right|\geq n / 2$, 
1. $\mathbb{E}[e_{G}(S , V \backslash S)]=\mathbb{E}[X_{S}]= p\left| S \right|\left| X \backslash S \right|\geq \frac{pkn}{2}$.

Therefore, using Chernoff, we have that: $$\mathbb{P}(\left|X_{S}-\mathbb{E}[X_S] \right|> \varepsilon \mathbb{E}[X_{S}] )\leq 2 \exp \left( -\frac{\varepsilon^{2} \mathbb{E}[X_{S}]}{3} \right)\leq2 \exp \left( -\frac{\varepsilon^{2}pkn}{6} \right)\leq 2 n^{-ck/6}$$Then, if $c\geq 12$, then:$$\mathbb{P}(\exists \text{bad cut})\leq\sum_{k=1}^{n/2}{n \choose k}2n^{-2k }\leq 2\sum_{k=1}^{n / 2}n^{-k}\leq \frac{2}{n-1}=o(1)$$.

