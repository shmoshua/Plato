#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]]. The ***compact-open topology*** on $C(X,Y)$ is a topology that has $$S(K,U):=\{ f\in C(X,Y):f(K)\subseteq U \}$$where $K\subseteq X$ compact and $U\subseteq Y$ open as a sub-basis, i.e. the finite intersections of these form the basis of the topology.
---
##### Properties
> [!lemma] Proposition 1
> If $X$ is discrete, then the compact-open topology on $C(X,Y)=Y^X$ is the product topology. 
---
> [!lemma] Lemma 2
> Let $X,Y,Z$ be Hausdorff spaces and $h:Z \to X$ continuous. Then, $$h^{*}:C(X,Y)\to C(Z,Y)$$is continuous w.r.t compact-open topologies.

> [!proof]-
> For $g\in C(X,Y)$, $K\subseteq Z$ compact and $U\subseteq Y$ open, s.t. $h^{*}(g)=g \circ h\in S(K,U)$. Then, $h(K)$ is compact and $h^{*}(S(h(K),U))\subseteq S(K,U)$.
---
> [!lemma] Proposition 1
> Let $(X,d)$ be a [[metric space]]. Then, the compact-open topology on $C(X)$ is equivalent to the topology of uniform convergence on compact subsets of $X$. 