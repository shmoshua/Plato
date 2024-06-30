#Definition #DifferentialGeometry 

> [!definition]
> We have that:
> 1. an ***orientation*** of a $n$-dimensional $\mathbb{R}$-vector space $V$ is an equivalence class on the set of ordered bases $(E_{1},\dots,E_{n})$ of $V$ given by: $$(E_{1},\dots,E_{n})\sim(E'_{1},\dots,E'_{n})\iff \det(B)>0$$where $B$ is the change of basis matrix from $(E_{1},\dots,E_{n})$ to $(E'_{1},\dots,E'_{n})$.
> 2. an ***orientable (double) cover*** of a [[smooth manifold]] $M$ is $\text{O}M:=\bigsqcup_{p\in M}^{}\text{O}_{p}M$ where $\text{O}_{p}M$ is the set of orientations of $\text{T}_{p}M$.
> 3. an ***orientation*** of a smooth manifold $M$ is a continuous map $o:M\to \text{O}M$ (w.r.t topology in )
- **Notation**: The orientation of an ordered basis $(E_{1},\dots,E_{n})$ is denoted as $[E_{1},\dots,E_{n}]$ and $-[E_{1},\dots,E_{n}]$ denotes the opposite orientation. 
- **Related definition**: An ***oriented vector space*** $(V,o)$ is a vector space $V$ equipped with an orientation.
- 
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
