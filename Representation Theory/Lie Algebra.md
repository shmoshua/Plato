#Definition #RepresentationTheory #LieGroups 

> [!definition]
> A ***Lie algebra*** over a [[field]] $K$ is a $K$-[[vector space]] $\mathfrak{g}$ endowed with a skew-symmetric bilinear map $[\cdot,\cdot]:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$, i.e. $[a,b]=-[b,a]$ s.t. 
> 1. Jacobi identity: $[[a,b],c]+[[b,c],a]+[[c,a],b]=0$ for all $a,b,c\in \mathfrak{g}$ holds.
- **Related definition**: A ***Lie subalgebra*** of $(\mathfrak{g},[,])$ is a subspace $\mathfrak{a}$ that is stable under $[,]$.
- **Remark**: Ado’s theorem says that any finite-dimensional Lie algebra is a Lie subalgebra of $\mathfrak{gl}(V)$ for a suitable finite dimensional vector space $V$.
- **Related definition**: A ***Lie algebra homomorphism*** is a $K$-linear map $\varphi:\mathfrak{g}_{1}\to \mathfrak{g}_{2}$ between $K$-Lie algebras s.t. $\varphi([a,b])=[\varphi(a),\varphi(b)]$.
---
##### Properties
> [!lemma] Proposition 1 (Lie Algebra of a Lie group)
> For a [[Lie group]] $G$ and a smooth group action $G\times G\to G$, let for $g\in G$: $$L_{g}:G\to G,\quad x\mapsto gx$$
> 1. $(L_{g})_{*}:\Gamma(\text{T}G)\to\Gamma(\text{T}G)$ is a Lie algebra isomorphism.
> 2. the space of [[Topological Vector Space with Seminorms|$G$-invariant vector fields]] $\mathfrak{g}\subseteq \Gamma(\text{T}G)$ is a Lie subalgebra.
> 3. the map: $$\mathfrak{g}\mapsto \text{T}_{e}G,\quad X\mapsto X_{e}$$ is a vector space isomorphism.

> [!proof]+
> We have:
> 1. $L_{g}$ is a diffeomorphism for any $g\in G$ with $L_{g}^{-1}=L_{g^{-1}}$. Therefore, by [[Vector Field|Proposition 2]], $(L_{g})_*$ is a Lie algebra isomorphism.
> 2. We have that for $X,Y\in \mathfrak{g}$, $$(L_{g})_{*}([X,Y])=[(L_{g})_{*}(X),(L_{g})_{*}(Y)]=[X,Y]$$
> 3. Define: $$\Psi:\text{T}_{e}G\to \mathfrak{g},\quad v\mapsto v^L$$where $v^L_{g}:=d_{e}L_{g}(v)$. Then, 
> 	1. **$\Psi$ is well-defined**:
---
##### Examples 
> [!h] Example 1
> Any space $\mathfrak{g}$ with $[\cdot,\cdot]\equiv 0$ is an abelian Lie algebra. 
---
> [!h] Example 2 (General Linear Lie Algebra)
> Following are Lie algebras:
> 1. $\mathfrak{g}$ is an [[associative algebra]] and $[a,b]=ab-ba$.
> 2. if $\mathfrak{g}=\text{End}(V)$ for a vector space $V$, we denote this Lie algebra with $\mathfrak{gl}(V)$.
> 3. any subspace $U$ of an associative algebra $A$ s.t. $U$ is stable under $[,]$.
---
> [!h] Example 3 (Derivations)
> The space of [[Derivation|derivations]] $\text{Der }C^\infty(M)\subseteq \text{End}(C^\infty(M))$ with $[a,b]=ab-ba$. Further, $\Gamma(\text{T}M)$ is a Lie algebra with the [[Lie bracket]].
---
> [!h] Example 5 (Cross product)
> $\mathbb{R}^3$ with $[u,v]:=u\times v$ as the cross product is a Lie algebra.
---
> [!h] Example 6 (Special Linear Lie Algebra)
> The ***special linear Lie algebra*** is $$\mathfrak{sl}_{n}(K):=\{ A\in \text{M}_{n,n}(K):\text{tr}(A)=0 \}$$with $[A,B]=AB-BA$. The basis of $\mathfrak{sl}_{2}(K)$ is given as: $$e:=\begin{bmatrix}0&1\\0&0\end{bmatrix},\quad f:=\begin{bmatrix}0&0\\1&0\end{bmatrix},\quad h:=\begin{bmatrix}1&0\\0&-1\end{bmatrix}$$where $[h,e]=2e$, $[h,f]=-2f$ and $[e,f]=h$.
---
> [!h] Example 7 (Heisenberg Lie Algebra)
> Defined as: $$\mathfrak{H}:=\left\{ A\in \text{M}_{3,3}(\mathbb{C}):A=\begin{bmatrix}0&*&*\\0&0&*\\0&0&0\end{bmatrix} \right\}$$with basis: $$x:=\begin{bmatrix}0&0&0\\0&0&1\\0&0&0\end{bmatrix},\quad y:=\begin{bmatrix}0&1&0\\0&0&0\\0&0&0\end{bmatrix},\quad c:=\begin{bmatrix}0&0&1\\0&0&0\\0&0&0\end{bmatrix}$$with $[y,x]=c$, $[y,c]=[x,c]=0$.
---
> [!h] Example 8 (Affine Transformations)
> Defined as: $$\text{aff}(1):=\left\{ A\in \text{M}_{2,2}(\mathbb{C}):A=\begin{bmatrix}*&*\\0&0\end{bmatrix} \right\}$$with basis: $$X:=\begin{bmatrix}1&0\\0&0\end{bmatrix},\quad Y:=\begin{bmatrix}0&1\\0&0\end{bmatrix}$$with $[X,Y]=Y$.
---
> [!h] Example 9 (Special Orthogonal Lie Algebra)
> $$\mathfrak{so}_{n}(\mathbb{R}):=\{ A\in \mathfrak{gl}_{n}(\mathbb{R}):A^\top+A=0 \}$$
---
