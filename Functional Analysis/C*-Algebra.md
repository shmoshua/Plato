#Definition #FunctionalAnalysis 

> [!definition]
> An ***involutive Banach algebra*** is a [[Banach Algebra]] $B$ with a map $x\mapsto x^{*}$ s.t. 
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
> Let $x\in A$ be normal. Then, $$\left\| x^{2n} \right\| ^2=\left\| (x^{2n})^{*}(x^{2n}) \right\|=\left\| (x^{*}x)^{2n} \right\| =\left\| (x^{*}x)^n (x^{*}x)^n \right\| =\left\| (x^{*}x)^n \right\| ^{2} $$Therefore, $\left\| x^{2n} \right\|=\left\| (x^{*} x)^n \right\|$. It follows that $$\left\| x^{2^m} \right\| =\left\| (x^{*}x)^{2^{m-1}} \right\| =\left\| (x^{*}x)^{2^{m-2}} (x^{*}x)^{2^{m-2}} \right\| =\left\| (x^{*} x)^{2^{m-2}} \right\| ^{2}=\left\| x^{2^{m-1}} \right\|^{2} $$Indeed, it follows that $\left\| x^{2^m} \right\|=\|x\|^{2^m}$ and: $$\|x\|=\|x^{2^m}\|^{1 / 2^m}\to\|x\|_{\text{sp}}$$
---
> [!lemma] Corollary 3
> If a $C^{*}$-algebra admits any other $C^{*}$-algebra norm $\|\cdot\|'$, then $\|\cdot\|=\|\cdot\|'$.

> [!proof]-
> We have that: $$(\|x\|')^{2}=\|x x^{*}\|'=\|x x^{*}\|_{\text{sp}}=\|x x^{*}\|=(\|x\|)^{2}$$
---
> [!lemma] Proposition 4
> Let $A$ be a non-unital $C^{*}$-algebra. Then, 
> 1. there is a $C^{*}$-algebra norm on $A_{I}$ extending the one on $A$.

> [!proof]-
> We will identify $A\to A_{I},x \mapsto (x,0)$ and with $e=(0,1)$, we will write $z\in A_{I}$ as $z=x+\lambda e$. Observe that $A$ is an ideal in $A_{I}$. Therefore, for $z\in A_{I}$: $$L_{z}:A\to A,\quad x\mapsto zx$$it holds that $L_{z}\in \mathcal{B}(A)$ and $A_{I}\to \mathcal{B}(A),z\mapsto L_{z}$ is an algebra homomorphism. Now, let $N(z):=\|L_{z}\|$. Then, 
> 1. $N(z_{1}+z_{2})=\left\| L_{z_{1}+z_{2}} \right\|=\left\| L_{z_{1}}+L_{z_{2}} \right\|\leq \left\| L_{z_{1}} \right\|+\left\| L_{z_{2}} \right\|=N(z_{1})+N(z_{2})$
> 2. $N(z_{1}z_{2})=\left\| L_{z_{1}z_{2}} \right\|=\left\| L_{z_{1}}\circ L_{z_{2}} \right\|\leq \left\| L_{z_{1}} \right\|\left\| L_{z_{2}} \right\|$
> 3. $N(z)=\|L_{z}\|=\sup_{x\in A:\|x\|\leq 1}\|zx \|$
> 
> Then, we have: 
> 1. **Showing $N:A_{I}\to[0,+\infty)$ extends $\|\cdot\|$ on $A$**: 
>    For $z\in A$, $N(z)=\sup_{\|x\|\leq 1}\|zx\|\leq\|z\|$. However, for $z\neq 0$, $$\left\| L_{z}\left( \frac{z^{*} }{\|z\|}\right)  \right\| =\frac{\left\| zz^{*} \right\| }{\|z\|}=\|z\|$$Therefore, $N(z)=\|z\|$.
> 2. **Showing positive definiteness of $N$**:
> 	We assume that $z=x+\lambda e$ with $x\in A$ and $\lambda\neq 0$. Assume that $N(z)=0$. Then, $L_{z}(y)=zy=0$ for any $y\in A$ and $(x+\lambda e)y=0$, i.e. $y=(-x / \lambda)y$.
> 	
> 	Then, there exists $u\in A$ s.t. $y=u y$ for all $y\in A$ and $A$ has a unit $u$, which is a contradiction. Therefore, $z\in A$ and from $0=N(z)=\|z\|$, $z=0$.
>3. **Showing that the involution $x+\lambda e\mapsto x^{*}+\overline{\lambda}e$ satisfies the properties of an involutive Banach algebra**: 
>   For all $a\in A$,
>	$$\left\| L_{z}(a) \right\| ^{2}=\|za\|^{2}=\|(za)^{*}za\|=\|a^{*}z^{*} z a\|\leq \|a\|\|L_{z^{*}z}(a)\|$$Then, $$\left(\frac{ \|L_{z}(a)\|}{\|a\|} \right)^{2} \leq\frac{\|L_{z^{*}z}(a)\|}{\|a\|}$$By taking all sup, $N(z)^{2}\leq N(z^{*}z)$. Therefore,
>	1. $N(z)^{2}\leq N(zz^{*})\leq N(z)N(z^{*})$ and $N(z)\leq N(z^{*})$ for all $z\in A_{I}$. Therefore, $N(z)=N(z^{*})$.
>	3. $N(zz^{*})\leq N(z)N(z^{*})=N(z)^{2}\leq N(zz^{*})$
>
>Therefore, $N$ is a $C^{*}$-algebra norm on $A_{I}$ extending $A$.
---
> [!lemma] Proposition 5
> Let $A$ be a $C^{*}$-algebra. 
> 1. If $A$ is unital and $u\in A$ is unitary, then $\text{Sp}_{A}(u)\subseteq \mathbb{T}:=\{ \xi\in \mathbb{C}:\left| \xi \right|=1 \}$.
> 2. If $h=h^{*}$, then $\text{Sp}_{A}(h)\subseteq \mathbb{R}$.

> [!proof]-
> We have:
> 1. Let $A$ be unital. Firstly, $\|e\|=\|ee^{*}\|=\|e\|^{2}$ and $\|e\|=1$.  Further, for any unitary $u\in A$, $$\|u\|^{2}=\|uu^{*}\|=\|e\|=1$$and $\|u\|=1$.
>    
>    Let $\lambda\notin \mathbb{T}$. 
> 	  1. if $\left| \lambda \right|<1$, then $u-\lambda e=(e-\lambda u^{*})u$ and: $\left\| \lambda u^{*} \right\| =\left| \lambda \right| \|u\|=\left| \lambda \right| <1$. Therefore, $e-\lambda u^{*}$ is invertible by [[Functional Analysis/Spectrum|Lemma 2]] and $u-\lambda e$ is invertible. Therefore, $\lambda\notin \text{Sp}_{A}(u)$.
> 	  2. if $\left| \lambda\right|>1$, then $u-\lambda e=\lambda(u / \lambda-e)$ and: $\left\| \frac{u}{\lambda} \right\| =\frac{1}{\left| \lambda \right| }<1$. Hence, $\frac{u}{\lambda}-e$ is invertible and $u-\lambda e$ is invertible. Therefore, $\lambda\notin \text{Sp}_{A}(u)$.
> 2. By definition, it suffices to show then $A$ is unital. Let $A$ be unital and $h=h^{*}$. Then, for $\lambda\in \text{Sp}_{A}(h)$, $\lambda-\mu\in \text{Sp}_{A}(h-\mu e)$. Indeed, $$(h-\mu e)-(\lambda-\mu)e=h-\lambda e$$Let $\mu=iy$ for some $y\in \mathbb{R}$. Then, $\lambda-iy\in \text{Sp}_{A}(h-iye)$ and: $$\left| \lambda-iy \right| ^{2}\leq \left\| h-iye \right\| ^{2}_{\text{sp}}\leq \left\| h-iye \right\| ^{2}=\left\| (h-iye)^{*}(h-iye) \right\| =\left\| h^{2}+y^{2}e \right\| \leq \left\| h \right\| ^{2}+y^{2}$$Let $\lambda=x_{0}+iy_{0}$. Then, $$\left\| h \right\| ^{2}+y^{2}\geq \left| \lambda-iy \right| ^{2}=\left| x_{0}+i(y_{0}-y) \right| ^{2}=x_{0}^{2}+y_{0}^{2}-2y_{0}y+y^{2}$$and $x_{0}^{2}+y_{0}^{2}-2y_{0}y\leq \left\| h \right\|^{2}$. By setting $y:=-y_{0}t$, $$x^{2}_{0}+y_{0}^{2}(1+2t)\leq \left\| h \right\| ^{2},\quad \forall t\in \mathbb{R}$$Therefore, $y_{0}=0$.
> 	
> 	
---
> [!lemma] Proposition 6
> Let $A,B$ be two commutative $C^{*}$-algebras. Then, TFAE:
> 1. $A\cong B$ as $\mathbb{C}$-algebras.
> 2. $\widehat{A}\cong \widehat{B}$ are homeomorphic.
> 3. $A\cong B$ as $C^{*}$-algebras. 

> [!proof]-
> We have:
> 1. (1=>2): Let $T:A\to B$ be a $\mathbb{C}$-algebra isomorphism. Then, as $C^{*}$-algebras are semisimple, by [[Jacobson Radical|Corollary 2]] both $T$ and $T^{-1}$ are continuous. Therefore, $$t:\widehat{B}\to \widehat{A},\quad \varphi\mapsto\varphi \circ T$$is a bijection. It remains to show that $t$ is continuous. 
>    
>    Let $\varphi_{0}\in \widehat{A}$, $a_{1},\dots,a_{n}\in A$ and $\varepsilon>0$. Then, for $\varphi\in \widehat{A}$: $$\left| \varphi_{0}(a_{i})-\varphi(a_{i}) \right| <\varepsilon \iff \left| (\varphi_{0}\circ T^{-1})(T(a_{i}))-(\varphi \circ T^{-1})(T(a_{i})) \right| <\varepsilon$$Therefore, $$t^{-1}(\mathcal{U}(\varphi_{0};a_{1},\dots,a_{n};\varepsilon))=\mathcal{U}(\varphi_{0}\circ T^{-1};T(a_{1}),\dots,T(a_{n});\varepsilon)$$which shows that $t$ is continuous. By symmetry, $t$ is a homeomorphism.
> 2. (2=>3): Let $t:\widehat{B}\to \widehat{A}$ be a homeomorphism. Then, we can define: $$\delta:C_{0}(\widehat{A})\to C_{0}(\widehat{B}),\quad f\mapsto f\circ t$$is an isometric $\mathbb{C}$-algebra isomorphism. Further, we have that: $$f^{*}(t(\varphi))=\overline{f(t(\varphi))}=(f\circ t)^{*}(\varphi)$$Hence, $\delta$ is a $C^{*}$-algebra isomorphism. We then define: $$T:A\to B,\quad x\mapsto \Delta_{B} ^{-1}(\delta(\widehat{x}))$$where $\Delta_{B}:B\to C_{0}(\widehat{B})$ is the Guelfand transform. Then, $T$ is a $C^{*}$-algebra isomorphism.
> 3. (3=>1): By definition.
---
> [!lemma] Proposition 7
> Let $e\in B\subseteq A$ be unital $C^{*}$-algebras. Then, 
> 1. $\text{Sp}_{B}(x)=\text{Sp}_{A}(x)$ for $x\in B$.

> [!proof]-
> Let $\lambda\in \text{Sp}_{A}(x)$. Then, $x-\lambda e$ is not invertible in $A$ and thereby not in $B$. Therefore, $\text{Sp}_{A}(x)\subseteq \text{Sp}_{B}(x)$.
> 
> Conversely, let $\lambda\notin \text{Sp}_{A}(x)$. 
> 1. if $x=x^{*}$, then $\text{Sp}_{B}(x)\subseteq \mathbb{R}$. Hence, if $\lambda\notin \mathbb{R}$, then $\lambda\notin \text{Sp}_{B}(x)$ and we are done. Assume that $\lambda\in \mathbb{R}$. Then, for all $\varepsilon>0$, $\lambda_{\varepsilon}:=\lambda+i\varepsilon\notin \text{Sp}_{B}(x)$. In other words, $(x-\lambda_{\varepsilon}e)^{-1}\in B$. 
>    
>    Since we have that $(x-\lambda e)^{-1}\in A$, $$[0,1]\to G(A),\quad \varepsilon \mapsto (x-\lambda_{\varepsilon}e)^{-1}$$is a continuous map. Therefore, $(x-\lambda e)^{-1}=\lim_{ \varepsilon \to 0^+ }(x-\lambda_{\varepsilon}e)^{-1}\in B$ as $B$ is closed from completeness. Therefore, $\lambda\notin \text{Sp}_{B}(x)$.
> 2. for a general $x\in B$, let $y:=x-\lambda e\in B$ which is invertible in $A$. Then, $y^{*}y\in B$ and $y^{*}y$ is invertible in $A$. Therefore, $0\notin \text{Sp}_{A}(y^{*}y)=\text{Sp}_{B}(y^{*}y)$ and it is invertible in $B$. Hence, there exists $z\in B$ with $z(y^{*}y)=e$. Similarly, there exists $w\in B$ s.t. $(yy^{*})w=e$. 
>    
>    By setting $a:=zy^{*}$ and $b:=y^{*}w$, we find that $ay=yb=e$. Therefore, $y^{-1}=a=b$ meaning that $y$ is invertible in $B$. Hence, $\lambda\notin \text{Sp}_{B}(x)$.     
---

> [!lemma] Theorem 8 (Pre-spectral Theorem)
> Let $A$ be a unital $C^{*}$-algebra and $x\in A$ normal. We define: $$B:=\overline{\{ P(x,x^{*}):P\in \mathbb{C}[X,Y] \}}\subseteq A$$with $x^0=e$. Then, 
> 1. $\widehat{x}:\widehat{B}\to \text{Sp}_{A}(x)$ is a homomorphism.
> 2. for every $f\in C(\text{Sp}_{A}(x))$ there exists a unique element denoted $f(x)\in B$ s.t. $$\widehat{f(x)}(\varphi)=f(\varphi(x)),\quad \forall \varphi\in \widehat{B}$$
> 3. The resulting map $C(\text{Sp}_{A}(x))\to B,\widehat{f}\mapsto f(x)$ is a $C^{*}$-algebra isomorphism with $1\mapsto e$ and $\text{id}\mapsto x$.
---
##### Examples
> [!h] Example 0
> Let $A$ be an involutive Banach algebra. We have that $A_{I}$ is an involutive Banach algebra with $$(x,\lambda)^{*}:=(x^{*},\overline{\lambda})$$
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
> 1. $L^1(\mathbb{R})$ with [[Convolution (Rn)]] product is a commutative [[Banach Algebra]].
> 2. $L^1(\mathbb{R})$ with $f^{*}(t)=f(-t)$ is involutive.
> 3. $L^1(\mathbb{R})$ with $f^{*}(t)=f(-t)$ is not a $C^{*}$-algebra.

> [!proof]-
> We know that:
> 1. $L^1(\mathbb{R})$ is a Banach space and $\left\| f*g \right\|_{1}\leq \left\| f \right\|_{1}\left\| g \right\|_{1}$ from [[Convolution (Rn)|Theorem 2]].
> 2. One can easily check.
> 3. Consider the function: $$f(x)=\begin{cases}1&0<x\leq 1\\-1&-1\leq x<0\\0&\text{otherwise}\end{cases}$$Then, $f^{*}=-f$ and: 
$$\begin{align}f*f^{*}(x)&=\int_{-1}^{0} f(x-t) \, dt -\int_{0}^{1} f(x-t) \, dt \\&=-\int_{x-1}^{x} f(t) \, dt +\int_{x}^{x+1} f(t) \, dt\\&=\begin{cases}-x-2&-2<x<-1\\3x+2&-1\leq x<0\\-3x+2&0\leq x\leq 1\\ x-2&1<x<2\\0&\text{otherwise}\end{cases} \end{align}$$It follows that: $$\left\| f *f^{*}\right\|_{1}=\int_{\mathbb{R}}^{} \left| f*f^{*}(x) \right|  \, dx= \frac{8}{3}<4=\left\| f \right\| _{1}^{2}  $$

---
> [!h] Example 5
> Let $\Gamma$ be a (countable) [[group]]. Then, consider $$\ell^1(\Gamma):=\left\{  f:\Gamma\to \mathbb{C} \left|\left\| f \right\| _{1}:=\sum_{\gamma\in \Gamma}^{} \left| f(\gamma) \right| <+\infty\right.\right\}$$
> 1. $\ell^1(\Gamma)$ with convolution product $$(f*g)(\gamma)=\sum_{\eta\in \Gamma}^{}f(\gamma \eta)g(\eta ^{-1})$$is a [[Banach Algebra]].
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
