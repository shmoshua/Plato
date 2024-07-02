#Definition #DifferentialGeometry 

> [!definition]
> We have that:
> 1. an ***orientation*** of a $n$-dimensional $\mathbb{R}$-vector space $V$ is an equivalence class on the set of ordered bases $(E_{1},\dots,E_{n})$ of $V$ given by: $$(E_{1},\dots,E_{n})\sim(E'_{1},\dots,E'_{n})\iff \det(B)>0$$where $B$ is the change of basis matrix from $(E_{1},\dots,E_{n})$ to $(E'_{1},\dots,E'_{n})$.
> 2. an ***orientable (double) cover*** of a [[smooth manifold]] $M$ is $\text{O}M:=\bigsqcup_{p\in M}^{}\text{O}_{p}M$ where $\text{O}_{p}M$ is the set of orientations of $\text{T}_{p}M$.
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
> [!lemma] Proposition 4 (Equivalent Definition of Orientable Manifolds)
> For a smooth manifold $M$, TFAE:
> 1. $M$ is orientable.
> 2. $M$ admits an ***oriented atlas***, i.e. an [[atlas]] $\mathcal{A}$ on $M$ where for any two overlapping charts $(U,\varphi),(V,\psi)$, $$\det d_{\tilde{p}}(\psi \circ \varphi ^{-1}|_{\varphi(U\cap V)})>0,\quad \forall \tilde{p}\in\varphi(U\cap V)$$

> [!proof]+
> We have:
> 1. First, assume that $M$ is orientable with orientation $o$. For each $p\in M$, let $(U_{p},\varphi_{p})$ be a chart containing $p$. Modulo taking a subset we can assume that $U_{p}$ is connected and there exists a local frame $E_{1},\dots,E_{m}$ over $U_{p}$ s.t. $$o(p)=[E_{1}(p),\dots,E_{m}(p)],\quad \forall p\in U$$Now, let $\varphi_{p}=(x^1,\dots,x^m)$. As $U_{p}$ is connected, $\varphi_{p}$ is either orientation preserving or orientation reversing. Modulo switching the sign of $x^1$, we can now assume that: $$[d\varphi_{p}(E_{1}(p)),\dots,d\varphi_{p}(E_{m}(p))]=[e_{1},\dots,e_{m}]$$where $e_{1},..,e_{m}$ denotes the standard ordered basis in $\mathbb{R}^m$. Let $\mathcal{A}:=\{ (U_{p},\varphi_{p}):p\in M \}$ and let $(U,\varphi),(V,\psi)$ to be two such charts with an overlap $p\in U\cap V$. Then, for the respective local frame $(E_{i})$ and $(F_{i})$, we have that: $$[E_{1}(p),\dots,E_{m}(p)]=o(p)=[F_{1}(p),\dots,F_{m}(p)]$$and $$\begin{align}[d_{\varphi(p)}(\psi \circ \varphi ^{-1})(e_{1}),\dots,d_{\varphi(p)}(\psi \circ \varphi ^{-1})(e_{m})]&=[d\psi_{p}(E_{1}(p)),\dots,d\psi_{p}(E_{m}(p))]\\&=[d\psi_{p}(F_{1}(p)),\dots,d\psi_{p}(F_{m}(p))]\\&=[e_{1},\dots,e_{m}]\end{align}$$Therefore, $\psi \circ\varphi ^{-1}|_{\varphi(U\cap V)}$ is orientation preserving and $\mathcal{A}$ is an oriented atlas.
> 2. Assume there exists an oriented atlas $\mathcal{A}$. We define the orientation as: $$o(p)=[d_{\varphi(p)}\varphi ^{-1}(e_{1}),\dots,d_{\varphi(p)}\varphi ^{-1}(e_{m})]$$
---
##### Examples
> [!h] Example 1
> We have:
> 1. $S^2$, $\mathbb{T}^2$ are orientable.
> 2. The Klein bottle $K^2$ and the Möbius strip $S$ are not orientable.
---
