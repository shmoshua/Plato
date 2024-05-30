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
> 3. For any $X\in \mathfrak{g}$, $X$ is $L_{g}$-related to itself for all $g\in G$.
> 4. the map: $$\mathfrak{g}\mapsto \text{T}_{e}G,\quad X\mapsto X_{e}$$ is a vector space isomorphism.

> [!proof]-
> We have:
> 1. $L_{g}$ is a diffeomorphism for any $g\in G$ with $L_{g}^{-1}=L_{g^{-1}}$. Therefore, by [[Vector Field|Proposition 2]], $(L_{g})_*$ is a Lie algebra isomorphism.
> 2. We have that for $X,Y\in \mathfrak{g}$, $$(L_{g})_{*}([X,Y])=[(L_{g})_{*}(X),(L_{g})_{*}(Y)]=[X,Y]$$
> 3. This is by [[Vector Field|Proposition 2]].
> 4. Clearly, the map is linear. Now, if $X_{e}=Y_{e}$ for $X,Y\in \mathfrak{g}$. Then, from 3, $dL_{g}\circ X =X\circ L_{g}$ for all $g\in G$. Therefore, for any $g\in G$, $$X_{g}=X_{L_{g}(e)}=d_{e}L_{g}(X_{e})=d_{e}L_{g}(Y_{e})=Y_{g}$$and the map is injective. For surjectivity, let $v\in \text{T}_{e}G$. define $X_{g}:=d_{e}L_{g}(v)$. Then, $X_{e}=d_{e}L_{e}(v)=v$ and we have for any $h\in G$: $$X_{gh}=d_{e}L_{gh}(v)=d_{h}L_{g}(d_{e}L_{h}(v))=d_{h}L_{g}(X_{h})$$Therefore, $X$ is $L_{g}$-related to itself for all $g\in G$. 
- **Remark**: From this isomorphism, for a [[Lie group]] $G$, we denote its Lie algebra $\mathfrak{g}$ as $\text{T}_{e}G$ with the bracket induced from $\Gamma(\text{T}G)$.
---
> [!lemma] Proposition 2 (Lie Group homomorphism induces a Lie Algebra homomorphism)
> Let $G,H$ be [[Lie Group|Lie groups]] with $\varphi:G\to H$ a Lie group homomorphism. Then, for the corresponding Lie algebras $\mathfrak{g}$ and $\mathfrak{h}$, the [[differential]] $d_{e}\varphi:\mathfrak{g}\to \mathfrak{h}$ is a Lie algebra homomorphism.

> [!proof]-
> We need to show that for $v_{1},v_{2}\in \mathfrak{g}$, $d_{e}\varphi[v_{1},v_{2}]=[d_{e}\varphi (v_{1}),d_{e}\varphi(v_{2})]$. 
> 
> Let $v\in \mathfrak{g}$ and $w:=d_{e}\varphi(v)\in \mathfrak{h}$. We first claim that $v^L\in \Gamma(\text{T}G)$ and $w^L\in \Gamma(\text{T}H)$ are $\varphi$ related. We have:$$\begin{align}(w^L)_{\varphi (g)}&=d_{e}L_{\varphi(g)}(w)=d_{e}L_{\varphi(g)}(d_{e}\varphi(v))=d_{e}(L_{\varphi(g)}\circ \varphi)(v)\\&=d_{e}(\varphi \circ L_{g})(v)=d_{g}\varphi(d_{e}L_{g}(v))=d_{g}\varphi((v^L)_{g})\end{align}$$Now let $w_{i}:=d_{e}\varphi(v_{i})$ for $i=1,2$. Then, by [[Vector Field|Proposition 2.3]], $[v_{1}^L,v_{2}^L]$ and $[w_{1}^L,w_{2}^L]$ are $\varphi$-related. Therefore, $$d_{e}\varphi[v_{1},v_{2}]=d_{e}\varphi([v_{1}^L,v_{2}^L]_{e})=[w_{1}^L,w_{2}^L]_{e}=[w_{1},w_{2}]$$This proves the statement.
- **Corollary**: For a Lie group $G$ and $H\leq G$ that is a [[Submanifold|regular submanifold]], $i:H\hookrightarrow G$ is a Lie group isomorphism and therefore, $\mathfrak{h}\subseteq \mathfrak{g}$ is a Lie subalgebra.
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
> The ***special linear Lie algebra*** is $$\mathfrak{sl}(n,\mathbb{R})=\{ A\in \text{Mat}_{n,n}(\mathbb{R}):\text{tr}(A)=0 \}$$with $[A,B]=AB-BA$. 
> 
> 
> 
> 
> 
> The basis of $\mathfrak{sl}_{2}(K)$ is given as: $$e:=\begin{bmatrix}0&1\\0&0\end{bmatrix},\quad f:=\begin{bmatrix}0&0\\1&0\end{bmatrix},\quad h:=\begin{bmatrix}1&0\\0&-1\end{bmatrix}$$where $[h,e]=2e$, $[h,f]=-2f$ and $[e,f]=h$.

> [!proof]-
> Let $\gamma:(-1,1)\to \text{SL}(n,\mathbb{R})$ be a [[smooth curve]] with $\gamma(0)=I$. Then, $\det(\gamma(s))=1$ for all $s\in(-1,1)$. Therefore, $$0=\left. \frac{d}{dt} \right| _{t=0}\det(\gamma(t))=\left( \left. \frac{d\det}{dt} \right| _{t=I} \right) \cdot \left( \left. \frac{d\gamma}{dt} \right|_{t=0}  \right)=\left. \frac{d}{dt} \right| _{t=0}\det(I+t\gamma'(0))=d_{I}\text{det}(\gamma'(0)_{I}) =\text{tr}(\gamma'(0))$$Further as $\text{SL}(n,\mathbb{R})$ is a smooth manifold, for any $v\in \text{T}_{I}\text{SL}(n,\mathbb{R})=\mathfrak{sl}(n,\mathbb{R})$, we can construct a smooth curve $\gamma$ s.t. $\gamma(0)=I$ and $\gamma'(0)=v$. Therefore, $$\mathfrak{sl}(n,\mathbb{R})\subseteq \{ A\in \text{Mat}_{n,n}(\mathbb{R}):\text{tr}(A)=0 \}$$As the RHS also has dimension $n^2-1$ and we know from [[Submanifold|Example 1]] that $\text{SL}(n,\mathbb{R})$ is $n^2-1$ dimensional, we have shown the equality. 
---
> [!h] Example 7 (Orthogonal Lie Algebra)
> For the [[orthogonal group]] $\text{O}(n,\mathbb{R})$, the corresponding Lie algebra is: $$\mathfrak{o}(n,\mathbb{R})=\{ A\in \text{Mat}_{n,n}(\mathbb{R}):A+A^\top=0 \}$$

> [!proof]-
> Let $\gamma:(-1,1)\to \text{O}(n,\mathbb{R})$ be a smooth curve with $\gamma(0)=I$. Then, $\gamma(s)\gamma(s)^\top=I$ for all $s$. Consider $\gamma\gamma^\top:s\mapsto \gamma(s)\gamma(s)^\top$ as a smooth curve. Then, $$(\gamma\gamma^\top)'(s)=\gamma'(s)\gamma(s)^\top+\gamma(s)(\gamma'(s))^\top$$from product rule. Therefore, $$0=\left. \frac{d}{dt} \right|_{t=0}\gamma\gamma^\top=(\gamma\gamma^\top)'(0)=\gamma'(0)+(\gamma'(0))^\top$$As $\text{O}(n,\mathbb{R})$ is a smooth manifold, we can find a smooth curve $\gamma:(-1,1)\to \text{O}(n,\mathbb{R})$ s.t. $\gamma(0)=I$ and $\gamma'(0)=v$ for any $v\in \text{T}_{I}\text{O}(n,\mathbb{R})=\mathfrak{o}(n,\mathbb{R})$. Therefore, $$\mathfrak{o}(n,\mathbb{R})\subseteq \{ A\in \text{Mat}_{n,n}(\mathbb{R}):A+A^\top=0 \}$$As the RHS has dimension $\frac{n(n-1)}{2}$ and so does $\text{O}(n,\mathbb{R})$ we have the desired equality.
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
