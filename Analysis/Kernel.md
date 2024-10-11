#Definition #FunctionalAnalysis 

> [!definition]
> A ***kernel*** on a set $X$ is a function $K:X\times X\to \mathbb{R}$. A kernel is:
> 1. ***symmetric*** if $K(x,y)=K(y,x)$ for all $x,y\in X$
> 2. ***positive semidefinite*** if for all $n\geq 1$ and $(x_{1},\dots,x_{n})\in X^n$, the ***Gram matrix*** $[K(x_{i},x_{j})]_{i,j\in[n]}\in \mathbb{R}^{n,n}$ is positive semidefinite, i.e. for all $(c_{1},\dots,c_{n})\in\mathbb{R}^n$:$$\sum_{i,j=1}^{n}c_{i}c_{j}K(x_{i},x_{j})\geq 0$$
- **Remark**: A kernel $K$ ***reproduces*** a [[Hilbert space]] $\mathcal{H}$, if for all $x\in X$, $K(x,\cdot)\in \mathcal{H}$ and for every $h\in \mathcal{H}$, $$\braket{ f , K(x,\cdot ) } =f(x)$$
- **Remark**: for a positive semidefinite kernel $K$, $K(x,x)\geq 0$ for all $x\in X$ by taking $n=1$.
- **Remark**: Let $(X,d)$ be a [[Compact Space|compact metric space]], $\mu\in M^1(X)$ a [[Borel Measure|Borel-regular]] probability measure on $X$. Given a continuous kernel $K\in C(X\times X,\mathbb{R})$, the operator $T_{K}:L^2(X,\mu)\to L^2(X,\mu)$ given as: $$T_{K}f(x)=\int_{X}^{}K(x,y)f(y)  \, d\mu(y) $$is [[Hilbert-Schmidt Operator|Hilbert-Schmidt]] and [[Compact Operator|compact]], from [[Hilbert-Schmidt Operator|Proposition 6]]. In addition, if $K$ is symmetric, $T_{K}$ is [[Compact, Self-adjoint Operators|self-adjoint]] and the spectral theorem applies.
---
> [!lemma] Lemma 1
> Let $(X,d)$ be a [[Compact Space|compact metric space]], $\mu\in M^1(X)$ a [[Borel Measure|Borel-regular]] probability measure on $X$ s.t. $\text{supp }\mu=X$, i.e. for all non-empty open $U\subseteq X$, $\mu(U)>0$. Let $K\in C(X\times X,\mathbb{R})$ be a continuous symmetric kernel on $X$. Then, the following are equivalent:
> 1. $K$ is positive semidefinite.
> 2. it holds that: $$\int_{X}^{} \int_{X}^{} f(x)f(y)K(x,y) \, d\mu(x)  \, d\mu(y)\geq 0,\quad \forall f\in C(X) $$
> 3. $\braket{ T_{K}f ,f  }\geq 0$ for all $f\in L^2(X,\mu)$.

> [!proof]- Proof
> - (1 => 2): As the Dirac masses $\{ \delta_{x}: x\in X \}$ are the extreme points in $M^1(X)$ and by [[Extreme Points and Sets|Krein-Milman]], for any $\mu\in M^1(X)$ there exists $(\nu_{n})_{n}\subseteq M^1(X)$ where $\nu_{n}\to \mu$ in weak\*-topology and for all $n$,$$\nu_{n}:=\sum_{i=1}^{m}\lambda_{i}\delta _{x_{i}}$$is a convex combination of Dirac masses at $x_{1},\dots,x_{m}$. Then for all $f\in C(X)$, 
>   $$\int_{X}^{} \int_{X}^{} f(x)f(y)K(x,y) \, d\nu_{n}(x)  \, d\nu_{n}(y) =\sum_{i,j=1}^{m}f(x_{i})f(x_{j})K(x_{i},x_{j})\lambda_{i}\lambda_{j}\geq 0$$where we achieve the last inequality from the positive semidefiniteness and by  setting $c_{i}:=\lambda_{i}f(x_{i})$ for all $i\in[m]$. 
>   
>   Then, assume that $F(x,y)=\sum_{i,j=1}^{k}f_{i}(x)g_{j}(y)$ where $f_{i},g_{j}\in C(X)$. By Stone-Weierstrass, we know that the set of such functions is dense in $C(X\times X,\mathbb{R})$. However, $$\begin{align}\int_{X}^{} \int_{X}^{} F(x,y) \, d\nu_{n}(x)  \, d\nu_{n}(y)&=\int_{X}^{} \int_{X}^{} \sum_{i,j=1}^{k}f_{i}(x)g_{j}(y) \, d\nu_{n}(x)  \, d\nu_{n}(y)\\&=\sum_{i,j=1}^{k}\left(  \int_{X}^{} f_{i}(x)\, d\nu_{n}(x) \right)\left( \int_{X}^{}g_{j}(y)   \, d\nu_{n}(y)  \right) \\&\to \sum_{i,j=1}^{k}\left(  \int_{X}^{} f_{i}\, d\mu\right)\left( \int_{X}^{}g_{j}  \, d\mu \right) \\&=\int_{X}^{} \int_{X}^{} F(x,y) \, d\mu(x)  \, d\mu(y)\end{align}$$Therefore, 
>   $$\begin{align}\int_{X}^{} \int_{X}^{} f(x)f(y)K(x,y) \, d\mu(x)  \, d\mu(y)\geq 0\end{align}$$
>  - (2 => 3): We have: $$\begin{align}\int_{X}^{} \int_{X}^{} f(x)f(y)K(x,y) \, d\mu(x)  \, d\mu(y)&=\int_{X}^{} f(x) T_{K}f(x)\, d\mu(x)=\braket{ T_{K}f , f }   \geq 0\end{align}$$for all $f\in C(X)$. As $C(X)$ is dense in $L^2(X)$ and $T_{K}$ is a bounded operator, we have 3. 
>  - (3 => 1): Fix $c_{1},\dots,c_{n}\in \mathbb{R}$ and $x_{1},\dots,x_{n}\in X$. Let $\varepsilon>0$ and $U_{i}$ open set s.t. $$\left| K(x,y)-K(x_{i},x_{j}) \right| <\varepsilon,\quad \forall(x,y)\in U_{i}\times U_{j}$$Then, $\mu(U_{i})>0$ by hypothesis. Now, let: $$f=\sum_{i=1}^{n}c_{i} \frac{\chi_{U_{i}}}{\mu(U_{i})}$$Then, $$0\leq \braket{ T_{K}f , f } =\sum_{i,j=1}^{n}\frac{c_{i}c_{j}}{\mu(U_{i})\mu(U_{j})}\int_{U_{i}\times U_{j}}K(x,y)  \, d\mu \times \mu(x,y) $$From $\left| K(x,y)-K(x_{i},x_{j}) \right|<\varepsilon$ we get: $$\begin{align}\left| \braket{ T_{K}f , f } -\sum_{i,j=1}^{n}c_{i}c_{j}K(x_{i},x_{j}) \right| &=\left| \sum_{i,j=1}^{n}c_{i}c_{j}\left( K(x_{i},x_{j})-\frac{1}{\mu(U_{i})\mu(U_{j})}\int_{U_{i}\times U_{j}}K \, d\mu \times \mu  \right)  \right|\\ &\leq\sum_{i,j=1}^{n}\left| c_{i}c_{j} \right| \left| K(x_{i},x_{j})-\frac{1}{\mu(U_{i})\mu(U_{j})}\int_{U_{i}\times U_{j}}K \, d\mu \times \mu   \right| \\&<\varepsilon \left( \sum_{i=1}^{n}\left| c_{i} \right|  \right)^{2}\end{align}$$Therefore, it is positive.
---
> [!lemma] Theorem 3 (Mercer)
> Let $X$ be a [[Compact Space|compact metric space]], $\mu\in M^1(X)$ a [[Borel Measure|Borel-regular]] probability measure on $X$ s.t. $\text{supp }\mu=X$, i.e. for all non-empty open $U\subseteq X$, $\mu(U)>0$. Let $K\in C(X\times X,\mathbb{R})$ be a continuous symmetric positive semidefinite kernel on $X$. Then, 
> 1. there exists an orthonormal basis $\{ \varphi_{1},\varphi_{2},\dots \}\subseteq(\text{ker }T_{K})^{\bot}$ consisting of continuous eigenfunctions of $T_{K}$
> 2. for each eigenvalue $\lambda_{i}$ of $\varphi_{i}$, $\lambda_{i}> 0$ and
> 3. for any $x,y\in X$: $$K(x,y)=\sum_{n=1}^{\infty}\lambda_{n}\varphi_{n}(x)\varphi_{n}(y)$$as an absolutely and uniformly convergent sum.

> [!proof]-
> We have:
> 1. **Showing $T_{K}f$ is continuous**:
>    For $f\in L^2(X,\mu)$, $T_{K}f(x)=\int_{X}^{} K(x,y)f(y) \, d\mu(y)=\braket{ K_{x} , \overline{f} }$ is well-defined for every $x\in X$. We further show that $T_{K}f$ is continuous. 
> 	$$\begin{align}\left| T_{K}f(x_{1})-T_{K}f(x_{2}) \right|&\leq \int_{X}^{} \left| K(x_{1},y)-K(x_{2},y) \right| \left| f(y) \right|  \, d\mu(y)\\&\leq \left( \int_{X}^{} \left| K(x_{1},y)-K(x_{2},y) \right|^2  \, d\mu(y)  \right) ^{1/2}\left\| f \right\| _{2} \end{align} $$
>    Notice that $K:X\times X\to \mathbb{R}$ is continuous on the compact metric space $X\times X$ with distance e.g. $D((x_{1},y_{1}),(x_{2},y_{2}))=d(x_{1},x_{2})+d(y_{1},y_{2})$. Therefore, it is uniformly convergent, i.e. for all $\varepsilon>0$ there exists $\delta>0$ s.t. whenever $d(x_{1},x_{2})+d(y_{1},y_{2})<\delta$ then $\left| K(x_{1},y_{1})-K(x_{2},y_{2}) \right|<\varepsilon$. In particular, this means when $d(x_{1},x_{2})<\varepsilon$, $$\left| K(x_{1},y)-K(x_{2},y) \right| <\varepsilon$$Therefore, $$\begin{align}\left| T_{K}f(x_{1})-T_{K}f(x_{2}) \right|&\leq \varepsilon\|f\|_{2} \end{align} $$which shows that $T_{K}f$ is continuous. 
> 2. **Using Spectral theorem on $T_{K}$**:
>    Now, we can use the [[Compact, Self-adjoint Operators|spectral theorem]], let $f_{1},f_{2},\dots$ be the orthonormal basis of $(\text{ker }T_{K})^{\bot}$ of eigenvectors: $T_{K}f_{n}=\lambda_{n}f_{n}$. 
>    
>    As $K$ is symmetric positive semidefinite, $\braket{ T_{K}f , f }\geq 0$ for all $f\in L^2(X,\mu)$ from Lemma 1. In particular, $$\lambda_{n}=\braket{ T_{K}f_{n} , f_{n} }\geq 0 $$and since $f_{n}\notin \text{ker }T_{K}$, $\lambda_{n}>0$. 
> 3. **Constructing the continuous eigenfunctions $\varphi_{n}$**:
>    Now let's write $\varphi_{n}:=\frac{1}{\lambda_{n}}T_{K}f_{n}$. Then, $\varphi_{n}$ is continuous and $f_{n}=\varphi_{n}$. Therefore, there exists an orthonormal basis $\{\varphi_{1},\varphi_{2},\dots  \}\subseteq (\text{ker }T_{K})^{\bot}$.
> 4. **Showing $K_{n}$ is positive semidefinite**:
>    Let's define $K_{n}(x,y):=K(x,y)-\sum_{k=1}^{n}\lambda_{k}\varphi_{k}(x)\varphi_{k}(y)$. Then, $K_{n}$ is continuous and symmetric. We further show that $K_{n}$ is positive semidefinite. We have for any $f\in L^2(X,\mu)$: $$\begin{align}\braket{ T_{K_{n}} f,f  }&=\int_{X}^{} \int_{X}^{} f(x)f(y)K_{n}(x,y) \, d\mu(x)  \, d\mu(y)\\&=\int_{X}^{} \int_{X}^{} f(x)f(y)\left( K(x,y)-\sum_{k=1}^{n}\lambda_{k}\varphi_{k}(x)\varphi_{k}(y) \right)  \, d\mu(x)  \, d\mu(y) \\&=\braket{ T_{K}f , f } -\sum_{k=1}^{n}\lambda_{k}\int_{X}^{} \int_{X}^{} f(x)f(y)\left( \varphi_{k}(x)\varphi_{k}(y) \right)  \, d\mu(x)  \, d\mu(y)  \\&=\braket{ T_{K}f , f } -\sum_{k=1}^{n}\lambda_{k}\braket{ f , \varphi_{k} } ^{2}\end{align}$$
> 	Then, by projecting $f$, we have: $$\begin{align}f&=\rho_{(\text{ker }T_{K})^{\bot}}(f)+\rho_{\text{ker }T_{K}}(f)\\&=\sum_{k=1}^{\infty}\braket{ f , \varphi_{k} } \varphi_{k}+\rho_{\text{ker }T_{K}}(f)\end{align}$$It follows that $$\begin{align}\braket{ T_{K}f , f }&=\left\langle \sum_{k=1}^{\infty}\lambda_{k}\braket{ f , \varphi_{k} } \varphi_{k} +T_{K}\rho_{\text{ker }T_{K}}(f),\sum_{k=1}^{\infty}\braket{ f , \varphi_{k} } \varphi_{k}+\rho_{\text{ker }T_{K}}(f)\right\rangle\\&= \sum_{k=1}^{\infty}\lambda_{k}\braket{ f , \varphi_{k} } ^{2}+\braket{ T_{K}\rho_{\text{ker }T_{K}}(f),\rho_{\text{ker }T_{K}}(f) } \\&=\sum_{k=1}^{\infty}\lambda_{k}\braket{ f , \varphi_{k} } ^{2}\end{align} $$Therefore, $$\braket{ T_{K_{n}}f , f } =\braket{ T_{K}f , f } -\sum_{k=1}^{n}\lambda_{k}\braket{ f , \varphi_{k} } ^{2}=\sum_{k=n+1}^{\infty}\lambda_{k}\braket{ f , \varphi_{k} } ^{2}\geq 0$$From lemma 1, $K_{n}$ is positive semidefinite. In particular, $K_{n}(x,x)\geq 0$ for all $x\in X$. 
> 	
> 	
> 5. **Absolute and Uniform convergence in each variable**:
>    We have that, $$\sum_{k=1}^{n}\lambda_{k}\varphi_{k}(x)^{2}\leq K(x,x)$$for all $n\geq 1$ and is a convergent sequence (bounded and monotonous). Now, consider for $1\leq N\leq M$: $$\begin{align}\sum_{k=N}^{M}\lambda_{k}|\varphi_{k}(x)| |\varphi_{k}(y)|&\leq \left( \sum_{k=N}^{M}\lambda_{k}\varphi_{k}(x)^{2} \right) ^{1/2}\left( \sum_{k=N}^{M}\lambda_{k}\varphi_{k}(y)^{2} \right) ^{1/2}\\&\leq \left( \sum_{k=N}^{M}\lambda_{k}\varphi_{k}(x)^{2} \right) ^{1/2}K(y,y)^{1/2}\\&\leq \left( \sum_{k=N}^{M}\lambda_{k}\varphi_{k}(x)^{2} \right) ^{1/2}\|K\|_{b}^{1/2}\end{align}$$Then, for a fixed $x\in X$ and $\varepsilon>0$, there exists $Q\geq 1$ s.t. for all $M\geq N\geq Q$: $$\sum_{k=N}^{M}\lambda_{k}\varphi_{k}(x)^{2}<\varepsilon$$and therefore, $$\begin{align}\sum_{k=N}^{M}\lambda_{k}|\varphi_{k}(x)| |\varphi_{k}(y)|\leq \varepsilon^{1/2}\|K\|_{b}^{1/2}\end{align}$$and $\sum_{k=1}^{\infty}\lambda_{k}\varphi_{k}(x)\varphi_{k}(y)$ converges absolutely and uniformly in $y\in X$, for all $x\in X$. By symmetry, it also converges absolutely and uniformly in $x\in X$, for all $y\in X$.
> 	
> 	Let $G(x,y):=\sum_{k=1}^{\infty}\lambda_{k}\varphi_{k}(x)\varphi_{k}(y)$. Then, for every $x$, $G(x,\cdot)$ is continuous and for every $y$, $G(\cdot,y)$ is continuous. 
> 	
> 	 Further let $K_{x}(y):=K(x,y)$ and let $\psi_{1},\psi_{2},\dots$ be an orthonormal basis or $\text{ker }T_{K}$. Then, $$\begin{align}K_{x}&=\sum_{k=1}^{\infty}\braket{ K_{x} , \varphi_{k} } \varphi_{k}+\sum_{k=1}^{\infty}\braket{ K_{x} , \psi_{k} } \psi_{k}\\&=\sum_{k=1}^{\infty}T_{K}\varphi_{k}(x)\varphi_{k}+\sum_{k=1}^{\infty}T_{K}\psi_{k} (x)\psi_{k}\\&=\sum_{k=1}^{\infty}\lambda_{k}\varphi_{k}(x)\varphi_{k}\end{align}$$Hence, $K_{x}=\lim_{ n \to \infty }\sum_{k=1}^{n}\lambda_{k}\varphi_{k}(x)\varphi_{k}$ in $L^2(X,\mu)$. In particular there exists $(n_{\ell})_{\ell}$ s.t. $$\lim_{ \ell \to \infty } \sum_{k=1}^{n_{\ell}}\lambda_{k}\varphi_{k}(x)\varphi_{k}(y)=K_{x}(y)=K(x,y)$$ for almost every $y\in X$. Hence, for all $x\in X$, $G(x,y)=K(x,y)$ for $y\in X$ $\mu$-a.e. Now for fixed $x$, $G_{x}:=\sum_{k=1}^{\infty}\lambda_{k}\varphi_{k}(x)\varphi_{k}$ is continuous. Further, $K_{x}$ is continuous. Therefore, $$\{ y\in X:G(x,y)\neq K(x,y) \}$$is an open set of measure zero, i.e. is empty. This shows that $G(x,y)=K(x,y)$ for all $x,y\in X$. 
> 4. Finally, we show that the sum is absolutely and uniformly convergent. We start by showing $$\sum_{k=1}^{n}\lambda_{k}\varphi_{k}(x)^{2}$$ converges uniformly to $K(x,x)$. For $\varepsilon>0$ and $n\geq 1$, let's define: $$V^\varepsilon_{n}=\left\{  x\in X:\sum_{k=1}^{n}\lambda_{k}\varphi_{k}(x)^{2}>K(x,x)-\varepsilon  \right\}$$which is an open set. Further, $V^{\varepsilon}_{n}\subseteq V^{\varepsilon}_{n+1}$ for all $n$. Indeed, as for all $x\in X$, $\sum_{k=1}^{n}\lambda_{k}\varphi_{k}(x)^{2}\to K(x,x)$, $$\bigcup_{n\geq 1}^{}V^\varepsilon_{n}=X$$However, as $X$ is compact, there exists $n_{1},\dots,n_{\ell}$ s.t. $$\bigcup_{i=1}^{\ell}V^{\varepsilon}_{n_{i}}=X$$Then, now let $m:=\max(n_{1},\dots,n_{\ell})$ and we have $V_{m}^{\varepsilon}=X$. In other words, for any $\varepsilon>0$, there exists $m\geq 1$ s.t. for all $x\in X$: $$K(x,x)-\sum_{k=1}^{m}\lambda_{k}\varphi_{k}(x)^{2}<\varepsilon$$which shows the uniform convergence. Lastly, from the inequality above, $$\sum_{k=N}^{M}\lambda_{k}\left| \varphi_{k}(x) \right| \left| \varphi_{k}(y) \right|\leq \left( \sum_{k=N}^{M}\lambda_{k}\varphi_{k}(x)^{2} \right) ^{1/2}\left( \sum_{k=N}^{M}\lambda_{k}\varphi_{k}(y)^{2} \right) ^{1/2}$$Since $\sum_{k=1}^{\infty}\lambda_{k}\varphi_{k}(x)^{2}$ is uniformly convergent, we have that $\sum_{n=1}^{\infty}\lambda_{n}\varphi_{n}(x)\varphi_{n}(y)$ is also absolutely and uniformly convergent. 
---
> [!lemma] Lemma 4 (Kernel Composition)
> Let $k_{1},k_{2}:X\times X\to \mathbb{R}$ be SPsD kernels. Then, the following are SPsD kernels.
> 1. $k(x,x'):=k_{1}(x,x')+k_{2}(x,x')$
> 2. $k(x,x'):=k_{1}(x,x')\cdot k_{2}(x,x')$
> 3. $k(x,x'):=c\cdot k_{1}(x,x')$
> 4. $k(x,x'):=f(x)k_{1}(x,x')f(x')$ for any function $f:X\to \mathbb{R}$. 
> 5. $k(x,x'):=p(k_{1}(x,x'))$ where $p\in \mathbb{R}[x]$ with non-negative coefficients.
> 6. $k(x,x'):=\exp (k_{1}(x,x'))$. 
> 7. $k(x,x'):=k_{3}(\phi(x),\phi(x'))$ where $\phi:X\to \mathbb{R}^d$ and $k_{3}:\mathbb{R}^d\times \mathbb{R}^d\to \mathbb{R}$ SPsD kernel.

> [!proof]+
> We have that:
> 1. Obvious.
> 2. Let $x_{1},\dots,x_{n}\in X$ and consider $K_{1},K_{2}\in \text{Mat}_{n,n}(\mathbb{R})$ as the gram matrix given by $x_{1},\dots,x_{n}$ with $k_{1},k_{2}$ respectively. Then, for the Kronecker product we have that: $$K:=K_{1}$$
>    
>    Symmetry is clear. For positive semidefiniteness, for $x_{1},\dots,x_{n}$ and $c_{1},\dots,c_{n}$: $$\sum_{i,j=1}^{n}c_{i}c_{j}k_{1}(x_{i},x_{j})k_{2}(x_{i},x_{j})=\left( \sum_{i,j=}^{} \right) $$
---
##### Examples
> [!h] Example 1 (Hilbert Space Kernels)
> Let $\mathcal{H}$ be a $\mathbb{R}$-[[Hilbert Space|Hilbert space]] and $\varphi:X\to \mathcal{H}$ any map. Then, 
> 1. $K(x,y):=\braket{ \varphi(x) , \varphi(y) }$ is a symmetric positive semidefinite kernel.
> 2. $K(x,y):=x^\top y$ is called the linear kernel.
> 3. $K(x,y):=x^2y^2+xy+1$ is also a kernel with $\varphi:\mathbb{R}\to \mathbb{R}^3,x\mapsto (1,x,x^{2})$.

> [!proof]-
> We have: 
> 1. for symmetry: $$K(x,y)=\braket{ \varphi(x) , \varphi(y) } =\braket{ \varphi(y) , \varphi(x) } =K(y,x)$$
> 2. for positive semidefiniteness:
> 	$$\sum_{i,j=1}^{n}c_{i}c_{j}\braket{ \varphi(x_{i}) , \varphi(x_{j}) }=\sum_{i,j=1}^{n}\braket{ c_{i}\varphi(x_{i}) , c_{j}\varphi(x_{j}) } =\left\| \sum_{i=1}^{n}c_{i}\varphi(x_{i}) \right\| ^2\geq 0$$
---
> [!h] Example 2 (RBF/Gaussian Kernel)
> Let $X$ be an [[inner product space]]. Then, 
> 1. $K_{\text{Gaus},h}(x,y):=\exp \left( -\left\| x-y \right\|^2/h^{2} \right)$ is a SPsD kernel called ***RBF/Gaussian kernel*** with $h$.
> 2. The RBF kernel is analytic. 

> [!proof]-
> We have:
> 1. Symmetry follows from that of the distance. For positive semi-definiteness, we have:  $$\left\| x-y \right\| ^{2}=\braket{ x-y , x-y } =\|x\|^{2}+\|y\|^{2}-2\braket{ x , y } $$Hence, $\exp\left( -\frac{\left\| x-y \right\| ^2}{h^{2}} \right)=\exp \left( -\frac{\|x\|^{2}}{h^{2}} \right)\exp \left( \frac{2\braket{ x , y }}{h^{2}} \right)\exp \left( -\frac{\|y\|^{2}}{h^{2}} \right)$. Then, the positive semidefiniteness follows from the fact that $(x,y)\mapsto \braket{ x , y }^k$ is positive semidefinite for all $k$.
---
> [!h] Example 3 (Exponential Kernel)
> Let $X$ be an [[inner product space]]. Then, 
> 1. $K_{\text{Laplace},h}(x,y):=\exp \left( -\left\| x-y \right\|/h \right)$ is a SPsD kernel called ***exponential/Laplace kernel*** with $h$.
> 2. The exponential kernel is not differentiable. 
---
> [!h] Example 4 (Matérn Kernel)
> Let $X$ be an inner product space and $v,h>0$. Then, 
> $$K_{v,h}(x,y)=\frac{2^{1-v}}{\Gamma(v)}\left( \frac{\sqrt{ 2 }}{h}\left\| x-y \right\| _{2} \right)^v \text{K}_{v}\left(\frac{\sqrt{ 2 }}{h}\left\| x-y \right\| _{2}  \right)  $$where $\Gamma$ is the [[gamma function]] and $\text{K}_{v}$ is the [[modified Bessel function of the second kind]], is a SPsD kernel called ***Matérn kernel***.
> 1. $K_{1 / 2,h}=K_{\text{Laplace}, h}$, i.e. the exponential kernel is Matérn kernel with $v = 1/2$.