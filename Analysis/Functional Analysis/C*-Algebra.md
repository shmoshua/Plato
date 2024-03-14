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
- **Related definition**: $x\in A$ is ***self-adjoint*** if $x=x^{*}$ and self-adjoint elements are trivially normal.
- **Related definition**: If $A$ is unital, $x\in A$ is ***unitary*** if $xx^{*}=x^{*}x=e$.
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
> [!lemma] Corollary 3
> If a $C^{*}$-algebra admits any other $C^{*}$-algebra norm $\|\cdot\|'$, then $\|\cdot\|=\|\cdot\|'$.

> [!proof]-
> We have that: $$(\|x\|')^{2}=\|x x^{*}\|'=\|x x^{*}\|_{\text{sp}}=\|x x^{*}\|=(\|x\|)^{2}$$
---
> [!lemma] Proposition 4
> Let $A$ be a non-unital $C^{*}$-algebra. Then, there is a $C^{*}$-algebra norm on $A_{I}$ extending the one on $A$.

> [!proof]-
> We will identify $A\to A_{I},x \mapsto (x,0)$ and with $e=(0,1)$, we will write $z\in A_{I}$ as $z=x+\lambda e$. Observe that $A$ is an ideal in $A_{I}$. Therefore, for:$$\begin{array}{cccc} {L_{z}:}&{A}&\to&{A}\\&{x} &\mapsto & {zx} \end{array}{}$$it holds that $L_{z}\in\mathcal{B}(A)$ and $A_{I}\to \mathcal{B}(A),z\mapsto L_{z}$ is a $\mathbb{C}$-algebra homomorphism. Now, let $N(z):=\|L_{z}\|$. Then, 
> 1. $N(z_{1}+z_{2})=\left\| L_{z_{1}+z_{2}} \right\|=\left\| L_{z_{1}}+L_{z_{2}} \right\|\leq \left\| L_{z_{1}} \right\|+\left\| L_{z_{2}} \right\|=N(z_{1})+N(z_{2})$
> 2. $N(z_{1}z_{2})=\left\| L_{z_{1}z_{2}} \right\|=\left\| L_{z_{1}}\circ L_{z_{2}} \right\|\leq \left\| L_{z_{1}} \right\|\left\| L_{z_{2}} \right\|$
> 3. $N(z)=\|L_{z}\|=\sup_{x\in A:\|x\|\leq 1}\left\| zx \right\|$
> 
> Then, we have: 
> 1. **Showing $N:A_{I}\to[0,+\infty)$ extends $\|\cdot\|$ on $A$**: 
>    For $z\in A$, $$N(z)=\sup_{\|x\|\leq 1}\|zx\|\leq\|z\|$$However, for $z\neq0$, $$\left\| L_{z}\left(  \frac{z^{*}}{\|z\|} \right) \right\| =\frac{\left\| zz^{*} \right\|}{\|z\|}=\frac{\|z\|^{2} }{\|z\|}=\|z\|$$Therefore, $N(z)=\|z\|$.
> 2. **Showing positive definiteness of $N$**:
> 	We assume that $z=x+\lambda e$ with $x\in A$ and $\lambda\neq 0$. Assume that $N(z)=0$. Then, $L_{z}(y)=zy=0$ for any $y\in A$ and $(x+\lambda e)y=0$, i.e. $y=(-x / \lambda)y$.
> 	
> 	Then, there exists $u\in A$ s.t. $y=u y$ for all $y\in A$ and $A$ has an identity $u$, which is a contradiction. Therefore, $z\in A$ and from $0=N(z)=\|z\|$, $z=0$.
>3. **Showing that the involution $x+\lambda e\mapsto x^{*}+\overline{\lambda}e$ satisfies the properties of an involutive Banach algebra**: For all $a\in A$
>	$$\left\| L_{z}(a) \right\| ^{2}=\|za\|^{2}=\|(za)^{*}za\|=\|a^{*}z^{*} z a\|\leq \|a\|\|L_{z^{*}z}(a)\|$$Then, $$\left(\frac{ \|L_{z}(a)\|}{\|a\|} \right)^{2} \leq\frac{\|L_{z^{*}z}(a)\|}{\|a\|}$$By taking all sup, $N(z)^{2}\leq N(z^{*}z)$. Therefore,
>	1. $N(z)^{2}\leq N(zz^{*})\leq N(z)N(z^{*})$ and $N(z)\leq N(z^{*})$ for all $z\in A_{I}$. Therefore, $N(z)=N(z^{*})$.
>	3. $N(zz^{*})\leq N(z)N(z^{*})=N(z)^{2}\leq N(zz^{*})$
>
>Therefore, $N$ is a $C^{*}$-algebra norm on $A_{I}$ extending $A$.
---
> [!lemma] Proposition 5
> Let $A$ be a unital $C^{*}$-algebra with identity $e$. 
> 1. If $u\in A$ is unitary, then $\text{Sp}_{A}(u)\subseteq \mathbb{T}:=\{ \xi\in \mathbb{C}:\left| \xi \right|=1 \}$.
> 2. If $h=h^{*}$, then $\text{Sp}_{A}(h)\subseteq \mathbb{R}$.

> [!proof]+
> Firstly, we have that: $$\|e\|=\|e e^{*}\|=\|e\|^{2}$$Therefore, $\|e\|=1$. Further, for any unitary $u\in A$, $$\|u\|^{2}=\|u u^{*}\|=\|e\|=1$$and $\|u\|=1$. 
> 
> Now, let $\lambda\notin \mathbb{T}$. 
> 1. If $\left| \lambda \right|<1$, $u-\lambda e=(e-\lambda u^{*})u$ and: $$\left\| \lambda u^{*} \right\| =\left| \lambda \right| \|u\|=\left| \lambda \right| <1$$Therefore, $e-\lambda u^{*}$ is invertible and $u-\lambda e$ is invertible. So $\lambda\notin \text{Sp}_{A}(u)$.
> 2. If $\left| \lambda \right|>1$, $u-\lambda e=\lambda\left( \frac{u}{\lambda}-e \right)$ and $\|\frac{u}{\lambda}\|= \frac{1}{\left| \lambda \right|}<1$. Therefore, $\frac{u}{\lambda}-e$ is invertible and $u-\lambda e$ is invertible. So $\lambda\notin \text{Sp}_{A}(u)$.
> 
> For self-adjoint $h\in A$, let $\lambda\in \text{Sp}_{A}(h)$. Then, $\lambda-\mu\in \text{Sp}_{A}(h-\mu e)$ as $$(h-\mu e)-(\lambda-\mu)e=h-\lambda e$$Let $\mu=iy$ for some $y\in \mathbb{R}$. Then, as $\left| \lambda-iy \right|\in \text{Sp}_{A}(h-iye)$, $$\begin{align}\left| \lambda-iy \right| ^{2}\leq \left\| h-iye \right\| _{\text{sp}}^{2}\leq \left\| h-iye \right\| ^2=\left\| (h-iye)^{*}(h-iye) \right\| =\left\| h^{2}+y^{2}e \right\| <\left\| h \right\| ^{2}+y^{2}\end{align}$$ 
---
##### Examples
> [!h] Example 0
> Let $A$ be an involutive Banach algebra. We have that $A_{I}$ is an involutive Banach algebra with$$(x,\lambda)^{*}:=(x^{*},\overline{\lambda})$$
---
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
