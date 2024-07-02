#Definition #DifferentialGeometry 

> [!definition]
> We have that:
> 1. an ***orientation*** of a $n$-dimensional $\mathbb{R}$-vector space $V$ is an equivalence class on the set of ordered bases $(E_{1},\dots,E_{n})$ of $V$ given by: $$(E_{1},\dots,E_{n})\sim(E'_{1},\dots,E'_{n})\iff \det(B)>0$$where $B$ is the change of basis matrix from $(E_{1},\dots,E_{n})$ to $(E'_{1},\dots,E'_{n})$.
> 2. an ***orientation (double) cover*** of a [[smooth manifold]] $M$ is $\text{O}M:=\bigsqcup_{p\in M}^{}\text{O}_{p}M$ where $\text{O}_{p}M$ is the set of orientations of $\text{T}_{p}M$.
> 3. an ***orientation*** of a smooth manifold $M$ is a map $o:M\to \text{O}M$ with $o(p)\in \text{O}_{p}M$ s.t. for all $p\in M$, there exists a [[local frame]] $E_{1},\dots,E_{m}$ of $M$ over an open $U\ni p$ s.t. $$o(p)=[E_{1}(p),\dots,E_{m}(p)],\quad \forall p\in U$$
- **Notation**: The orientation of an ordered basis $(E_{1},\dots,E_{n})$ is denoted as $[E_{1},\dots,E_{n}]$ and $-[E_{1},\dots,E_{n}]$ denotes the opposite orientation. 
- **Related definition**: An ***oriented vector space*** $(V,o)$ is a vector space $V$ equipped with an orientation.
- **Related definition**: A smooth manifold is ***orientable***, if it admits an orientation. ***Non-orientable*** otherwise. A smooth manifold $M$ equipped with an orientation $o$ is an ***oriented manifold*** $(M,o)$.
- **Related definition**: A [[local diffeomorphism]] $f:(M,o_{M})\to(N,o_{N})$ is called:
	1. ***orientation-preserving*** if $d_{p}f:(\text{T}_{p}M,o_{M}(p))\to(\text{T}_{f(p)}N,o_{N}(f(p)))$ is orientation-preserving for all $p\in M$.
	2. ***orientation-reversing*** if $d_{p}f$ is orientation-reversing for all $p\in M$.
---
##### Properties
> [!lemma] Proposition 1 (Orientation is Well-defined)
> We have that:
> 1. $\sim$ is an equivalence relation.
> 2. there are exactly two equivalence classes.

> [!proof]-
> We have that:
> 1. $\det(I)=1>0$, $\det(B^{-1})=\frac{1}{\det(B)}>0$ and $\det(AB)=\det(A)\det(B)$. 
> 2. $(e_{1},\dots,e_{n})$ and $(-e_{1},e_{2}\dots ,e_{n})$ do not belong in the same equivalence class. However, for ordered bases $E,F,G$, if $\det(B_{EF})<0$ and $\det(B_{EG})<0$, then $\det(B_{GE})<0$ and: $$\det(B_{GF})=\det(B_{GE})\det(B_{EF})>0$$Therefore, $F\sim G$. This proves the statement.
---
> [!lemma] Proposition 2
> Let $V$ be a $n$-dimensional $\mathbb{R}$-vector space. For $0\neq\omega\in \Lambda^n(V^{*})$, 
> 1. $\mathcal{O}_{\omega}:=\{ (E_{i}):\omega(E_{1},\dots,E_{n})>0 \}$ defines an orientation.

> [!proof]-
> Let $(E_{i}),(F_{i})\in \mathcal{O}_{\omega}$. Then, let $B\in \mathcal{B}(V)$ be the linear map sending $E_{i}$ to $F_{i}$, i.e. $F_{i}=BE_{i}$ for all $i$. Therefore, $$\omega(F_{1},\dots,F_{n})=\omega(BE_{1},\dots,BE_{n})=\det(B)\omega(E_{1},\dots,E_{n})$$Therefore, $\det(B)>0$ and $(E_{i})\sim (F_{i})$.
---
> [!lemma] Proposition 3
> Let $f,g:(M,o_{M})\to(N,o_{N})$ be [[local diffeomorphism|local diffeomorphisms]].
> 1. if $M$ is connected, $f$ is either orientation preserving or orientation reversing.
> 2. if $f$ is OP and $g$ is OP, $g\circ f$ is OP.
> 3. if $f$ is OP and $g$ is OR, $g\circ f$ is OR.
> 4. if $f$ is OR and $g$ is OP, $g\circ f$ is OR.
> 5. if $f$ is OR and $g$ is OR, $g\circ f$ is OP.
> 6. $f$ is OP if and only if $\det(d_{p}f)>0$ for all $p\in M$.
> 7. $f$ is OR if and only if $\det(d_{p}f)<0$ for all $p\in M$.

> [!proof]-
> We have:
> 1. Let $p\in M$ and check if $d_{p}f$ is orientation preserving or reversing. As $f$ is a local diffeomorphism $d_{p}f$ is bijective and it has to be one of the two. Wlog we may assume that it is preserving. The other case is analogous. Now, let: $$V:=\{ p\in M : d_{p}f\text{ is orientation-preserving}\}$$Then, by the existence of local frames, for any $q\in V$, there exists an open neighborhood $U$ s.t. $U\subseteq V$. Therefore, $V$ is open. However, for $q\in M\backslash V$ (if it exists), we also get an open neighborhood $U\subseteq M \backslash V$. Hence, $V$ is clopen and by the connectedness, $V=M$, as $V$ is non-empty.
> 2. Obvious.
---
> [!lemma] Proposition 4 (Connected Manifolds and Orientation)
> Let $o$ and $o'$ be two orientations on a connected smooth manifold $M$. Then, 
> 1. $M$ admits exactly two orientations.
> 3. if $o(p)=o'(p)$ at some point $p\in M$, $o=o'$.

> [!proof]-
> Let $o,o'$ be two orientations. Let $V:=\{ p\in M:o(p)=o'(p) \}$. Then, we will show that $V$ is clopen. For $p\in V$, let $E_{1},\dots,E_{m}$ be the local frame over $U$ w.r.t. $o$ and $F_{1},\dots,F_{m}$ be the local frame over $U'$ w.r.t. $o'$ s.t. they coincide at: $$[E_{1},\dots,E_{m}]=o(p)=o'(p)=[F_{1},\dots,F_{m}]$$Then, modulo taking a subset we may assume that $U\cap U'$ is connected. Then, $\text{id}_{U\cap U'}$ is a local diffeomorphism and it is orientation preserving. Therefore, $o=o'$ on $U\cap U'$ and $U\cap U'\subseteq V$. Analogously, $M\backslash V$ is open and $V$ is clopen. 
> 
> As $M$ is connected, $V=M$ or $V=\varnothing$. If $V=M$, then $o=o'$ on $M$. If $V=\varnothing$, then $o(p)\neq o'(p)$ everywhere. As there exists only 2 options for each $p$, this shows that there exists only two orientations. 
---
> [!lemma] Proposition 5 (Properties of Orientation Cover)
> Let $M$ be a smooth manifold and $\text{O}M$ its orientation cover with the map: $$\pi:\text{O}M\to M,\quad (p,o)\mapsto p$$Then, 
> 1. $\text{O}M$ admits a topology that endows a smooth structure on $\text{O}M$.
> 2. $\pi:\text{O}M\to M$ is a smooth covering space of degree 2.
> 3. $\text{O}M$ is orientable.

> [!proof]-
> We have:
> 1. Let $U\subseteq M$ be open. $(U,o_{U})$ be a pair where $U\subseteq M$ is an open set and $o:U\to \text{O}M$ an orientation s.t. $o(p)\in \text{O}_{p}M$ for all $p\in U$. Then, let: $$\text{O}U_{o_{U}}:=\{ (p, o_{p}):p\in U,o_{U}(p)=o_{p} \}$$We show that these form a base of a topology. Firstly, for any $(p,o_{p})\in \text{O}M$, there exists $U\ni p$ with an orientation $o_{U}$. Modulo taking the opposite orientation, $(p,o_{p})\in \text{O}U_{o_{U}}$. 
>    
>    For $\text{O}U_{o_{U}}$ and $\text{O}V_{o_{V}}$ and $(p,o_{p})$ is in the intersection and $W$ is the connected component of $p$ in $U\cap V$, by Proposition 4, $o_{W}=o'_{W}$. Therefore, the intersection is open and this defines a basis of topology. 
>  2. We see that $\pi$ is a local homeomorphism. Further, for any connected $U\subseteq M$, $$\pi ^{-1}(U)=\{ \text{O}U_{o_{U}},\text{O}U_{-o_{U}} \}$$This proves the statement.
>  3. We now define an orientation on $\text{O}M$. Let $(p,o_{p})$ be a point in $\text{O}M$. By definition, $o_{p}$ is an orientation of $\text{T}_{p}M$; so we can give $\text{T}_{(p,o_{p})}\text{O}M$ the unique orientation $\widehat{o}_{(p,o_{p})}$ s.t. $d_{(p,o_{p})}\pi:(\text{T}_{(p,o_{p})}\text{O}M,\widehat{o}_{(p,o_{p})})\to (\text{T}_{p}M,o_{p})$ is orientation-preserving. 
>     
>     For $U\ni p$ an open connected neighborhood with orientation $o_{U}$ s.t. $o_{U}(p)=o_{p}$, we have that $\pi:\text{O}U_{o_{U}}\to U$ is a homeomorphism, hence $\text{O}U_{o_{U}}$ is connected. As $\widehat{o}$ coincides with the pullback orientation of $\pi|_{\text{O}U_{o_{U}}}$ on $\text{O}U_{o_{U}}$, it is continuous.
---
> [!lemma] Proposition 5 (Equivalent Definition of Orientable Manifolds)
> For a smooth manifold $M$ with $m>1$, TFAE:
> 1. $M$ is orientable.
> 2. $M$ admits an ***oriented atlas***, i.e. an [[atlas]] $\mathcal{A}$ on $M$ where for any two overlapping charts $(U,\varphi),(V,\psi)$, $$\det d_{\tilde{p}}(\psi \circ \varphi ^{-1}|_{\varphi(U\cap V)})>0,\quad \forall \tilde{p}\in\varphi(U\cap V)$$
> 3. there exists a continuous map $o:M\to \text{O}M$.
> 4. $\text{O}M\cong M\times \{ \pm 1 \}$

> [!proof]+
> We have:
> 1. (1=>2): First, assume that $M$ is orientable with orientation $o$. For each $p\in M$, let $(U_{p},\varphi_{p})$ be a chart containing $p$. Modulo taking a subset we can assume that $U_{p}$ is connected and there exists a local frame $E_{1},\dots,E_{m}$ over $U_{p}$ s.t. $$o(p)=[E_{1}(p),\dots,E_{m}(p)],\quad \forall p\in U$$Now, let $\varphi_{p}=(x^1,\dots,x^m)$. As $U_{p}$ is connected, $\varphi_{p}$ is either orientation preserving or orientation reversing. Modulo switching the sign of $x^1$, we can now assume that: $$[d\varphi_{p}(E_{1}(p)),\dots,d\varphi_{p}(E_{m}(p))]=[e_{1},\dots,e_{m}]$$where $e_{1},..,e_{m}$ denotes the standard ordered basis in $\mathbb{R}^m$. Let $\mathcal{A}:=\{ (U_{p},\varphi_{p}):p\in M \}$ and let $(U,\varphi),(V,\psi)$ to be two such charts with an overlap $p\in U\cap V$. Then, for the respective local frame $(E_{i})$ and $(F_{i})$, we have that: $$[E_{1}(p),\dots,E_{m}(p)]=o(p)=[F_{1}(p),\dots,F_{m}(p)]$$and $$\begin{align}[d_{\varphi(p)}(\psi \circ \varphi ^{-1})(e_{1}),\dots,d_{\varphi(p)}(\psi \circ \varphi ^{-1})(e_{m})]&=[d\psi_{p}(E_{1}(p)),\dots,d\psi_{p}(E_{m}(p))]\\&=[d\psi_{p}(F_{1}(p)),\dots,d\psi_{p}(F_{m}(p))]\\&=[e_{1},\dots,e_{m}]\end{align}$$Therefore, $\psi \circ\varphi ^{-1}|_{\varphi(U\cap V)}$ is orientation preserving and $\mathcal{A}$ is an oriented atlas.
> 2. (2=>1): Assume there exists an oriented atlas $\mathcal{A}$. For $p\in M$ with chart $(U,\varphi)\in \mathcal{A}$ with $p\in U$, we define the orientation as: $$o(p)=[d_{\varphi(p)}\varphi ^{-1}(e_{1}),\dots,d_{\varphi(p)}\varphi ^{-1}(e_{m})]$$We first show that this is well-defined. For $p$, let $(U,\varphi)$ and $(V,\psi)$ be two charts in $\mathcal{A}$ containing $p$. Then, as $\psi \circ\varphi ^{-1}$ is orientation preserving and $$d_{\varphi(p)}\varphi ^{-1}=d_{\varphi(p)}\psi ^{-1}\circ\psi \circ\varphi ^{-1}=d_{\psi(p)}\psi ^{-1}\circ d_{\varphi(p)}(\psi \circ \varphi ^{-1})$$we get the same pointwise orientation. Further, $p\mapsto d_{\varphi(p)}\varphi ^{-1}(e_{i})$ is a smooth vector field defined on $U$. 
> 3. (1=>3): Let $M$ be orientable with orientation $o$. We will show that this is continuous. Let $p\in M$ and let $(p,o_{p})\in \text{O}M$. Further, let $\text{O}U_{o_{U}}$ be an open neighborhood of $(p,o_{p})$. Then, let $U$ be the open neighborhood of $p$ with a continuous local  
---


##### Examples
> [!h] Example 1
> We have:
> 1. $S^2$, $\mathbb{T}^2$ are orientable.
> 2. The Klein bottle $K^2$ and the Möbius strip $S$ are not orientable.
---
