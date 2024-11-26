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

> [!proof]+
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
>    Further, we have that $\mu_{k_{0}-1}>n^{1/2}$. Then, $\mu_{k_{0}-1}\to \infty$ and as $k_{0}-1 \sim 2 \log_{2} n$, $\omega(G)\geq k_{0}+1$ w.h.p
>    
>    $$\frac{\mu_{k}}{\mu_{k+1}}=2^k \frac{k+1}{n-k}\leq 2^k  \frac{2k+1}{n}= n^{1+\text{o}(1)}$$Therefore, $\mu_{k_{1}+1}\leq$
 with $1>\mu_{k_{0}}\geq n^{-1/2}$. We have that for $k\sim 2\log_{2} n$, $$\mu_{k}\leq \frac{n^k}{k!}2^{-k^2/2+k/2}<1$$
>    
>    For $k\sim 2\log_{2} n$, we have that: $$\frac{\mu_{k}}{\mu_{k+1}}=2^k \frac{k+1}{n-k}\leq 2^k  \frac{2k+1}{n}= n^{1+\text{o}(1)}$$where for the last equality, it suffices to show that  ${k+\log (2k+1)-2\log n}= {\text{o}(\log n)}$. We have: $$\lim_{  n \to \infty } \frac{k+\log(2k+1)-2\log n}{\log n}=2-2=0$$Let $k_{0}\sim 2\log_{2}n$ with $\mu_{k_{0}}\geq n^{-1/2}> \mu_{k_{0}+1}$. Then, $\mathbb{E}[\mu_{k_{0}+1}]\to 0$ and $\omega(G)\leq k_{0}$ w.h.p. by 1. 

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