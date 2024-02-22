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