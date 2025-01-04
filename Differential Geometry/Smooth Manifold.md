#Definition #DifferentialGeometry 

> [!definition]
> A ***smooth manifold*** is a [[topological manifold]] $M$ equipped with a ***smooth structure*** $\mathcal{X}$, i.e. a maximal [[Atlas|smooth atlas]].
- **Related definition**: A ***$C^k$-differential manifold*** is a topological manifold with a maximal $C^k$-atlas.
---
##### Properties
> [!lemma] Lemma 1
> Let $M,N$ be smooth manifolds  with atlases $\mathcal{A},\mathcal{B}$. Further, let $f:\mathbb{R}^n\to \mathbb{R}^m$ be a smooth map.
> 1. Let $a\in \mathbb{R}^m$ be a ***regular value***, i.e. for every $x\in f^{-1}(a)$ the derivative $D_{x}f:\mathbb{R}^n\to \mathbb{R}^m$ has full rank $m$. Then, $f^{-1}(a)$ is a smooth manifold.
> 2. For $U\subseteq M$ open, $\mathcal{A}|_{U}:=\{ (U\cap V,\varphi|_{U\cap V})|(V,\varphi)\in \mathcal{A} \}$ is a smooth atlas on $U$ that is not necessarily maximal. However, it is contained in a unique maximal smooth atlas by [[Atlas|Lemma 2]].
> 3. $\mathcal{P}:=\{ (U_{\alpha}\times V_{\beta},\varphi_{\alpha}\times \psi_{\beta}) |(U_{\alpha},\varphi_{\alpha})\in \mathcal{A},(V_{\beta},\psi_{\beta})\in \mathcal{B}\}$ is a smooth atlas on $M\times N$ that is not necessarily maximal.
> 

> [!proof]-
> Let $\mathcal{X}=\{ (U_{\alpha},x_{\alpha}) \}_{\alpha}$ be a smooth structure on $M$. Then, $$\{ x_{\alpha}|_{U_{\alpha}\cap W}: U_{\alpha}\cap W\to x_{\alpha}(U_{\alpha}\cap W)\}_{\alpha}$$is a smooth structure on $W$. 
---
> [!lemma] Lemma 2
> Let $M$ be a Hausdorff space. Given a collection  $\{ (U_{\alpha},x_{\alpha} )\}_{\alpha\in A}$ where $U_{\alpha}\subseteq M$ is open and $x_{\alpha}:U_{\alpha}\to \mathcal{O}_{\alpha}$ is a bijection with $\mathcal{O}_{\alpha}\subseteq \mathbb{R}^m$ as an open set. If additionally, 
> 1. $x_{\alpha}(U_{\alpha}\cap U_{\beta})\subseteq \mathbb{R}^m$ is open for all $\alpha,\beta\in A$,
> 2. $x_{\beta}\circ x_{\alpha}^{-1}: x_{\alpha}(U_{\alpha}\cap U_{\beta})\to x_{\beta}(U_{\alpha}\cap U_{\beta})$ is a [[diffeomorphism]] for $U_{\alpha}\cap U_{\beta}\neq \varnothing$.
> 3. countably many of $U_{\alpha}$ cover $M$
> 4. If $p\neq q$, then either there exists $\alpha\in A$ s.t. $\{ p,q \}\subseteq U_{\alpha}$ or there exists $\alpha,\beta\in A$ s.t. $p\in U_{\alpha}, q\in U_{\beta}$ and $U_{\alpha}\cap U_{\beta}=\varnothing$.
> 
> Then, $M$ has a unique smooth manifold structure for which $\{ (U_{\alpha},x_{\alpha}) \}_{\alpha\in A}$ is a smooth atlas.

> [!proof]-
> Define a topology on $M$ by declaring all $x_{\alpha}$ to be homeomorphisms. This is well-defined as $x_{\alpha}$ are bijections. Then, $M$ is 2nd-countable Hausdorff by 3 and 4, and is a topological manifold. By 2, we have a smooth manifold.
---
> [!lemma] Theorem 3 (Smooth Urysohn's Lemma)
> Let $M$ be a smooth manifold. Let $A\subseteq U\subseteq M$ where $A$ is closed and $U$ open. Then, there exists a smooth function $\varphi\in C^\infty_{00}(M)$ s.t.
> 1. $\text{im }\varphi \subseteq[0,1]$
> 2. $\varphi|_{A}=1$
> 3. $\text{supp }\varphi \subseteq U$

> [!proof]-
> There is a partition of unity $\{ \varphi,\psi \}$ subordinate to the cover $\{ U, M \backslash A \}$ of $M$ per [[Partition of Unity|Example 2]] with $\text{supp }\varphi \subseteq G$ and $\text{supp }\psi \subseteq M\backslash A$. Then, $\varphi$ is the desired function.

---
> [!lemma] Theorem 4
> Let $f:M\to N$ be a continuous function between manifolds. Then, there exists a smooth map $g:M\to N$ s.t. $f$ and $g$ are [[Homotopy|homotopic]].

> [!proof]+
> 

---
##### Examples
> [!h] Example 1
> We have that: 
> 1. $\mathbb{R}^m$ has the smooth structure $\{ \text{id}:\mathbb{R}^m\to \mathbb{R}^m \}$
> 2. Any $m$-dimensional $\mathbb{R}$-vector space $V$ has the smooth structure $\{ \ell:V\to \mathbb{R}^m \}$ where $\ell$ is some linear isomorphism.
> 3. For any smooth $f:U\to \mathbb{R}^n$ where $U\subseteq \mathbb{R}^m$ open, $\text{graph}(f)\subseteq \mathbb{R}^m\times \mathbb{R}^n$ is a smooth $n$-manifold with a single chart $\varphi:\text{graph}(f)\to U,(x,f(x))\mapsto x$.
> 4. For any $M\subseteq \mathbb{R}^N$ s.t. locally $M$ can be viewed as a graph of some smooth $f:U\subseteq \mathbb{R}^n\to \mathbb{R}^{N-n}$ in an orthogonal coordinate system, then for each such open set, the chart is given by $\varphi$ in 3. E.g. [[Surface|smooth surfaces]] in $\mathbb{R}^3$.
---
> [!h] Example 2
> The unit sphere defined as: $$S^m:=\{ p\in \mathbb{R}^{m+1}|\left\| p \right\| =1 \}$$is a compact smooth manifold of dimension $m$.

> [!proof]-
> We give $S^m$ the [[Topological Space|subspace topology]] from $\mathbb{R}^{m+1}$. Therefore, $S^m$ is second-countable Hausdorff. Now, we will construct a smooth atlas for $S^m$. We define:
> 1. $p_{N}:=(0,\dots,0,1)$ the north pole and
> 2. $p_{S}:=(0,\dots,0,-1)$ the south pole.
> 
> Then, we define $U_{N}:=S^m \backslash \{ p_{N} \}$ and $U_{S}:=S^m \backslash\{ p_{S} \}$, which results in $\{ U_{N},U_{S} \}$ being an open cover of $S^m$. We define the charts:
> 1. $x_{N}:U_{N}\to \mathbb{R}^m,x_{N}(u^1,\dots,u^{m+1}):= \frac{1}{1-u^{m+1}}(u^1,\dots,u^{m})$
> 2. $x_{S}:U_{S}\to \mathbb{R}^m,x_{S}(u^1,\dots,u^{m+1}):= \frac{1}{1+u^{m+1}}(u^1,\dots,u^{m})$
>    
> which are the stereographic projection from the north/south pole respectively. Then, the transition maps are given as: $$(u^1,\dots,u^m)\mapsto \frac{1}{\sum_{i=1}^{m}(u^i)^{2}}(u^1,\dots,u^m)$$which is obviously a diffeomorphism. Therefore, this is a smooth structure on $S^m$, called the standard smooth structure. 
---
![[Open Equivalence Relation#^88f964]]
![[Open Equivalence Relation#^1a186e|p]]
---
![[Grassmannian#^af4191]]
![[Grassmannian#^a87389|p]]
---