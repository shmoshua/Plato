#Definition #AlgebraicGeometry 

> [!definition]
> A ***ringed space*** is a [[topological space]] $X$ together with a [[sheaf]] $\mathcal{O}_{X}$ of rings, called the ***structure sheaf***.
- **Related definition**: Let $f:X\to Y$ be a map of ringed spaces.
	1. For any map $\varphi:U\to K$ where $U$ is open, $f^{*}\varphi:=\varphi \circ f:f^{-1}(U)\to K$ is the ***pullback*** of $\varphi$ by $f$.
	2. $f$ is the ***morphism of ringed spaces*** if it is continuous and if for all open $U\subseteq Y$ and $\varphi\in \mathcal{O}_{Y}(U)$, we have $f^{*}\varphi\in \mathcal{O}_{X}(f^{-1}(U))$. In other words, $$f^{*}:\mathcal{O}_{Y}(U)\to \mathcal{O}_{X}(f^{-1}(U)),\quad \varphi\mapsto f^{*}\varphi$$is a $K$-algebra homomorphism.
	3. $f$ is an ***isomorphism*** if it has an inverse morphism.
- **Remark**: The composition and restriction of morphisms is a morphism.
---
##### Properties
> [!lemma] Lemma 1 (Gluing Property for Morphisms)
> Let $f:X\to Y$ be a morphism of ringed spaces. 
> 1. Suppose there is an open cover $\{ U_{i} \}_{i\in I}$ of $X$ s.t. all restrictions $f|_{U_{i}}:U_{i}\to Y$ are morphisms. Then $f$ is a morphism.

> [!proof]-
> We have that: 
> 1. The continuity is obvious. Let $V\subseteq Y$ be open and $\varphi\in \mathcal{O}_{Y}(V)$. Then, $$(f^{*}\varphi)|_{U_{i}\cap f^{-1}(V)}=(f|_{U_{i}\cap f^{-1}(V)})^{*} \varphi\in \mathcal{O}_{X}(U_{i}\cap f^{-1}(V))$$By the gluing property of sheaves, we have that there exists a unique $f^{*}\varphi\in \mathcal{O}_{X}(f^{-1}(V))$.

---
> [!lemma] Proposition 2 (Morphisms between Affine Varieties)
> Let $U$ be an open subset of an affine variety $X$ and $Y\subseteq \mathbb{A}^n$ another affine variety. 
> 1. the morphisms from $U$ to $Y$ are exactly maps of the form: $$(\varphi_{1},\dots,\varphi_{n}):U\to Y,\quad x\mapsto (\varphi_{1}(x),\dots,\varphi_{n}(x))$$with $\varphi_{i}\in \mathcal{O}_{X}(U)$

> [!proof]-
> We have that: 
> 2. Assume that $f:U\to Y$ is a morphism. We have that the $i$-th coordinate function $y_{i}$ on $Y$ is definitely in $\mathcal{O}_{Y}(Y)$. So $\varphi_{i}:=f^{*}y_{i}\in \mathcal{O}_{X}(f^{-1}(Y))=\mathcal{O}_{X}(U)$. Hence, we have $f=(\varphi_{1},\dots,\varphi_{n})$. 
>    
>    Conversely, let $f=(\varphi_{1},\dots,\varphi_{n})$ with $\varphi_{i}\in \mathcal{O}_{X}(U)$ and $f(U)\subseteq Y$. First, $f$ is continuous. If $Z\subseteq Y$ be closed. Then, $Z$ is of the form $V(g_{1},\dots,g_{m})$ for some $g_{1},\dots,g_{m}\in A(Y)$.  Then, $$f^{-1}(Z)=\{ x\in U:g_{i}(\varphi_{1}(x),\dots,\varphi_{n}(x))=0,\forall i\in[m] \}$$However, $x\mapsto g_{i}(\varphi_{1}(x),\dots,\varphi_{n}(x))$ are regular in $U$. Hence, $f^{-1}(Z)$ is closed as a zero locus of a regular function. Hence, $f$ is continuous. Similarly, if $\varphi\in \mathcal{O}_{Y}(W)$ is a regular function of some open $W\subseteq Y$, $$f^{*}\varphi=\varphi \circ f:f^{-1}(W)\to K,\quad x \mapsto \varphi(\varphi_{1}(x),\dots,\varphi_{n}(x))$$ which is regular again. Hence, $f$ is a morphism.
- **Corollary**: the morphisms from $U$ to $\mathbb{A}^1$ are exactly the [[Regular Function|regular functions]] in $\mathcal{O}_{X}(U)$.  
---
> [!lemma] Corollary 3
> For any to affine varieties $X,Y$ there is a bijection: 
> $$\begin{array}{rcl}\{ \text{Morphisms }X\to Y \} & \leftrightarrow  & \{ K\text{-algebra homomorphisms }A(Y)\to A(X) \}\\f&\mapsto &f^{*}\end{array}$$
> In particular, isomorphisms from $X\to Y$ correspond to $K$-algebra isomorphisms

> [!proof]-
> We have that: 
> 1. By definition $f^{*}$ is a $K$-algebra homomorphism $\mathcal{O}_{Y}(Y)\to \mathcal{O}_{X}(X)$. From Corollary or [[Regular Function|Proposition 3]], this is a homomorphism from $A(Y)$ to $A(X)$. 
>    
>    Conversely, let $g:A(Y)\to A(X)$ be a $K$-algebra homomorphism. Assume that $Y\subseteq \mathbb{A}^n$ and denote $y_{1},\dots,y_{n}$ as the coordinate functions in $\mathbb{A}^n$. Then, $\varphi_{i}:=g(y_{i})\in A(X)=\mathcal{O}_{X}(X)$. If we set: $$f=(\varphi_{1},\dots,\varphi_{n}):X\to \mathbb{A}^n$$then we get that for any $h\in K[y_{1},\dots,y_{n}]$, $$(f^{*} h)(x)=h(f(x))=h(\varphi_{1}(x),\dots,\varphi_{n}(x))=g(h)(x)$$Therefore, $h(f(x))=0$ for all $h\in I(Y)$. Hence, the image of $f$ lies in $V(I(Y))=Y$. As coordinate functions are regular, this is indeed a morphism. Lastly, we get that $f^{*}=g$. 