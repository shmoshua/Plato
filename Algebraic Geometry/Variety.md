#Definition #AlgebraicGeometry 

> [!definition]
> We have that:
> 1. A ***prevariety*** is a [[ringed space]] $X$ that has a finite open cover by affine varieties. 

- **Related definition**: Any open set of a prevariety that is an affine variety is called an ***affine open set***.
- **Remark**: We have that:
	1. Any open subset $U\subseteq X$ of a prevariety is a prevariety called ***open subprevariety*** of $X$.
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
> [!lemma] Proposition 3 (Closed Subprevariety)
> Let $X$ be a prevariety and $Y\subseteq X$ a closed subset. We define: $$\mathcal{O}_{Y}(U):=\{ \varphi:U\to K: \forall a\in U, \exists V\ni a\text{ in }X\text{ and }\psi\in \mathcal{O}_{X}(V)\text{ s.t. }\varphi=\psi \text{ on }U\cap V \}$$
> Then,
> 1. $Y$ is a prevariety. 

> [!proof]+
> We have that:
> 1. Let $U\subseteq X$ be an affine open set. Then, we have an isomorphism $f:U\to V$ for some $V\subseteq \mathbb{A}^n$ an [[affine variety]]. We claim that $U\cap Y$ as an affine subvariety of $U$ is isomorphic to $U\cap Y$ as an open subset of $Y$. 
>    
>    Firstly, as $Y$ is closed $X$, $U\cap Y$ is closed in $U$ and $f(U\cap Y)=:Z$ is closed in $V$. Hence, $f(U\cap Y)$ is an affine variety. We now want to show that $f|_{Y}:U\cap Y\to Z$ is an isomorphism. 
>    
>    Let $W_{Y}\subseteq U\cap Y$ be open. Let $\varphi:W_{Y}\to K$. We claim that $\varphi\in \mathcal{O}_{Y}(W_{Y})$ if and only if $(f|_{Y}^{-1})^{*}\varphi\in \mathcal{O}_{Z}(f(W_{Y}))$.
>    
>    Let $\varphi\in \mathcal{O}_{Y}(W_{Y})$. Then, for all $a\in W_{Y}$, there exists $V_{Y}\ni a$ in $X$ and $\psi \in \mathcal{O}_{X}(V_{Y})$ s.t. $\varphi=\psi$ on $W_{Y}\cap V_{Y}$. Because $U$ is open in $X$, $W_{U}:=V_{Y}\cap U$
---
> [!lemma]
---
##### Examples
> [!h] Example 1
> Let $X_{1},X_{2}:=\mathbb{A}^1$ and $U_{1,2}=U_{2,1}=\mathbb{A}^1 \backslash \{ 0 \}$. Then by the isomorphism $f:U_{1,2}\to U_{2,1},x\mapsto 1 / x$, we have that $\mathbb{P}^1$ is the glued prevariety of $X_{1}$ and $X_{2}$.
> 1. every morphism $g:U_{1,2}\to \mathbb{P}$ can be extended to $g':X_{1}\to \mathbb{P}$.
> 2. not every morphism $\mathbb{A}^2 \backslash \{ 0 \}\to \mathbb{P}^1$ can however be extended to a morphism $\mathbb{A}^2 \to \mathbb{P}^1$. 
> 3. every morphism $\mathbb{P}^1\to \mathbb{A}^1$ is constant.
> 4. every isomorphism $\mathbb{P}^1\to \mathbb{P}^1$ is of the form $f(x)=\frac{ax+b}{cx+d}$ for some $a,b,c,d\in K$.

> [!proof]-
> We have that: 
> 1. We know that any morphism $g:\mathbb{A}^1 \backslash \{ 0 \}\to \mathbb{A}^1$ are is a regular function in $\mathcal{O}_{\mathbb{A}^1}(U_{1,2})$. Further, $U_{1,2}=D(x)$. Hence, $$\mathcal{O}_{X}(U_{1,2})=\left\{  \frac{h}{x^n}:h\in K[x],n\in \mathbb{N}  \right\}$$Let $g=\frac{h}{x^n}$. Then, $g \circ f^{-1}(x)=\frac{x^n}{h(x)}$. So we can define $g'$ where $g'(0)=i_{2}(0)$ and $g'(x)=i_{1}(g(x))$ otherwise. To show that this is a morphism we use the gluing property for morphisms. Notice that $U_{1,2},D(h)$ is an open cover of $X_{1}$. Then, $$g'|_{U_{1,2}}=g$$which is a morphism by definition. Similarly for $x\in D(h)$ $$g'(x)=i_{2}\left( \frac{x^n}{h(x)} \right)$$which is.a regular function and is a morphism. Hence, $g'$ is a morphism.
> 2. Consider $g:\mathbb{A}^2 \backslash \{ 0 \}\to \mathbb{P}^1,(x,y)\mapsto [x:y]$. This cannot be extended.
> 3. Let $g:\mathbb{P}^1\to \mathbb{A}^1$. Then, $g \circ i_{1}:\mathbb{A}^1 \to \mathbb{A}^1$ is a valid morphism. Hence, $g \circ i_{1}=:p\in \mathcal{O}_{\mathbb{A}^1}(\mathbb{A}^1)=K[x]$. Similarly $g\circ i_{2}=:q\in K[y]$. Therefore, we have that: $$p(x)=g \circ  i_{1}(x)= g\circ  i_{2}\left( \frac{1}{x} \right)=q \left( \frac{1}{x} \right)$$Therefore, we have that $p,q$ are constant.
> 4. Let $f:\mathbb{P}^1\to \mathbb{P}^1$ be an isomorphism. Then, $f \circ i_{1}:\mathbb{A}^1\to \mathbb{P}^1$ and $f\circ i_{2}:\mathbb{A}^1\to \mathbb{P}^1$ are morphisms. Let $\infty:=i_{2}(0)$. Then, 
> 	- If $f(\infty)=\infty$, then $f :\mathbb{A}^1\to \mathbb{A^1}$ and $f\in K[x]$ is an isomorphism. Hence, $f$ is linear with $f(x)=ax+b$. 
> 	- If $f(\infty)=q$ for some $q\neq \infty$. Let's define an isomorphism: $$h(x):=\frac{1}{x-q}$$Then, $h\circ f$ is also an isomorphism that sends $h\circ f(\infty)=\infty$. Hence, $h \circ  f$ is constant, i.e. $$ax+b=h(f(x))=\frac{1}{f(x)-q}$$Hence, $f(x)=\frac{1}{ax+b}+q=\frac{qax+qb+1}{ax+b}$.
