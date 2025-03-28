#definition #GraphTheory 

> [!definition]
> Let $n\in \mathbb{N}$ and $p\in[0,1]$. The ***Erdös-Rényi graph*** $G:=(V:=[n],E)$ is an [[graph|undirected graph]] given by a distribution $G\sim G(n,p)$ where for each $e\in {V \choose 2}$, 
> 1. $\mathbb{P}(e\in E)=p$ for all $e\in {V \choose 2}$
> 2. $\{ \mathbb{1}_{e\in E} \}_{e\in {V \choose 2}}$ are [[Independence|independent]].

^2cce3e

- **Remark**: Notice that $\sigma(G)=\sigma(X_{1},\dots,X_{n})$ where $X_{i}\in \{ 0,1 \}^{i-1}$ where $X_{i,j}=1$ if and only if $\{ i,j \}\in E$. Further, $X_{1},\dots,X_{n}$ are independent.  ^f62064
- **Related definition**: For a graph property $\mathcal{P}$ and $G\sim G(n,p)$, let $f_{\mathcal{P}}(n,p):=\mathbb{P}(G\text{ has }\mathcal{P})$.  ^6823b3
	1. A ***weak threshold*** is a function $p_{0}:\mathbb{N}\to [0,1]$ s.t. for every $\varepsilon>0$ there exists $C>1$ s.t. for every $n$:
		1. $f_{\mathcal{P}}(n,p)<\varepsilon$ for all $p<p_{0}(n)/C$
		2. $f_{\mathcal{P}}(n,p)> 1-\varepsilon$ for all $p>Cp_{0}(n)$.
	2. A ***sharp threshold*** is a function $p_{0}:\mathbb{N}\to [0,1]$ s.t. for every $\varepsilon>0$:
		1. $f_{\mathcal{P}}(p)=\text{o}(1)$ if $p<(1-\varepsilon)p_{0}$ and 
		2. $f_{\mathcal{P}}(p)=1-\text{o}(1)$ if $p>(1+\varepsilon)p_{0}$
---
##### Properties

> [!lemma] Theorem 1 (Vertex Exposure Martingales)
> Let $f$ be a function on graphs s.t. $\mathbb{E}[\left| f(G) \right|]<+\infty$ for all $n,p$ where $G\sim G(n,p)$. Further, for $V_{i}:=[i]$ and $H_{i}:=G[V_{i}]$, we let $\mathcal{B}_{i}:=\sigma(H_{1},\dots,H_{i})$. Then,
> 1. $X_{i}:=\mathbb{E}[f(G)|\mathcal{B}_{i}]$ defines a [[Martingale|martingale]] called ***vertex exposure***.

^26d955

> [!proof]-
> We have that: $$\mathbb{E}[X_{i}|\mathcal{B}_{i-1}]=\mathbb{E}[\mathbb{E}[f(G)|\mathcal{B}_{i}]|\mathcal{B}_{i-1}]=\mathbb{E}[f(G)|\mathcal{B}_{i-1}]=X_{i-1}$$

^f425df

---
> [!lemma] Theorem 2 (Triangle Free Random Graphs)
> Let $G \sim G(n,p)$. 
> 1. if $p=\text{o}(n^{-1/2})$ then $\mathbb{P}(G\text{ is triangle-free})=e^{-(1+\text{o}(1))n^3 p^3 /6}$

> [!proof]-
> https://ocw.mit.edu/courses/18-226-probabilistic-methods-in-combinatorics-fall-2022/mit18_226_f22_lec16-17.pdf

---
> [!lemma] Theorem 3 (Bollobás, 1981)
> Let $H$ be a graph. Let $m(H):= \max_{H'\subseteq H} e_{H'} / v_{H'}$. Then, 
> 1. $p_{0}=n^{-1/m(H)}$ is a sharp threshold for containing $H$ as a subgraph.

> [!proof]+
> Let $H'$ be the subgraph of $H$ achieving the maximum. Let $X$ denote the number of copies of $H$ in $G\sim G(n,p)$. 
> 
> Let $\varepsilon>0$. If $p<(1-\varepsilon)n^{-1/m(H)}$, then: 
> 1. $f_{\mathcal{P}}(n,p)=\mathbb{P}(X\geq 1)\leq \mathbb{E}[X]={n \choose v_{H}}p^{e_{H}}<{n \choose v_{H}}(1-\varepsilon)^{e_{H}} n^{-1/m(H)}<$
---
##### Examples
> [!h] Example 1 (Random graph containing K4)
> We have that:
> 1. $p_{0}=n^{-2/3}$ is a weak threshold for containing $K_{4}$.

^a1d995

> [!proof]-
> Let $X$ be the number of $K_{4}$ in $G\sim G(n,p)$. Then, 
> 1. $\mathbb{E}[X]={n \choose 4}p^6$ and 
> 2. Let $S,T\in {[n] \choose 4}$. Then, let $X_{S},X_{T}$ be the indicator variables that $G[S]$ and $G[T]$ are cliques.  Then, $$\text{Cov}(X_{S},X_{T})=\begin{cases} p^6-p^{12}&S=T\\p^9-p^{12}&\left| S\cap T \right| =3\\p^{11}-p^{12}&\left| S\cap T \right| =2\\0&\text{otherwise}\end{cases}$$However, for any $k\in\{ 0,1,2,3,4 \}$, the number of ordered pairs $(S,T)$ s.t. $\left| S\cap T \right|=k$ is given by $${n \choose 4}{n -4 \choose 4-k}<n^{8-k}$$Therefore, $$\text{Var}(X)<p^6n^4-p^{12}n^4+p^9 n^5-p^{12}n^5+p^{11}n^6-p^{12}n^6<p^6n^4+p^9 n^5+p^{11}n^6$$
>    
> 
> Let $\varepsilon>0$. Choose $C>\left( \frac{1}{\varepsilon} \right)^{1/6}$. Then, for all $p<p_{0} / C=n^{-2 /3} / C$, we have that: $$f_{\mathcal{P}}(n,p)=\mathbb{P}(X\geq 1)\leq \mathbb{E}[X]={n \choose 4} p^6 <n^4 p^6<\frac{1}{C^6}<\varepsilon$$and for $p>Cp_{0}=Cn^{-2 / 3}$ with $C>4^8\cdot 3 / \varepsilon$, $$\begin{align}1-f_{\mathcal{P}}(n,p)&=\mathbb{P}(X= 0)\leq \frac{\text{Var}(X)}{\mathbb{E}[X]^{2}}<4^8\cdot \frac{p^6n^4+p^9 n^5+p^{11}n^6}{n^8 p^{12}}\\&<4^8\left( \frac{1}{n^4p^6}+\frac{1}{n^3p^3}+\frac{1}{n^2p} \right)\\&\leq 4^8\left( \frac{1}{C^6}+\frac{1}{C^3n}+\frac{1}{Cn^{4/3}} \right)\\&<4^8\cdot 3 \frac{1}{C}<\varepsilon\end{align}$$Therefore, by taking the maximum $C$, $p_{0}$ is a weak threshold.

^fd55e7

---
