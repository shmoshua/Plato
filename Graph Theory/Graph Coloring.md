#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]]. 
> 1. A ***proper vertex $k$-coloring*** is a map $c:V\to[k]$ s.t. for every $\{ u,v \}\in E$: $c_{u}\neq c_{v}$.
- **Remark**: For a finite graph on $n$ nodes, there exists a proper vertex $n$-coloring.
- **Related definition**: The ***chromatic number*** $\chi(G)$ is given by: $$\chi(G):=\min\{  k\geq 1: \exists \text{proper vertex }k\text{-coloring on }G \}$$
---
##### Properties

> [!lemma] Proposition 1 (Shamir-Spencer, 1987)
> Let $G\sim G(n,p)$, i.e. the [[Erdös-Rényi Graph]]. For any $\lambda>0$, $$\mathbb{P}(\left| \chi(G)-\mathbb{E}[\chi(G)] \right| \geq \lambda)\leq 2 \exp \left( -2\lambda^{2} / n \right) $$

> [!proof]-
> We have that from [[Erdös-Rényi Graph|Remark]] that $\sigma(G)=\sigma(X_{1},\dots,X_{n})$. Let $$\chi(G)=f_{\chi}(X_{1},\dots,X_{n})$$Then, we see that $f_{\chi}$ is $1$-Lipschitz. Therefore, by [[Martingale|McDiarmid]], $$\mathbb{P}(\left| \chi(G)-\mathbb{E}[\chi(G)] \right| \geq \lambda)\leq 2\exp \left( -\frac{2\lambda^{2}}{n} \right) $$
---

> [!lemma] Theorem 2 (Bollobás)
> Let $G\sim G(n , 1/2)$ and $\mu_{k}:={n \choose k}2^{-{k \choose 2}}$. Further, let $k_{0}:=\min\{ k:\mu_{k}<1 \}$.
> 1. $\mathbb{P}(\alpha(G)<k_{0}-4)\leq \exp(-n^{2-\text{o}(1)})$

> [!proof]+
> Let $k_{1}:=k_{0}-4$. 
> 1. Let $Y(G)$ be the maximum size of the collection of pair-disjoint independent sets of size $k_{1}$ in $G$, i.e. $I_{1},\dots,I_{t}$ s.t. $\left| I_{i}\cap I_{j} \right|\leq 1$. Then, for $\{ X_{e} \}_{e\in {V \choose 2}}$ and $m:={n \choose 2}$ we have that $Y(G)=f_{Y}(X_{1},\dots,X_{m})$ where $f_{Y}$ is $1$-Lipschitz. Therefore, by [[Martingale|McDiarmid]], $$\mathbb{P}(\alpha(G)<k_{1})=\mathbb{P}(Y(G)=0)\leq \mathbb{P}(f_{Y}(X)\leq \mathbb{E}[f_{Y}(X)]-\mathbb{E}[f_{Y}(X)])\leq \exp \left( -\frac{4\mathbb{E}[Y]^{2}}{n^2} \right) $$
>    Hence, it suffices to show that $2\mathbb{E}[Y]=n^{2-\text{o}(1)}$.
>     
>     Let $W$ be the number of unordered pairs of independent sets of size $k$ which intersect in more than $2$ elements. Then, $$\mathbb{E}[W]=\sum_{j=2}^{k-1} \frac{1}{2}{n \choose k}{k \choose j}{n-k \choose k-j}2^{-(2 {k \choose 2}-{j \choose 2})}=\frac{1}{2}\mu^{2}\sum_{j=2}^{k-1}{k \choose j}\frac{{n-k \choose k - j}}{n \choose k}2^{j \choose 2}$$If $j=2$, then: $${k \choose 2}\frac{k(k-1)}{n^{2}}2 \sim \frac{k^4}{n^{2}}$$and if $j=k-1$ then: $$k \frac{n-k}{{n \choose k}}2^{k-1 \choose 2}=\frac{k(n-k)}{\mu}2^{-(k-1)}=\frac{1}{\mu n^{1-\text{o}(1)}}$$Therefore, $$\mathbb{E}[W]=(1+\text{o}(1)) \frac{1}{2}\mu^{2}$$
> 	
> 	1. Claim 1: For $q\in[0,1]$, we have that $Y\geq qX_{k}-q^{2}W$.
> 	   
> 	   Choose each of the independent set independently with probability $q$. For independent set $Z$ of size $k$, let $\mathcal{A}$ be the set of all independent sets with intersection more than 1. Then, $$Y\geq \mathbb{E}[Z]-\mathbb{E}[\mathcal{A}]=q X_{k}-q^{2}W$$
> 	   
> 	Hence, $$\mathbb{E}[Y]\geq q \mu-(1+\text{o}(1))\frac{q^{2}}{2}\frac{k^4}{n^{2}}\mu^{2}\geq (1+\text{o}(1))\frac{n^2}{2k^4}$$for $q=\frac{n^2}{k^4\mu}$.
---
> [!lemma] Theorem 2 (Bollobas)
> For $G\sim G(n , 1/2)$, w.h.p.$$\chi(G)=(1+\text{o(1)})\frac{n}{2\log_{2}n}$$

> [!proof]-
> Let $G=G(n, 1/2)$ and $\mu_{k}:=\mathbb{E}[\#\text{ independent sets of size }k]$. Then, $$\mu_{k}={n \choose k}2^{-{k \choose 2}}$$
> Now, let $k_{0}$ s.t. $\mu_{k_{0}-1}> 1 > \mu_{k_{0}}$ and let $k:=k_{0}-4$. Then, 
> 1. Claim 1: $k=(1+\text{o}(1))2\log_{2}n$.
> 1. Claim 2: $\mathbb{P}(\alpha(G)< k)\leq \exp\left( -n ^{2-\text{o(1)}}\right)$
> 
> Then, let $m:=\left\lfloor n / \ln^2 n\right\rfloor$ and let $k'$ be s.t. $\mu_{k'+3}>1>\mu_{}$. Now, let $S\subseteq  V$ of $m$ vertices, which has a distribution of $G(m, 1/2)$. By applying Claim 2, we have: $$\mathbb{P}(\alpha(G[S])<k')\leq \exp \left( -m^{2-\text{o}(1)} \right) $$
