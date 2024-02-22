#Definition #FunctionalAnalysis 

> [!definition]
> An ***involutive Banach algebra*** is a [[Banach algebra]] $B$ with a map $x\mapsto x^{*}$ s.t. 
> 1. $(x^{*})^{*}=x$ for all $x\in B$,
> 2. $(\alpha x+\beta y)^{*}=\overline{\alpha} x^{*}+\overline{\beta} y^{*}$ for all $\alpha,\beta\in \mathbb{C}$, $x,y\in B$,
> 3. $(xy)^{*}=y^{*}x^{*}$ for all $x,y\in B$,
> 4. $\left\| x^{*} \right\|=\|x\|$ for $x\in B$.
>
> An involutive Banach algebra is a ***C\*-algebra***, if $\left\| xx^{*} \right\|=\|x\|\|x^{*}\|$ for all $x\in B$.
---
##### Properties
> [!lemma] Lemma 1
> Let $e$ be the unit in an involutive Banach algebra $B$. Then, $e=e^{*}$.

> [!proof]-
> Firstly, a unit is unique as $e=e e'=e'$ if $e\neq e'$ and both are units. Then, for all $x\in B$:$$xe^{*}=(ex^{*})^{*}=(x^{*})^{*}=x,\quad e^{*}x=(x^{*}e)^{*}=(x^{*})^{*}=x$$
> Therefore, $e=e^{*}$.
> 
---
##### Examples
> [!h] Example 1
> For a [[locally compact Hausdorff space]] $X$, Then, 
> 1. $C_{b}(X)$ is a Banach algebra
> 2. $C_{b}(X)$ is involutive with $f^{*}=\overline{f}$.
> 3. $C_{b}(X)$ is a $C^{*}$-algebra.

> [!proof]-
> We have that $(C_{b}(X),\|\cdot\|_{b})$ is a Banach space. Then, 
> 1. **Showing $C_{b}$ is a Banach algebra**: 
> 	$$\left\| fg \right\| _{b}=\sup_{x\in X}\left| f(x)g(x) \right| \leq\sup_{x\in X}\left| f(x) \right| \cdot \sup_{x\in X}\left| g(x) \right| =\left\| f \right\| _{b}\left\| g \right\| _{b}$$
> 2. **Showing $C_{b}$ is involutive**: obvious.
> 	
> 3. **Showing $C_{b}$ is C\*-algebra**:$$\left\| ff^{*} \right\|_{b}=\sup_{x\in X}\left| \overline{f(x)}f(x) \right| =\sup_{x\in X}\left| f(x) \right| ^{2}=\left\| f \right\| ^2_{b}=\left\| f^{*} \right\|_{b}\left\| f \right\|_{b} $$
---
> [!h] Example 2
> For a [[locally compact Hausdorff space]] $X$, Then, 
> 1. $C_{0}(X)$ is a C*-algebra.
> 2. $C_{0}(X)$ is [[C-Algebra|unital]], if and only if $X$ is compact.

> [!proof]-
> We have that $(C_{0}(X),\|\cdot\|_{b})$ is a Banach space. Then, 
> 1. **Showing $C_{0}$ is a C\*-algebra**: 
> 	Analogous to Example 1. 
> 2. **Showing $C_{0}(X)$ is unital if $X$ is compact**:
>    Let $f=1$. Then, $1\in C_{0}(X)$ and it is clearly a unit.
> 3. **Showing $X$ is compact if $C_{0}(X)$ is unital**:
> 	Assume $X$ is not compact but that we have a unit $f\in C_{0}(X)$. Then, $f=1$ as we can have a bump function in $C_{00}(X)\subseteq C_{0}(X)$ around any point. This is a contradiction to $f\in C_{0}(X)$. 
---
> [!h] Example 3
> For a [[Hilbert Space]] $\mathcal{H}$,  $\mathcal{B}(\mathcal{H})$ is a $C^{*}$-algebra with the [[Adjoint Linear Map|adjoint]].

> [!proof]-
> We have: 
> 1. $\mathcal{H}$ is a Banach algebra from [[Banach Algebra|Example 2]] and involutive from the adjoint properties.
> 2. We have: $$\left\| Tx \right\| ^{2}=\braket{ Tx , Tx } =\braket{ x , T^{*}Tx } \leq \left\| T^{*}T x\right\| \|x\|\leq \left\| T^{*} T\right\| \|x\|^{2}$$Therefore, $\left\| T \right\|^{2}\leq \left\| T^{*}T \right\|$. The other direction holds from the Banach algebra property.
---
> [!h] Example 4
> Let $\Gamma$ be a group. Then, $$\ell^1(\Gamma):=\left\{  f:\Gamma\to \mathbb{C} |\left\| f \right\| _{1}:=\sum_{\gamma\in \Gamma}^{} \left| f(\gamma) \right| <+\infty\right\}$$is Banach with the convolution: $$(f*g)(\gamma)=\sum_{\eta\in \Gamma}^{}f(\gamma \eta)g(\eta ^{-1})$$with $\left\| f*g \right\|_{1}\leq \left\| f \right\|_{1}\left\| g \right\|_{1}$ and 
> 1. $\delta_{\alpha}*\delta_{\beta}=\delta_{\alpha\beta}$ 
> 2. involution $f^{*}(\gamma)=\overline{f(\gamma ^{-1})}$
> 3. Therefore it is an involutive Banach algebra. 
---
> [!h] Example 5
> For $d>2$, let $T_{d}:=(V,E)$ be a $d$-regular tree. Then, we can define a distance $\delta:V\times V\to \mathbb{N}$. Let $K:V\times V\to \mathbb{C}$ be point-pair invariant, i.e. $K(v,w)$ only depends on $\delta(v,w)$, i.e. there exists $k:\mathbb{N}\to \mathbb{C}$ s.t. $$K(v,w)=k(\delta(v,w)),\quad v,w\in V$$
> If $\sum_{w\in V}^{}K(v,w)$ converges, then the value is independent of the vertex $v$. 
> 
> Let $L^1(V)^\natural:=\left\{  K:V\times V\to \mathbb{C}|K\text{ is point-pair invariant s.t. }\left\| K \right\|_{1}:=\sum_{w\in V}^{}\left| K(v,w) \right|<+\infty   \right\}$: $$(K_{1}*K_{2})(u,v)=\sum_{w\in W}^{}K_{1}(u,w)K_{2}(w,v)$$
> Then:
> 1. $K_{1}*K_{2}\in L^1(V)^{\natural}$ and $\left\| K_{1}*K_{2} \right\|_{1}\leq \left\| K_{1} \right\|_{1}\left\| K_{2} \right\|_{1}$ and
> 2. $K_{1}*K_{2}=K_{2}*K_{1}$
>    
> $g\in\text{Aut}(T_{d})$ is a bijection $g:V\to V$ preserving adjacency, i.e. $g$ is a isometry of $(V,\delta)$. 
> 
> There is no group $\Gamma$ s.t. $\ell^1(\Gamma)\cong L^1(V)^\natural$

> [!lemma]+
> Given $(v_{1},w_{1})$ and $(v_{2},w_{2})$ pairs of vertices, TFAE:
> 1. $\delta(v_{1},w_{2})=\delta(v_{2},w_{2})$ and
> 2. there exists $g\in \text{Aut}(T_{d})$ s.t. $g(v_{1})=v_{2}$ and $g(w_{1})=w_{2}$

> [!proof]+
> Let $S_{n}(v)$ denote the sphere of radius $n$ from $v$. However, for any $v\in V$, $\left| S_{n}(v) \right|=d(d-1)^{n-1}$. Then, $$\begin{align}\sum_{w\in V}^{}K(v,w)&=\sum_{w\in V}^{}k(\delta(v,w))=\sum_{n=0}^{\infty}\sum_{w\in S_{n}(v)}^{}k(n)=\sum_{n=0}^{\infty}\left| S_{n}(v) \right| \cdot k(n)=k(0)+\sum_{n=1}^{\infty}k(n)\cdot d(d-1)^{n-1}\end{align}$$
---
$\mathbb{H}^2:=\{ z\in \mathbb{C}: y>0 \}$ then $\text{SL}(2,\mathbb{R})$ acts on it. acts similarly. Given $(z_{1},z_{2})$ and $(w_{1},w_{2})$ with $d(z_{1},z_{2})=d(w_{1},w_{2})$, there exists $g\in \text{SL}(2,\mathbb{R})$ s.t. $g(z_{1})=w_{1}$ and $g(z_{2})=w_{2}$.
