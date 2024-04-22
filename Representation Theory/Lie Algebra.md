#Definition #RepresentationTheory 

> [!definition]
> Let $\mathfrak{g}$ be a $K$-[[vector space]]  and $[,]:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$ be a skew-symmetric bilinear map, i.e. $[a,b]=-[b,a]$. A ***Lie algebra*** is a tuple $(\mathfrak{g},[,])$ s.t. 
> 1. Jacobi identity: $[[a,b],c]+[[b,c],a]+[[c,a],b]=0$ for all $a,b,c\in \mathfrak{g}$.
- **Related definition**: A ***Lie subalgebra*** of $(\mathfrak{g},[,])$ is a subspace $\mathfrak{a}$ that is stable under $[,]$.
- **Remark**: Ado’s theorem says that any finite-dimensional Lie algebra is a Lie subalgebra of $\mathfrak{gl}(V)$ for a suitable finite dimensional vector space $V$.
---
##### Examples 
> [!h] Example 1
> Any space $\mathfrak{g}$ with $[,]\equiv 0$ is an abelian Lie algebra.
---
> [!h] Example 2 (General Linear Lie Algebra)
> Following are Lie algebras:
> 1. $\mathfrak{g}$ is an [[associative algebra]] and $[a,b]=ab-ba$.
> 2. if $\mathfrak{g}=\text{End}(V)$ for a vector space $V$, we denote this Lie algebra with $\mathfrak{gl}(V)$.
> 3. any subspace $U$ of an associative algebra $A$ s.t. $U$ is stable under $[,]$.
---
> [!h] Example 3 (Derivations)
> The space of [[Derivation|derivations]] $\text{Der }C^\infty(M)\subseteq \text{End}(C^\infty(M))$ with $[a,b]=ab-ba$.
---
> [!h] Example 4 (Cross product)
> $\mathbb{R}^3$ with $[u,v]:=u\times v$ as the cross product is a Lie algebra.
---
> [!h] Example 5 (Special Linear Lie Algebra)
> The ***special linear Lie algebra*** is $$\mathfrak{sl}_{n}(K):=\{ A\in \text{M}_{n,n}(K):\text{tr}(A)=0 \}$$with $[A,B]=AB-BA$. The basis of $\mathfrak{sl}_{2}(K)$ is given as: $$e:=\begin{bmatrix}0&1\\0&0\end{bmatrix},\quad f:=\begin{bmatrix}0&0\\1&0\end{bmatrix},\quad h:=\begin{bmatrix}1&0\\0&-1\end{bmatrix}$$where $[h,e]=2e$, $[h,f]=-2f$ and $[e,f]=h$.
---
> [!h] Example 6 (Heisenberg Lie Algebra)
> Defined as: $$\mathfrak{H}:=\left\{ A\in \text{M}_{3,3}(\mathbb{C}):A=\begin{bmatrix}0&*&*\\0&0&*\\0&0&0\end{bmatrix} \right\}$$with basis: $$x:=\begin{bmatrix}0&0&0\\0&0&1\\0&0&0\end{bmatrix},\quad y:=\begin{bmatrix}0&1&0\\0&0&0\\0&0&0\end{bmatrix},\quad c:=\begin{bmatrix}0&0&1\\0&0&0\\0&0&0\end{bmatrix}$$with $[y,x]=c$, $[y,c]=[x,c]=0$.
---
> [!h] Example 7 (Affine Transformations)
> 