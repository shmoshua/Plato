#Definition #GraphTheory 
> [!definition]
> Let $G$ be a [[graph]]. 
> 1. $G$ is ***planar*** if it has a drawing without crossings.

^49eb13

- **Related definition**: A ***plane graph*** is a particular drawing of a planar graph with no crossings.  ^06ee29
- **Related definition**: For $G=(V,E)$, $\text{cr}(G)$ is the minimum number of crossing pairs of edges. ^98b3fd
---
##### Properties
> [!lemma] Theorem 1
> Let $G=(V,E)$ be a planar graph with $n\geq 3$. Then
> 1. $e(G)\leq 3n-6$.
> 2. $e(G)\leq 2n-4$ if it is triangle free.

^f8d45e

> [!proof]-
> We have:
> 1. First assume that $G$ is connected and has no leaves. 
> 	1. if $e(G)=0$, then the statement trivially holds. 
> 	2. if $e(G)\geq 1$, then as $\delta(G)\geq 2$, there exists a cycle and more than one face. Let $\{ f_{i} \}$ be the face lengths. We then have: $$2e=\sum_{i}^{}f_{i}\geq 3f$$Hence, $f\leq \frac{2}{3}e$ and plugging it back we have that: $$n-e+\frac{2}{3}e\geq 2$$and $e\leq 3n-6$. 
> 	
> 	Now, if $G$ is not connected, we can always add more edges and make it connected. Similarly, if $G$ has a leaf $v$, let $G':= G \backslash v$. Then, $$3(n-1)-6-e(G')=3n-6-e(G)-2$$Hence, we have that the statement holds. 
> 2. Similarly to 1, if $G$ is triangle free, $2e\geq 4f$ and $e\leq 2n-4$. We now conclude by showing that: $$2(n-1)-4-e(G')=2n-4-e(G)-1$$

^227361

- **Corollary**: A bipartite planar graph with $n\geq 3$ nodes has at most $2n-4$ edges. ^ec1ae0
---
> [!lemma] Theorem 1 (Ajtai-Chvátal-Newborn-Szemerédi, Leighton)
> For any simple graph $G=(V,E)$:
> 1. $\text{cr}(G)\geq m-3n+6$.
> 2. $\text{cr}(G)\geq \frac{m^3}{64n^2}$ if $m\geq 4n$

^c09fc4

> [!proof]-
> We have:
> 1. From Theorem 1. 
> 2. Fix a particular drawing of $G$ with $\text{cr}(G)$ crossings. Let $S\subseteq V$ chosen by sampling each vertex with probability $p$ independently. Let $G':=G[S]$. Let $n',m'$ be the number of vertices and edges in $G'$, further let $c'$ be the number of crossings that occur by drawing $G'$ in the fixed drawing we have of $G$.
>    
>    Then,
>    1. $\mathbb{E}[n']=pn$.
>    2. $\mathbb{E}[m']=p^{2} m$.
>    3. $\mathbb{E}[c']=p^4 \text{cr}(G)$.
>    
>    As we have that $c'\geq \text{cr}(G')\geq m'-3n'+6$, we have that: $$p^4\text{cr}(G)=\mathbb{E}[c']\geq \mathbb{E}[m']-3\mathbb{E}[n']=p^2m-3pn$$Hence, $p^3\text{cr}(G)\geq pm-3n$ and by choosing $p:= \frac{4n}{m}$, we have that: $$\text{cr}(G)\geq \frac{m^{3}}{16n^{2}}-\frac{3m^3}{64 n^{2}}=\frac{m^3}{64n^{2}}$$

^d80cd4

---
> [!lemma] Theorem 2 (Szemerédi-Trotter, 1983)
> We have that: $$I(P,L)\leq 4(m^{2/3}n^{2/3}+m+n)$$

^b577a8

- **Remark**: This bound is tight up to a constant! ^df2625
---