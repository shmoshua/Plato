#Series #Algorithms 

##### Problem 1: Tree embedding in cycle

Let $T$ be such a tree. Then, assume we have $u<w<v$ s.t. $\{ u,v \}\in T$. In $T \backslash\{ u,v \}$ either $w$ is connected to $u$ or $v$. Wlog let $w$ be connected to $u$. Then, 
Consider $T'=T \backslash \{ u,v \}\cup \{\{ v,w \}\}$. Then, we have that:
1. $T'$ is still a tree as we have $n-1$ edges and for any two paths that contain $\{ u,v \}$ in $T$ we can replace it by the $u$-$w$-path in $T$ and $\{ v,w \}$. 
2. For any $i,j$, we have that if it doesn't contain $\{ u,v \}$ then $d_{T'}(i,j)=d_{T}(i,j)$. If it does then, $$d_{T'}()$$


We have that: $$\sum_{i,j}^{}d_{T}(i,j)\geq (n-1)\sum_{i,j}^{}d_{G}(i,j)$$

We have that: $$\sum_{i,j}^{}d_{G}(i,j)=\sum_{i,j}^{}\min\{ \left| j-i \right| ,\left| n-j+i \right|  \}=\frac{n}{2}\left( \frac{n}{2}+1 \right) + $$
Assume that $d_{T}(i,j)<(n-1)d_{G}(i,j)$ for all $i,j$. Then, $$\sum_{i,j}^{}d_{T}(i,j)<(n-1)d_{T}$$$$I<(n-1)I$$and $0<(n-2)I$

We have that: $$\sum_{e\in T}^{}l(e)\geq $$
