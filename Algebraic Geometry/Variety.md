#Definition #AlgebraicGeometry 

> [!definition]
> We have that:
> 1. A ***prevariety*** is a [[ringed space]] $X$ that has a finite open cover by affine varieties. 

- **Related definition**: Any open set of a prevariety that is an affine variety is called an ***affine open set***.
---
##### Properties
> [!lemma] Proposition 1 (Gluing Prevarieties)
> Let $X_{1},X_{2}$ be prevarieties and let $U_{1,2}\subseteq X_{1}$ and $U_{2,1}\subseteq X_{2}$ be open subsets. 
> 1. given an isomorphism $f:U_{1,2}\to U_{2,1}$, we can define $X:=(X_{1}\sqcup X_{2}) /_{\sim}$ given by $a\sim f(a)$ with the quotient topology given by $i_{1}:X_{1}\to X$ and $i_{2}:X_{2}\to X$. It has the structural sheaf: $$\mathcal{O}_{X}(U):=\{ \varphi:U\to K: i_{1}^{*}\varphi\in \mathcal{O}_{X_{1}}(i_{1}^{-1}(U))\text{ and }i_{2}^{*}\varphi\in \mathcal{O}_{X_{2}}(i_{2}^{-1}(U)) \}$$for all open subsets $U\subseteq X$. 
> 2. $i_{1}(X_{1})\cong X_{1}$ and $i_{2}(X_{2})\cong X_{2}$ and are open.
> 3. $X$ is a prevariety.

> [!proof]-
> We have that:
> 1. Clear.
> 2. The fact that they are open is clear. Further, $$i_{1}:X_{1}\to i_{1}(X_{1})$$ is continuous and for all open $U\subseteq i_{1}(X_{i})$ i.e. $i_{1}^{-1}(U)\subseteq X_{1}$ is open and $\varphi\in \mathcal{O}_{i_{1}(X_{1})}(U)$, we have a morphism. Further, it has an inverse morphism. 
> 3. Since $X_{1},X_{2}$ have a finite open cover by affine varieties, so does $X$. 

---
> [!lemma] Proposition 2 (General Gluing)
> For a finite index set $I$ and a set of prevarieties $\{ X_{i} \}_{i\in I}$ and open subsets $U_{i,j}\subseteq X_{i}$ for all $i,j\in I$, $i\neq j$:
> 1. given isomorphisms $f_{i,j}:U_{i,j}\to U_{j,i}$ s.t. for every distinct $i,j,k\in I$, $f^{-1}_{i,j}=f_{j,i}$ and $$f^{-1}_{i,j}(U_{j,k})\subseteq U_{i,k}$$ and $f_{j,k}\circ f_{i,j}=f_{i,k}$ on $f^{-1}_{i,j}(U_{j,k})$. Then $X:= (\bigsqcup_{i\in I} X_{i}) / _\sim$ given by $a\sim f_{i,j}(a)$ is a prevariety. 


---
##### Examples
> [!h] Example 1
> Let $X_{1},X_{2}:=\mathbb{A}^1$ and $U_{1,2}=U_{2,1}=\mathbb{A}^1 \backslash \{ 0 \}$. Then by the isomorphism $f:U_{1,2}\to U_{2,1},x\mapsto 1 / x$, we have that $\mathbb{P}^1$ is the glued prevariety of $X_{1}$ and $X_{2}$.
> 1. every morphism $g:U_{1,2}\to \mathbb{P}$ can be extended to $f:X_{1}\to \mathbb{P}$.

> [!proof]+
> We have that: 
> 1. We know that any morphism $g:\mathbb{A}^1 \backslash \{ 0 \}\to \mathbb{A}^1$ are is a regular function in $\mathcal{O}_{\mathbb{A}^1}(U_{1,2})$. Further, $U_{1,2}=D(x)$. Hence, $$\mathcal{O}_{X}(U_{1,2})=\left\{  \frac{h}{x^n}:h\in K[x],n\in \mathbb{N}  \right\}$$Let $g=\frac{h}{x^n}$. 
