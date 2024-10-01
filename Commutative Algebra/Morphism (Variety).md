#Definition #CommutativeAlgebra 

> [!definition]
> Let $X\subseteq \mathbb{A}_{K}^n$, $Y\subseteq \mathbb{A}_{K}^m$ be two [[Variety|varieties]]. 
> 1. A ***morphism*** is a map $f:X\to Y$ given by polynomials, i.e. there exist: $f_{1},\dots,f_{m}\in K[x_{1},\dots,x_{n}]$ s.t. $$f(x)=(f_{1}(x),\dots,f_{m}(x)),\quad \forall x\in X$$

^f860e3

- **Related definition**: A morphism $f$ is an isomorphism, if there exists a morphism $g:Y\to X$ s.t. $f\circ g=\text{id}_{Y}$ and $g\circ f=\text{id}_{X}$. ^999568
- **Related definition**: for a morphism $f:X\to Y$ and $g\in A(Y)$, the ***pullback*** of $g$ through $f$ is defined as $f^{*}(g):=g\circ f=g(f_{1},\dots,f_{m})$. ^cc40e0
---
##### Properties
> [!lemma] Lemma 1
> Let $y_{1},\dots,y_{m}$ be the coordinate functions of $Y\subseteq \mathbb{A}_{K}^m$ and $f:X\to Y$. TFAE:
> 1. $f$ is a morphism.
> 2. $f_{i}:=y_{i}\circ f\in A(X)$ for all $i\in[m]$

^fb7c53

> [!proof]-
> We have that if $f$ is a morphism, $f_{i}\in A(X)$ by [[Ring of Polynomial Functions|Remark]]. Conversely, if $f_{i}\in A(X)$, then there exists $F_{1},\dots,F_{m}\in K[x_{1},\dots,x_{n}]$ s.t. $f(x)=(F_{1}(x),\dots,F_{n}(x))$. 

^1b25df

---
> [!lemma] Proposition 2 (Bijection of Varieties and K-algebra homomorphisms)
> Let $X\subseteq \mathbb{A}_{K}^n$, $Y\subseteq \mathbb{A}_{K}^m$ be two [[Variety|varieties]].
> 1. for any morphism $f:X\to Y$, $f^{*}:A(Y)\to A(X)$ is a [[Algebra|$K$-algebra homomorphism]].
> 2. $(f_{2}\circ f_{1})^{*}=f_{1}^{*}\circ f_{2}^{*}$.
> 3. for any $K$-algebra homomorphism $\varphi:A(Y)\to A(X)$, there exists a unique morphism $f:X\to Y$ s.t. $\varphi=f^{*}$. 

^71ae98

> [!proof]-
> We have:
> 1. Firstly, $f^{*}(g)=g\circ f:X\to K$ is in $A(X)$. Now, for $g_{1},g_{2}\in A(Y)$, $$f^{*}(g_{1}+g_{2})=(g_{1}+g_{2})\circ f=g_{1}\circ f+g_{2}\circ f=f^{*}(g_{1})+f^{*}(g_{2})$$ $$f^{*}(g_{1}g_{2})=(g_{1}g_{2})\circ f=(g_{1}\circ f)(g_{2}\circ f)=f^{*}(g_{1})f^{*}(g_{2})$$ and for any $c\in K$, we have that $f^{*}(c)=c\circ f= c$. Therefore, $f^{*}$ is an $K$-algebra homomorphism.
> 2. We have: $$(f_{2}\circ f_{1})^{*}(g)=g\circ f_{2}\circ f_{1}=f_{1}^{*}(g\circ f_{2})=f^{*}_{1}(f_{2}^{*}(g))$$
> 3. Let $A(Y)=K[y_{1},\dots,y_{m}] / I(Y)=K[\overline{y}_{1},\dots,\overline{y}_{m}]$ for some $\overline{y}_{i}\in A(Y)$. Now, let $f_{i}:=\varphi(\overline{y}_{i})\in A(X)$. Then, we claim that $$f:=(f_{1},\dots,f_{m}):X\to \mathbb{A}_{K}^n$$ is a morphism and $f(X)\subseteq Y$. Let $g\in I(Y)$. Then, 
>    
>    $$g(f(x))=g(f_{1}(x),\dots,f_{m}(x))=g(\varphi(\overline{y}_{1})(x),\dots,\varphi(\overline{y}_{n})(x)=\varphi(g\circ (\overline{y}_{1},\dots,\overline{y}_{m}))=0$$Also by construction, we have $f^{*}(\overline{y}_{i})=\overline{y}_{i}\circ f=f_{i}=\varphi(\overline{y}_{i})$. Therefore, $f^{*}=\varphi$ and $f$ is unique with this property.

^1db0b2

- **Corollary**: $f:X\to Y$ is an isomorphism if and only if $f^{*}:A(Y)\to A(X)$ is a $K$-algebra isomorphism. 
- **Remark**: Hence, we have an equivalence between category of varieties and category of finitely generated reduced $K$-algebras.
---
