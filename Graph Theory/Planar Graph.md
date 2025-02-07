#Definition #GraphTheory 
> [!definition]

- **Related definition**: For $G=(V,E)$, $\text{cr}(G)$ is the minimum number of crossing pairs of edges. ^98b3fd
---
##### Properties
> [!lemma] Theorem 1
> Let $G=(V,E)$ be a planar graph. Then
> 1. $\left| E \right|\leq 3n-6$.

^f8d45e

> [!proof]+
> Using [[Topology/Algebraic Topology/Euler Characteristic|Euler]], if $G$ is connected, 

^227361

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