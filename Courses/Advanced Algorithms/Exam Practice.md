##### Problem 3
We have that:
1. We will use a DP and rounding to solve the problem. Let $n=\left| V \right|$ and $m=\left| E \right|$. Further, let $d:= \varepsilon  \frac{w_{\max}}{k}$ and let $w'_{j}:=d\left\lceil w_{j} / d\right\rceil$. 

3. Root the tree $G$ at the destination node $v^{*}$. Then, for any subtree rooted at $v\in V$ define: $$\text{DP}[v,]=\max\sum_{j\in[k]}^{}t_{j}\cdot \mathbb{1}_{v_{j}\in T_{v}}\cdot \mathbb{1}_{\exists(v_{j},v)\text{-path }P\text{ with}\min_{e\in P}}$$
4. 