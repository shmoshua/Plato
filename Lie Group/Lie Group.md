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
> 1. $H$ can be equipped with a unique smooth structure s.t. $H$ is a Lie subgroup of $G$.

> [!proof]-
> Let $H\leq G$ be a closed subgroup. Then, we can define: $$\mathfrak{h}:=\{ v\in \mathfrak{g}: \text{exp}(tv)\in H, \forall t\in \mathbb{R} \}$$We have that:
> 1. **$\mathfrak{h}$ is a linear subspace of $\mathfrak{g}$**:
>    Of course $\mathfrak{h}$ is closed under scalar multiplication. Under vector addition, $$H\ni \lim_{ n \to \infty }\left( \exp \left( \frac{tv}{n} \right) \exp \left( \frac{tw}{n} \right)  \right)^n= \lim_{ n \to \infty }\left( \exp \left( \frac{t(v+w)}{n} +O(1 / n^{2})\right)  \right)^n =\exp(t(v+w)) $$
> 2. **Lemma**: Let $(v_{n})_{n}\subseteq \mathfrak{g}$ be non-zero s.t. $v_{n}\to 0$. Further, let $\exp(v_{n})\in H$ and $$\lim_{ n \to \infty } \frac{v_{i}}{\left\| v_{i} \right\| }=:v\in \mathfrak{g}$$ Then, $v\in \mathfrak{h}$. 
>    
>    For any fixed $t\neq 0$, let $n_{i}:=\lfloor t / \|v_{i}\|\rfloor$. Then, $$\exp(tv)=\lim_{ i \to \infty } \exp(n_{i}v_{i})=\lim_{ i \to \infty } \exp(v_{i})^{n_{i}}\in H$$
> 
>   
- **Corollary**: For a Lie group $G$ and a closed subgroup $H\leq G$, $\mathfrak{h}=\{  v\in \mathfrak{g}: \exp_{G}(tv)\in H, \forall t\in \mathbb{R}\}$
---
> [!lemma] Proposition 3
> Let $\varphi:G\to H$ be a Lie group homomorphism. Then,
>1. $\text{Lie}(\text{ker }\varphi)=\text{ker }d_{e}\varphi$ 

> [!proof]+
> We have by Corollary above,
> $$\begin{align}\text{Lie}(\text{ker }\varphi)&=\{ v\in \mathfrak{g}: \exp_{G}(tv)\in \text{ker }\varphi,\forall t\in \mathbb{R} \}\\&=\{ v\in \mathfrak{g}: \varphi(\exp_{G}(tv))=e,\forall t\in \mathbb{R} \}\\&=\{ v\in \mathfrak{g}: \exp_{G}(t\cdot d_{e}\varphi(v))=e,\forall t\in \mathbb{R} \}\\&=\{ v\in \mathfrak{g}: d_{e}\varphi(v)=0,\forall t\in \mathbb{R} \}\\&=\text{ker }d_{e}\varphi\end{align}$$
---
> [!lemma] Theorem 4 (Quotient Manifold Theorem)
> Let $G$ be a Lie group acting smoothly, freely and properly on a smooth manifold $M$. Then, 
> 1. $M / G$ is a topological manifold with a unique smooth structure.
> 2. $\pi:M\to M / G$ is a smooth submersion.
- **Corollary**: For a Lie group $G$ and $H\leq G$ closed, $G / H$ is a topological manifold with a unique smooth structure. If $H\unlhd G$, then $G / H$ is a Lie group with Lie algebra $\mathfrak{g} / \mathfrak{h}$.
---
> [!lemma] Proposition 5
> Let $G,H$ be two Lie groups.
> 1. A Lie group homomorphism $\varphi:G\to H$ has constant rank.
> 1. Any continuous group homomorphism $\varphi:G\to H$ between two Lie groups is smooth. 

> [!proof]-
> We have:
> 1. For any $x\in G$, we have: $\varphi \circ L_{g}=L_{\varphi(g)}\circ\varphi$. Therefore, $$d_{g}\varphi \circ d_{e}L_{g}=d_{e}L_{\varphi(g)}\circ d_{e}\varphi$$As $L_{g},L_{\varphi(g)}$ are diffeomorphisms, $d_{e}L_{g}$ and $d_{e}L_{\varphi(g)}$ are bijections and hence $\varphi$ has constant rank.
> 2. We will define a graph map $\Gamma:G\to \text{graph}(\varphi),g\mapsto (g,\varphi(g))$.  Then, $\Gamma$ is continuous and $\Gamma ^{-1}=\text{pr}_{1}|_{\text{graph}(\varphi)}$ is also continuous. Therefore, $\Gamma$ is a homeomorphism. Hence, $\text{graph}(\varphi)$ is closed and by closed subgroup theorem, $\text{graph}(\varphi)$ is a Lie subgroup of $G\times H$. 
>    
>    Further, $\Gamma ^{-1}$ is a projection, hence a Lie group homomorphism. Therefore, by 1, $\Gamma ^{-1}$ has constant rank and by the [[Rank|global rank theorem]], $\Gamma$ is a diffeomorphism. Let $\text{pr}_{2}:\text{graph}(\varphi)\to H$ be the second projection, which is smooth. Then, $$\varphi=\text{pr}_{2}\circ \Gamma$$Therefore, $\varphi$ is smooth.
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
> Let $G$ be a [[Solvable Group|solvable]] connected Lie group. Further, let $\rho:G\to \text{GL}(V)$ be a [[Lie group representation]] to a finite dimensional complex vector space $V$. Then, 
> 1. there exists a basis of $V$ s.t. $\rho(g)$ is upper triangular w.r.t. the basis for all $g\in G$.

> [!proof]-
> We prove by induction on $n:=\text{dim}(V)$. 
> 1. If $n=1$, then the statement trivially holds.
> 2. if $n>1$, then by [[Weight|Theorem 3]], let $\chi:G\to \mathbb{C}^\times$ be the [[weight]] of $G$ in $V$. 
>    
>    Consider $V / V_{\chi}$ and note that $\text{dim}(V / V_{\chi})<n$. We now define a representation $$\overline{\rho}:G\to \text{GL}(V / V_{\chi}),\quad g\mapsto(v+V_{\chi}\mapsto \rho(g)v+V_{\chi})$$This is well-defined as for $v+V_{\chi}=w+V_{\chi}$, $v-w\in V_{\chi}$ and: $$\begin{align}\overline{\rho}(g)(v+V_{\chi})&=\rho(g)v+V_{\chi}=\rho(g)w+\rho(g)(v-w)+V_{\chi}=\rho(g)w+\chi(g)(v-w)+V_{\chi}\\& =\overline{\rho}(g)(w+V_{\chi})\end{align}$$Further, it is a representation as $$\overline{\rho}(gh)(v+V_{\chi})=\rho(gh)v+V_{\chi}=\rho(g)\rho(h)v+V_{\chi}=\overline{\rho}(g)(\rho(h)v+V_{\chi})=\overline{\rho}(g)\overline{\rho}(h)(v+V_{\chi})$$ Now, let $m:=\text{dim}V_{\chi}$ and $e_{1},\dots,e_{m}$ the basis of $V_{\chi}$. Further, let $e_{m+1},\dots,e_{n}\in V$ s.t. $e_{i}+V_{\chi}\in V / V_{\chi}$ form a basis of $V / V_{\chi}$ s.t. $\overline{\rho}(g)$ is upper triangular w.r.t. this basis for all $g\in G$.
> 
> 	I n other words, $$\overline{\rho}(g)\overline{e_{i}}=\chi_{i}(g)\overline{e_{i}}+\sum_{j=m+1}^{i-1}\overline{\rho}(g)_{ji}\overline{e_{j}},\quad \forall m+1\leq i\leq n$$where $\chi_{i}(g)$ is the diagonal elements. Therefore, $$\rho(g)e_{i}=\chi_{i}(g)e_{i}+\sum_{j=m+1}^{i-1}\overline{\rho}(g)_{ji}e_{j}\mod V_{\chi}$$It follows that $\rho(g)$ is upper triangular w.r.t. $e_{1},\dots,e_{n}$.
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
