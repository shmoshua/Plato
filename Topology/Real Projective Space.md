#Definition #Topology 

> [!definition]
> The ***real projective space*** $\mathbb{R}\mathbb{P}^n$ is given by $$\mathbb{R}\mathbb{P}^n:=(\mathbb{R}^{n+1}\backslash\{ 0 \} )/(\mathbb{R} \backslash \{ 0 \})$$given by the [[Group Action|action]] $\mathbb{R}\backslash\{ 0 \}\curvearrowright\mathbb{R}^{n+1}\backslash \{ 0 \}, (\lambda,x)\mapsto\lambda x$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\mathbb{R}\mathbb{P}^n$ is a [[Metric Space]] given by $S^n$.
> 2. $\mathbb{R}\mathbb{P}^n$ is a [[smooth manifold]] of dimension $n$ given by charts: $(U_{j},\varphi_{j})_{0\leq j\leq n}$ where: 
> 	- $U_{j}:=\pi(V_{j})$ where $V_{j}:=\{ x\in \mathbb{R}^{n+1} \backslash \{ 0 \}: x^j\neq 0 \}$ and
> 	$$\varphi_{j}:U_{j}\to \mathbb{R}^n,\quad \pi(x)\mapsto \frac{(x^0,\dots,\widehat{x^j},\dots,x^n)}{x^j}$$

> [!proof]-
> We will verify that they are charts.
> 1. Firstly for $x\in \mathbb{R}^{n+1} \backslash \{ 0 \}$, there exists $0\leq j\leq n$ s.t. $x^j\neq 0$. Therefore, $x\in V_{j}$ and $\pi(x)\in \pi(U_{j})$. 
> 2. We show that $\varphi_{j}$ is well-defined. For $y=\lambda x$ with $\pi(y)=\pi(x)\in U_{j}$, we have: $$\varphi_{j}(\pi(y))=\frac{\lambda(x^0,\dots,\widehat{x^j},\dots,x^n)}{\lambda x^j}=\frac{(x^0,\dots,\widehat{x^j},\dots,x^n)}{x^j}=\varphi_{j}(\pi(x))$$
> 3. $\varphi_{j}$ is a homeomorphism to an open set:  We have that: $$\varphi_{j}(U_{j})=\varphi_{j}(\pi(V_{j}))=\mathbb{R}^n$$Then, we first show the injectivity: if $\varphi_{j}(\pi(x))=\varphi_{j}(\pi(y))=(a^0,\dots,a^{n-1})$, then set: $$\tilde{a}:=(a^0,\dots,a^{j-1},1,a^j,\dots,a^{n-1})\in\mathbb{R}^{n+1}\backslash\{ 0 \}$$ and $\pi(x)=\pi(\tilde{a})$ as $x^j \tilde{a}=x$. The surjectivity is also given by $\tilde{a}$. To show that it is a homeomorphism, $a\mapsto \pi(\tilde{a})$ is continuous. Similarly, $\varphi_{j}$ is continuous as $\varphi_{j}\circ\pi$ is continuous. 
>  4. We finally show that the charts are smoothly compatible. For $0\leq j< k\leq n$, we have that for $a\in\varphi_{k}(U_{j}\cap U_{k})$: $$\begin{align}\varphi_{j}\varphi_{k}^{-1}(a^0,\dots,a^{n-1})&=\varphi_{j}(\pi(a^0,\dots,a^{k-1},1,a^k,\dots,a^{n-1}))\\&=\frac{(a^0,\dots,\widehat{a^j},\dots,a^{k-1},1,a^k,. ..,a^{n-1})}{a^j}\end{align}$$which is smooth.

---

> [!lemma] Theorem 1
> We have that: 
> 1. $\mathbb{R}\mathbb{P}^n \cong S^n / \{ \pm1 \}$ where $\{ \pm 1 \} \curvearrowright S^n,(\lambda,x)=\lambda x$.
> 2. $\mathbb{R}\mathbb{P}^n \cong B^n / {\sim}$ where $x\sim-x$ for all $x\in \partial B^n$.
> 3. For any point $x_{0}\in \mathbb{R}\mathbb{P}^{n}$, $\mathbb{R}\mathbb{P}^n \backslash \{ x_{0} \}\cong \mathbb{R}\mathbb{P}^{n-1}$.

> [!proof]-
> We have that:
> 1. Define: $$\psi:S^n / \{ \pm 1 \}\to \mathbb{R}\mathbb{P}^n,\quad x\mapsto \mathbb{R} \backslash \{ 0 \}\cdot x$$Then, $\psi$ is continuous and surjective. Further, for $\mathbb{R} \backslash \{ 0 \}\cdot x=\mathbb{R} \backslash \{ 0 \}y$, then, $x/y\in \mathbb{R} \backslash \{ 0 \}$ and as $\|x\| / \|y\| = 1$, we have that $x / y\in \{ \pm 1 \}$. This shows the injectivity. Hence, we conclude from the fact that $S^n / \{ \pm 1 \}$ is compact and $\mathbb{R}\mathbb{P}^n$ is Hausdorff. 
> 1. Define: $$\psi:B^n/ {\sim} \to \mathbb{R}\mathbb{P}^n,\quad [x_{1},\dots,x_{n}]\mapsto [x_{1},\dots,x_{n},\sqrt{ 1-\|x\|^{2} }]$$is continuous. Further, it is injective as if $[x_{1},\dots,x_{n},\sqrt{ 1-\|x\|^{2} }]=[y_{1}:\dots:y_{n}:\sqrt{ 1-\|y\|^{2} }]$, then $x_{i}=\lambda y_{i}$ and $$\sqrt{ 1-\|x\|^{2} }=\sqrt{ 1-\left| \lambda \right| ^{2}\|y\|^{2} }=\lambda\sqrt{ 1-\|y\|^{2} }$$so we have that $1-\left| \lambda \right|^{2}\|y\|^{2}=\lambda^{2}(1-\|y\|^{2})$ and $1=\lambda^{2}$. Hence, $\lambda=\pm 1$ and $\psi$ is injective. Plus, one can see that $\psi$ is surjective. 
>    
>    As $B^n / {\sim}$ is compact and $\mathbb{R}\mathbb{P}^n$ is Hausdorff, $\psi$ is a homeomorphism.
---

> [!lemma] Theorem 3 (Cellular Homology)
> We have that:
> 1. $\mathbb{R}\mathbb{P}^n$ is a $n$-dimensional [[CW-complex]].
> 2. The cellular homology with integer coefficients is given by: $$H^{\text{cw}}_{p}(\mathbb{R}\mathbb{P}^n)\cong \begin{cases}0&p=n, p\text{ even}\\\mathbb{Z}&p=n, p\text{ odd}\\0&0<p<n, p\text{ even}\\\mathbb{Z} / 2\mathbb{Z}&0<p<n, p\text{ odd}\\\mathbb{Z}&p=0\\0&p<0\text{ or }p>n\end{cases}$$
> 3. The cellular homology with coefficients $G$ is given by: $$H^{\text{cw}}_{p}(\mathbb{R}\mathbb{P}^n;G)\cong \begin{cases}K&p=n, p\text{ even}\\G&p=n, p\text{ odd}\\K&0<p<n, p\text{ even}\\G / 2G&0<p<n, p\text{ odd}\\G&p=0\\0&p<0\text{ or }p>n\end{cases}$$where $K:=\text{ker }(G\xrightarrow{\times2} G)$. 

^3af109

> [!proof]-
> We have: 
> 1. Let: $$f:B^n\to \mathbb{R}\mathbb{P}^n,\quad (x_{1},\dots,x_{n})\mapsto [x_{1}:\dots:x_{n}:\sqrt{ 1-\|x\|^{2} }]$$Then, for $x\in \partial B^n$, $$f(x)=[x_{1}:\dots: x_{n}: 0]\in \mathbb{R}\mathbb{P}^{n-1}$$Now, we show that $\mathbb{R}\mathbb{P}^n$ is a CW-complex. 
> 	 1. For $n=0$, $\mathbb{R}\mathbb{P}^0\cong P$ where $P$ is a one-point space, which is a CW-complex.
> 	 2. For $n\geq 1$, let $\mathbb{R}\mathbb{P}^{n-1}$ be a $n-1$ dimensional CW-complex with one cell in each dimension up to $n-1$. Then, we can attach $B^n$ using $f:(B^n,\partial B^n)\to(\mathbb{R}\mathbb{P}^{n},\mathbb{R}\mathbb{P}^{n-1})$. Hence, $\mathbb{R}\mathbb{P}^n$ is a $n$-dimensional CW-complex.
> 2. Let $\sigma_{k}\in I_{k}$ be the only $n$-cell for all $k\leq n$. Then, we find the degree of $p_{\sigma_{k-1}}\circ f_{\partial\sigma_{k}}$. We have that $(0,\dots,0,1)\in S^{k-1}$ has two points in the preimage, $N:=(0,\dots,0,1)$ and $S:=(0,\dots,0,-1)$. Hence, $\deg f|_{N}=1$ and $\deg f|_{S}=(-1)^{k}$. It follows that: $$[\sigma_{k-1}:\sigma_{k}]=1+(-1)^k=\begin{cases}0&k\text{ odd}\\2&k\text{ even}\end{cases}$$Hence, by setting $e_{i}$ as the $i$-cell, we have that $\partial(ge_{i})=(1+(-1)^i)e_{i-1}$. It follows that: $$Z_{i}:=\begin{cases}Ke_{i}&0< i \leq n, i\text{ even}\\Ge_{i}&0< i \leq n, i\text{ odd}\\G e_{0}&i=0\\0&\text{otherwise}\end{cases},\quad B_{i}:=\begin{cases}0&0\leq i < n, i\text{ even}\\2Ge_{i}&0\leq i < n, i\text{ odd}\\ 0&i=n\\0&\text{otherwise}\end{cases}$$Therefore, we have that: $$H_{p}^{\text{cw}}(\mathbb{R}\mathbb{P}^n;G)\cong  \begin{cases}K&p=n, n\text{ even}\\G&p=n, n\text{ odd}\\K&0<p<n, p\text{ even}\\G / 2G&0<p<n, p\text{ odd}\\G&p=0\\0&p<0\text{ or }p>n\end{cases}$$

^c79c2d

---
> [!lemma] Proposition 2
> The projection $S^n\to \mathbb{R} \mathbb{P}^n,x\mapsto \pi(x)$ is smooth.

> [!proof]-
> Let $p\in S^n$. Then, let wlog $p\in U_{j}^+$ from [[Sphere|Proposition 1]], we have that $\pi(p)\in U_{j}$ from above further, $\pi(U_{j}^+)\subseteq U_{j}$. Therefore, for any $x\in B_{<1}(0)\subseteq \mathbb{R}^n$,$$\begin{align}\varphi_{j}\pi(\varphi_{j}^+)^{-1}(x)&=\varphi_{j}\pi(x^1,\dots,x^{j-1},\sqrt{ 1-\|x\|^{2} },x^j,\dots,x^{n-1})\\&=\frac{x}{\sqrt{ 1-\|x\|^{2} }}\end{align}$$which is smooth.
---
> [!lemma] Proposition 3
> For $n\geq 2$, we have that:
> 1. $\pi_{1}(\mathbb{R}\mathbb{P}^n,*)\cong \mathbb{Z} / 2\mathbb{Z}$

---
##### Examples
> [!h] Example 1 (Cellular Homology with coefficients)
> We have that: 
> 1. with $G:= \mathbb{Z} / 2\mathbb{Z}$:$$H^{\text{cw}}_{p}(\mathbb{R}\mathbb{P}^n;\mathbb{Z} / 2\mathbb{Z})\cong \begin{cases}\mathbb{Z} / 2\mathbb{Z}&0\leq p\leq n\\0&\text{otherwise}\end{cases}$$
> 2. with $G:= \mathbb{R} , \mathbb{Q},\mathbb{C}$, we have that: $$H^{\text{cw}}_{p}(\mathbb{R}\mathbb{P}^n;G)\cong \begin{cases}G&p=n, p\text{ odd}\\G&p=0\\0&\text{otherwise}\end{cases}$$

^309c40

---

