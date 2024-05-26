#Definition #LieGroups 

> [!definition]
> Let $G$ be a [[topological group]] and $X$ a [[topological space]]. $X$ is a ***homogeneous space*** of $G$ if there exists a continuous [[Group Action|transitive group action]] $G\times X\to X$.
- **Related definition**: A subset $Y\subseteq X$ is ***$G$-invariant***  if for any $y\in Y$ and $g\in G$, $gy\in Y$.
- **Notation**: The [[Orbit and Stablizer|stabilizer]] $\text{Stab}_{G}(x)$ is also denoted as $G_{x}$.
---
##### Properties

> [!lemma] Proposition 1
> For a topological group $G$ and its homogeneous space $X$, 
> 1. for $x\in X$, the $G$-map: $$G/G_{x}\to X,\quad g\cdot G_{x}\mapsto gx$$is an isomorphism of $G$-spaces, i.e. it is a bijection that commutes with the action. ($G_{x}$ denotes the stabilizer $\text{Stab}_{G}(x):=\{ g\in G:gx=x \}$)
> 2. the $G$-map is continuous.
> 3. If $G$ is LCH and second countable and $X$ is LCH, then the bijection is a homeomorphism.

> [!proof]-
> We have:
> 1. Let $\Psi$ denote the map. Then, it is well-defined: for $g,h\in G$ with $g^{-1}h\in G_{x}$, $$hx=g g^{-1}hx=gx$$Then, it is injective as if $gx=hx$, then $g^{-1}hx=x$ and $g^{-1}h\in G_{x}$. Therefore, $gG_{x}=hG_{x}$. It is surjective as for any $y\in X$, there exists $g\in G$ s.t. $gx=y$ by transitivity of the group action.
>    
>    Lastly, it commutes with the $G$-action as: $$h\Psi(gG_{x})=hgx=\Psi(hgG_{x})$$
> 2. Consider $\Phi:G\to X,g\mapsto gx$, which is continuous as the group action is continuous. As $\Phi=\Psi \circ p$, $\Psi$ is continuous.
> 3. 
---
> [!lemma] Lemma 2
> Let $G$ be a topological group, $X$ a topological space and $\mu:G\times X\to X$ a continuous transitive group action. Then,
> 1. if $G$ is compact, then $X$ is compact.
> 2. if $G$ is connected, then $X$ is connected.

> [!proof]-
> Let $x\in X$. Then, from the transitivity, $\mu(G\times \{ x \})=X$. As $G\times \{ x \}$ is compact and connected if $G$ is compact and connected, $X$ is compact and connected.
> 
---
> [!lemma] Theorem 3 (Weil's Formula)
> Let $G$ be a LCH group with left Haar measure $\mu_{G}$. Let $H\leq G$ closed with left Haar measure $\mu_{H}$. Then, 
> 1. there exists a $G$-invariant regular Borel measure on $G / H$ if and only if $\Delta_{G}|_{H}=\Delta_{H}$.
> 2. in this case, $\mu_{G / H}$ is unique up to multiplication by positive scalars. 
> 3. there exists a unique $G$-invariant regular Borel measure $\mu_{G / H}$ s.t. $$\int_{G}f \, d\mu_{G}=\int_{G / H}^{} \int_{H}^{} f(gh) \, d\mu_{H}(h)  \, d\mu_{G / H}(gH),\quad \forall f\in C_{00}(G)  $$

> [!proof]-
> We will show that the formula is well-defined:
> 1. We have that given $g\in G$, $h\mapsto f(gh)$ is a continuous compactly supported function as $f\in C_{00}(G)$.
> 2. Let $T_{H}f(g):=\int_{H}^{} f(gh) \, d\mu_{H}(h)$. By [[Uniformly Continuous Function|Lemma 1]] and [[Summable Function|DCT]], $T_{H}f$ is continuous. Moreover, for any $v\in H$, we have: $$T_{H}f(gv)=\int_{H}^{} f(gvh) \, d\mu_{H}(h)=\int_{H}^{} f(gh) \, d\mu_{H}(h)=T_{H}f(g) $$Therefore, we can view $T_{H}f$ can be viewed as a continuous function from $G / H$. 
> 3. Lastly, if $p:G\to G / H$ the standard projection, $$\text{supp }T_{H}f\subseteq p(\text{supp }f)$$and as $p(\text{supp }f)$ is compact, $\text{supp }T_{H}f$ is compact and $T_{H}f\in C_{00}(G / H)$.
---
##### Examples
> [!h] Example 1
> Consider the action $\text{SO}(n+1,\mathbb{R})\curvearrowright S^n$. Then, 
> 1. this action is transitive.
> 2. for $e_{n+1}\in S^n$ unit vector, $$\text{SO}(n+1,\mathbb{R})_{e_{n+1}}=\{ g\in \text{SO}(n+1,\mathbb{R}):ge_{n+1}=e_{n+1} \}=\left\{ \begin{bmatrix}h&0\\0&1\end{bmatrix} :h\in \text{SO}(n,\mathbb{R})\right\}$$Therefore, $\text{SO}(n+1,\mathbb{R}) / \text{SO}(n,\mathbb{R})\cong S^n$.
---
> [!h] Example 2
> Let $\text{GO}_{k}:=\{ (v_{1},\dots,v_{k})\in (\mathbb{R}^n)^k:v_{1},\dots,v_{k}\text{ are orthonormal} \}$. Then, 
> 1. $\text{O}(n,\mathbb{R})\curvearrowright\text{GO}_{k}$ by multiplication is transitive.
> 2. If $k\leq n-1$, $\text{SO}(n,\mathbb{R})\curvearrowright \text{GO}_{k}$ is transitive.
> 3. For $(e_{1},\dots,e_{k})\in \text{GO}_{k}$, we have: $$\text{O}(n,\mathbb{R})_{(e_{1},\dots,e_{k})}=\left\{ \begin{bmatrix}\text{Id}_{k}&0\\0&h\end{bmatrix} :h\in \text{O}(n-k,\mathbb{R})\right\}$$Therefore, $\text{O}(n,\mathbb{R}) / \text{O}(n-k,\mathbb{R})\cong \text{GO}_{k}$.
---
> [!h] Example 3
> Let $\mathcal{R}$ be the set of [[Lattice|lattices]] on $\mathbb{R}^n$. Then, 
> 1. $\text{GL}(n,\mathbb{R})\curvearrowright \mathcal{R}$ as $\mathcal{R}:=\{ \mathbb{Z}f_{1}+\dots+\mathbb{Z}f_{n}:f_{1},\dots,f_{n}\in \mathbb{R}^n\text{ linearly independent} \}$ by [[Lattice|Example 1]].
> 2. For $\Gamma_{0}:=\mathbb{Z}e_{1}+\dots+\mathbb{Z}e_{n}$, $$\begin{align}\text{GL}(n,\mathbb{R})_{\Gamma_{0}}&=\{ g\in \text{GL}(n,\mathbb{R}):\mathbb{Z}g(e_{1})+\dots+\mathbb{Z}g(e_{n})=\mathbb{Z}e_{1}+\dots+\mathbb{Z}e_{n} \}\\&=\text{GL}(n,\mathbb{Z})\end{align}$$
>    Therefore, $\mathcal{R}\cong \text{GL}(n,\mathbb{R}) / \text{GL}(n,\mathbb{Z})$
---
