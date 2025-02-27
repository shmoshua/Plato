#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a simple [[Path|connected]] [[graph]].
> 1. $G$ is ***$k$-connected*** if:
> 	1. $\left| V \right|> k$ and:
> 	2. for any $S\in {V \choose k-1}$, $G \backslash S$ is connected.
> 2. $G$ is ***$k$-edge-connected*** if:
> 	1. for any $E'\in {E \choose k-1}$, $G \backslash E'$ is connected.

^203f06

- **Related definition**: For a connected graph $G=(V,E)$,
	1. A ***cut vertex*** is a vertex $v\in V$ s.t. $G \backslash v$ is disconnected.
	2. A ***bridge*** is an edge $e\in E$ s.t. $G \backslash e$ is disconnected.
	3. For $A,B\subseteq V$, $X\subseteq V$ or $X\subseteq E$ ***separates*** $A$ and $B$ if every $AB$-path contains a vertex/an edge in $X$.
- **Related definition**: 
	1. The ***connectivity number*** $\kappa(G):=\text{max }\{ k\in \mathbb{N} :G\text{ is }k\text{-connected}\}$
	2. The ***edge connectivity number*** $\kappa'(G):=\text{max }\{ k\in \mathbb{N} :G\text{ is }k\text{-edge-connected}\}$ ^cc03cf

---
##### Properties
> [!lemma] Theorem 1
> Let $G=(V,E)$ be a graph.
> 1. $\kappa(G)\leq \delta(G)$
> 2. $\kappa'(G)=\min_{S\subseteq V}e(S,\overline{S})$.
> 3. $\kappa(G)\leq \kappa'(G)\leq \delta(G)$

^4e811f

> [!proof]-
> We have:
> 
> 1. Let $k> \delta(G)$. Then, we show that $G$ cannot be $k$-connected. Assume that $\left| V \right|>k$. Let $v$ s.t. $d(v)=\delta(G)$. Then, $k-1\geq \delta(G)$ and 
> 	1. if $N(v)=V \backslash \{ v \}$. Then, as $d(u)\geq \delta(G)=d(v)$, we have that $G$ is a complete graph on $\delta(G)+1$ vertices and we get that $\kappa(G)\leq \delta(G)$. 
> 	2. otherwise, there exists $w\neq v$ that is not in $N(v)$. Hence, by deleting $N(v)$, we disconnect $v$ and $w$. 
> 2. Follows from the fact that a minimal disconnecting set is always a cut.
> 3. Take $v$ with $d(v)=\delta(G)$. Then, we can delete all the incident edges to $v$ and we get a disconnected graph.
>    
>    Let $S\subseteq V$ s.t. $\kappa'(G)=e(S,\overline{S})$ with $\left| S \right|=s$. 
> 	1. If the cut is complete, then $\kappa'(G)=s(n-s)\geq n-1$. However, obviously,  $\kappa(G)\leq n-1$. 
> 	2. if the cut is not complete, then there exists $x\in S$ and $y\in \overline{S}$ s.t. $xy\notin E$. Let $T_{1}:= \overline{S}\cap N(x)$ and let $T_{2}:=\{ v\in S \backslash \{ x \}:N(v)\cap \overline{S}\neq \varnothing \}$.
> 	   
> 	   Now, note that $T_{1}\cup T_{2}$ disconnects $x$ from $y$. Then, $$T_{1}\cup T_{2}\hookrightarrow E (S,\overline{S}),\quad v\mapsto \begin{cases}xv&\text{if }v\in T_{1}\\vw&\text{if }v\in T_{2}\text{ which exists by definition }\end{cases}$$Therefore $\kappa(G)\leq \left| T_{1}\cup T_{2} \right|\leq e(S,\overline{S})=\kappa'(G)$.

^049821

---
> [!lemma] Theorem 2 (Mader)
> Let $G$ be a graph and $k\in \mathbb{N}$.
> 1. if $d(G)\geq 4k$, then $G$ has a $k$-connected subgraph.

^dd00c3

> [!proof]-
> If $k\in \{ 0,1 \}$, then the statement is trivial. Hence, let $k\geq 2$. Let further $m:=e(G)$. 
> 
> Now, let $\Gamma$ be an arbitrary simple graph on $n$ vertices and $m$ edges s.t. $n\geq 2k-1$ and $m\geq (2k-3)(n-k+1)+1$. Then, we claim that $G$ has a $k$-connected subgraph.
> 
> If this claim holds, then we have that for our original graph $G$, i.e. $d(G)\geq 4k$. Then: $$n\geq \Delta(G)\geq d(G)\geq 4k\geq 2k-1,\quad e(G)=\frac{n}{2}d(G)\geq 2kn\geq (2k-3)(n-k+1)+1$$
> Hence, it suffices to show the claim.
> 
> We show this using induction over $n$.
> 1. Let $n=2k-1$. Then, $k=\frac{n+1}{2}$ and the number of edges is: $$m\geq (n-2)\left( \frac{n+1}{2} \right)+1=\frac{n^2-n}{2}=\frac{n(n-1)}{2}$$and $\Gamma=K_{n}$ and $\Gamma$ is $n-1=2k-2\geq k$-connected. 
> 2. Let $n\geq 2k$. If there exists $v\in V$ s.t. $d(v)\leq 2k-2$, then $\Gamma':=\Gamma \backslash \{ v \}$. Then, $\left| V(\Gamma') \right|=n-1\geq 2k-1$ and $e(\Gamma')\geq e(\Gamma)-2k+3=(2k-3)(n-k)+1$. Hence, by induction we have a $k$-connected subgraph. 
>    
>    Now, assume that $\delta(\Gamma)\geq 2k-2$. 
> 	1. If $\Gamma$ is $k$-connected, then we are done. 
> 	2. if $\Gamma$ is not $k$-connected, then there exists $S\subseteq V$ with $\left| S \right|\leq k-1$ s.t. $\Gamma \backslash S$ is disconnected. 
> 	   
> 	   Hence, we can write $V=V_{1}\sqcup S \sqcup V_{2}$ s.t. $V_{1},V_{2}\neq \varnothing$ and $e(V_{1},V_{2})= 0$. Now, let $\Gamma_{1}:=\Gamma[V_{1}\cup S]$ and $\Gamma_{2}:=\Gamma[V_{2}\cup S]$.
> 	   
> 	   For any $v\in V_{1}$, $N_{v}\subseteq \Gamma_{1}$ and $\left| V(\Gamma_{1}) \right|\geq N_{v}+1\geq 2k-2+1=2k-1$. If $e(\Gamma_{1})\geq (2k-3)(\left| V(\Gamma_{1}) \right|-k+1)+1$, then we are done by induction. Otherwise, $$e(\Gamma_{1})\leq (2k-3)(\left| V(\Gamma_{1}) \right| -k+1)$$
> 	   By symmetry, we are left to show it for the case that: $$e(\Gamma_{1})\leq (2k-3)(\left| V(\Gamma_{1}) \right| -k+1),\quad e(\Gamma_{2})\leq (2k-3)(\left| V(\Gamma_{2}) \right| -k+1)$$Then, $$e(\Gamma)\leq e(\Gamma_{1})+e(\Gamma_{2})\leq(2k-3)(n-k+1)$$which is a contradiction so this cannot happen. 

^ab76d0

---
> [!lemma] Theorem 3 (Whitney, 1932)
> Let $G=(V,E)$ be a graph with $\left| V \right|\geq 3$. TFAE:
> 1. $G$ is $2$-connected.
> 2. for all $u,v\in V$, there exist two internally disjoint $uv$-paths.
> 3. for all $u,v\in V$, there exists a cycle that contains $u,v$. 

> [!proof]-
> We have that:
> 1. (1=>2): Let $G$ be $2$-connected and fix $u,v\in V$. We show by induction on $d(u,v)$. 
> 	1. Let $d(u,v)=1$ and $e=uv$. As $G$ is $2$-connected, $G$ is $2$-edge-connected and $G \backslash e$ is connected. Hence, there exists a $uv$-path in $G \backslash e$, i.e. there exist two internally disjoint $uv$-paths.
> 	2. Let $d(u,v)\geq 2$. Let $w$ be vertex adjacent to $v$ in the shortest $uv$ path of length $k:= d(u,v)$. Then, $d(u,w)=k-1$ and there exist two internally disjoint $uw$-paths $Q,R$. Now, if we delete $w$, then $G \backslash w$ is still connected as $G$ is $2$-connected. 
> 	   
> 	   Let $P$ be a $uv$-path in $G \backslash e$. Let $x$ be the last vertex from either $Q$ or $R$ on $P$. Wlog we may assume $x\in Q$. Now, by taking $Q':=Q|_{u\dots x}+P|_{x\dots v}$ and $R':=R+wv$ which are internally vertex disjoint by definition.
> 2. (2=>3): The two paths form a cycle.
> 3. (3=>1): Deletion of one vertex cannot separate $u,v\in V$ for all $u,v\in V$. 
---
> [!lemma] Theorem 4 (Menger, 1927)
> Let $G=(V,E)$ be a graph and $S,T\subseteq V(G)$.
> 1. the maximal number of vertex disjoint $ST$-paths is the size of the minimal $ST$-separating set.

> [!proof]-
> Obviously, the maximum number of disjoint paths does not exceed the minimum size of a separating set, because for any collection of disjoint paths, any separating set must contain a vertex from each path. Hence, $\leq$ holds.
> 
> Suppose we have a separating set of size $k$. We need to show that there exist $k$ vertex disjoint $ST$-paths. We show this using induction over $\left| E \right|+\left| V \right|$.
> 1. Let $\left| E \right|=\varnothing$. Then, the minimal $ST$-separating set is $X:=S\cap T$. This is precisely the number of vertex disjoint $ST$-paths. 
> 2. Let $\left| V \right|+\left| E \right|> \left| V \right|$. 
> 	1. Assume that $S\cap T=\varnothing$. Take $e:=uv\in E$ arbitrary and let $G':= G \backslash e$. 
> 		1. If the minimal separa
---
##### Examples
> [!h] Example 1
> We have:
> 1. $\kappa(K_{n})=n-1$.
> 2. $\kappa(K_{r,s})=\min \{ r,s \}$.
> 3. $\kappa'(K_{n})=n-1$.

^b902c3

> [!proof]+
> We have:
> 1. Obvious.
> 2. Let $V(K_{r,s})=A\sqcup B$. Assume wlog $\min \{ r,s \}=r$. Then, for any $S\in {V \choose r-1}$, there will be at least $u$.
> 3. From Proposition 1.2, $$\kappa'(G)=\min_{s\in[n-1]}s(n-s)=n-1$$

^d93829

---
> [!h] Example 2
> We have that:
> 1. A [[Cut (Graph)|cut]] is always a disconnecting set. 
> 2. A minimal disconnecting set is always a cut.

---