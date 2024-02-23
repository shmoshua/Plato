#Definition #LieGroups 

> [!definition]
> A [[topological group]] $G$ is ***locally compact***, if the underlying [[topological space]] is [[Locally Compact Topological Space|locally compact]].
---
##### Examples
> [!h] Example 1 (Elementary Topological Groups)
> We have:
> 1. Any group $G$ w.r.t the discrete topology is locally compact Hausdorff.
> 2. $(\mathbb{R}^n,+)$ w.r.t the Euclidean topology is locally compact Hausdorff.
> 3. $\mathbb{R}^{*},\mathbb{C}^{*}$ is locally compact Hausdorff.
> 4. [[General Linear Group|$\text{GL}(n,\mathbb{R})$]] is locally compact Hausdorff by [[Locally Compact Hausdorff Space|Lemma 4]] as it is open in $\text{M}_{n,n}(\mathbb{R})$.
---
> [!h] Example 2
> 
---
> [!h] Example 2
> Let $X$ be a [[locally compact Hausdorff space]]. Then, with respect to the [[compact-open topology]],
> 1. $\text{Homeo}(X)$ is not necessarily a topological group.
> 1. $\text{Homeo}(X)$ is a topological group if $X$ is compact.
> 2. $\text{Homeo}(X)$ is a topological group if $X$ is locally connected.
> 3. $\text{Homeo}(X)$ is a topological group if $X$ is a [[topological manifold]].

> [!proof]-
> We have:
> 1. Let $C$ be the [[Cantor Set]] and consider:
> 	1. $U_{n}:=C\cap [0,3^{-n}]$ and
> 	2. $V_{n}:=C\cap[1-3^{-n},1]$
> 	3. $X:= C \backslash\{ 0 \}$.
> 	  
>    Then, $h_{n}|_{X}\to \text{id}$ but $h_{n}|_{X}^{-1}\not\to \text{id}$. 
> 1. Assume $X$ is compact. For $K$ compact and $U$ open, we have that: $$i^{-1}(S(K,U))=S(U^c,K^c)$$where $U^c$ is compact (as $X$ is compact) and $K^c$ is open. Therefore, $i$ is continuous. 
>    
>    For $K$ compact and $U$ open, assume $m^{-1}(S(K,U))\neq \varnothing$ and let $(f,g)\in m^{-1}(S(K,U))$. Then, $f(g(K))\subseteq U$ and as $X$ is Hausdorff, there exists $U_{1},U_{2}\subseteq X$ open s.t. $$g(K)\subseteq U_{1}\subseteq U_{2}^c\subseteq f^{-1}(U)$$Therefore, $(f,g)\in S(U^c_{2},U)\times S(K,U_{1})$. Let $(p,q)\in S(U^c_{2},U)\times S(K,U_{1})$. Then, $$p(q(K))\subseteq p(U_{1})\subseteq p(U^c_{2})\subseteq U$$This proves that $m^{-1}(S(K,U))$ is open.
> 2. Assume $X$ is locally connected. 
---
> [!h] Example 3
> If $M$ is a [[smooth manifold]], for any $r\in \mathbb{N}$, and $$\text{Diff}^r:=\{ f\in \text{Homeo}(M):f,f^{-1}\in C^r(M) \}$$
> 1. $\text{Diff}^r$ is a topological group.
> 2. $\text{Diff}^r$ is not a closed subgroup of $\text{Homeo}(M)$.
---
> [!h] Example 4
> Let $(X,d)$ be a proper [[metric space]], i.e. all closed balls are compact. Then, the group of isometries $\text{Iso}(X)$ is a topological group w.r.t the compact-open topology.
---
> [!h] Example 5
> For $\text{GL}(n,\mathbb{R})$, 
> 1. $\text{A}:=\{ \text{diag}(\lambda_{1},\dots,\lambda_{n}):\lambda_{i}\in\mathbb{R}_{>0} \}\cong \mathbb{R}_{>0}^n$ is a closed subgroup of $\text{GL}(n,\mathbb{R})$.
> 2. $\text{UT}(n,\mathbb{R})$, the upper unitriangular group, is a closed subgroup of $\text{GL}(n,\mathbb{R})$. $\text{UT}(n,\mathbb{R})$ is homeomorphic to $\mathbb{R}^{n(n-1)/2}$ but not isomorphic, as $\text{UT}(n,\mathbb{R})$ is non-abelian.
> 3. [[Orthogonal Group|$\text{O}(n)$]] is the closed subgroup of $\text{GL}(n,\mathbb{R})$.
> 4. $\text{O}(n)\times \text{A}\times \text{UT}(n,\mathbb{R})\to \text{GL}(n,\mathbb{R}),(O,A,N)\mapsto OAN$ is a homeomorphism.
> 5. The following symmetric bilinear form on $\mathbb{R}^n$: $$B(x,y):=-\sum_{i=1}^{p}x_{i}y_{i}+\sum_{j=p+1}^{n}x_{j}y_{y}=x^\top \begin{bmatrix}-I_{p}&\\&I_{{n-p}}\end{bmatrix}y$$Then, $$O(p,q):=\{ g\in \text{GL}(n,\mathbb{R}):B_{p}(g,g) \}$$is closed in $\text{GL}(n,\mathbb{R})$.
---
> [!h] Example 6
> For $\text{GL}(n,\mathbb{C})$,
> 1. $\text{GL}(n,\mathbb{C})$ is an open subset of $\text{M}_{n,n}(\mathbb{C})$.
> 2. $\text{GL}(n,\mathbb{C})$ is a topological group w.r.t the induced topology.
> 3. $\text{U}(n) \times \text{A}\times \text{UT}(n,\mathbb{C})\to \text{GL}(n,\mathbb{C}),(U,A,N)\mapsto UAN$ is a homeomorphism.
---
> [!h] Example 7
> For $\text{SO}(p,q):=\text{O}(p,q)\cap \text{SL}(n,\mathbb{R})$ and $\text{SU}(n)=\text{U}(n)\cap \text{SL}(n,\mathbb{C})$: