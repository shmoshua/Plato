#Definition #LieGroups 

> [!definition]
> A ***Lie group*** is a [[topological group]] $G$ endowed with a [[Smooth Manifold|smooth manifold structure]] s.t. 
> 1. the multiplication $m:G\times G\to G$ is smooth and
> 2. the inverse $i:G\to G$ is smooth.
- **Related defintion**: For Lie groups $G,H$, a ***Lie group homomorphism*** is a smooth group homomorphism $G\to H$. It is a ***Lie group isomorphism*** if it's bijective and the inverse is also a Lie group homomorphism. 
---
##### Properties
> [!lemma] Proposition 1
> For a Lie group $G$ and a subgroup $H\leq G$ that is also a [[submanifold|regular submanifold]], 
> 1. $H$ is a Lie group with smooth structure induced by $\{ (U\cap H,\varphi|_{U\cap H}) \}$.
> 2. $H$ is closed in this case.

> [!proof]-
> We have that $H\leq G$ and by [[Topological Group|Proposition 2.1]], $\overline{H}\leq G$. 
> 1. **Claim: every $p\in H$ has a neighborhood $V\subseteq G$ s.t. $H$ is closed in $V$, i.e. $H\cap V=\overline{H}\cap V$.**
> 	Fix $p\in H$. Let $(U,\varphi)$ be a chart at $p$. Then, $\varphi|_{H}:U\cap H\to \mathbb{R}^n$ is a chart of $p$ in $H$. Let $h:=\varphi \circ\varphi|_{H}^{-1}$. Let further $B:=B_{<1}(0)\subseteq \mathbb{R}^n$. Then, $h(B)$ is open in $\varphi(N)$ and there exists $W\subseteq \mathbb{R}^{m}$ open s.t. $W\cap \varphi(N)=h(B)$. As $\overline{B}$ is compact, $h(\overline{B})$ is compact and hence closed. Then, $$h(B)\subseteq W\cap h(\overline{B}) \subseteq W\cap\varphi(H)=h(B)$$Therefore, $W\cap h(\overline{B})=W\cap\varphi(H)$ and $V:=\varphi ^{-1}(W)\subseteq G$ is a neighborhood of $p$ s.t. $$V\cap H=V\cap\varphi ^{-1}(h(\overline{B}))$$which is closed.
> 2. For any $h\in H$, let $V\subseteq G$ be the neighborhood with $H\cap V=\overline{H}\cap V$. As $\overline{H}\leq G$, for any $x\in \overline{H}$, $Hx\cap Vx=\overline{H}\cap Vx$ which is contained in $Hx$ and open in $\overline{H}$. Therefore, $Hx$ is open and dense in $\overline{H}$.
> 3. Therefore, for any $x\in \overline{H}$, $Hx\cap H$ is non-empty. Therefore, $gx\in H$ for $g\in H$ and this shows that $x\in H$. One sees that $\overline{H}=H$.
---
> [!lemma] Theorem 2 (Cartan, Closed Subgroup Theorem)
> Let $G$ be a Lie group and $H\leq G$ a closed subgroup. Then, 
> 1. $H$ is a [[Submanifold|regular submanifold]] of $G$.
> 2. $H$ is a Lie group.

> [!proof]-
> Let $H\leq G$ be a closed subgroup. As $\mathfrak{g}$ is a vector space, we can define a norm $\|\cdot\|$ on $\mathfrak{g}$. Let $S^1:=\{ v\in \mathfrak{g}:\|v\|=1 \}$ and: $$\pi:\mathfrak{g} \backslash \{ 0 \}\to S^1,\quad v\mapsto v /\|v\|$$the projection map. We also define: $$W:=\{ 0 \}\cup \{ \xi\in \mathfrak{g} \backslash\{ 0 \}: \exists(v_{n})_{n\geq 1}\subseteq \mathfrak{g}\backslash\{ 0 \},\exp(v_{n})\in H,\lim_{ n \to \infty } v_{n}=0,\lim_{ n \to \infty } \pi(v_{n})=\pi(\xi) \}$$
> 1. **Showing $W$ is a cone**:
>    For $0\neq \xi\in W$ and $\lambda\geq 0$, $\pi(\xi)=\pi(\lambda \xi)$.
>  2. **Showing that $\exp(W)\subseteq H$**:
>     Firstly, $\exp(0)=e\in H$. Let $0\neq \xi\in W$ with $(v_{n})_{n\geq 1}$. Then, $\lim_{ n \to \infty } \frac{v_{n}}{\|v_{n}\|}= \frac{\xi}{\left\| \xi \right\|}$ and $$\lim_{ n \to \infty } \frac{\|\xi\|}{\left\| v_{n} \right\| }v_{n}=\xi$$Let $a_{n}:=\left[ \frac{\|\xi\|}{\|v_{n}\|} \right]$ be the integer part of $\|\xi\| / \|v_{n}\|$. Then, we claim that $\lim_{ n \to \infty }a_{n}v_{n}=\xi$. Indeed, $$\left\| \frac{\left\| \xi \right\|}{\left\| v_{n} \right\| }v_{n}-a_{n}v_{n}  \right\|=\left| \frac{\left\| \xi \right\|}{\left\| v_{n} \right\| }-a_{n}  \right|\left\| v_{n} \right\| \leq \left\| v_{n} \right\|   $$and $\lim_{ n \to \infty }\left\| v_{n} \right\|=0$. Therefore, $$\exp(\xi)=\lim_{ n \to \infty } \exp(a_{n}v_{n})=\lim_{ n \to \infty } (\exp(v_{n}))^{a_{n}}\in H$$
>  3. **Showing that $W$ is a vector subspace of $\mathfrak{g}$:**
> 	Let $\xi,\eta\in W$ s.t. $\xi,\eta,\xi+\eta$ are all non-zero. Then, by 1 and 2, we have:$$\exp(t\xi)\cdot \exp(t\eta)\in H,\quad \forall t\in \mathbb{R}$$As $\exp$ gives a local chart of $e$ (cf. [[Exponential Map|Proposition 2.2]]), there exists $I_{\delta}:=(-\delta,\delta)$ for $\delta>0$ and a smooth curve $\gamma:I_{\delta}\to \mathfrak{g}$ s.t. $\gamma(0)=0$ and $$\exp(\gamma(t))=\exp(t\xi)\exp(t\eta),\quad \forall t\in I_{\delta}$$Then, we get: $$\gamma'(0)=d_{0}\exp(\gamma'(0))=\left. \frac{d}{dt} \right| _{t=0}\exp(\gamma(t))=d_{0}\exp(\xi)+d_{0}\exp(\eta)=\xi+\eta$$by [[Exponential Map|Proposition 2.1]]. Now define $v_{n}:= \gamma\left( \frac{1}{n} \right)$ for $n\geq \frac{1}{\delta}$. Then, 
> 	- $\lim_{ n \to \infty }v_{n}=\lim_{ n \to \infty }\gamma\left( \frac{1}{n} \right)=\gamma(0)=0$.
> 	- $\lim_{ n \to \infty }nv_{n}=\lim_{ n \to \infty }n\gamma\left( \frac{1}{n} \right)=\lim_{ n \to \infty }\frac{\gamma\left( \frac{1}{n} \right)-\gamma(0)}{\frac{1}{n}-0}=\gamma'(0)=\xi+\eta\neq 0$. Therefore, there exists some $N\in \mathbb{N}$ s.t. $v_{n}\neq 0$ for all $n\geq N$.
> 	  
> 	Then,$$\lim_{ n \to \infty }\pi(v_{n})=\lim_{ n \to \infty }\frac{\gamma\left( \frac{1}{n} \right)}{\|\gamma\left( \frac{1}{n} \right)\|}\overset{ \text{L'Hopital} }{ = }\frac{\gamma'(0)}{\left\| \gamma'(0) \right\| }=\pi(\xi+\eta)$$Therefore, $\xi+\eta\in W$.
> 4. **Claim: There exists an open $U\ni 0$ in $\mathfrak{g}$ and a diffeomorphism $\Phi:U\to \Phi(U)$ where $\Phi(U)\subseteq G$ is open and $\Phi(0)=e$ s.t. $\Phi(U\cap W)=\Phi(U)\cap H$.**
>    Let $W'$ be the orthogonal complement of $W$ in $\mathfrak{g}$, i.e. $\mathfrak{g}=W\oplus W'$. Then, let $\text{pr}_{W},\text{pr}_{W'}$ be the projections of $\mathfrak{g}$ onto $W$ and $W'$. We claim that the map: $$\varphi:\mathfrak{g}\to G,\quad \xi\mapsto \exp \text{pr}_{W}(\xi)\exp \text{pr}_{W'}(\xi)$$has derivative $\text{id}_{\mathfrak{g}}$ at $\xi=0$. Indeed, $$d_{0}\varphi(v)=d_{0}\exp \text{pr}_{W}(v)+d_{0}\exp \text{pr}_{W'}(v)=\text{pr}_{W}(v)+\text{pr}_{W'}(v)=v$$Therefore, by [[Differential|Inverse Function Theorem]], there exists an open set $V\ni 0$ s.t. $\Phi=\varphi|_{V}$ is a diffeomorphism to its on image. Clearly $\Phi(0)=e$ and $\Phi(V\cap W)\subseteq \Phi(V)\cap H$.
>    
>    It is left to show that there exists $U$ s.t. $\Phi(U\cap W)=\Phi(U)\cap W$. Assume that there exists a sequence $(U_{n})_{n\geq 1}$ open subsets of $V$ s.t.
> 	1. $0\in U_{n}$,
> 	2. $U_{n}\subseteq U_{n-1}$
> 	3. $\Phi(U_{n}\cap W)\subsetneq \Phi(U_{n})\cap H$
> 	4. $\bigcap_{n\geq 1}^{}U_{n}=\{ 0 \}$
> 	
> 	From 3, we get for every $n\geq 1$ a vector $v_{n}+v_{n}'\in U_{n}$ s.t. $v_{n}\in W$, $v'_{n}\in W'$ and $v'_{n}\neq 0$. Further, $$\exp(v_{n})\exp(v_{n}')\in H$$hence $\exp(v'_{n})\in H$. As $S^1$ is compact, passing to a subsequence, we may assume that $$\xi:=\lim_{ n \to \infty } \pi(v'_{n})\in S^1$$exists. Since $v_{n}+v_{n}'\in U_{n}$ and $\bigcap_{n\geq 1}^{}U_{n}=\{ 0 \}$, we get that $\lim_{ n \to \infty }\|v'_{n}\|=0$. Therefore, $\xi\in W$. On the other hand, $$\xi=\lim_{ n \to \infty } \frac{v'_{n}}{\left\| v'_{n} \right\| }\in W'$$Therefore, $\xi\in W\cap W'=(0)$, which is a contradiction.
>   
- **Corollary**: For a Lie group $G$ and a closed subgroup $H\leq G$, $\mathfrak{h}=\{  v\in \mathfrak{g}: \exp_{G}(tv)\in H, \forall t\in \mathbb{R}\}$
---
> [!lemma] Proposition 3
> Let $\varphi:G_{1}\to G_{2}$ be a Lie group homomorphism. Then, for $H:=\text{ker }\varphi\leq G$, $$\mathfrak{h}=\text{ker }d_{e}\varphi$$

> [!proof]-
> We have by Corollary above,
> $$\begin{align}\mathfrak{h}&=\{ v\in \mathfrak{g}: \exp_{G_{1}}(tv)\in \text{ker }\varphi,\forall t\in \mathbb{R} \}\\&=\{ v\in \mathfrak{g}: \varphi(\exp_{G_{1}}(tv))=e,\forall t\in \mathbb{R} \}\\&=\{ v\in \mathfrak{g}: \exp_{G_{2}}(t\cdot d_{e}\varphi(v))=e,\forall t\in \mathbb{R} \}\\&=\{ v\in \mathfrak{g}: d_{e}\varphi(v)=0,\forall t\in \mathbb{R} \}\\&=\text{ker }d_{e}\varphi\end{align}$$
---
###### Connected Lie Group
> [!lemma] Theorem 1
> Let $G$ be a connected abelian Lie group with $n:=\text{dim }G$. Then, $$G\cong\mathbb{T}^a\times \mathbb{R}^{n-a}$$ as Lie groups for some $a$.

> [!proof]-
> We have:
> 1. Let $V$ be a finite dimensional $\mathbb{R}$-vector space and $\Gamma\leq V$ is a discrete subgroup. We claim that there exist $\gamma_{1},\dots,\gamma_{r}\in \Gamma$ linearly independent in $V$ s.t. $\Gamma=\mathbb{Z}\gamma_{1}+\dots+\mathbb{Z}\gamma_{r}$.
>    
>    We show this via induction over $n:=\text{dim}(V)$. Let $n=1$. Then, by [[Lattice|Example 1 proof]], a non-empty $\Gamma\leq V$ is dense or $\mathbb{Z}\gamma$ for $\gamma\in V$.
>    
>    Let $0\neq a\in \Gamma$. Then, $\Gamma \cap a\mathbb{R}$ is a discrete subgroup of dimension 1. Therefore, there exists $\gamma\in \Gamma \cap a\mathbb{R}$ s.t. $\Gamma \cap a\mathbb{R}=\mathbb{Z}\gamma$. Let $\Gamma'=p(\Gamma)$ where $p:\Gamma\to \Gamma / (\Gamma \cap a\mathbb{R})$. We have that, $\text{dim}(\Gamma')=n-1$. Therefore, there exists $a_{1},\dots,a_{\ell}\in \Gamma'$ with: $$\Gamma'=\mathbb{Z}a_{1}+\dots+\mathbb{Z}a_{\ell}$$Then, for $\gamma_{i}\in \Gamma$ s.t. $p(\gamma_{i})=a_{i}$, we have $\Gamma=\mathbb{Z}\gamma_{1}+\dots+\mathbb{Z}\gamma_{\ell}+\mathbb{Z}{\gamma_{\ell+1}}$ where $\gamma_{\ell+1}=\gamma$. For linear independence, if $\sum_{i=1}^{\ell+1}\xi_{i}\gamma_{i}=0$, $p\left( \sum_{i=1}^{\ell+1}\xi_{i}\gamma_{i} \right)=p\left( \sum_{i=1}^{\ell}\xi_{i}\gamma_{i} \right)=\sum_{i=1}^{\ell}\xi_{i}p(\gamma_{i})=0$. Therefore, $\xi_{i}=0$ and $\xi_{\ell+1}=0$. Further, similarly, we have the equality.
> 2. Let $G$ be an connected abelian group with dimension $n$. Then, $\exp:\mathfrak{g}\to G$ is a homomorphism of abelian groups: indeed, as $G$ is connected, by [[Topological Group|Lemma 2.4]] and [[Exponential Map|Proposition 2.2]], $\exp$ is surjective. Now, let $\Gamma:=\text{ker}\exp\leq \mathfrak{g}$. As $\exp$ forms a diffeomorphism in a neighborhood around $0$, we have that $\Gamma$ is discrete. Hence, by 1, $\Gamma=\mathbb{Z}\gamma_{1}+\dots+\mathbb{Z}\gamma_{r}$ for $\gamma_{i}\in \text{ker}\exp$ linearly independent. We can extend this to a basis of $\mathfrak{g}$ with $\gamma_{r+1},\dots,\gamma_{n}$. Then, $$G\cong \mathbb{R}^n / (\mathbb{Z}^r )\cong \mathbb{T}^r \times \mathbb{R}^{n-r}$$
---
> [!lemma] Theorem 2 (Lie, 1st)
> Let $G$ be a connected Lie group that is [[Solvable Group|solvable]]. Further, let $\rho:G\to \text{GL}(V)$ be a [[Lie group representation]] to a finite dimensional complex vector space $V$. Then, 
> 1. there exists a basis of $V$ s.t. $\rho(g)$ is upper triangular w.r.t. the basis for all $g\in G$.

> [!proof]+
> We continue with a proof by induction on $n:=\text{dim}(V)$. Then, by [[Weight|Theorem 3]], let $\chi:G\to \mathbb{C}^\times$ be the [[weight]] of $G$ in $V$. 
> 
> Consider $V / V_{\chi}$ and note that $\text{dim}(V / V_{\chi})<n$. We now define a representation $$\overline{\rho}:G\to \text{GL}(V / V_{\chi}),\quad g\mapsto(v+V_{\chi}\mapsto \rho(g)v+V_{\chi})$$This is well-defined as for $v+V_{\chi}=w+V_{\chi}$, $v-w\in V_{\chi}$ and: $$\overline{\rho}(g)(v+V_{\chi})=\rho(g)v+V_{\chi}=\rho(g)v+$$
> 
---
##### Examples
> [!h] Example 1
> A discrete group is a Lie group if and only if it is countable, in which case the dimension is $0$.

> [!proof]-
> If it is not countable, then it is not second countable.
---
> [!h] Example 2
> We have the following Lie groups:
> 1. $(\mathbb{R}^n,+)$
> 2. $(\mathbb{R}^\times,\cdot),(\mathbb{C}^\times,\cdot)$
> 3. $\text{GL}(n,\mathbb{R})$ is a $n^2$ dimensional Lie group with the multiplication as polynomial and inversion as rational.
> 4. $\text{GL}(n,\mathbb{C})$ is a $n^2$ dimensional Lie group with the multiplication as polynomial and inversion.
---
> [!h] Example 3
> $\text{Homeo}(X)$ is generally not a Lie group as it is not locally compact generally, but topological manifolds are.
---
> [!h] Example 4
> For a [[proper metric space]] $X$, 
> 1. $\text{Iso}(X)$ can be a Lie group but not always.
> 2. $\text{Iso}(\mathbb{R}^n)$ is a Lie group w.r.t. the euclidean distance.
> 3. $\text{Iso}(M)$ is a Lie group for a [[Riemannian manifold]] $M$.
---
> [!h] Example 5
> From [[Submanifold|Example 1]] and Proposition 1,
> 1. $\text{SL}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a Lie group.
> 2. $\text{O}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a Lie group.
> 3. $\text{O}(p,q,\mathbb{R})\leq \text{GL}(p+q,\mathbb{R})$ is a Lie group.
> 4. $\text{SL}(n,\mathbb{C})\leq \text{GL}(n,\mathbb{C})$ is a Lie group.
> 5. $\text{U}(n,\mathbb{C})\leq \text{GL}(n,\mathbb{C})$ is a Lie group.
---
