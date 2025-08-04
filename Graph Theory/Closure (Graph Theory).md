#Definition #GraphTheory 

> [!definition]
> Let $G$ be a [[graph]] on $n$ nodes.
> 1. The ***closure*** $C(G)$ of a graph $G$, is the supergraph of $G$ on $V(G)$ obtained by iteratively adding edges between a pair of non-adjacent vertices whose degree sum is at least $n$.

^56af79

---
##### Properties
> [!lemma] Proposition 1
> Any graph $G$ has a unique closure.

^0d8c43

> [!proof]-
> Let $C_{1}\neq C_{2}$ be closures of $G$. Let $e_{1},\dots,e_{k}$ and $f_{1},..,f_{\ell}$ be the edges we add to $G$ to create $C_{1}$ and $C_{2}$ respectively. Wlog we may assume $k<\ell$. Then, there exists an edge $f_{i}\notin C_{i}$. Let us assume that $i$ is also small as possible. Then, we have that: $$G':=G\cup \{ f_{1},..,f_{i-1} \}\subseteq C_{1}$$and as we are able to add $f_{i}$ to $G'$, we should be able to add it to $C_{1}$ as well, which is a contradiction. 

^2e374d

---
> [!lemma] Theorem 2 (Bondy Chvatal 1976)
> Let $G$ be a simple graph on $n$ vertices. TFAE:
> 1. $G$ is [[Hamiltonian Path|Hamiltonian]].
> 2. $C(G)$ is Hamiltonian.

^654eca

> [!proof]-
> We have that:
> 1. (1=>2): If $G$ is Hamiltonian then as $C(G)$ is a supergraph of $G$, it contains the Hamiltonian cycle. Hence, $C(G)$ is Hamiltonian as well.
> 2. (2=>1): Let $G$ be a graph and $u,v$ be an edge where $d_{G}(u)+d_{G}(v)\geq n$. We show that if $G\cup uv$ is Hamiltonian then $G$ is Hamiltonian as well. As $G\cup uv$ is Hamiltonian, it has a Hamiltonian cycle and there is a Hamiltonian path from $u$ to $v$. 
>    
>    Let $P:=v_{1}\dots.v_{n}$ be the Hamiltonian path. Let: $S:=\{ i\in[n-1]: uv_{i+1}\in G\}$ and $T:=\{ i\in[n-1]:v_{i}v\in G \}$. Then, $$\left| S \right| +\left| T \right| =d_{G}(u)+d_{G}(v)\geq n $$and there exists $i\in S\cap T$. Therefore, we have a Hamiltonian cycle $C:=u\dots v_{i}vv_{n-1}\dots v_{i+1}u$ in $G$.

^d75485

---
> [!lemma] Theorem 3 (Chvatal 1972)
> Let $G$ be a graph with vertex degrees $d_{1}\leq\dots\leq d_{n}$. 
> 1. if $i<n /2$ implies that $d_{i} > i$ or $d_{n-i}\geq n-i$, then $G$ is Hamiltonian.

^b0e3a6

> [!proof]-
> As adding edges to form the closure does not decrease the degree sequence and from Bondy Chvatal theorem, we may assume that $G$ is closed already. 
> 
> We show instead that $G=K_{n}$ via contrapositive. Assume that $G\neq K_{n}$. We will show that there exists $i<n / 2$ s.t. at least $i$ vertices have degree at most $i$ and at least $n-i$ vertices have degree less than $n-i$ i.e. $d_{i}\leq i$ and $d_{n-i}<n-i$. 
> 
> If $G\neq K_{n}$, then among the pairs of non-adjacent pairs, we choose $u,v$ s.t. $d(u)+d(v)$ is maximal. However, as $G$ is closed, $d(u)+d(v)<n$. Wlog assume that $d(u)\leq d(v)$. Then, we have that $d(u)< n /2$. Let $i:=d(u)$.
> 
> By the maximality assumption, every vertex of $V \backslash v$ that is not adjacent to $v$ has degree at most $i$. However, there are at least $n-1-d(v)\geq d(u)=i$ of these vertices. Similarly, every vertex of $V \backslash u$ that is not adjacent to $u$ has degree at most $d(v)<n-d(u)=n-i$. There are $n-1-d(u)=n-1-i$ of these. Since $d(u)\leq d(v)$, we can also count $u$ as one of those vertices and have $n-i$ vertices with degree less than $n-i$. This proves the statement.

^070269


---
> [!lemma] Theorem 4 (Chvatal-Erdös 1972)
> Let $G\neq K_{2}$ be a graph.
> 1. if $\kappa(G)\geq \alpha(G)$ then $G$ is Hamiltonian.

^3ed9fa

> [!proof]-
> We have that $G$ is trivially true if $G$ is complete. Otherwise, we have that $\kappa(G)\geq \alpha(G)\geq 2$. We show that if $G$ has no Hamiltonian cycle, then $k:=\kappa(G)<\alpha(G)$. 
> 
> Let $C$ be the longest cycle, which is not Hamiltonian. Let $H$ be a component in $G \backslash C$. Since $\delta(G)\geq \kappa(G)$ and by [[Path (Graph)|Proposition 2]] $G$ has a cycle of length at least $\delta(G)+1$, we have that $C$ has at least $k+1$ vertices. Also $C$ has at least $k$ vertices with edges to $H$ from $\kappa(G)=k$. 
> 
> Let $u_{1},\dots,u_{\ell}$ be the vertices on $C$ with edges to $H$ where $\ell\geq k$ in clockwise order. Let $a_{i}$ be the vertices right after $u_{i}$ on $C$. 
> 
> 1. If $a_{i}$ has a neighbor in $H$, then $a_{i}=u_{i+1}$ and we have a longer cycle by replacing $u_iu_{i+1}$ with the path that goes through $H$. Hence, $a_{i}$ has no neighbor in $H$.
> 2. if $a_{i}a_{j}\in E$, then we can extend the cycle by taking $C':=a_{i}a_{j}\dots u_{i} P u_{j}\dots a_{i}$ where $P$ is the $u_{i}u_{j}$ path that goes through $H$. 
> 
> In both cases, we have a contradiction. Therefore, we have that $\{ a_{1},\dots,a_{k} \}$ together with a vertex in $H$ creates an independent set of size $k+1$. This shows that $\alpha(G)\geq k+1$. 

^b220de

---
