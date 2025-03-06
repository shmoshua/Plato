#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a (multi)-[[graph]]. 
> 1. An ***Eulerian trail*** in $G$ is a [[walk]] that passes through each edge exactly once. 
> 2. An ***Eulerian tour*** is an Eulerian trail that is closed.

^af172c

---
##### Properties
> [!lemma] Lemma 1
> Any maximal trail in an even graph is closed.

^bb32a6

> [!proof]-
> Let $T$ be a maximal trail. If $T$ is not closed, then there are odd number of edges in $T$ that are incident to the final vertex $v$ of $T$. However, as $v$ has even degree, we have an edge incident to $v$ that is not in $T$. Hence, we can extend $T$, which is a contradiction.

^bdc3a8

---
> [!lemma] Theorem 2
> Let $G$ be a connected (multi)graph. Then,
> 1. $G$ has an Eulerian tour if and only if $G$ is even.
> 2. $G$ has an Eulerian trail if and only if there are either $0$ or $2$ vertices with odd degree. 

^b2ca6d

> [!proof]-
> We have that:
> 1. Let $C$ be an Eulerian tour. If $C$ visits $v$ exactly $k$ times. Then, we use $2$ edges every visit and $d(v)=2k$.
>    
>    Let $G$ be an even connected graph. Let $T=e_{1}e_{2}\dots e_{\ell}$ be the longest trail with $e_{i}=(v_{i-1},v_{i})$. Then, by Lemma 1, $T$ is closed. If $T$ doesn't include all edges, as $G$ is connected there exists an edge $e=(u,v_{i})$ outside of $T$. However, then we have that: $$T':=e e_{i+1}e_{i+2}\dots e_{\ell}e_{1}\dots e_{i}$$ is a trail longer than $T$. This is a contradiction, hence $T$ includes all edges, i.e. it is a Eulerian tour.
> 2. Let $G$ have an Eulerian trail $T$. If this is a tour, then $G$ is even and there are no vertices of odd degree. Otherwise, $(u,v)\notin G$ where $u,v$ are the endpoints of $T$. However, $G \cup e$ has an Eulerian tour $T \cup e$. Hence, $G\cup e$ is even which implies that $u,v$ are the only odd vertices in $G$.
>    
>    Conversely, if there are no vertices of odd degree, then $G$ is even and $G$ has an Eulerian tour, which is a trail. If there are $2$ vertices of odd degree, $u$ and $v$, then by adding $e:=(u,v)$ we have that $G\cup e$ is even and $G\cup e$ has an Eulerian tour. By deleting $e$, we get an Eulerian trail in $G$. 

^59ce63

---
