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
> [!lemma] Proposition 2 (Functoriality)
> Let $X,Y,Z$ be varieties. Then, 
> 1. $(\text{id}_{X})^{*}=\text{id}_{A(X)}$.
> 2. for any morphism $f:X\to Y$, $g:Y\to Z$, $( g\circ f)^{*}=f^{*}\circ g^{*}$.
> 3. for any morphisms $f,g:X\to Y$ with $f^{*}=g^{*}$, then $f=g$.

> [!proof]-
> We have that:
> 1. for any $g\in A(X)$, $(\text{id}_{X})^{*} (g)=g\circ \text{id}_{X}=g$.
> 2. for any $h\in A(Z)$, $(g \circ   f)^{*}(h)=h \circ  g \circ  f=f^{*}(h \circ  g)=f^{*}(g^{*}(h))$.
> 3. Consider $A(Y)=K[y_{1},\dots,y_{m}] / I(Y)$. Then, we have $f^{*}(\overline{y_{i}})=g^{*}(\overline{y_{i}})$ for all $i\in[m]$. Therefore, $\overline{y_{i} }\circ f=\overline{y_{i} }\circ g$.
> 
>    Let $f=(f_{1},\dots,f_{m})$ and $g=(g_{1},\dots,g_{m})$ with $f_{i},g_{i}\in K[x_{1},\dots,x_{n}]$. Then, $$f_{i}=\overline{y_{i} }\circ  f=\overline{y_{i} } \circ  g=g_{i}$$
>    
---
> [!lemma] Proposition 3 (Bijection of Varieties and K-algebra homomorphisms)
> Let $X\subseteq \mathbb{A}_{K}^n$, $Y\subseteq \mathbb{A}_{K}^m$ be two [[Variety|varieties]].
> 1. for any morphism $f:X\to Y$, $f^{*}:A(Y)\to A(X)$ is a [[Algebra|$K$-algebra homomorphism]].
> 3. for any $K$-algebra homomorphism $\varphi:A(Y)\to A(X)$, there exists a unique morphism $f:X\to Y$ s.t. $\varphi=f^{*}$. 

^71ae98

> [!proof]-
> We have:
> 1. Firstly, $f^{*}(g)=g\circ f:X\to K$. Hence, $f^{*}(g)\in A(X)$ and $f^{*}$ is well-defined. Now, to show that $f^{*}$ is a $K$-algebra homomorphism:
> 	1. **Claim 1**: $f^{*}$ is a ring homomorphism: For $g_{1},g_{2}\in A(Y)$, $$f^{*}(g_{1}+g_{2})=(g_{1}+g_{2})\circ f=g_{1}\circ f+g_{2}\circ f=f^{*}(g_{1})+f^{*}(g_{2})$$ $$f^{*}(g_{1}g_{2})=(g_{1}g_{2})\circ f=(g_{1}\circ f)(g_{2}\circ f)=f^{*}(g_{1})f^{*}(g_{2})$$
> 	2. **Claim 2**: $f^{*}$ is an algebra homomorphism: Let $c\in K$. Then, $c\in A(Y)$ as a constant function and $f^{*}(c)= c \circ f=c$. 
> 2. Let $q:K[y_{1},\dots,y_{m}]\to A(Y)$ be the quotient map and define $\Phi:= \varphi \circ q$. Then, $\Phi$ is a $K$-algebra homomorphism as a composition of two $K$-algebra homomorphisms. 
>    
>    Let $f_{1},\dots,f_{m}\in K[x_{1},..,x_{n}]$ s.t. $\Phi(y_{i})=\overline{f_{i}}$. Then, for all $g\in K[y_{1},\dots,y_{m}]$, by [[Algebra|Proposition 4]], $$g(\overline{f_{1}},\dots,\overline{f_{m}})=g(\Phi(y_{1}),\dots,\Phi(y_{m}))=\Phi(g(y_{1},\dots,y_{m}))=\Phi(g)$$If we now define $f:=(f_{1},\dots,f_{m})$. Let $g\in I(Y)$. Then, $$g(\overline{f_{1}},\dots,\overline{f_{m}})=\Phi(g)=0$$and $g(f_{1},\dots,f_{m})\in I(X)$. Hence, for all $x\in X$, $g(f(x))=0$. This shows that $f(x)\in Y$.
>     
>    It is left to show that $\varphi=f^{*}$. For any $g\in K[y_{1},\dots,y_{m}]$, $$\varphi(\overline{g})=\Phi(g)=g(\overline{f_{1}},\dots,\overline{f_{m}})=\overline{g(f_{1},\dots,f_{m})}=\overline{g \circ  f}=f^{*}(\overline{g})$$Uniqueness follows from Proposition 2.3.

^1db0b2

- **Corollary**: $f:X\to Y$ is an isomorphism if and only if $f^{*}:A(Y)\to A(X)$ is a $K$-algebra isomorphism. 
- **Remark**: Hence, we have an equivalence between category of varieties and category of finitely generated reduced $K$-algebras.
---
