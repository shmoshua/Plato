#Definition #GraphTheory 
> [!definition]

- **Related definition**: For $G=(V,E)$, $\text{cr}(G)$ is the minimum number of crossing pairs of edges.
---
##### Properties
> [!lemma] Theorem 1
> Let $G=(V,E)$ be a planar graph. Then
> 1. $\left| E \right|\leq 3n-6$.

> [!proof]+
> Using Euler, if $G$ is connected, 
---
> [!lemma] Theorem 1 (Ajtai-Chvátal-Newborn-Szemerédi, Leighton)
> For any simple graph $G=(V,E)$:
> 1. $\text{cr}(G)\geq m-3n+6$.
> 2. $\text{cr}(G)\geq \frac{1}{64}\frac{m^3}{n^2}$ if $m\geq 4n$

> [!proof]+
> We have:
> 1. From Theorem 1. 
> 2. Fix a particular drawing of $G$ with $\text{cr}(G)$ crossings. Let $S\subseteq V$ chosen by sampling each vertex with probability $p$ independently. Let $G':=G[S]$. Let $n',m'$ be the number of vertices and edges in $G'$, further let $c'$ be the number of crossings that occur by drawing $G'$ in the fixed drawing we have of $G$.
>    
>    Then,
>    1. $\mathbb{E}[n']=pn$.
>    2. $\mathbb{E}[m']=p^{2} m$.
>    3. $\mathbb{E}[c']=p^4 \text{cr}(G)$.