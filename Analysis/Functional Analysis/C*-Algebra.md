#Definition #FunctionalAnalysis 

> [!definition]
> An ***involutive Banach algebra*** is a [[Banach algebra]] $B$ with a map $x\mapsto x^{*}$ s.t. 
> 1. $(x^{*})^{*}=x$ for all $x\in B$,
> 2. $(\alpha x+\beta y)^{*}=\overline{\alpha} x^{*}+\overline{\beta} y^{*}$ for all $\alpha,\beta\in \mathbb{C}$, $x,y\in B$,
> 3. $(xy)^{*}=y^{*}x^{*}$ for all $x,y\in B$,
> 4. $\left\| x^{*} \right\|=\|x\|$ for $x\in B$.
>
> An involutive Banach algebra is a ***C\*-algebra***, if $\left\| xx^{*} \right\|=\|x\|\|x^{*}\|$ for all $x\in B$.
- **Related definition**: $x\in A$ is ***normal*** if $xx^{*}=x^{*}x$.
---
##### Properties
> [!lemma] Lemma 1
> Let $e$ be the unit in an involutive Banach algebra $B$. Then, $e=e^{*}$.

> [!proof]-
> Firstly, a unit is unique as $e=e e'=e'$ if $e\neq e'$ and both are units. Then, for all $x\in B$:$$xe^{*}=(ex^{*})^{*}=(x^{*})^{*}=x,\quad e^{*}x=(x^{*}e)^{*}=(x^{*})^{*}=x$$
> Therefore, $e=e^{*}$.
---
> [!lemma] Proposition 2
> Let $A$ be a $C^{*}$-algebra and $x\in A$ normal. Then, $$\|x\|=\|x\|_{\text{sp}}$$

> [!proof]-
> Let $x\in A$ be normal. Then, $$\left\| x^{2n} \right\| ^2=\left\| (x^{2n})^{*}(x^{2n}) \right\|=\left\| (x^{*}x)^{2n} \right\| =\left\| (x^{*}x)^n (x^{*}x)^n \right\| =\left\| (x^{*}x)^n \right\| ^{2} $$Therefore, $\left\| x^{2n} \right\|=\left\| (x^{*} x)^n \right\|$. It follows that $$\left\| x^{2^m} \right\| =\left\| (x^{*}x)^{2^{m-1}} \right\| =\left\| (x^{*}x)^{2^{m-2}} (x^{*}x)^{2^{m-2}} \right\| =\left\| (x^{2} x)^{2^{m-2}} \right\| ^{2}=\left\| x^{2^{m-1}} \right\|^{2} $$Indeed, it follows that $\left\| x^{2^m} \right\|=\|x\|^{2^m}$ and: $$\|x\|=\|x^{2^m}\|^{1 / 2^m}\to\|x\|_{\text{sp}}$$

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
> [!h] Example 4 (L1 and convolution)
> We have that:
> 1. $L^1(\mathbb{R})$ with [[convolution]] product is a commutative [[Banach algebra]].
> 2. $L^1(\mathbb{R})$ with $f^{*}(t)=f(-t)$ is involutive.
> 3. $L^1(\mathbb{R})$ with $f^{*}(t)=f(-t)$ is not a $C^{*}$-algebra.

> [!proof]-
> We know that:
> 1. $L^1(\mathbb{R})$ is a Banach space and $\left\| f*g \right\|_{1}\leq \left\| f \right\|_{1}\left\| g \right\|_{1}$ from [[Convolution|Theorem 2]].
> 2. One can easily check.
> 3. Consider the function: $$f(x)=\begin{cases}1&0<x\leq 1\\-1&-1\leq x<0\\0&\text{otherwise}\end{cases}$$Then, $f^{*}=-f$ and: 
$$\begin{align}f*f^{*}(x)&=\int_{-1}^{0} f(x-t) \, dt -\int_{0}^{1} f(x-t) \, dt \\&=-\int_{x-1}^{x} f(t) \, dt +\int_{x}^{x+1} f(t) \, dt\\&=\begin{cases}-x-2&-2<x<-1\\3x+2&-1\leq x<0\\-3x+2&0\leq x\leq 1\\ x-2&1<x<2\\0&\text{otherwise}\end{cases} \end{align}$$It follows that: $$\left\| f *f^{*}\right\|_{1}=\int_{\mathbb{R}}^{} \left| f*f^{*}(x) \right|  \, dx= \frac{8}{3}<4=\left\| f \right\| _{1}^{2}  $$

---
> [!h] Example 5
> Let $\Gamma$ be a (countable) [[group]]. Then, consider $$\ell^1(\Gamma):=\left\{  f:\Gamma\to \mathbb{C} \left|\left\| f \right\| _{1}:=\sum_{\gamma\in \Gamma}^{} \left| f(\gamma) \right| <+\infty\right.\right\}$$
> 1. $\ell^1(\Gamma)$ with convolution product $$(f*g)(\gamma)=\sum_{\eta\in \Gamma}^{}f(\gamma \eta)g(\eta ^{-1})$$is a [[Banach algebra]].
> 2. $\ell^1(\Gamma)$ with $f^{*}(\gamma)=\overline{f(\gamma ^{-1})}$ is involutive.

> [!proof]-
> We have that:
> Consider for $\alpha\in \Gamma$, $\delta_{\alpha}=\chi_{\{ \alpha \}}$. Then, $$(\delta_{\alpha}*\delta_{\beta})(\gamma)=\sum_{\eta\in \Gamma}^{}\delta_{\alpha}(\gamma \eta)\delta_{\beta}(\eta ^{-1})=1\iff\gamma=\alpha\beta$$and $\delta_{\alpha}*\delta_{\beta}=\delta_{\alpha\beta}$. As $\{ \delta_{\gamma}:\gamma\in \Gamma \}$ forms the basis of $\mathbb{C}[\Gamma]$, $\ell^1(\Gamma)$ is a $\mathbb{C}$-algebra. Then, $\ell^1(\Gamma)$ is a Banach space and:
> $$\begin{align}\left\| f*g \right\| _{1}&\leq\sum_{\eta\in \Gamma}^{}\sum_{\gamma\in \Gamma}^{}\left| f(\gamma \eta) \right|\left| g(\eta ^{-1}) \right|   =\left\| f \right\|_{1} \left\| g \right\|_{1}\end{align}$$
> The involutivity is easy to check.
---
**Other Examples**
1. [[Volterra Algebra]]
2. 
