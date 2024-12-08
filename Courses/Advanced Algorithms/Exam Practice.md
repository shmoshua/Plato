##### Problem 3
We have that:
1. We will use a DP and rounding to solve the problem. Let $n=\left| V \right|$ and $m=\left| E \right|$. We will first solve the problem with the following assumption:
	1. **Assumption 1:** the algorithm knows $x$ s.t. $\text{OPT}(B)\leq x\leq 2\text{OPT}(B)$.
   
   Let $d:= \varepsilon x / m$ and let $w'_{j}:=d\left\lceil w_{j} / d\right\rceil$. Further, let $D:=\{ 0,d,2d, \dots,{\left\lceil 2x / d\right\rceil}d \}$. Now,  root the tree $G$ at the destination node $v^{*}$. For any $v\in V$, let $T_{v}$ denote the subtree rooted at $v$. For all $v\in V$ and $c\in D$, $$\text{DP}[v,c,]=\max_{r:\sum_{e\in E(T)}r_{e}\leq c}\sum_{j\in[k]}^{}t_{j}\cdot \mathbb{1}_{v_{j}\in T_{v}}\cdot \mathbb{1}_{\min_{e\in P_{v_{j}v}}r_{e}\geq w'_{j}}$$
   Let $\text{child}(v)=\{ w_{1},\dots,w_{\ell} \}$. Then, we compute: $$\text{DP}[v,c]=\max_{\begin{subarray}{c}r_1,\dots,r_{\ell},c_{1},\dots,c_{\ell}\in D\\c_{1}+\dots+c_{\ell}\leq c\end{subarray}}\sum_{i=1}^{\ell}\text{DP}[w_{i},\max\{c_{i}-r_{i},0\}]\cdot \mathbb{1}_{\forall v_{j}\in T_{w_{i}}:\min_{e\in P_{v_{j}v}}r_{e}\geq w'_{j}}$$Notice that there are $O\left( \frac{nm}{\varepsilon} \right)$ states the compute in total and for each state, we need 
1. 