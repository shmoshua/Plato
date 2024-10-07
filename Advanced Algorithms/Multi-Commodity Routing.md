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
> Let $\lambda,\{ x_{ip} \}_{i\in[K],p\in P_{i}}$ be the optimal solution of the LP: $$\begin{align}\text{min}\quad & \lambda\\ \text{subject to}\quad&\sum_{p\in P_{i}}^{}x_{ip}=1&&\forall i\in[K]\\&\sum_{i=1}^{K}\sum_{p:e\in p\in P_{i}}^{}x_{ip}\leq\lambda&& \forall e\in E\\&0\leq x_{ip}\leq 1&&\forall i\in [K], p\in P_{i}\end{align}$$
> Let $p_{i}\in P_{i}$ be chosen with probability $x_{ip}$ and let $y_{ip}=\mathbb{1}_{\{ p=p' \}}$. Then,

> [!proof]-
> We have: $$\mathbb{E}\left[ \sum_{i=1}^{K}\sum_{p:e\in p\in P_{i}}^{} y_{ip} \right]=\sum_{i=1}^{K}\sum_{p: e\in p \in P_{i}}^{} x_{ip} \leq\lambda$$Notice that $\tilde{y}_{i}:=\sum_{p:e\in p\in P_{i}}^{} y_{ip}$ are independent Bernoulli random variables. Then, for $Y:=\sum_{i=1}^{K}\tilde{y}_{i}$, by Chernoff, $$\mathbb{P}(Y\geq(1+9\ln n)\lambda)\leq\mathbb{P}(Y\geq(1+9\ln n)\mathbb{E}[Y])\leq \exp \left( -27 \ln^{2} n\cdot  \mathbb{E}[Y] \right) \leq \exp(-27 \ln^{2} n)?\leq \frac{1}{n^{3}}$$Hence, $\mathbb{P}()$

---
> [!lemma] Theorem 2 (LP)
> Let $f:E \times[K]\to \mathbb{R}$ be the optimal solution of the LP: $$\begin{align}\text{min}\quad & \lambda  \\ \text{subject to}\quad& \sum_{i=1}^{K}f(e,i)\leq\lambda&&\forall e\in E\\&\sum_{e\in \text{out}(s_{i})}^{}f(e,i)-\sum_{e\in \text{in}(s_{i})}^{}f(e,i)=1&&\forall i\in[K]\\&\sum_{e\in \text{out}(t_{i})}^{}f(e,i)-\sum_{e\in \text{in}(t_{i})}^{}f(e,i)=-1&&\forall i\in[K]\\&\sum_{e\in \text{out}(v)}^{}f(e,i)-\sum_{e\in \text{in}(v)}^{}f(e,i)=0&&\forall i\in [K],v\in V \backslash \{ s_{i},t_{i} \}\\&0\leq f(e,i)\leq 1&&\forall e\in E,i\in [K]\end{align}$$For $m:=\left| E \right|$, let $\pi_{i1},\dots,\pi_{i m}$ be the decomposition of the flow $f_{i}$ with weights $w_{1},\dots,w_{m}$. 
