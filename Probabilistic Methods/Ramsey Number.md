#ProbabilisticMethods #Definition 

> [!definition]
> For $k,\ell\in \mathbb{Z}_{>0}$, the **Ramsey number** $R(k,\ell)$ is the smallest integer $n$ s.t. 
> 1. every red-blue edge-coloring of the [[complete graph]] $K_{n}$ has a red clique of size $k$ or a blue clique of size $\ell$.

^bf6551

---
##### Properties
> [!lemma] Theorem 1
> For $k,\ell>2$, we have that:
> 1. $R(k,\ell)\leq R(k-1,\ell)+R(k,\ell-1)$

> [!proof]+
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

