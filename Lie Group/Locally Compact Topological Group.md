#Definition #LieGroups 

> [!definition]
> A [[topological group]] $G$ is ***locally compact***, if the underlying [[topological space]] is [[Locally Compact Topological Space|locally compact]].
---
##### Properties
> [!lemma] Lemma 1
> Let $\{ G_{\alpha} \}_{\alpha\in A}$ be a collection of Hausdorff [[Topological Group|topological groups]]. Then, 
> 1. $\prod_{\alpha\in A}^{}G_{\alpha}$ is compact if and only if $G_{\alpha}$ is compact for all $\alpha\in A$.
> 2. $\prod_{\alpha\in A}^{}G_{\alpha}$ is locally compact if and only if $G_{\alpha}$ is locally compact for all $\alpha\in A$ and $G_{\alpha}$ is compact for all except finitely many $\alpha\in A$.

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

> [!proof]-
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
>  Further, we have that $f_{k}(B_{<\varepsilon / 2}(x_{0}))=B_{<\varepsilon / 2}(x_{0})$ and $f_{k}(x_{0})=x_{0}$. Therefore, for every $x\in B_{\varepsilon / 2}(x_{0})$:$$d(f_{k}(x),x)\leq d(f_{k}(x),f_{k}(x_{0}))+d(x_{0},x)<\varepsilon$$This means, $(f_{k})_{k}\subseteq B^\infty_{<\varepsilon}(\text{id})$. However, $f_{k}\to f_{\infty}$ pointwise, where: $$f_{\infty}(x):=\begin{cases}x&x\notin \varphi ^{-1}(B_{\leq1}(0))\\x_{0}&x\in \varphi ^{-1}(B_{\leq1}(0))\end{cases}$$which is not even continuous. Therefore, $(f_{k})_{k}$ cannot have a convergent subsequence and $\text{Homeo}(M)$ is not locally compact.

 
---
> [!h] Example 3
> Let $(X,d)$ be a [[proper metric space]]. Then, 
> 1. $\text{Iso}(X)$ is locally compact.
> 2. $\text{Iso}(X)$ is compact, if $X$ is compact.

> [!proof]+
> We have: 
> 1. Assume $X$ is compact. The [[compact-open topology]] on $\text{Homeo}(X)$ coincides with the topology induced by the metric of uniform convergence: $$d_{\infty}(f,g)=$$ d∞(f, g) = sup{d(f(x), g(x)) : x ∈ X}. Note that by Arzel`a–Ascoli a family F ⊆ C(X, X) of continuous maps is compact if and only if F is equicontinuous, and F is closed. Equicontinuity of F := Iso(X) is clear, because we are dealing with isometries. We check that Iso(X) is closed. Let f ∈ C(X, X) and let (fn)n∈N ⊂ Iso(X) be a sequence converging to it. Let x, y ∈ X then 0 ⩽ |d(f(x), f(y)) − d(x, y)| = |d(f(x), f(y)) − d(fn(x), fn(y))| ⩽ |d(f(x), f(y)) − d(fn(x), f(y))| + |d(fn(x), f(y)) − d(fn(x), fn(y))| ⩽ d(f(x), fn(x)) + d(f(y), fn(y)) → 0 (n → ∞). Hence, f is an isometry as wished for. Because f was arbitrary this shows that Iso(X) ⊆ C(X, X) is closed.
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