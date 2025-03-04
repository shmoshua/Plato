#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]] on $n$ nodes. For a size $k$ subset $U\subseteq V$, the induced subgraph $G[U]$ is a ***$k$-clique*** if:
> 1. for every $e\in {U \choose 2}$, $e\in E$.

- **Related definition**: If $G=(V,E)$ has a $n$-clique, then $G$ is a ***complete graph*** $K_{n}$. 
- **Related definition**: The ***clique number*** $\omega(G):=\max \{ k\geq 1:G\text{ has a }k\text{-clique}  \}$.
---
##### Properties

> [!lemma] Theorem 1 (Bollobás, Erdös, Matula, 1976)
> Let $G \sim G(n,1 / 2)$ be a [[Erdös-Rényi Graph|random graph]] and $k:=k(n)$ some sequence of positive integers. Let $\mu_{k}:=\mathbb{E}[\#\text{cliques of size }k]$. Then,
> 1. $k_{1}:=\min\{ k:\mu_{k}<1 \}\sim 2\log_{2}n$.
> 1. If $\mu_{k}\to 0$ as $n\to \infty$, then $\omega(G)< k$ w.h.p.
> 2. If $k\sim 2\log_{2} n$ and  $\mu_{k}\to \infty$ as $n\to \infty$, then $\omega(G)\geq k$ w.h.p.
> 3. there exists $k_0\in \mathbb{N}$ s.t. $\omega(G)\in \{k_{0}-1,k_{0}\}$ w.h.p.

^7a36d7

> [!proof]-
> Let $X_{k}$ be the number of cliques of size $k$ of $G$. Then, $X_{k}=\sum_{S}^{}X_{S}$ where $S\in {V \choose k}$ and $X_{S}$ is the indicator variable if $S$ spans a clique or not. Then,$$\mu_{k}:=\mathbb{E}[X_{k}]={n \choose k}2^{-{k \choose 2}}$$
> Then, 
> 1. Notice that $\mu_{k}^{1/k}=\Theta\left( \frac{n}{k}2^{-k/2} \right)$. Let $\varepsilon>0$. If $k\leq (1-\varepsilon)2\log n$, then $2^{-k/2}\geq n^{-(1-\varepsilon)}$ and: $\mu_{k}^{1/k}\geq \frac{C}{\log n}n^{\varepsilon}>1$ for large $n$. Hence, $k<k_{1}$. Similarly, if $k\geq (1+\varepsilon)2\log n$ then $\mu_{k}< 1$ and $k\geq k_{1}$. Therefore, $$1-\varepsilon<\lim_{ n \to \infty } \frac{k_{1}}{2\log_{2}n}\leq 1+\varepsilon$$and $k_{1}\sim 2\log_{2}n$.
> 1. If $\mu_{k}\to 0$, then by Markov: $$\mathbb{P}(\omega(G)\geq k)=\mathbb{P}(X_{k}\geq 1)\leq \mathbb{E}[X_{k}]=\mu_{k}=\text{o}(1)$$
> 2. We consider the setting from [[Variance|Theorem 4]]. For a fixed $S\in {V \choose k}$, we have that for any $T\in {S \choose 2}$ with $S\neq T$, $S \sim T$ if and only if $\left| S\cap T \right|\geq 2$. Then, $$\sum_{T: T \sim S}^{}\mathbb{P}(T\text{ is clique}|S\text{ is clique})=\sum_{i=2}^{k-1}{k \choose i}{n -k \choose k - i}2^{{i \choose 2}-{k \choose 2}}=\Delta ^{*}$$Therefore, $\frac{\Delta ^{*}}{\mathbb{E}[X_{k}]}=\sum_{i=2}^{k-1}$ $g(i)$ where $g(i):=\frac{{k \choose i}{n-k \choose k-i}}{n \choose k}2^{i \choose 2}$. 
>    
>    We split into two ranges:
>    1. If $2\leq i\leq k / 2$: $$\begin{align}g(i)&\leq \frac{k^i}{i!}\cdot \frac{(n-k)\dots(n-2k+i+1)}{(k-i)!}\cdot \frac{k!}{n(n-1)\dots (n-k+1)}\cdot 2^{i \choose 2}\\&\leq k^{2i} \cdot  \frac{1}{n(n-1)\dots (n-i+1)i!}\cdot 2^{i^2 / 2}\\&\leq  k^{2i} n^{-i}\cdot 2^{i^2 / 2}\\&\leq  (k^{2} n^{-1}\cdot 2^{k / 4})^i\end{align}$$
>       Then, as $k^{2} \frac{2^{k / 4}}{n}=\text{o}(1)$ with:$$\lim_{ n \to \infty } \frac{k^22^{k / 4}}{n}=\lim_{ n \to \infty } 4\frac{\log n}{n^{1/2}}=0$$We have that $\sum_{i=2}^{k/2} g(i)\leq \sum_{i=1}^{\infty} g(i)=\text{o}(1)$ by [[Landau Notations|Lemma 3.7]].
>    2. If $\frac{k}{2}<i\leq k-1$, we have that: $$\begin{align}\mu_{k}g(i)&={k \choose i}{n-k \choose k-i}2^{{i \choose 2}-{k \choose 2}}\\&\leq {k \choose k-i}{n \choose k-i}2^{{i \choose 2}-{k \choose 2}}\\&\leq (kn)^{k-i}2^{-(k-i)(k+i-1)/2}\\&=(kn 2^{-(k+i-1) / 2})^{k-i}\\&=(kn 2^{-(3k-1)/ 4})^{k-i}\end{align}$$Then, again: $$\lim_{ n \to \infty } kn 2^{-(3k-1) / 4}=\lim_{ n \to \infty } 2n\log n\cdot  n^{-\frac{3}{2}} 2^{1/4}=0$$ Therefore, $\mu_{k}\sum_{i=k /2 }^{k-1}g(i)=\text{o}(1)$. As $\mu_{k}\to \infty$, $\sum_{i=k /2 }^{k-1}g(i)=\text{o}(1)$.
>   
> 	 Hence, we have that  $\frac{\Delta ^{*}}{\mu_{k}}=\text{o(1)}$ and $\Delta ^{*}=\text{o}(\mathbb{E}[X_{k}])$. Therefore by [[Variance|Theorem 4]], $X_{k}>0$ almost surely, i.e. $\omega(G)\geq k$ almost surely.
> 3. Let $k_{0}$ be the minimal $k\sim 2\log_{2} n$ s.t. $\mu_{k}\leq n^{1/2}$. As we have that for $k\sim 2\log n$: $$\frac{\mu_{k+1}}{\mu_{k}}=2^{-k}\frac{n-k}{k+1}=n^{-1+\text{o}(1)}$$
>    it follows that $\mu_{k_{0}+1}=n^{-1+\text{o}(1)}\cdot \mu_{k_{0}}\leq n^{-1/2+\text{o}(1)}$. Therefore, $\mu_{k_{0}+1}\to 0$ and by 2, $\omega(G)\leq k_{0}$ w.h.p. 
>    
>    Further, we have that $\mu_{k_{0}-1}>n^{1/2}$. Then, $\mu_{k_{0}-1}\to \infty$ and as $k_{0}-1 \sim 2 \log_{2} n$, $\omega(G)\geq k_{0}+1$ w.h.p. by 3.
>    
>    This proves the statement.

^05c6d7

---
