#Definition #Topology  #LieGroups 
> [!definition]
> A [[group]] $G$ is ***topological*** if the underlying set is a [[topological space]] and the group operations are continuous, i.e.
> 1. $m:G\times G\to G,(g,h)\mapsto gh$ is continuous and
> 2. $i:G\to G,g\mapsto g^{-1}$ is continuous.

^de795b

- **Remark**: $g\mapsto g^{-1}$ is a [[Homeomorphism]].
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
> Therefore, $\varphi$ is continuous if and only if it is continuous at $e\in G_{1}$.

> [!proof]-
> One direction is trivial. 
> 
> For the other, if $\varphi$ is continuous at $e$. Let $U\subseteq G_{2}$ open. If $\varphi^{-1}(U)=\varnothing$, we are done. Otherwise, let $x\in G_{1}$ s.t. $\varphi(x)\in U$. We have that: $$\varphi^{-1}(U)=x\varphi^{-1}(\varphi(x ^{-1})U)$$As $\varphi(x ^{-1})U=L_{\varphi(x ^{-1})}(U)$ is open and $\varphi(e)=e_{2}\in \varphi(x ^{-1})U$. Therefore,  by continuity at $e$, $\varphi ^{-1}(\varphi(x ^{-1})U)$ is open. Therefore, $\varphi ^{-1}(U)=x\varphi^{-1}(\varphi(x ^{-1})U)=L_{x}(\varphi^{-1}(\varphi(x ^{-1})U))$ is open.
---
> [!lemma] Proposition 2
> Let $G$ be a topological group. Then, 
> 1. If $H\leq G$, then $\overline{H}\leq G$ and if $H\unlhd G$, then $\overline{H}\unlhd G$.
> 3. If $H\leq G$ is open, then it is closed.
> 4. Let $G_{0}$ be the [[Connected Space|connected component]] of $e\in G$. Then, $G_{0}$ is closed and $G_{0}\unlhd G$.

> [!proof]-
> Then, we have:
> 1. Since $m$ is continuous, $$m(\overline{H}\times \overline{H})= m(\overline{H\times H})\subseteq \overline{m(H\times H)}\subseteq\overline{H}$$Also, as $i$ is a homeomorphism, $i(\overline{H})=\overline{H}$. Therefore, $\overline{H}$ is a subgroup.
>    
>    Further if $H\unlhd G$, for any $g\in G$, we have $x\mapsto gxg^{-1}$ is continuous. Therefore, $$g\overline{H}g\subseteq \overline{gHg^{-1}}\subseteq \overline{H}$$
> 2. Let $R$ be the representatives of $G / H$ with $e\in R$. Then, $$G=H \sqcup\bigsqcup_{r\in R \backslash\{ e \}}^{}rH=H \sqcup\bigsqcup_{r\in R \backslash\{ e \}}^{}L_{r}(H)$$As $L_{r}(H)$ is open, the disjoint union is also open. Therefore, $H$ is closed.
> 3. We have that $G_{0}\times G_{0}$ is connected and contains $(e,e)$. Therefore, $m(G_{0}\times G_{0})$ is also connected by [[Connected Space|Lemma 3]]. As $m(e,e)=e\in G_{0}$, $m(G_{0}\times G_{0})\subseteq G_{0}$. Since $i$ is a homeomorphism and $i(e)=e$, $i(G_{0})=G_{0}$, i.e. $G_{0}$ is a subgroup.
>    
>    Since $\overline{G_{0}}$ is connected, by the maximality, $\overline{G_{0}}=G_{0}$ and $G_{0}$ is closed.
>    
>    Lastly, consider the conjugation: $$\begin{array}{cccc} {\varphi_{g}:}&{G}&\to&{G}\\&{x} &\mapsto & {gxg^{-1}} \end{array}{}$$which is continuous. Therefore, $\varphi_{g}(G_{0})$ is connected but as $\varphi_{g}(e)=e$, $\varphi_{g}(G_{0})\subseteq G_{0}$. This proves that $G_{0}\unlhd G$.
- **Remark**: $G / G_{0}=:\pi_{0}(G)$ is a group.
---
> [!lemma] Lemma 3 (Local Base of e)
> Let $G$ be a topological group with identity $e$.
> 1. $e$ has a [[Local Base of Topology|local base]] of open symmetric sets, i.e. $V=V^{-1}$.
> 2. $e$ has a local base of open symmetric square root sets, i.e. for any neighborhood $U\ni e$, there exists an open symmetric neighborhood $V\ni e$ s.t. $V^{2}\subseteq U$.

> [!proof]-
> We have:
> 1. Let $e\in W\subseteq U$ with $W$ open. Then, $W^{-1}=i(W)$ is open and $e\in W^{-1}$. Therefore, $$V:=W\cap W^{-1}$$is an open symmetric neighborhood of $e$.
> 2. For $U\ni e$, as $m:G\times G\to G$ is continuous at $(e,e)$, there is a neighborhood $W$ of $e$ s.t. $$W^{2}=m(W\times W)\subseteq U$$Then, by 1, there exists open symmetric neighborhood $V$ of $e$ s.t. $V^{2}\subseteq W^{2}\subseteq U$.
---
###### Connected Topological Groups

> [!lemma] Proposition 1
> Let $G$ be a connected topological group. Then, 
> 1. For any neighborhood $U\ni e$, $G=\bigcup_{n=1}^{\infty}U^n$.
> 2. Any discrete normal subgroup $N\unlhd G$ is contained in the [[Center of a group|center]] $Z(G)$.


> [!proof]-
> We have:
> 1. From Lemma 3, we have an open symmetric neighborhood $V\subseteq U$ of $e$. Then, $$H:=\bigcup_{n=1}^{\infty}V^n\subseteq \bigcup_{n=1}^{\infty}U^n$$where $H$ is an open subgroup. Therefore, it is closed by 2. This implies that $H=G$ which proves the statement.
>  5. Let $N\unlhd G$ be a discrete subgroup. Then for all $n\in N$, there exists a continuous map: $$\begin{array}{cccc} {}&{G}&\to&{N}\\&{g} &\mapsto & {gng^{-1}} \end{array}{}$$is continuous and its image is continuous and contains $n$. As $N$ is discrete, this image has to be $\{ n \}$. Therefore, $N \subseteq Z(G)$.
---
> [!lemma] Lemma 2
> Let $G$ be a topological group and $H\leq G$ a closed subgroup. 
> 1. If $H$ and $G / H$ are connected, then $G$ is connected.

> [!proof]-
> Let $G=A\sqcup B$ be a non-empty open decomposition of $G$. Wlog we assume that $e\in A$. Since $H$ is connected, so is $gH$. Since each coset meets either $A$ or $B$, each must be contained entirely in one or the other. Consequently, each of $A$ or $B$ is a union of left cosets of $H$. 
> 
> Consider the canonical projection $\pi:G\to G / H$. Then, it is open by [[Quotient Topology|Lemma 2.1]] and $G / H=\pi(A)\sqcup \pi(B)$ where both are non-empty open sets and disjoint. This is a contradiction.

---
##### Examples
> [!h] Example 1
> Let $G,\{ G_{\alpha} \}_{\alpha\in A}$ be a topological group. Then:
> 1. $H\leq G$ is a topological group with the subspace topology.
> 2. $\prod_{\alpha\in A}^{}G_{\alpha}$ is a topological group with the product topology.
> 3. For $H\leq G$, the canonical projection $\pi:G \to G / H$ is [[Open and Closed Maps|open]].
> 4. for $N\unlhd G$, $G / N$ is a topological group with the quotient topology.

^6c2e6c

> [!proof]-
> We have that:
> 1. The restriction of the group operations is continuous.
> 2. For $\Gamma:=\prod_{\alpha\in A}^{}G_{\alpha}$, $\pi_{\alpha}\circ m_{\Gamma}=m_{\alpha}\circ(\pi_{\alpha},\pi_{\alpha})$ and therefore continuous. This shows that $\times_{\Gamma}$ is continuous [[Initial Topology|Lemma 2]]. Similarly, $\pi_{\alpha}\circ i_{\Gamma}=i_{\alpha}\circ(\pi_{\alpha}\times\pi_{\alpha})$ is continuous.
> 3. Suppose $U\subseteq G$ is an open set. Then, $\pi ^{-1}(\pi(U))=UH=\bigcup_{h\in H}^{}Uh=\bigcup_{h\in H}^{}R_{h}(U)$ is open. Therefore, $\pi(U)$ is open in the quotient topology.
> 4. For $U\subseteq G / N$ open, $\pi \circ m_{G}=m_{G / N}\circ(\pi \times \pi)$ and $\pi \circ m_{G}$ is continuous. As $\pi \times \pi$ is open, $m_{G /N}$ is continuous. Analogously for inversion.

^182301

---
> [!h] Example 2 (Elementary Topological Groups)
> We have:
> 1. Any group $G$ is a topological group with respect to the discrete topology. 
> 2. $(\mathbb{R}^n,+)$ is a topological group with respect to the Euclidean topology.
> 4. $\mathbb{R}^{\times},\mathbb{C}^{\times}$ are locally compact abelian topological groups.
> 5. [[General Linear Group|$\text{GL}(n,\mathbb{R})$]] is a topological group.
> 6. For any [[Topological Vector Space]] $V$, $(V,+)$ is a topological group.
---
> [!h] Example 3
> Let $X$ be a [[Locally Compact Hausdorff Space]]. Then, with respect to the [[Compact-Open Topology]],
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
> [!h] Example 4
> If $M$ is a [[smooth manifold]], for any $r\in \mathbb{N}$, and $$\text{Diff}^r(M):=\{ f\in \text{Homeo}(M):f,f^{-1}\in C^r(M) \}$$
> 1. $\text{Diff}^r(M)$ is a topological group.
> 2. $\text{Diff}^r(M)$ is not a closed subgroup of $\text{Homeo}(M)$.
---
> [!h] Example 5
> Let $(X,d)$ be a [[Proper Metric Space]]. Then, the group of isometries $\text{Iso}(X)$ is a topological group w.r.t the compact-open topology.
---
> [!h] Example 6 (Matrix Groups)
> For $\text{GL}(n,\mathbb{R})$, 
> 1. $\text{A}:=\{ \text{diag}(\lambda_{1},\dots,\lambda_{n}):\lambda_{i}\in\mathbb{R}_{>0} \}\cong \mathbb{R}_{>0}^n$ is a closed subgroup of $\text{GL}(n,\mathbb{R})$.
> 2. $\text{UT}(n,\mathbb{R})$, the upper unitriangular group, is a closed subgroup of $\text{GL}(n,\mathbb{R})$. $\text{UT}(n,\mathbb{R})$ is homeomorphic to $\mathbb{R}^{n(n-1)/2}$ but not isomorphic, as $\text{UT}(n,\mathbb{R})$ is non-abelian.
> 3. [[Orthogonal Group|$\text{O}(n)$]] is the closed subgroup of $\text{GL}(n,\mathbb{R})$.
> 4. $\text{O}(n)\times \text{A}\times \text{UT}(n,\mathbb{R})\to \text{GL}(n,\mathbb{R}),(O,A,N)\mapsto OAN$ is a homeomorphism.
> 5. The following symmetric bilinear form on $\mathbb{R}^n$: $$B(x,y):=-\sum_{i=1}^{p}x_{i}y_{i}+\sum_{j=p+1}^{n}x_{j}y_{y}=x^\top \begin{bmatrix}-I_{p}&\\&I_{{n-p}}\end{bmatrix}y$$Then, $$O(p,q):=\left\{ A\in \text{GL}(p+q,\mathbb{R}):A^\top \begin{bmatrix}-I_{p}&\\&I_{{q}}\end{bmatrix}A=\begin{bmatrix}-I_{p}&\\&I_{{q}}\end{bmatrix}\right\}$$is closed in $\text{GL}(p+q,\mathbb{R})$.
---
> [!h] Example 7
> For $\text{GL}(n,\mathbb{C})$,
> 1. $\text{GL}(n,\mathbb{C})$ is an open subset of $\text{M}_{n,n}(\mathbb{C})$.
> 2. $\text{GL}(n,\mathbb{C})$ is a topological group w.r.t the induced topology.
> 3. $\text{U}(n) \times \text{A}\times \text{UT}(n,\mathbb{C})\to \text{GL}(n,\mathbb{C}),(U,A,N)\mapsto UAN$ is a homeomorphism.
---
> [!h] Example 8
> For $\text{SO}(p,q):=\text{O}(p,q)\cap \text{SL}(n,\mathbb{R})$ and $\text{SU}(n)=\text{U}(n)\cap \text{SL}(n,\mathbb{C})$:
---

