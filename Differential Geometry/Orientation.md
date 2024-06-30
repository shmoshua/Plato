#Definition #DifferentialGeometry 

> [!definition]
> We have that:
> 1. an ***orientation*** of a $n$-dimensional $\mathbb{R}$-vector space $V$ is an equivalence class on the set of ordered bases $(E_{1},\dots,E_{n})$ of $V$ given by: $$(E_{1},\dots,E_{n})\sim(E'_{1},\dots,E'_{n})\iff \det(B)>0$$where $B$ is the change of basis matrix from $(E_{1},\dots,E_{n})$ to $(E'_{1},\dots,E'_{n})$.
- **Notation**: The orientation of an ordered basis $(E_{1},\dots,E_{n})$ is denoted as $[E_{1},\dots,E_{n}]$ and $-[E_{1},\dots,E_{n}]$ denotes the opposite orientation. 
---
##### Properties
> [!lemma] Proposition 1 (Orientation is Well-defined)
> $\sim$ is an equivalence relation.

> [!proof]+
> We have that:
> 1. $\det(I)=1>0$ and $\sim$ is reflexive. Transitivity follows from $\det(AB)=\det(A)\det(B)$