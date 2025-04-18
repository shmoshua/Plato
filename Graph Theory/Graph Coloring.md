#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]]. 
> 1. A ***proper $k$-vertex coloring*** is a map $c:V\to[k]$ s.t. for every $\{ u,v \}\in E$: $c_{u}\neq c_{v}$.
> 2. A ***proper $k$-edge coloring*** is a map $c:E\to[k]$ s.t. for every $e,f\in E$ if $e\cap f\neq \varnothing$ then $c_{e}\neq c_{f}$.
- **Remark**: For a finite graph on $n$ nodes, there exists a proper vertex $n$-coloring.
- **Related definition**: The ***chromatic number*** $\chi(G)$ is given by: $$\chi(G):=\min\{  k\geq 1: \exists \text{proper vertex }k\text{-coloring on }G \}$$
---
##### Properties
> [!lemma] Proposition 1 (Basic Properties of Chromatic Number)
> Let $G$ be a graph on $n$ vertices. Then, 
> 1. $\chi(H)\leq \chi(G)$ for all $H\leq G$.
> 2. $\chi(G)\geq \omega(G)$ where $\omega(G)$ is the [[Independence and Clique|clique number]].
> 3. $\chi(G)\geq \left| V(G) \right| / \alpha(G)$ where $\omega(G)$ is the [[Independence and Clique|independence number]].
> 4. for any $U\subseteq V(G)$, $\chi(G)\leq \chi(G[U])+\chi(G[V \backslash U])$.
> 5. $\chi(G_{1}\cup G_{2})\leq \chi(G_{1})\chi(G_{2})$.
> 6. $\chi(G)\chi(\overline{G})\geq n$.
> 7. $\chi(G)+\chi(\overline{G})\leq n+1$.
> 8. $\chi(G)\leq \Delta(G)+1$

> [!proof]-
> We have:
> 1. Any proper coloring for $G$ restricted to $V(H)$ is a proper coloring on $H$.
> 2. Otherwise we can color a $k$-clique with less than $k$ colors, which is a contradiction. 
> 3. Let $c$ be a proper $\chi(G)$-coloring. Then, every color induced an independent set. Hence, there exists an independent set of size larger than $\left| V(G) \right| / \chi(G)$. This shows the statement.
> 4. For a proper $\chi(G[U])$ coloring $c$ on $G[U]$ and proper $\chi(G[V \backslash U])$ coloring $c'$ on $G[V \backslash U]$. Then, $c \oplus c'$ defines a proper coloring on $G$.
> 5. Let $c_{1},c_{2}$ be the proper coloring for $G_{1},G_{2}$ of chromatic number. Let $c:= c_{1}\times c_{2}$. Then, for any $uv\in G_{1}\cup G_{2}$, $(c_{1}(u),c_{2}(u))\neq(c_{1}(v),c_{2}(v))$. 
> 6. From 5.
> 7. We show by induction over $n$. 
> 	1. if $n=1$, then $\chi(G)+\chi(\overline{G})=2=n+1$.
> 	2. if $n\geq 2$, take an arbitrary vertex $v\in G$ and consider $G':= G \backslash v$. Then, $$\chi(G')+\chi(\overline{G'})\leq n$$Let $k:= \chi(G')$ and $\ell:= n-k\geq \chi(\overline{G'})$. 
> 		1. if $d(v)\leq k-1$, then $G$ is also $k$ colorable and $\chi(G)\leq k$. However, we have that $\chi(G')\leq \chi(\overline{G'})+1\leq n-k+1$. Hence, $\chi(G)+\chi(\overline{G})\leq n+1$.
> 		2. if $d(v)\geq k$. Then, $d(v)+d_{\overline{G}}(v)=n-1$ and we have that $d_{\overline{G}}(v)\leq n-k-1\leq \ell-1$. Hence, analogously as above, we have $\chi(\overline{G})\leq \ell$ and $\chi(G)\leq \chi(G')+1\leq k+1$. This shows that $\chi(G)+\chi(\overline{G})\leq n+1$. 
> 8. Analogous to the proof in $8$. 

---
> [!lemma] Proposition 2 (Greedy Coloring)
> ```pseudo
> \begin{algorithm} \caption{Greedy$(G)$}\begin{algorithmic}
> \State Let $v_{1},\dots,v_{n}$ be an ordering of $V(G)$.
> \For{$i\in[n]$}
> \State $c(v_{i})\gets \min\{ i\in[n]: i\notin  N(v_{i})\cap \{ v_{1},\dots,v_{i-1} \} \}$
\EndFor
> \Return $c$
\end{algorithmic}
\end{algorithm}
> ```

---
> [!lemma] Proposition 1 (Shamir-Spencer, 1987)
> Let $G\sim G(n,p)$, i.e. the [[Erdös-Rényi Graph]]. For any $\lambda>0$, $$\mathbb{P}(\left| \chi(G)-\mathbb{E}[\chi(G)] \right| \geq \lambda)\leq 2 \exp \left( -2\lambda^{2} / n \right) $$

^ffc682

> [!proof]-
> We have that from [[Erdös-Rényi Graph|Remark]] that $\sigma(G)=\sigma(X_{1},\dots,X_{n})$. Let $$\chi(G)=f_{\chi}(X_{1},\dots,X_{n})$$Then, we see that $f_{\chi}$ is $1$-Lipschitz. Therefore, by [[Martingale|McDiarmid]], $$\mathbb{P}(\left| \chi(G)-\mathbb{E}[\chi(G)] \right| \geq \lambda)\leq 2\exp \left( -\frac{2\lambda^{2}}{n} \right) $$

^fb140c

---

> [!lemma] Theorem 2 (Bollobás, 1988)
> Let $G\sim G(n , 1/2)$ and $\mu_{k}:={n \choose k}2^{-{k \choose 2}}$. Further, let $k_{0}:=\min\{ k:\mu_{k}<1 \}$.
> 1. $\mathbb{P}(\alpha(G)<k_{0}-4)\leq \exp(-4n^{2-\text{o}(1)})$

^6db2cc

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

^dbdce1

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

> [!proof]-
> Let $\chi(G)=:k$ and $c:V\to[k]$ be a proper $k$-coloring of $G$. Let $S\subseteq V$. Then, we can partition $S$ into $S_{1},\dots,S_{k}$ by the colors and each of them form an independent set. Therefore, there is $i$ with $\left| S_{i} \right|\geq \left| S \right| / k$ and: $$\frac{\left| S \right|}{\chi(G)}\leq \left| S_{i} \right| \leq \alpha(S) $$which proves the lower bound.
> 
> For the upper bound, consider the following greedy algorithm: 
> ```pseudo
> \begin{algorithm} \caption{Greedy$(G)$}\begin{algorithmic}
> \State $S_{0}\gets V$, $i\gets 0$
> \For{$S_{i}\neq \varnothing$}
> \State $V_{i}\gets$ maximum independent set of $S_{i}$.
> \State $S_{i+1}\gets S_{i} \backslash V_{i}$
> \State $i\gets i+1$
\EndFor
> \Return $(V_{1},\dots,V_{k})$
\end{algorithmic}
\end{algorithm}
> ```
> Then, firstly the algorithm returns a valid coloring as $V_{1},\dots,V_{k}$ are all independent sets and because it holds that $V_{1}\cup\dots \cup V_{k}=V$. Therefore, it suffices to show that $k\leq \text{O}(\log n)\rho(G)$. 
> 
> We have that $\rho(G)\geq |S_{i}| / \left| V_{i} \right|$ and $\left| V_{i} \right|\geq \left| S_{i} \right| / \rho(G)$. Therefore, $$\left| S_{i+1} \right|\leq \left| S_{i} \right| -\left| V_{i} \right| \leq\left| S_{i} \right| \left( 1-\frac{1}{\rho(G)} \right) $$By induction we have that: $$\left| S_{j} \right| \leq n\left( 1-\frac{1}{\rho(G)} \right) ^j\leq ne^{-j / \rho(G)}$$In other words, $\left| S_{j} \right|=0$ for all $j>\rho(G)\log n$ which proves the statement.
---
###### Edge Coloring
> [!lemma] Theorem 1 (Online Edge Coloring)
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm} \caption{OnlineEdgeColoring($G=(V,E)$)}
> \begin{algorithmic} 
> \State $C_{v}\gets \varnothing$ for all $v\in V$
> \For{$e=\{ u,v \}\in V$}
> \State $c_{e}\gets\min\{  i\in \mathbb{Z}_{\geq 0}:  i\notin C_{u}\land i\notin C_{v}\}$\EndFor
> \Return $c$
\end{algorithmic}
\end{algorithm}
> ```
> In the online setting, 
> 1. $\text{OnlineEdgeColoring}(G)$ returns a $(2\Delta(G) -1)$-edge coloring.
> 2. Any deterministic online algorithm requires at least $(2\Delta(G)-1)$ colors. 

^18c39b

> [!proof]-
> For $\Delta:=\Delta(G)$, we have that:
> 1. For an edge $e=\{ u,v \}$, there are at most $\Delta-1$ other edges on each side that could have come before. Hence, there are at most $2\Delta-2$ colors that are already taken. Hence, we use at most $2\Delta-1$ colors. 
> 2. Consider the following adversary. The adversary first inputs ${2\Delta-2 \choose \Delta-1}(\Delta-1)+1$ distinct stars $K_{\Delta-1,1}$. Then, we have the following two cases:
> 	1. $\mathcal{A}$ has used more than $2\Delta-2$ colors. Then, we are done.
> 	2. $\mathcal{A}$ has used at most $2\Delta-2$ colors. Then, there exists by construction $\Delta$ stars that use the same set of colors. By connecting the center nodes of the $\Delta$ stars to a new vertex, we have that $\mathcal{A}$ uses $\Delta$ colors that are not in the $\Delta-1$ colors used for the stars. Hence, we have that $\mathcal{A}$ uses more than $2\Delta-1$ colors. 

^ae9f8d

---
##### Examples
