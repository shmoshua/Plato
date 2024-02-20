#Definition #Algebra

> [!definition]
> A [[group]] $G$ is ***simple***, if $G$ doesn't have any non-trivial [[Normal Subgroup|normal divisors]].

---
##### Properties
- An abelian group is simple if and only if it doesn't have any non-trivial subgroup.
  Examples: 
  - $C$ is not simple.
  - $C_{p}$ is simple for prime $p$. 
  - $D_{n}$ is not simple for $n \geq 3$
---
> [!lemma] Proposition 1
> Let $G$ be a group of order $pq^k$ for two different primes $p,q$ s.t. $p < q$. Then, $G$ is not simple and is [[Solvable Group|solvable]]. 

> [!proof]-
> Consider $\text{Syl}_{q}(G)$. Then, we have: 
> 1. $|\text{Syl}_{q}(G)|\equiv_{q} 1$ and
> 2. $\left| \text{Syl}_{q}(G) \right| | p$
>    
> Therefore, $|\text{Syl}_{q}(G)|=1$ and the Sylow $q$-subgroup $P$ is normal. 
> 
---
> [!lemma] Proposition 2
> Let $p,q,r$ be pairwise different primes. Then, for any $G$ s.t. $\left| G \right|=pqr$, it cannot be simple.

> [!proof]-
> Let $s_{p}:=\left| \text{Syl}_{p}(G) \right|$ for all prime $p$. Assume that $p\leq q\leq r$. Then,
> 1. $s_{p}\equiv_{p}1$ and $s_{p}|qr$. Therefore, $s_{p}\in \{ 1,q,r,qr \}$
> 2. $s_{q}\equiv_{q}1$ and $s_{q}|pr$. Therefore, $s_{q}\in \{ 1,r,pr \}$
> 3. $s_{r}\equiv_{r}1$ and $s_{r}|pq$. Therefore, $s_{r}\in \{ 1,pq \}$
>    
> If $s_{p}\neq 1$, $s_{q}\neq 1$, $s_{r}\neq 1$, then, 
> 1. $s_{p}\geq q$
> 2. $s_{q}\geq r$
> 3. $s_{r}\geq pq$
> 
> Since, they are prime, the Sylow $p$-subgroups only intersect at $e$. Therefore, $$\begin{align}\left| G \right| &\geq 1+s_{p}(p-1)+s_{q}(q-1)+s_{r}(r-1)\\&\geq 1+q(p-1)+r(q-1)+pq(r-1)\\&=pqr+(q-1)(r-1)\\&> |G|\end{align}$$
> Therefore, $s_{p}=1$ or $s_{q}=1$ or $s_{r}=1$, which implies that $G$ is not simple.
---
##### Examples
- [[Alternating Group]] $A_{n}$ for $n\geq 5$.
- $C_{p}$ is simple for prime $p$. 
---