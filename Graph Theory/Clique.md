#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]] on $n$ nodes. For a size $k$ subset $U\subseteq V$, the induced subgraph $G[U]$ is a ***$k$-clique*** if:
> 1. for every $e\in {U \choose 2}$, $e\in E$.

- **Related definition**: If $G=(V,E)$ has a $n$-clique, then $G$ is a ***complete graph*** $K_{n}$. 
- **Related definition**: The ***clique number*** $\omega(G):=\max \{ k\geq 1:G\text{ has a }k\text{-clique}  \}$.
---
##### Properties

> [!lemma] Theorem 1 (Bollobás, Erdös, Matula, 1976)
> Let $G \sim G(n,1 / 2)$ be a [[Erdös-Rényi Graph|random graph]]. 
> 1. $\mathbb{E}[\#\text{cliques of size }k]={n \choose k}2^{-{k \choose 2}}$
> 2. for $k:=\left\lceil2 \log_{2}n\right\rceil$,  $\mathbb{E}[\#\text{cliques of size }k]<1$ for all $n\geq 3$.
> 3. if $k\sim 2 \log_{2}n$ then $\mathbb{E}[\#\text{cliques of size }k] =n^{1+\text{o}(1)} \mathbb{E}[\#\text{cliques of size }k+1]$
> 4. there exists $k_0\in \mathbb{N}$ s.t. $\omega(G)\in \{k_{0}-1,k_{0}\}$ w.h.p.

> [!proof]+
> We have that:
> 1. Let $X_{k}$ be the number of cliques of size $k$ in $G$. Then, $X_{k}=\sum_{S}^{}X_{S}$ where $S\in {V \choose k}$ and $X_{S}$ is the indicator variable if $S$ spans a clique or not. Then,$$\mu_{k}:=\mathbb{E}[X_{k}]={n \choose k}2^{-{k \choose 2}}$$
> 2. Let $k:=\left\lceil2 \log_{2}n\right\rceil$. Then, $2^{k / 2}\geq n$ and: $$\mu_{k}\leq \frac{n^k}{k!}2^{-k(k-1)/2}\leq \frac{2^{k^{2}/2}}{k!}2^{-k(k-1)/2}=\frac{2^{k/2}}{k!}$$Then, $\mu_{k}<1$ for all $k\geq 3$. This happens for all $n\geq 3$.
> 3. Let $k(n) \sim 2 \log_{2}n$, i.e. $k=(1+\text{o}(1))2\log_{2} n$. Then, $$\frac{\mu_{k}}{\mu_{k+1}}=2^k \frac{k+1}{n-k}=2^{k+\log_{2}(k+1) - \log_{2}(n-k)}$$We claim that $k+\log_{2}(k+1) - \log_{2}(n-k)=(1+\text{o}(1))\log_{2}n$
> 	$$\lim_{ n \to \infty } \frac{k+\log_{2}(k+1) - \log_{2}(n-k)}{\log_{2} n}=1-\lim_{ n \to \infty }\frac{ \log_{2}\left(  1-\frac{k}{n}  \right)}{\log_{2}(n)}=1$$Therefore, $\frac{\mu_{k}}{\mu_{k+1}}=n^{1+\text{o}(1)}$.
> 4. Assume that $k_{0}:=\min\{ \mu_{k}\leq n^{1/2} \}$. We show that $k_{0} \sim 2 \log_{2}n$. Assume that $\lim_{ n \to \infty }k/\log n>1/2$. Then, $$\mu_{k}^{1/k}=\Theta \left(  \right) $$
   
>    First, we have that $\mu_{k}^{1/k}=\Theta\left( \frac{n}{k}\left( \frac{1}{2} \right)^{k/2} \right)$. Let $\varepsilon>0$ fixed. If $k\leq (1-\varepsilon)2 \log_{2} n$, then $$\left( \frac{1}{2} \right)^{k/2}\geq \left( \frac{1}{2} \right) ^{(1-\varepsilon)\log_{2}n}=n^{-1+\varepsilon}$$Hence, $$\mu_{k}^{1/k}\geq \frac{Cn^{\varepsilon}}{\log n}\geq Cn^{\varepsilon -1}>n^{1/2}$$
> 	  1. 
>    $$\mu_{k}=  2^{(1+\text{o}(1))(k \log n-k^{2})}$$
> Let $$k\log n-k^{2} \sim \log n / 2$$$$\lim_{ n \to \infty }k \left(1 -\frac{k}{\log n} \right)=\frac{1}{2}$$
>    
 Then, $k\log n-k \log k-k(k-1) / 2\sim k \log n-k^{2}$. Then, $$\lim_{ n \to \infty } \frac{k}{\log n}$$
>    
>    Let $k_{0}(n)$ be the first value s.t. $\mu_{k_{0}}\leq n^{1/2}$. Then, $$\mu_{k}=2^{k\log {n}-k\log k-k(k-1) / 2}\leq 2^{\log_{2}n/2}$$Then, $2k\log n-2\log k!-k(k-1)\geq  \log n$ and 
>    
 Then, we have $$\mu_{k_{0}+1}\leq \frac{n^{1/2}}{n^{1-o(1)}}\leq n^{-1/2+o(1)}$$By Markov, $$\mathbb{P}(X_{k_{0}+1}\geq 1)\leq \mu_{k_{0}+1}\leq n^{-1/2+o(1)}$$
> On the other hand, let $k:=k_{0}-1$ and $\mu_{k}\geq \sqrt{ n }$ which goes to infinity. Hence, $$\mathbb{P}(X_{k}=0)\leq \frac{\text{Var}(X_{k})}{(\mathbb{E}[X_{k}])^{2}}$$Here, $$\text{Var}(X_{k})=\sum_{S,T}\text{Cov}(X_{S},X_{T})<\sum_{\left| S\cap T \right| \geq 2}^{}\mathbb{E}(X_{S}X_{T})$$
> Let $r:=\left| S\cap T \right|$. Then, $\mathbb{E}[X_{S}X_{T}]=2^{{r \choose_{2}}-2{k \choose 2}}$ and the number of such pairs is ${n \choose k}{k \choose r}{n-k \choose k-r}$. Therefore, $$\text{Var}(X_{k})<\sum_{r=2}^{k}2^{{r \choose_{2}}-2{k \choose 2}}{n \choose k}{k \choose r}{n-k \choose k-r}=:g(k)$$Then, $$\frac{g(k)}{\mu_{k}^{2}}=\sum_{r=2}^{k}2^{{r \choose_{2}}}\frac{{k \choose r}{n-k \choose k-r}}{{n \choose k}}=\frac{1}{\mu_{k}}+\sum_{r=2}^{k-1}2^{{r \choose_{2}}}\frac{{k \choose r}{n-k \choose k-r}}{{n \choose k}}$$Now let $a_{r}:=2^{{r \choose_{2}}}\frac{{k \choose r}{n-k \choose k-r}}{{n \choose k}}$
> 1. if $r=2$, $$a_{2}=2\frac{{k \choose 2}{n-k \choose k-2}}{n \choose k}=\Theta\left( \frac{k^4}{n^2} \right)=n^{-2+o(1)}$$
> 2. if $r=k-1$, then : $$a_{k-1}=2^{k-1 \choose_{2}}\frac{k(n-k)}{{n \choose k}}=2^{-k+1}\frac{k(n-k)}{\mu_{k}}<n^{-1+o(1)}$$