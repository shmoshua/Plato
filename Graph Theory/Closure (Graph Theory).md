#Definition #GraphTheory 

> [!definition]
> Let $G$ be a [[graph]] on $n$ nodes.
> 1. The ***closure*** $C(G)$ of a graph $G$, is the supergraph of $G$ on $V(G)$ obtained by iteratively adding edges between a pair of non-adjacent vertices whose degree sum is at least $n$.

---
##### Properties
> [!lemma] Proposition 1
> Any graph $G$ has a unique closure.

> [!proof]-
> Let $C_{1}\neq C_{2}$ be closures of $G$. Let $e_{1},\dots,e_{k}$ and $f_{1},..,f_{\ell}$ be the edges we add to $G$ to create $C_{1}$ and $C_{2}$ respectively. Wlog we may assume $k<\ell$. Then, there exists an edge $f_{i}\notin C_{i}$. Let us assume that $i$ is also small as possible. Then, we have that: $$G':=G\cup \{ f_{1},..,f_{i-1} \}\subseteq C_{1}$$and as we are able to add $f_{i}$ to $G'$, we should be able to add it to $C_{1}$ as well, which is a contradiction. 

---
> [!lemma] Theorem 2 (Bondy Chvatal 1976)
> Let $G$ be a simple graph on $n$ vertices. TFAE:
> 1. $G$ is [[Hamiltonian Path|Hamiltonian]].
> 2. $C(G)$ is Hamiltonian.

> [!proof]-
> We have that:
> 1. (1=>2): If $G$ is Hamiltonian then as $C(G)$ is a supergraph of $G$, it contains the Hamiltonian cycle. Hence, $C(G)$ is Hamiltonian as well.
> 2. (2=>1): Let $G$ be a graph and $u,v$ be an edge where $d_{G}(u)+d_{G}(v)\geq n$. We show that if $G\cup uv$ is Hamiltonian then $G$ is Hamiltonian as well. As $G\cup uv$ is Hamiltonian, it has a Hamiltonian cycle and there is a Hamiltonian path from $u$ to $v$. 
>    
>    Let $P:=v_{1}\dots.v_{n}$ be the Hamiltonian path. Let: $S:=\{ i\in[n-1]: uv_{i+1}\in G\}$ and $T:=\{ i\in[n-1]:v_{i}v\in G \}$. Then, $$\left| S \right| +\left| T \right| =d_{G}(u)+d_{G}(v)\geq n $$and there exists $i\in S\cap T$. Therefore, we have a Hamiltonian cycle $C:=u\dots v_{i}vv_{n-1}\dots v_{i+1}u$ in $G$.

---
> [!lemma] Theorem 3 (Chvatal 1972)
> Let $G$ be a graph with vertex degrees $d_{1}\leq\dots\leq d_{n}$. 
> 1. if $i<n /2$ implies that $d_{i} > i$ or $d_{n-i}\geq n-i$, then $G$ is Hamiltonian.

> [!proof]+
> As adding edges to form the closure does not decrease the degree sequence and from Bondy Chvatal theorem, we may assume that $G$ is closed already. 
> 
> We show instead that $G=K_{n}$ via contrapositive. Assume that $G\neq K_{n}$. We will show that there exists $i<n / 2$ s.t. at least $i$ vertices have degree at most $i$ and at least $n-i$ vertices have degree less than $n-i$ i.e. $d_{i}\leq i$ and $d_{n-i}<n-i$. 
> 
> If $G\neq K_{n}$, then among the pairs of non-adjacent pairs, we choose $u,v$ s.t. $d(u)+d(v)$ is maximal. However, as $G$ is closed, $d(u)+d(v)<n$. Wlog assume that $d(u)\leq d(v)$. Then, we have that $d(u)< n /2$. Let $i:=d(u)$.



Hey Igor, sorry for only getting back to you now. Thanks for the honesty and also taking the time to send the voice note. I’ve listened to it and I understand your concerns about the age gap, life stages and all the other differences you’ve felt.

I appreciate the honesty and thanks for the voice note. 
