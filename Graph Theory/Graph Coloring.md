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

> [!lemma] Theorem 2 (Bollobás, 1988)
> Let $G\sim G(n , 1/2)$ and $\mu_{k}:={n \choose k}2^{-{k \choose 2}}$. Further, let $k_{0}:=\min\{ k:\mu_{k}<1 \}$.
> 1. $\mathbb{P}(\alpha(G)<k_{0}-4)\leq \exp(-4n^{2-\text{o}(1)})$

> [!proof]-
> Let $k_{1}:=k_{0}-4$. 
> 1. Let $Y(G)$ be the maximum size of the collection of pair-disjoint independent sets of size $k_{1}$ in $G$, i.e. $I_{1},\dots,I_{t}$ s.t. $\left| I_{i}\cap I_{j} \right|\leq 1$. Then, for $\{ X_{e} \}_{e\in {V \choose 2}}$ and $m:={n \choose 2}$ we have that $Y(G)=f_{Y}(X_{1},\dots,X_{m})$ where $f_{Y}$ is $1$-Lipschitz. Therefore, by [[Martingale|McDiarmid]], $$\mathbb{P}(\alpha(G)<k_{1})=\mathbb{P}(Y(G)=0)\leq \mathbb{P}(f_{Y}(X)\leq \mathbb{E}[f_{Y}(X)]-\mathbb{E}[f_{Y}(X)])\leq \exp \left( -\frac{4\mathbb{E}[Y]^{2}}{n^2} \right) $$
>    Hence, it suffices to show that $\mathbb{E}[Y]=n^{2-\text{o}(1)}$.
>    
>    Let $W$ be the number of unordered pairs of independent sets of size $k_{1}$ which intersect in more than $2$ elements. Then, $$\mathbb{E}[W]=\frac{1}{2} {n \choose k_{1}}\sum_{j=2}^{k_{1}-1}{k_{1} \choose j}{n-k_{1} \choose k_{1}-j}2^{-(2 {k_{1} \choose 2}-{j \choose 2})}=\frac{\mu^{2}_{k_{1}}}{2}\sum_{j=2}^{k_{1}-1}\underbrace{ \frac{{k_{1} \choose j}{n-k_{1} \choose k_{1} - j}}{n \choose k_{1}}2^{j \choose 2} }_{ =:g(j) }$$
> 	   1. For $2\leq j\leq \frac{k}{2}$, we have that: $$\begin{align}g(j)&={k \choose j}\end{align}$$
>    
>    
>    From [[Clique|Proof of Theorem 1.3]], we have that $\sum_{j=2}^{k_{1}-1}g(j)=\text{o}(1)$. Hence, $$\mathbb{E}[W]=\frac{\mu_{k_{1}}^{2}}{2}\text{o}(1)\leq (1+\text{o}(1))\frac{\mu^2_{k_{1}}}{2}$$
>    Let $q\in[0,1]$. Then, we claim that $Y\geq qX_{k_{1}}-q^{2}W$. Let $S_{1},\dots,S_{X_{k_{1}}}$ be the independent sets in $G$ and let $A\subseteq [X_{k_{1}}]$ where $\mathbb{P}(i\in A) = q$ independently. Let $W'$ be the number of unordered pairs $\{ i,j \}\subseteq A$ s.t. $\left| S_{i}\cap S_{j} \right|\geq 2$. Then, $\mathbb{E}[W']=q^{2}W$. 
>    
>    By removing one independent set from each pair, we have that: $Y\geq |A|-W'$ and $$Y\geq \mathbb{E}[\left| A \right| ]-\mathbb{E}[W']=qX_{k}-q^{2}W$$
>    Hence, by taking expectation over $G$, we have that: $$\mathbb{E}[Y]\geq q\cdot \mu_{k_{1}}-q^{2}\mathbb{E}[W]$$By choosing $q=\frac{\mu_{k_{1}}}{2\mathbb{E}[W]}$, we have that: $\mathbb{E}[Y]\geq \frac{\mu_{k_{1}}^{2}}{4\mathbb{E}[W]}\geq (1-\text{o}(1))$
>    
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
---
![[Girth and Circumference#^4ba9e0]]
![[Girth and Circumference#^819748|p]]
---
> [!lemma] Theorem 4 (Chromatic Inequality)
> Let $G=(V,E)$ be a graph and for any $S\subseteq V$, we let $\alpha(S)$ denote the size of the biggest independent set. Further, $\rho(G):=\max_{S\subseteq V}|S| / \alpha(S)$. Then, $$\rho(G)\leq \chi(G)\leq \text{O}(\log n)\cdot \rho(G)$$

> [!proof]+
> Let $\chi(G)=:k$ and $c:V\to[k]$ be a proper $k$-coloring of $G$. Let $S\subseteq V$. Then, we can partition $S$ into $S_{1},\dots,S_{k}$ by the colors and each of them form an independent set. Therefore, there is $i$ with $\left| S_{i} \right|\geq \left| S \right| / k$ and: $$\frac{\left| S \right|}{\chi(G)}\leq \left| S_{i} \right| \leq \alpha(S) $$which proves the lower bound.
> 
> For the upper bound, 