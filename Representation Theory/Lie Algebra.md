#Definition #LieGroups

> [!definition]
> A ***Lie algebra*** over a [[field]] $K$ is a $K$-[[vector space]] $\mathfrak{g}$ endowed with a skew-symmetric bilinear map $[\cdot,\cdot]:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$, i.e. $[a,b]=-[b,a]$ s.t. 
> 1. Jacobi identity: $[[a,b],c]+[[b,c],a]+[[c,a],b]=0$ for all $a,b,c\in \mathfrak{g}$ holds.
- **Related definition**: A Lie algebra $\mathfrak{g}$ is ***abelian*** if $[\cdot,\cdot]=0$.
- **Related definition**: A ***Lie subalgebra*** of $(\mathfrak{g},[,])$ is a subspace $\mathfrak{a}$ that is stable under $[,]$.
- **Remark**: Ado’s theorem says that any finite-dimensional Lie algebra is a Lie subalgebra of $\mathfrak{gl}(V)$ for a suitable finite dimensional vector space $V$.
- **Related definition**: A ***Lie algebra homomorphism*** is a $K$-linear map $\varphi:\mathfrak{g}_{1}\to \mathfrak{g}_{2}$ between $K$-Lie algebras s.t. $\varphi([a,b])=[\varphi(a),\varphi(b)]$. A ***Lie algebra isomorphism*** is an invertible Lie algebra homomorphism.
---
##### Properties
> [!lemma] Proposition 1 (Lie Algebra of a Lie group)
> For a [[Lie group]] $G$ and a smooth group action $G\times G\to G$, let for $g\in G$: $$L_{g}:G\to G,\quad x\mapsto gx$$
> 1. $(L_{g})_{*}:\Gamma(\text{T}G)\to\Gamma(\text{T}G)$ is a Lie algebra isomorphism.
> 2. the space of [[Vector Field|$G$-invariant vector fields]] $\mathfrak{g}\subseteq \Gamma(\text{T}G)$ is a Lie subalgebra.
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
> [!lemma] Proposition 3 (Lie Algebra of Product of Lie Groups)
> Let $G,H$ be [[Lie Group|Lie groups]] with respective Lie algebras $\mathfrak{g}$ and $\mathfrak{h}$. Then, the Lie algebra of $G\times H$ is $\mathfrak{g\oplus h}$ where the bracket is given componentwise. 

> [!proof]-
> We will show an Lie algebra isomorphism:$$\begin{array}{cccc} {\Psi:}&{\Gamma(\text{T}G)^L\times\Gamma(\text{T}H)^L}&\to&{\Gamma(\text{T}(G\times H))^L}\\&{(X,Y)} &\mapsto & {X\oplus Y} \end{array}{}$$Then, $$\Psi([(X_{1},Y_{1}),(X_{2},Y_{2})])=\Psi([X_{1},X_{2}],[Y_{1},Y_{2}])=[X_{1},X_{2}]\oplus [Y_{1},Y_{2}]=[X_{1}\oplus Y_{1},X_{2}\oplus Y_{2}]$$Therefore, $\Psi$ is a Lie algebra homomorphism
---
> [!lemma] Proposition 4
> Let $G$ be a connected Lie group. Then the following are equivalent:
> 1. $G$ is abelian.
> 2. $\mathfrak{g}$ is abelian.

> [!proof]-
> Assume that $G$ is abelian. Then, for any $v,w\in \mathfrak{g}$, $$\varphi_{v^L}(s)\varphi_{w^L}(t)=\varphi_{w^L}(t)\varphi_{v^L}(s),\quad \forall s,t\in \mathbb{R}$$Therefore, $\Phi^s_{v^L}$ and $\Phi_{w^L}^t$ commute for all $s,t\in \mathbb{R}$. By [[Flow|Proposition 3]], $[v^L,w^L]=0$ and $[v,w]=0$ in $\mathfrak{g}$.
> 
> Conversely, assume that $\mathfrak{g}$ is abelian. By [[Exponential Map|Lemma 1.2]], $\exp$ is a smooth homomorphism. Then, by [[Exponential Map|Proposition 2.2]], there exists $0\in U\subseteq \mathfrak{g}$ open s.t. $\exp(U)\subseteq G$ is an open neighborhood of $e$. By [[Topological Space|Proposition 2.4]], $G$ is abelian.
---
> [!lemma] Theorem 5
> Let $G,H$ be Lie groups with $\pi:\mathfrak{g}\to \mathfrak{h}$ a Lie algebra homomorphism. Then, 
> 1. there exists a [[Local Homomorphism|local Lie group homomorphism]] $\varphi:U\to H$ s.t. $d_{e}\varphi=\pi$.
> 2. if $\pi$ is an isomorphism, then $\varphi$ is a local isomorphism.

> [!proof]- 
> Consider $\text{graph}(\pi)\subseteq \mathfrak{g}\times \mathfrak{h}$. Then, we claim that $\text{graph}(\pi)$ is a Lie subalgebra of $\mathfrak{g}\times \mathfrak{h}$. Indeed, $$[(v,\pi(v)),(w,\pi(v))]=([v,w],\pi([v,w]))\subseteq \text{graph}(\pi)$$Then, by [[Lie Subgroup|Theorem 1]], there exists a unique connected Lie subgroup $K\leq G\times H$ with Lie algebra $\mathfrak{k}$ s.t. $\mathfrak{k}=\text{graph}(\pi)$. Therefore, we have the diagram: $$\begin{CD}K@>>>G\times H@>\text{pr}_{G}>>G\\@A\exp AA@A\exp AA@A\exp AA\\\text{graph}(\pi)@>>>\mathfrak{g}\times \mathfrak{h} @>d_{e}\text{pr}_{G}=\text{pr}_{\mathfrak{g}}>> \mathfrak{g}\end{CD}$$By construction $\text{pr}_{G}|_{K}:K\to G$ is a Lie group homomorphism and for its derivative: $$d_{e}(\text{pr}_{G}|_{K})=\text{pr}_{\mathfrak{g}}|_{\text{graph}(\pi)}$$is an isomorphism. Therefore, by [[Differential|Inverse Function Theorem]], there exists an open neighborhood $e\in U\subseteq K$ s.t. $\text{pr}_{G}|_{U}:U\to \text{pr}_{G}(U)$ is a diffeomorphism. Then, $(\text{pr}_{G}|_{U})^{-1}:\text{pr}_{G}(U)\to U$ has the differential: $$d_{e}(\text{pr}_{G}|_{U})^{-1}(v)=(v,\pi(v))$$Therefore, consider the Lie group homomorphism $\text{pr}_{H}:G\times H\to H$, then we have: $$\text{pr}_{H}\circ (\text{pr}_{G}|_{K})^{-1}:\text{pr}_{G}(U)\to H$$is the sought local homomorphism. Further, $$d_{e}(\text{pr}_{H}\circ (\text{pr}_{G}|_{K})^{-1})(v)=\text{pr}_{\mathfrak{h}}(v,\pi(v))=\pi(v) $$This proves the statement.
- **Corollary**: Let $G$ be a connected Lie group with Lie algebra $\mathfrak{g}$. Then, there exists a simply connected Lie group $H$ whose Lie algebra is $\mathfrak{g}$ by [[Local Homomorphism|Theorem 1]]
---
> [!lemma] Corollary 6
> Let $G,H$ be two simply connected, [[Lie Group|connected Lie groups]]. 
> 1. If $\mathfrak{g}\cong\mathfrak{h}$ as Lie algebras, then $G\cong H$ as Lie groups.

> [!proof]-
> Let $\pi:\mathfrak{g}\to \mathfrak{h}$ be the Lie algebra isomorphism. Then, by Theorem 5, there exists a local isomorphism $\varphi:U\to H$ where $U$ is open in $G$. By [[Local Homomorphism|Extension of local homomorphisms]], we can lift it to a unique continuous group homomorphism $\varphi:G\to H$. Then, by [[Lie Group|Proposition 5]], $\varphi$ is smooth with $d_{e}\varphi=\pi$. Similarly, there exists a Lie group homomorphism $\psi:H\to G$ with $d_{e}\psi=\pi^{-1}$.
> 
> We may assume that the neighborhoods $U\subseteq G$ and $V\subseteq H$ on which the local isomorphisms $\varphi,\psi$ are defined, are given by $U=\exp(L)$ and $V=\exp(f(L))$ for an open subset $L\subseteq \mathfrak{g}$, so that $\varphi(U)=V$ and $\psi(V)=U$.
> 
> We now claim that $\varphi:G\to H$ is a covering, i.e. for every $h\in H$ there is a neighborhood $W\subseteq H$ of $h$ such that $\varphi ^{-1}(W)$ is a disjoint union of open sets $U_{0}\subseteq G$ which are homeomorphic to $W$. For $h\in H$ we take $hV$ as the open neighborhood. We have $$\varphi ^{-1}(h_{2}V) = \bigcup_{g\in \varphi ^{-1}(h)}gU$$ so we just have to prove that the $gU$ are disjoint: if there are $g,g'\in \varphi ^{-1}(h)$ with $g'\in gU$, then $g^{-1}g'\in U$, and so $$\varphi(g^{-1}g')=\varphi(g)^{-1}\varphi(g')=h^{-1}h=e\in\varphi(U)=V$$hence $g^{-1}g'=e$ and $g=g'$. 
> 
> Now a [[covering of a simply connected space is bijective]], so $\varphi:G\to H$ is a bijective smooth group homomorhpism with invertable differential, so the inverse is also a smooth group homomorphism, so $G\cong H$ are isomorphic Lie groups.
---
###### Complex Lie Algebras
> [!lemma] Proposition 1 (Complex Lie Algebra)
> Let $\mathfrak{g}$ be a $\mathbb{R}$-Lie algebra. Consider $\mathfrak{g}_{\mathbb{C}}:=\mathfrak{g}\otimes_{\mathbb{R}}\mathbb{C}$. Then, 
> 1. the bracket $[\cdot,\cdot]:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$ extends uniquely to a $\mathbb{C}$-bilinear map $\mathfrak{g}_{\mathbb{C}}\times \mathfrak{g}_{\mathbb{C}}\to \mathfrak{g}_{\mathbb{C}}$.
> 2. the canonical injection $\mathfrak{g}\to \mathfrak{g}_{\mathbb{C}},X\mapsto X\otimes 1$ is a Lie algebra homomorphism and $\mathfrak{g}_{\mathbb{C}}=\mathfrak{g}+ i \mathfrak{g}$.
> 3. Then, the bracket is:
> 4. $\mathfrak{g}$ is solvable if and only if $\mathfrak{g}_{\mathbb{C}}$ is solvable.
> 5. $\mathfrak{g}$ is nilpotent if and only if $\mathfrak{g}_{\mathbb{C}}$ is nilpotent.
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
> For the [[orthogonal groups]], the corresponding Lie algebras are: 
> 1. $\mathfrak{o}(n,\mathbb{R})=\{ A\in \text{Mat}_{n,n}(\mathbb{R}):A+A^\top=0 \}$
> 2. $\mathfrak{o}(p,q)=\{  A\in \text{Mat}_{n,n}(\mathbb{R}):XA+A^\top X=0 \}$ where $n:=p+q$ and $X=\begin{bmatrix}-I_{p}\\&I_{q}\end{bmatrix}$.
> 3. $\mathfrak{so}(p,q)=\mathfrak{sl}(p+q,\mathbb{R})\cap \mathfrak{o}(p,q)$.

> [!proof]-
> We have:
> 1. Let $\gamma:(-1,1)\to \text{O}(n,\mathbb{R})$ be a smooth curve with $\gamma(0)=I$. Then, $\gamma(s)\gamma(s)^\top=I$ for all $s$. Consider $\gamma\gamma^\top:s\mapsto \gamma(s)\gamma(s)^\top$ as a smooth curve. Then, $$(\gamma\gamma^\top)'(s)=\gamma'(s)\gamma(s)^\top+\gamma(s)(\gamma'(s))^\top$$from product rule. Therefore, $$0=\left. \frac{d}{dt} \right|_{t=0}\gamma\gamma^\top=(\gamma\gamma^\top)'(0)=\gamma'(0)+(\gamma'(0))^\top$$As $\text{O}(n,\mathbb{R})$ is a smooth manifold, we can find a smooth curve $\gamma:(-1,1)\to \text{O}(n,\mathbb{R})$ s.t. $\gamma(0)=I$ and $\gamma'(0)=v$ for any $v\in \text{T}_{I}\text{O}(n,\mathbb{R})=\mathfrak{o}(n,\mathbb{R})$. Therefore, $$\mathfrak{o}(n,\mathbb{R})\subseteq \{ A\in \text{Mat}_{n,n}(\mathbb{R}):A+A^\top=0 \}$$As the RHS has dimension $\frac{n(n-1)}{2}$ and so does $\text{O}(n,\mathbb{R})$ we have the desired equality.
> 2. Let $\gamma:(-1,1)\to \text{O}(p,q)$ be a smooth curve with $\gamma(0)=I$. Then, let $X:=\begin{bmatrix}-I_{p}&\\&I_{q}\end{bmatrix}$ and $\chi:(-1,1)\to \text{O}(p,q), t\mapsto \gamma(t)^\top X\gamma(t)$ is a smooth curve. Hence $\chi(t)=X$ for all $t$ and, $$0=\left. \frac{d}{dt} \right| _{t=0}\gamma(t)^\top X\gamma(t)=X\gamma'(0)+\gamma'(0)^\top X$$Therefore, $\mathfrak{o}(p,q)=\{ A\in \text{Mat}_{n,n}(\mathbb{R}):XA+A^\top X=0 \}$.
---
> [!h] Example 8 (Matrix Group Lie Algebra)
> Let $\text{UT}(n,\mathbb{R})$ be the upper unitriangular group and $\text{A}:=\{\text{diag}(\lambda_{1},\dots,\lambda_{n}):\lambda_{i}\in \mathbb{R}_{>0}  \}$. Then, 
> 1. $\mathfrak{ut}(n,\mathbb{R})=\left\{ A\in\text{Mat}_{n,n}(\mathbb{R}):A=\begin{bmatrix}0&&&*\\&0&\\&&\ddots\\&&&0\end{bmatrix}\right\}$
> 2. $\mathfrak{a}=\{ \text{diag}(x_{1},\dots,x_{n}):x_{i}\in \mathbb{R} \}$

> [!proof]-
> We have: 
> 1. Let $\gamma:(-1,1)\to \text{UT}(n,\mathbb{R})$ be a smooth curve with $\gamma(0)=I$. Then, let $p_{i,j}:\text{GL}(n,\mathbb{R})\to \mathbb{R}$ be a projection s.t. $p_{i,j}(A)\mapsto A_{i,j}$. $p_{i,j}$ is smooth and for $i\geq j$, $p_{i,j}(\gamma(t))$ is constant. Hence, $$0=\left. \frac{d}{dt} \right|_{t=0}p_{i,j}(\gamma(t))=\left. \frac{d}{dt} \right| _{t=0}p_{i,j}(I+t\gamma'(0))= d_{I}p_{ij}(\gamma'(0))=p_{ij}(\gamma'(0))$$Therefore, $\text{ut}(n,\mathbb{R})\subseteq RHS$. However, as $\text{dim}\ \text{UT}(n,\mathbb{R})=n(n-1) / 2$, the equation holds.
> 2. Similarly as above, we know that $\mathfrak{a}$ only has diagonal matrices. From the dimensions, we have the equality.
> 
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
