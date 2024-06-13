#Definition #Topology 

> [!definition]
> Let $X$ be a [[topological space]] and $\sim$ an [[equivalence relation]]. Let $X /_{\sim}$ be the set of equivalence classes and $p:X \to X /_{\sim}$ the canonical projection. The ***quotient topology*** on $X /_{\sim}$ has $U\subseteq X / _\sim$ if and only if $p ^{-1}(U)\subseteq X$ is open.
- **Remark**: As $X / _\sim$ is a continuous image of $X$, $X /_{\sim}$ inherits the compactness of connectedness of $X$.
---
##### Properties
> [!lemma] Lemma 1
> A map $f:X/_{\sim}\to Y$ is continuous if and only if $f\circ p:X\to Y$ is continuous.

> [!proof]-
> We have that $p$ is continuous by definition. Therefore, if $f$ is continuous, $f\circ p$ is continuous.
> 
> Conversely, assume that $f\circ p$ is continuous and let $U\subseteq Y$ be open. Then, $p ^{-1}(f^{-1}(U))$ is open and thereby $f^{-1}(U)$ is open.
---
> [!lemma] Lemma 2 (Quotient Lemma)
> Let $G$ be a topological group and $H\leq G$. Then, 
> 1. the canonical projection $p:G\to G / H$ is an open map.
> 2. the action $G \curvearrowright G /H$ given by $g\circ xH=gxH$ is continuous.
> 3. $G / H$ is Hausdorff if and only if $H$ is closed in $G$.
> 4. if $G$ is locally compact, then $G / H$ is locally compact.
> 5. if $G$ is locally compact and $H\leq G$ closed, then for any compact $C\subseteq G/H$, there exists a compact set $K\subseteq G$ s.t. $p(K)=C$.

> [!proof]-
> We have:
> 1. let $U\subseteq G$ open. Then, we have: $$\pi ^{-1}(\pi(U))=\bigcup_{g\in H}^{}Ug$$Indeed, $x\in \pi ^{-1}(\pi(U))$ is equivalent to $xH=yH$ for some $y\in U$. This happens if and only if $y^{-1}x=h$, i.e. $x=yh$ for some $h\in H$ and $y\in U$. As $\bigcup_{g\in H}^{}Ug$ is open, $\pi(U)$ is open.
> 2. Let $U$ be open in $G / H$. Let $g\in G$ and $xH\in G / H$ s.t. $gxH\in U$. Then, as $\pi(U)$ is open in $G$ by definition and $gx\in \pi(U)$, there exists $V\ni g,W\ni x$ s.t. $VW\subseteq \pi(U)$. As $\pi$ is open, $\pi(W)$ is open and for any $g'\in V$ and $yH\in \pi(W)$, there exists $z\in W$ s.t. $\pi(z)=yH$. Therefore, $$g'yH=g'zH\subseteq U$$
> 3. If $G / H$ is Hausdorff, then $H$ is closed as a point. Therefore, $H\subseteq G$ is closed. 
>    
>    Conversely, if $H$ is closed, it suffices to show that the diagonal $\Delta:G / H\to G / H\times G / H$ is closed. Then, let: $$U:=(G / H \times G / H )\backslash\text{im}(\Delta)=\{ (p(g),p(g')):g^{-1}g'\notin H \}$$As $p$ is open, $q:(x,y)\mapsto(p(x),p(y))$ is open. Therefore, $q^{-1}(U)=\{ (g,g'):g^{-1}g'\notin H \}$ is open as $(x,y)\mapsto x ^{-1}y$ is continuous and $H^c$ is open. It follows that $U=q(q^{-1}(U))$ is open as $q$ is open. 
> 4. Let $p(x)\in G / H$. Since $G$ is locally compact, there exists a fundamental system $\{ K_{\alpha} \}$ of compact neighborhoods of $x$. Then, $p(K_{\alpha})$ is a compact neighborhood as a continuous image and this forms a fundamental system of compact neighborhoods of $p(x)$. 
> 5. As $G$ is locally compact there exists $e\in U\subseteq L\subseteq G$ with $U$ open and $L$ compact. Then, $$C\subseteq \bigcup_{x\in G}^{}p(xU)$$and there exists $x_{1},\dots,x_{n}$ s.t. $C\subseteq p(x_{1}U)\cup\dots \cup p(x_{n}U)$. In particular $C\subseteq \bigcup_{i=1}^{n}p(x_{i}L)$. 
>    
>    Since $H$ is closed, $G / H$ is Hausdorff and $C$ is closed. Then, let: $$K:= p ^{-1}\left(C\cap \bigcup_{i=1}^{n}p(x_{i}L)\right)$$which is compact as a closed subset of a compact set. 

---
##### Examples
> [!h] Example 1
> Consider the following equivalence relation on $\mathbb{R}$: $$x\sim y \iff x-y\in \mathbb{Z}$$Then, $\mathbb{R} / \mathbb{Z}\cong S^1$.

> [!proof]-
> Consider the map: $$\begin{array}{cccc} {e:}&{\mathbb{R}}&\to&{S^1}\\&{t} &\mapsto & {e^{2i\pi t}} \end{array}{}$$It is continuous and surjective. Further, it's compatible with $\sim$ as for $x\sim y$, $$e(x)=e^{2i\pi x}=e^{2i\pi y}e^{2i\pi(x-y)}=e(y)$$Therefore, there exists a continuous map $\tilde{e}:\mathbb{R} / \mathbb{Z}\to S^1$ and by Analysis, it is a bijection. As $\mathbb{R} / \mathbb{Z}=\pi([0,1])$, $\mathbb{R} / \mathbb{Z}$ is compact and by [[Compact Space#^2251ae|Proposition 1]], $\tilde{e}$ is a homeomorphism.
---
> [!h] Example 2 (Möbius Strip)
> Let $X:=[0,1]^{2}\subseteq \mathbb{R}^2$. Consider the following equivalence classes: 
> 1. $\{ (x,y) \}$ if $0<x<1$ and 
> 2. $\{ (0,y),(1,1-y) \}$ if $0\leq y\leq 1$.
> 
> Then, the quotient space $X / _\sim$ is called the ***Möbius strip*** and:
> 1. it is connected and compact as $X$ is.
> 2. $X/_{\sim}$ is Hausdorff.
> 3. $X / _\sim$ is a topological manifold with boundary.
---
> [!h] Example 3
> Let $X=\mathbb{R}$ and consider the following equivalence relation: $$x\sim y\iff x-y\in \mathbb{Q}$$Then, 
> 1. the only open sets in $\mathbb{R} / \mathbb{Q}$ are $\varnothing$ and $\mathbb{R} / \mathbb{Q}$.
> 2. $\mathbb{R} / \mathbb{Q}$ is not Hausdorff.

> [!proof]-
> Let $U\neq \varnothing$ be open and $U':=p ^{-1}(U)$ which is open. Then, $U'=\mathbb{Q}+U'$ and therefore $U'=\mathbb{R}$ and $U=\mathbb{R} / \mathbb{Q}$.
---

