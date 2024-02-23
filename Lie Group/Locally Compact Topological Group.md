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
> Let $M$ be a [[topological manifold]] of dimension $m\geq 1$. Then, $\text{Homeo}(M)$ is a topological group but not locally compact.

> [!proof]+
> We will show that $\text{Homeo}(M)$ is not locally compact for any compact manifold $M$. Note that we can think of $M$ as a compact metric space $(M,d)$ by Urysohn’s metrization theorem. In the case when $M$ is a smooth manifold this is even easier to see by endowing it with a Riemannian metric. 
> 
> This puts us now in the favorable position of being able to identify the compact-open topology on $\text{Homeo}(X)$ with the topology of uniform convergence. We denote by $$d_{\infty}(f,g):=\sup\{ d(f(x),g(x)): x\in M \}$$
>  the metric of uniform convergence on $\text{Homeo}(M)$. Further denote by $B^\infty_{<r}(f)\subseteq\text{Homeo}(M)$ the ball of radius $r>0$ about a homeomorphism $f\in \text{Homeo}(M)$. 
>  
>  In order to show that $\text{Homeo}(M)$ is not locally compact, for every $\varepsilon>0$, we will construct $(f_{k})_{k}\subseteq B^\infty_{<\varepsilon}(\text{id})$ with no convergent subsequence.
>  
>  Let $B:=B^\infty_{<\varepsilon}(\text{id})$ and $x_{0}\in M$. Choose a chart $(\varphi,U)$ s.t.
>  1. $U\subseteq B_{<\varepsilon /2}(x_{0})$ and 
>  2. $\varphi(x_{0})=0$
>  
>  Consider the following homeomorphisms: $$\begin{array}{cccc} {\psi_{k}:}&{B_{\leq 1}(0)}\subseteq \mathbb{R}^m&\to&{B_{\leq 1}(0)\subseteq \mathbb{R}^m}\\&{x} &\mapsto & {\|x\|^kx} \end{array}{}$$which fix $0\in \mathbb{R}^m$ and the boundary $\partial B_{<1}(0)\subseteq \mathbb{R}^m$ pointwise. Then, $\psi_{k}\to \psi_{\infty}$ pointwise where: $$\psi_{\infty}(x)=\begin{cases}x&x\in \partial B_{<1}(0)\\0&\text{otherwise}\end{cases}$$
>  
>  Now, define $f_{k}:M\to M$: $$f_{k}(x):=\begin{cases}x&x\notin \varphi ^{-1}(B_{\leq1}(0))\\\varphi ^{-1}(\psi_{k}(\varphi(x)))&x\in \varphi ^{-1}(B_{\leq1}(0))\end{cases}$$Then, $f_{k}\in \text{Homeo}(M)$ as $\varphi ^{-1}\circ\psi_{k}\circ\varphi:\varphi ^{-1}(B_{\leq 1}(0))\to\varphi ^{-1}(B_{\leq 1}(0))$ is a homeomorphism and $f_{k}$ is $\text{id}$ everywhere else. Further they coincide on the boundary $\varphi ^{-1}(\partial B_{<1}(0))$.
>  
>  Further, we have that $f_{k}(B_{<\varepsilon / 2}(x_{0}))=B_{<\varepsilon / 2}(x_{0})$
Further, the homeomorphisms fk map the ε/2-ball Bε/2(x0) to itself and fix x0. Therefore, d(fk(x), x) ⩽ d(fk(x), fk(x0) | {z } =x0 ) + d(x0, x) < ε, for every x ∈ Bε/2(x0), and clearly fk(x) = x for every x /∈ Bε/2(x0). Hence, the sequence (fk)k∈N is in B∞ ε (id). However, the sequence (fk)k∈N converges pointwise to f∞(x) = ( x, if x /∈ φ −1 (B1(0)), x0, if x ∈ φ −1 (B1(0)), 4 If there were a subsequence (fkl )l∈N converging to some f ∈ Homeo(M) uniformly then this sequence would also converge pointwise to f, i.e. f needs to coincide with f∞. But f∞ is not even continuous which contradicts our assumption of f ∈ Homeo(M). Therefore (fk)k∈N ⊂ B∞ ε (id) has no uniformly convergent subsequences.
 
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