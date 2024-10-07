#Definition #Algorithms 

> [!definition]
> For a [[Graph|directed graph]] $G=(V,E)$ and $(s_{i},t_{i})_{i\in [K]}\subseteq V\times V$ ***routing demands***, 
> 1. the ***minimum congestion multi-commodity routing problem*** aims to find a $s_{i}$-$t_{i}$-path $p_{i}$ for all $i\in [K]$, i.e. $$\{ p_{i}^{\text{OPT}} \}\in \underset{ p_{i}\text{ }s_{i}\text{-}t_{i}\text{-path} }{ \arg\min }\left( \max_{e\in E}\left| \{ i\in [K]: e\in p_{i} \} \right|  \right) $$

---
##### Properties
> [!lemma] Theorem 1
> With the assumptions that:
> 1. for each $i\in [K]$, there exists a polynomial-size set $P_{i}$ of $(s_{i},t_{i})$-paths s.t. $p_{i}^\text{OPT}\in P_{i}$. 
> 
> Let $\{ x_{ip} \}_{i\in[K],p\in P_{i}}$ be the optimal solution of the LP: $$\begin{align}\text{min}\quad & \lambda\\ \text{subject to}\quad&\sum_{p\in P_{i}}^{}x_{ip}=1&&\forall i\in[K]\\&\sum_{i=1}^{K}\sum_{p:e\in p\in P_{i}}^{}x_{ip}\leq\lambda&& \forall e\in E\\&0\leq x_{ip}\leq 1&&\forall i\in [K], p\in P_{i}\end{align}$$
> Let $p_{i}\in P_{i}$ be chosen with probability $x_{ip}$ and let $y_{ip}=\lambda_{pp_{i}}$. Then,

> [!proof]+
> We have: $$\mathbb{E}\left[ \sum_{i=1}^{K}\sum_{p:e\in p\in P_{i}}^{} y_{ip} \right]=\sum_{i=1}^{K}\sum_{p \in P_{i}}^{} x_{ip}\cdot \mathbb{1}_{e\in p}\leq K\cdot \lambda$$