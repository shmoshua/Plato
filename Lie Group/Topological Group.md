#Definition #LieGroups 
> [!definition]
> A [[group]] $G$ is ***topological*** if the underlying set is a [[topological space]] and the group operations are continuous, i.e.
> 1. $m:G\times G\to G,(g,h)\mapsto gh$ is continuous (under the product topology) and
> 2. $i:G\to G,g\mapsto g^{-1}$ is continuous.
- **Remark**: $g\mapsto g^{-1}$ is a [[homeomorphism]].
- **Related definition**: For any $g\in G$, the ***left/right translation*** are: $$\begin{array}{cccc} {L_{g}:}&{G}&\to&{G}\\&{x} &\mapsto & {gx} \end{array}{}\quad\quad\quad\quad\quad \begin{array}{cccc} {R_{g}:}&{G}&\to&{G}\\&{x} &\mapsto & {xg} \end{array}{}$$continuous and homeomorphisms (with inverses as $L_{g^{-1}},R_{g^{-1}}$).
---
> [!lemma] Proposition 1
> Let $G_{1},G_{2}$ be topological groups. If $\varphi:G_{1}\to G_{2}$ is a [[group homomorphism]], it holds that: 
> ```tikz 
> \usepackage{tikz-cd} \usepackage{amsfonts} 
> \usepackage{amssymb} 
> \begin{document} 
> \begin{tikzcd}
> G_1 \arrow[r, "\varphi"] & G_2\arrow[d, "L_{\varphi(g)}"] \\G_1 \arrow[u,"L_{g^{-1}}"]\arrow[r, swap,"\overline{\varphi}"]&G_2
> \end{tikzcd}
> \end{document}
> ```
> Therefore, $\varphi$ is continuous if and only if it is continuous at one point.
---
> [!lemma] Proposition 2
> Let $G,\{ G_{\alpha} \}_{\alpha\in A}$ be a topological group. Then:
> 1. $H\leq G$ is a topological group with the subspace topology.
> 2. $\prod_{\alpha\in A}^{}G_{\alpha}$ is a topological group with the product topology.
> 3. For $H\leq G$, the canonical projection $\pi:G \to G / H$ is [[Open and Closed Maps|open]].
> 4. for $N\unlhd G$, $G / N$ is a topological group with the quotient topology.

> [!proof]+
> We have that:
> 1. The restriction of the group operations is continuous.
> 2. For $\Gamma:=\prod_{\alpha\in A}^{}G_{\alpha}$, $\pi_{\alpha}\circ m_{\Gamma}=m_{\alpha}\circ(\pi_{\alpha},\pi_{\alpha})$ and therefore continuous. This shows that $\times_{\Gamma}$ is continuous [[Initial Topology|Lemma 2]]. Similarly, $\pi_{\alpha}\circ i_{\Gamma}=i_{\alpha}\circ(\pi_{\alpha},\pi_{\alpha})$ is continuous.
> 3. Suppose $U\subseteq G$ is an open set. Then, $\pi ^{-1}(\pi(U))=UH$
> 4. For $U\subseteq G / N$ open, $$
> 
---
##### Examples
> [!h] Example 1 (Elementary Topological Groups)
> We have:
> 1. Any group $G$ is a topological group with respect to the discrete topology. 
> 2. $(\mathbb{R}^n,+)$ is a topological group with respect to the Euclidean topology.
> 3. $\mathbb{R}^{*},\mathbb{C}^{*}$ are topological groups.
> 4. [[General Linear Group|$\text{GL}(n,\mathbb{R})$]] is a topological group.
---
> [!h] Example 2
> Let $X$ be a [[locally compact Hausdorff space]]. Then, with respect to the [[compact-open topology]],
> 1. $\text{Homeo}(X)$ is not necessarily a topological group.
> 2. $\text{Homeo}(X)$ is a topological group if $X$ is compact.
> 3. $\text{Homeo}(X)$ is a topological group if $X$ is locally connected.
> 4. $\text{Homeo}(X)$ is a topological group if $X$ is a [[topological manifold]].
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