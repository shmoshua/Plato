#ProbabilisticMethods #Definition 

> [!definition]
> For $s,t\in \mathbb{Z}_{>0}$, the ***Ramsey number*** $R(s,t)$ is the smallest integer $n$ s.t. 
> 1. every red-blue edge-coloring of the [[Clique]] $K_{n}$ has a red clique of size $s$ or a blue clique of size $t$.
> 2. for a graph $G$, the ***Ramsey number $R(G)$*** is the smallest integer $n$ s.t. any 2-edge-coloring of $K_{n}$ contains a monochromatic $G$. 

^bf6551

---
##### Properties
> [!lemma] Theorem 1
> For $s,t>2$, we have that:
> 1. $R(s,t)\leq R(s-1,t)+R(s,t-1)$
> 2. if $R(s-1,t),R(s,t-1)$ are both even, $R(s,t)\leq R(s-1,t)+R(s,t-1)-1$

^5ce7f6

> [!proof]-
> We have:
> 1. Assume that $R(s,t)>R(s-1,t)+R(s,t-1)=:n$. Now, consider a red-blue coloring of $K_{n}$ s.t. there is no red $K_{s}$ and no blue $K_{t}$. Now, choose a vertex $v$ and let $N_{r}$ be the set of vertices connected to $v$ with a red edge and $N_{b}$ the set of vertices connected to $v$ with a blue edge. Then, it holds that $\left| N_{r} \right|+\left| N_{b} \right|=n-1$. 
>    
>    However, by any assumptions, there cannot be any blue $K_{t}$ in $N_{r}$. Further, if there exists a red $K_{s-1}$ in $N_{r}$, $N_{r}\cup \{ v \}$ is a $K_{s}$ and therefore, $\left| N_{r} \right|\leq R(s-1,t)-1$. Similarly, $\left| N_{b} \right|\leq R(s,t-1)-1$. Therefore, $$n-1=\left| N_{r} \right| +\left| N_{b} \right| \leq R(s-1,t)+R(s,t-1)-2=n-2$$which is a contradiction.
> 2. Suppose $R(s-1,t)=2p$ and $R(s,t-1)=2q$. Then, take $K_{2p+2q-1}$ with a vertex $v$. Then, from the $2p+2q-2$ edges connected to $v$, we have the following cases:
> 	1. $2p$ or more red edges end at $v$. Let $T$ be the endpoints of the edges (without $v$). Then, $\left| T \right|\geq R(s-1,t)$ and $T$ contains either a red $K_{s-1}$ or a blue $K_{t}$. However, if there is a red $K_{s-1}$, then $T\cup \{ v \}$ contains a red $K_{s}$. 
> 	2. $2q$ or more blue edges end at $v$. This case is analogous to case 1.
> 	3. $2p-1$ red edges and $2q-1$ blue edges end at $v$. We will show that this cannot hold for all vertices $v$. If it did, then we would have $(2p+2q-1)(2p-1)$ red endpoints. However, this is an odd number which is a contradiction. 
> 	   
> 	Therefore, there exists at least one vertex $v$ for which either case 1 or 2 holds. This proves the statement.

^3cf037

- **Corollary**: As $R(n,2)=R(2,n)={n\choose 1}$, $R(s,t)\leq {s+t-2\choose s-1}$ using induction. Similarly by induction, one can show that $R(s,t)\leq 2^{s+t}$. ^8e9a7c

---
> [!lemma] Theorem 2 (Diagonal Ramsey Numbers)
> We have:
> 1. $(k-1)^{2}< R(k,k)\leq 2^{2k}$
> 2. If ${n\choose k}2^{1-{k\choose 2}}<1$, then $R(k,k)>n$.
> 3. for $k\geq 3$, $R(k,k)> 2^{k / 2}$.

^0bfef8

> [!proof]-
> We have:
> 1. Partition $K_{(k-1)^{2}}$ into $(k-1)$ sets of vertices of equal size and color the edges inside the sets as red and all the other edges blue. Then, there is no red or blue clique of size $k$. 
>    
>    The upper bound follows from the Corollary above.
> 2. Consider an edge coloring of $K_{n}$ where the colors are assigned randomly uniformly. As there are ${n\choose k}$ copies of $K_{k}$ in $K_{n}$, we define $A_{i}$ to denote the event that $i$-th $K_{k}$ is monochromatic. Then, $$\mathbb{P}(A_{i})=2\left( \frac{1}{2} \right) ^{k \choose 2}=2^{1-{k \choose 2}}$$Then, $$\mathbb{P}(\exists \text{ monochromatic }K_{k})=\mathbb{P}\left( \bigcup_{i=1}^{n\choose k} A_{i}\right)={n \choose k}2^{1- {k \choose 2}}<1$$Therefore, there exists a coloring with no monochromatic $K_{k}$. 
> 3. Given $k\geq 3$, define $n:= \left\lfloor 2^{ k /2}\right\rfloor$. Then, $${n \choose k}2^{1- {k \choose 2}}\leq \frac{n^k}{k!}2^{1-k(k-1)/2}\leq\frac{(2^{k / 2})^k}{k!}2^{1-k^2 / 2+k / 2}=\frac{2^{1+k /2}}{k!}$$As $2^{1+k / 2} / k!<1$ for $k\geq 3$, we have the statement.

^9fbe8f

---
> [!lemma] Theorem 3 
> We have:
> 1. $R(4,k)\geq \Omega((k / \ln k)^{2})$

> [!proof]+
> We have:
> 1. Let $G\sim G(n,p)$ with $G=(V,E)$ be a [[Erdös-Rényi Graph|random graph]]. We define the two random variables:
> 	1. $Y:=$ number of $K_{4}$s in $G$.
> 	2. $Z:=$ number of $K_{k}$s in $\overline{G}$ where $\overline{G}:=(V,{V \choose 2} \backslash E)$
> 	
> 	Finally, let $X:=Y+Z$. Then, $$\mathbb{E}[X]=\mathbb{E}[Y]+\mathbb{E}[Z]= {n \choose 4}p^6+{n \choose k} (1-p)^{k \choose 2}$$Hence, we have that there exists an instance where $X\leq \mathbb{E}[X]$ and by removing one vertex from each $K_{4}$ and each $K_{k}$ in $Y$ and $Z$, we have a lower bound in the Ramsey number. 
> 	
> 	Hence, $R(4,k)\geq n-Y - Z= n-X\geq n-{n \choose 4}p^6+{n \choose k} (1-p)^{k \choose 2}$. However, we have that: $$n-{n \choose 4}p^6+{n \choose k} (1-p)^{k \choose 2}\geq n-\frac{n^4}{4!}p^6+\frac{n^k}{k^k}(1-p)^{k^2 /2}$$Let $n=\frac{1}{4}\left( \frac{k}{\ln k} \right)^{2}$ and $p=\frac{1}{\sqrt{ n }}$. Then, we have: $$\mathbb{R}(4,k)\geq n-\frac{n}{24} +\frac{n^k}{k^k}\left( \frac{\sqrt{ n }-1}{\sqrt{ n }} \right)^{k^{2}/2}$$
> 
---
##### Examples
> [!h] Example 1 (Trivial Results)
> We have:
> 1. $R(n,2)=n$. 
> 2. $R(3,3)=6$.
> 3. $R(4,4)=18$ (no proof)

^ba602f

> [!proof]-
> We have:
> 1. Consider a complete graph $K_{n-1}$ colored with red. Then, there doesn't exists a blue edge but nor a red $K_{n}$. Therefore, $R(n,2)>n-1$.
>    
>     However, for any 2-coloring of $K_{n}$, if there is no blue edge, then $K_{n}$ is a red clique of size $n$. Therefore, $R(n,2)\leq n$. 
> 2. Firstly, we see that $R(3,3)>5$. For $n=3,4$ we can easily find a 2-coloring without a monochromatic triangle. For $n=5$, we can color the outer pentagon red and the insides blue. 
> 
> 	Now, to show that $R(3,3)=6$, choose a vertex $v$. Then, by pigeonhole, at least 3 of the incident edges to $v$ are of the same color, wlog, red. Choose any 3 and consider the triangle formed by connecting the other endpoints of the 3 edges. If this is a blue triangle, we are done. Otherwise there exists a red edge which together with the red edges to $v$ form a red triangle. This proves the statement.

^13672b

