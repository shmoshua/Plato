#Series #Algorithms 

##### Problem 1: Tree embedding in cycle

Let $T$ be such a tree. Then, assume that there exists $u<v<w$ s.t. $\{ u,w \},\{ v,w \}\in T$. Consider $T':=T \backslash \{ u,w \}\cup \{ u,v \}$ which is still a tree with weight $d_{G}(u,v)$. Then,
1. We have that: $$l$$
1. 
In $T \backslash\{ u,v \}$ either $w$ is connected to $u$ or $v$. Wlog let $w$ be connected to $u$. Then, 
Consider $T'=T \backslash \{ u,v \}\cup \{\{ v,w \}\}$. Then, we have that:
1. $T'$ is still a tree as we have $n-1$ edges and for any two paths that contain $\{ u,v \}$ in $T$ we can replace it by the $u$-$w$-path in $T$ and $\{ v,w \}$. 
2. For any $i,j$, we have that if it doesn't contain $\{ u,v \}$ then $d_{T'}(i,j)=d_{T}(i,j)$. If it does then, $$d_{T'}()$$


We have that: $$\sum_{i,j}^{}d_{T}(i,j)\geq (n-1)\sum_{i,j}^{}d_{G}(i,j)$$

We have that: $$\sum_{i,j}^{}d_{G}(i,j)=\sum_{i,j}^{}\min\{ \left| j-i \right| ,\left| n-j+i \right|  \}=\frac{n}{2}\left( \frac{n}{2}+1 \right) + $$
Assume that $d_{T}(i,j)<(n-1)d_{G}(i,j)$ for all $i,j$. Then, $$\sum_{i,j}^{}d_{T}(i,j)<(n-1)d_{T}$$$$I<(n-1)I$$and $0<(n-2)I$

We have that: $$\sum_{e\in T}^{}l(e)\geq $$
2. Consider leaving a random edge out. Then, for $i,j$, then, $$\mathbb{E}[d_{T}(i,j)]=\frac{d_{G}(i,j)}{n}\cdot (n-d_{G}(i,j))+\frac{n-d_{G}(i,j)}{n}d_{G}(i,j)=\frac{2(n-d_{G}(i,j))}{n}d_{G}(i,j)\leq 2d_{G}(i,j)$$ 

---
##### Problem 2: Steiner Forest
---
##### Problem 3: Ball Carving
Hehe
1. We have that: $$\mathbb{P}\left( r_{v}\geq \frac{1}{\beta}\log n \right)\leq \frac{1}{n}$$
2. Let $w$ be on the shortest path from $u$ to $v$. But $w\in B_{z}$ for $z\neq v$. Then, $$r_{z}-d(w,z)\geq r_{v}-d(w,v)$$and as $d(u,v)=d(u,w)+d(w,v)$, we have that: $$r_{z}-d(u,z)\geq r_{z}-d(u,w)-d(w,z)\geq r_{v}-d(u,w)-d(w,v)=r_{v}-d(u,v)$$which is a contradiction.

