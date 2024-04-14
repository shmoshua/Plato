#Definition #Topology  #LieGroups 
> [!definition]
> A [[group]] $G$ is ***topological*** if the underlying set is a [[topological space]] and the group operations are continuous, i.e.
> 1. $m:G\times G\to G,(g,h)\mapsto gh$ is continuous and
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
> Therefore, $\varphi$ is continuous if and only if it is continuous at $e\in G_{1}$.

> [!proof]-
> One direction is trivial. 
> 
> For the other, if $\varphi$ is continuous at $e$. Let $U\subseteq G_{2}$ open. If $\varphi^{-1}(U)=\varnothing$, we are done. Otherwise, let $x\in G_{1}$ s.t. $\varphi(x)\in U$. We have that: $$\varphi^{-1}(U)=x\varphi^{-1}(\varphi(x ^{-1})U)$$As $\varphi(x ^{-1})U=L_{\varphi(x ^{-1})}(U)$ is open and $\varphi(e)=e_{2}\in \varphi(x ^{-1})U$. Therefore,  by continuity at $e$, $\varphi ^{-1}(\varphi(x ^{-1})U)$ is open. Therefore, $\varphi ^{-1}(U)=x\varphi^{-1}(\varphi(x ^{-1})U)=L_{x}(\varphi^{-1}(\varphi(x ^{-1})U))$ is open.
---
> [!lemma] Proposition 2
> Let $G,\{ G_{\alpha} \}_{\alpha\in A}$ be a topological group. Then:
> 1. $H\leq G$ is a topological group with the subspace topology.
> 2. $\prod_{\alpha\in A}^{}G_{\alpha}$ is a topological group with the product topology.
> 3. For $H\leq G$, the canonical projection $\pi:G \to G / H$ is [[Open and Closed Maps|open]].
> 4. for $N\unlhd G$, $G / N$ is a topological group with the quotient topology.

> [!proof]-
> We have that:
> 1. The restriction of the group operations is continuous.
> 2. For $\Gamma:=\prod_{\alpha\in A}^{}G_{\alpha}$, $\pi_{\alpha}\circ m_{\Gamma}=m_{\alpha}\circ(\pi_{\alpha},\pi_{\alpha})$ and therefore continuous. This shows that $\times_{\Gamma}$ is continuous [[Initial Topology|Lemma 2]]. Similarly, $\pi_{\alpha}\circ i_{\Gamma}=i_{\alpha}\circ(\pi_{\alpha}\times\pi_{\alpha})$ is continuous.
> 3. Suppose $U\subseteq G$ is an open set. Then, $\pi ^{-1}(\pi(U))=UH=\bigcup_{h\in H}^{}Uh=\bigcup_{h\in H}^{}R_{h}(U)$ is open. Therefore, $\pi(U)$ is open in the quotient topology.
> 4. For $U\subseteq G / N$ open, $\pi \circ m_{G}=m_{G / N}\circ(\pi \times \pi)$ and $\pi \circ m_{G}$ is continuous. As $\pi \times \pi$ is open, $m_{G /N}$ is continuous. Analogously for inversion.
---
> [!lemma] Proposition 3
> Let $G$ be a topological group. Then, 
> 1. If $H\leq G$, then $\overline{H}\leq G$.
> 2. If $H\leq G$ is open, then it is closed.
> 3. Let $G^\circ$ be the [[Connected Space|connected component]] of $e\in G$. Then, $G^{\circ}$ is closed and $G^\circ\unlhd G$.
> 4. If $G$ is [[Connected Space|connected]] and $U\subseteq G$ is a neighborhood of $e$, then $G=\bigcup_{n=1}^{\infty}U^n$
> 5. If $G$ is [[Connected Space|connected]] and $N\unlhd G$ is discrete. Then, $N\subseteq Z(G)$ where $Z(G)$ denotes the [[Center of a group|center]].

> [!proof]-
> > [!lemma]
> > We have:
> > 1. If $U$ is a neighborhood of $e$, there exists an open symmetric neighborhood $V\subseteq U$ of $e$, i.e. $V=V^{-1}$.
> > 2. If $U$ is a neighborhood of $e$, there exists an open symmetric neighborhood $V$ of $e$ s.t. $$V^{2}=V^{-1}V\subseteq U$$
> 
> > [!proof]-
> > We have:
> > 1. Let $e\in W\subseteq U$ with $W$ open. Then, $W^{-1}=i(W)$ is open and $e\in W^{-1}$. Therefore, $$V:=W\cap W^{-1}$$is an open symmetric neighborhood of $e$.
> > 2. As $m:G\times G\to G$ is continuous at $(e,e)$, there is a neighborhood $W$ of $e$ s.t. $$W^{2}=m(W\times W)\subseteq U$$Then, by 1, there exists open symmetric neighborhood $V$ of $e$ s.t. $V^{2}\subseteq W^{2}\subseteq U$.
> 1. Since $m$ is continuous, $$m(\overline{H}\times \overline{H})\subseteq m(\overline{H\times H})\subseteq \overline{m(H\times H)}=\overline{H}$$Also, as $i$ is a homeomorphism, $i(\overline{H})=\overline{H}$. Therefore, $\overline{H}$ is a subgroup.
> 2. Let $R$ be the representatives of $G / H$ with $e\in R$. Then, $$G=H \sqcup\bigsqcup_{r\in R \backslash\{ e \}}^{}rH=H \sqcup\bigsqcup_{r\in R \backslash\{ e \}}^{}L_{r}(H)$$As $L_{r}(H)$ is open, the disjoint union is also open. Therefore, $H$ is closed.
> 3. We have that $G^\circ\times G^\circ$ is connected and contains $(e,e)$. Therefore, $m(G^\circ\times G^\circ)$ is also connected by [[Connected Space|Lemma 1]]. Further, $m(G^\circ\times G^\circ)\subseteq G^\circ$. Since $i$ is a homeomorphism and $i(e)=e$, $i(G^\circ)=G^\circ$, i.e. $G^\circ$ is a subgroup.
>    
>    Since $\overline{G^\circ}$ is connected, by the maximality, $\overline{G^\circ}=G^\circ$ and $G^\circ$ is closed.
>    
>    Lastly, consider the conjugation: $$\begin{array}{cccc} {\text{int}(g):}&{G}&\to&{G}\\&{x} &\mapsto & {gxg^{-1}} \end{array}{}$$which is continuous. Therefore, $\text{int}(g)(G^\circ)$ is connected but as $\text{int}(g)(e)=e$, $\text{int}(g)(G^\circ)\subseteq G^\circ$, i.e. $G^\circ\unlhd G$.
>  4. From the lemma, we have an open symmetric neighborhood $V\subseteq U$ of $e$. Then, $$H:=\bigcup_{n=1}^{\infty}V^n\subseteq \bigcup_{n=1}^{\infty}U^n$$where $H$ is an open subgroup. Therefore, it is closed by 2. This implies that $H=G$ which proves the statement.
>  5. Let $N\unlhd G$ be a discrete subgroup. Then for all $n\in N$, there exists a continuous map: $$\begin{array}{cccc} {}&{G}&\to&{N}\\&{g} &\mapsto & {gng^{-1}} \end{array}{}$$is continuous and its image is continuous and contains $n$. As $N$ is discrete, this image has to be $\{ n \}$. Therefore, $N \subseteq Z(G)$.
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
> Let $(X,d)$ be a [[proper metric space]]. Then, the group of isometries $\text{Iso}(X)$ is a topological group w.r.t the compact-open topology.
---
> [!h] Example 5
> For $\text{GL}(n,\mathbb{R})$, 
> 1. $\text{A}:=\{ \text{diag}(\lambda_{1},\dots,\lambda_{n}):\lambda_{i}\in\mathbb{R}_{>0} \}\cong \mathbb{R}_{>0}^n$ is a closed subgroup of $\text{GL}(n,\mathbb{R})$.
> 2. $\text{UT}(n,\mathbb{R})$, the upper unitriangular group, is a closed subgroup of $\text{GL}(n,\mathbb{R})$. $\text{UT}(n,\mathbb{R})$ is homeomorphic to $\mathbb{R}^{n(n-1)/2}$ but not isomorphic, as $\text{UT}(n,\mathbb{R})$ is non-abelian.
> 3. [[Orthogonal Group|$\text{O}(n)$]] is the closed subgroup of $\text{GL}(n,\mathbb{R})$.
> 4. $\text{O}(n)\times \text{A}\times \text{UT}(n,\mathbb{R})\to \text{GL}(n,\mathbb{R}),(O,A,N)\mapsto OAN$ is a homeomorphism.
> 5. The following symmetric bilinear form on $\mathbb{R}^n$: $$B(x,y):=-\sum_{i=1}^{p}x_{i}y_{i}+\sum_{j=p+1}^{n}x_{j}y_{y}=x^\top \begin{bmatrix}-I_{p}&\\&I_{{n-p}}\end{bmatrix}y$$Then, $$O(p,q):=\left\{ A\in \text{GL}(p+q,\mathbb{R}):A^\top \begin{bmatrix}-I_{p}&\\&I_{{q}}\end{bmatrix}A=\begin{bmatrix}-I_{p}&\\&I_{{q}}\end{bmatrix}\right\}$$is closed in $\text{GL}(p+q,\mathbb{R})$.
---
> [!h] Example 6
> For $\text{GL}(n,\mathbb{C})$,
> 1. $\text{GL}(n,\mathbb{C})$ is an open subset of $\text{M}_{n,n}(\mathbb{C})$.
> 2. $\text{GL}(n,\mathbb{C})$ is a topological group w.r.t the induced topology.
> 3. $\text{U}(n) \times \text{A}\times \text{UT}(n,\mathbb{C})\to \text{GL}(n,\mathbb{C}),(U,A,N)\mapsto UAN$ is a homeomorphism.
---
> [!h] Example 7
> For $\text{SO}(p,q):=\text{O}(p,q)\cap \text{SL}(n,\mathbb{R})$ and $\text{SU}(n)=\text{U}(n)\cap \text{SL}(n,\mathbb{C})$:
---
