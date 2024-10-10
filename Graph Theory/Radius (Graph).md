#Definition #GraphTheory 
> [!definition]
> Let $G$ be a [[graph]].
> 1. The ***radius*** of $G$ is given by: $$\text{rad}(G):=\min_{u\in V}\max_{v\in V}d_{G}(u,v)$$

- **Related definition**: $v\in \arg\min_{u\in V}\max_{v\in V}d_{G}(u,v)$ is called ***central***.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\text{rad}(G)\leq \text{diam}(G)\leq 2\cdot \text{rad}(G)$

> [!proof]-
> We have:
> 1. The first inequality is trivial by definition. Let $v\in V$ be central. Then, for any $x,y\in V$, $$d_{G}(x,y)\leq d_{G}(v,x)+d_{G}(v,y)\leq 2\cdot  \text{rad}(G)$$
---
> [!lemma] Proposition 2
> For a finite graph $G$, 
> 1. if $\text{rad}(G)\leq k$ and $\Delta(G)\leq d$ where $d\geq 3$, $$\left| G \right| < \frac{d}{d-2}(d-1)^k$$

> [!proof]-
> Let $z$ be a central vertex. Let $D_{i}:=\{ v\in G: d_{G}(z,v)=i \}$. Then 
> 1. $\left| D_{0} \right|=1$.
> 2. $\left| D_{1} \right|\leq d$.
> 3. $\left| D_{i+1} \right|\leq(d-1)\left| D_{i} \right|$. 
>  
>  Hence, $$\left| G \right| \leq 1+\sum_{i=1}^{k}\left| D_{i} \right|=1+d\sum_{i=0}^{k-1}(d-1)^i=1+\frac{d}{d-2}((d-1)^k-1)< \frac{d}{d-2}(d-1)^k$$
---
