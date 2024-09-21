#ProbabilisticMethods #Definition 

> [!definition]
> For $s,t\in \mathbb{Z}_{>0}$, the **Ramsey number** $R(s,t)$ is the smallest integer $n$ s.t. 
> 1. every red-blue edge-coloring of the [[complete graph]] $K_{n}$ has a red clique of size $s$ or a blue clique of size $t$.

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

^3cf037

- **Corollary**: As $R(n,2)=R(2,n)={n\choose 1}$, $R(s,t)\leq {s+t-2\choose s-1}$ using induction.

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

