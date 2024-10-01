#Definition #CommutativeAlgebra 

> [!definition]
> Let $X\subseteq \mathbb{A}_{K}^n$, $Y\subseteq \mathbb{A}_{K}^m$ be two [[Variety|varieties]]. 
> 1. A ***morphism*** is a map $f:X\to Y$ given by polynomials, i.e. there exist: $f_{1},\dots,f_{m}\in K[x_{1},\dots,x_{n}]$ s.t. $$f(x)=(f_{1}(x),\dots,f_{m}(x)),\quad \forall x\in X$$
- **Related definition**: A morphism $f$ is an isomorphism, if there exists a morphism $g:Y\to X$ s.t. $f\circ g=\text{id}_{Y}$ and $g\circ f=\text{id}_{X}$.
- **Related definition**: for a morphism $f:X\to Y$ and $g\in A(Y)$, the ***pullback*** of $g$ through $f$ is defined as $f^{*}(g):=g\circ f$.
---
##### Properties
> [!lemma] Lemma 1
> Let $y_{1},\dots,y_{m}$ be the coordinate functions of $Y\subseteq \mathbb{A}_{K}^m$ and $f:X\to Y$. TFAE:
> 1. $f$ is a morphism.
> 2. $f_{i}:=y_{i}\circ f\in A(X)$ for all $i\in[m]$

> [!proof]-
> We have that if $f$ is a morphism, $f_{i}\in A(X)$ by [[Ring of Polynomial Functions|Remark]]. Conversely, if $f_{i}\in A(X)$, then there exists $F_{1},\dots,F_{m}\in K[x_{1},\dots,x_{n}]$ s.t. $f(x)=(F_{1}(x),\dots,F_{n}(x))$. 
---
> [!lemma] Proposition 2
> We have that:
> 1. for any morphism $f:X\to Y$, $f^{*}:A(Y)\to A(X)$ is a [[Algebra|$K$-algebra homomorphism]].