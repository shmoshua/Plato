#definition #GraphTheory 

> [!definition]
> Let $n\in \mathbb{N}$ and $p\in[0,1]$. The ***Erdös-Rényi graph*** $G:=(V:=[n],E)$ is an [[graph|undirected graph]] given by a distribution $G\sim G(n,p)$ where for each $e\in {V \choose 2}$, 
> 1. $\mathbb{P}(e\in E)=p$ for all $e\in {V \choose 2}$
> 2. $\{ \mathbb{1}_{e\in E} \}_{e\in {V \choose 2}}$ are [[Independence|independent]].
- **Remark**: Notice that $\sigma(G)=\sigma(X_{1},\dots,X_{n})$ where $X_{i}\in \{ 0,1 \}^{i-1}$ where $X_{i,j}=1$ if and only if $\{ i,j \}\in E$. Further, $X_{1},\dots,X_{n}$ are independent. 
- **Related definition**: For a graph property $\mathcal{P}$ and $G\sim G(n,p)$, let $f_{\mathcal{P}}(n,p):=\mathbb{P}(G\text{ has }\mathcal{P})$. A ***threshold*** is a function $p_{0}:\mathbb{N}\to [0,1]$ s.t. for every $\varepsilon>0$ there exists $C>1$ with:
	1. $f_{\mathcal{P}}(n,p)<\varepsilon$ for all $p<p_{0}/C$
	2. $f_{\mathcal{P}}(n,p)> 1-\varepsilon$ for all $p>Cp_{0}$.
---
##### Properties

> [!lemma] Theorem 1 (Vertex Exposure Martingales)
> Let $f$ be a function on graphs s.t. $\mathbb{E}[\left| f(G) \right|]<+\infty$ for all $n,p$ where $G\sim G(n,p)$. Further, for $V_{i}:=[i]$ and $H_{i}:=G[V_{i}]$, we let $\mathcal{B}_{i}:=\sigma(H_{1},\dots,H_{i})$. Then,
> 1. $X_{i}:=\mathbb{E}[f(G)|\mathcal{B}_{i}]$ defines a [[Martingale|martingale]] called ***vertex exposure***.

> [!proof]-
> We have that: $$\mathbb{E}[X_{i}|\mathcal{B}_{i-1}]=\mathbb{E}[\mathbb{E}[f(G)|\mathcal{B}_{i}]|\mathcal{B}_{i-1}]=\mathbb{E}[f(G)|\mathcal{B}_{i-1}]=X_{i-1}$$
---
> [!lemma] Theorem 2 (Triangle Free Random Graphs)
> Let $G \sim G(n,p)$. 
> 1. if $p=\text{o}(n^{-1/2})$ then $\mathbb{P}(G\text{ is triangle-free})=e^{-(1+\text{o}(1))n^3 p^3 /6}$

> [!proof]-
> https://ocw.mit.edu/courses/18-226-probabilistic-methods-in-combinatorics-fall-2022/mit18_226_f22_lec16-17.pdf

---
