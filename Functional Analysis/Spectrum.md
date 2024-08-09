#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a unital [[C-Algebra|$\mathbb{C}$-algebra]] and $x\in A$. Then, the ***spectrum*** of $x$ is:
> $$\text{Sp}_{A}(x):=\{ \lambda\in \mathbb{C}:x-\lambda e\notin G(A) \}$$
> If $A$ is non-unital, we define: $$\text{Sp}_{A}(x):=\text{Sp}_{A_{I}}(x)$$
- **Related definition**: The complement of a spectrum $\rho_{A}(x):=\mathbb{C} \backslash \text{Sp}_{A}(x)$ is called the ***resolvent set***.
- **Related definition**: In a [[Banach Algebra|Banach algebra]], for $x\in A$, define $r_{A}(x):=\inf_{n\geq 1}\left\| x^n \right\|^{1/n}$.
- **Related definition**: In a [[Banach Algebra|Banach algebra]], for $x\in A$, the ***spectral radius*** is defined as:$$\|x\|_{\text{sp}}:=\max\{ \left| \lambda \right| :\lambda\in \text{Sp}_{A}(x) \}$$where the existence of the maximum is given by Theorem 4.
---
##### Properties
> [!lemma] Proposition 1 
> Let $A$ be a [[Banach Algebra|Banach algebra]]. For $x\in A$, we have that:
> 1. $r_{A}(x)\leq \|x\|$.
> 2. $r_{A}(x)=\lim_{ n \to \infty }\left\| x^n \right\|^{1/n}$ which is well-defined.

> [!proof]-
> We have:
> 1. By Banach algebra, $\|x^n\|\leq\|x\|^n$. Therefore, $\|x^n\|^{1/n}\leq\|x\|$. 
> 2. This holds for any general function $f:\mathbb{N}^*\to \mathbb{R}_{\geq0}$ s.t. $f(n+m)\leq f(n)f(m)$. If $f(1)=0$, then $f(n)=0$ for all $n\geq 1$ and the statement trivially holds. Therefore, assume that $f(1)>0$. 
>    
>    Let $$r:=\inf_{n\geq 1}f(n)^{1/n}$$Let further $\varepsilon>0$ and pick $k\geq 1$ s.t. $f(k)^{1/k}<r+\varepsilon$. Then, for $n\geq k$, by writing $n=ak+b$, we have $a\geq 1$ and $0\leq b\leq k-1$. Then, $$f(n)=f(ak+b)\leq f(k)^af(1)^b$$Therefore, $$f(n)^{1/n}\leq f(k)^{a/n}f(1)^{b/n}=(f(k)^{1/k})^{ak/n}f(1)^{b/n}=(f(k)^{1/k})^{1-b/n}f(1)^{b/n}\to f(k)^{1/k}$$Hence,$$r\leq \liminf_{ n \to \infty } f(n)^{1/n}\leq\limsup_{ n \to \infty } f(n)^{1/n}\leq f(k)^{1/k}<r+\varepsilon$$
---
> [!lemma] Lemma 2
> Let $A$ be a unital [[Banach Algebra|Banach algebra]] and $x\in A$ with $r_{A}(x)<1$. Then, 
> 1. $e-x$ is invertible and
> 2. $(e-x)^{-1}=\sum_{n=0}^{\infty}x^n$ where $x^0=e$, as an absolutely convergent series.

> [!proof]-
> We have: 
> 1. **Showing the series is absolutely convergent**: 
>    Pick $r_{A}(x)<q<1$. Then, as $r_{A}(x)=\lim_{ n \to \infty }\|x^n\|^{1/n}$, there exists $N\geq 1$ such that $\|x^n\|^{1/n}\leq q$ for all $n\geq N$, i.e. $\|x^n\|\leq q^n$. Therefore, $$\sum_{n=N}^{\infty}\left\| x^n \right\| \leq \sum_{n=N}^{\infty}q^n= \frac{q^N}{1-q}$$is absolutely convergent, (hence convergent)
>2. **Showing that it is the inverse**:
>   We have: $$(e-x)\sum_{n=0}^{\infty}x^n=\sum_{n=0}^{\infty}x^n-\sum_{n=1}^{\infty}x^n=e$$
- **Corollary**: If $\|x\|<1$, then $r_{A}(x)\leq\|x\|<1$ and the same result holds.
---
> [!lemma] Lemma 3
> Let $A$ be a unital [[Banach Algebra|Banach algebra]]. Then, 
> 1. the inversion map $G(A)\to G(A), x\mapsto x^{-1}$ is locally [[Lipschitz Function|Lipschitz continuous]]. More precisely, if $\left\| y-x \right\| \leq \frac{1}{2\left\|x ^{-1} \right\|}$, then: $$\left\| y^{-1}-x ^{-1} \right\| \leq 2\left\|  x ^{-1} \right\|^2 \left\| y-x \right\| $$
> 2. Alternatively, we can directly show that $G(A)\to G(A),x\mapsto x ^{-1}$ is continuous. 
> 3. For $x\in G(A)$, if $y\in A$ satisfies $\left\| y-x \right\|< \frac{1}{\left\| x ^{-1} \right\|}$, then $y\in G(A)$. 

> [!proof]-
> We have
> 1. $(y^{-1}-x ^{-1})=y^{-1}(x-y) x ^{-1}$ and: $$\left\| y^{-1} \right\| -\left\| x ^{-1} \right\|\leq \left\| y^{-1}-x ^{-1} \right\| \leq \left\| y^{-1} \right\|\left\| x-y \right\| \left\| x ^{-1} \right\| \leq \frac{1}{2}\left\| y^{-1} \right\|  $$Therefore, $\left\| y^{-1} \right\|\leq 2\left\| x ^{-1} \right\|$ and $\left\| y^{-1}-x ^{-1} \right\|\leq 2\left\| x ^{-1} \right\|^2\left\| x-y \right\|$
> 2. Let $x_{n}\to x$ in $G(A)$. Then, we have that: $$x_{n}^{-1}=x_{n}^{-1}x x ^{-1}=(x^{-1}x_{n})^{-1}x ^{-1}$$where $(x ^{-1}x_{n})\to e$ by continuity of multiplication. Therefore it suffices to show that $x_{n}\to e$ implies $x_{n}^{-1}\to e$. Wlog we may assume that $\left\| e-x_{n} \right\|<1$ for all $n\in \mathbb{N}$. Then, $$\lim_{ n \to \infty } x_{n}^{-1}=\lim_{ n \to \infty } \sum_{m=0}^{\infty}(e-x_{n})^m=e$$by the dominated convergence theorem. 
> 3. We have: $e-x ^{-1}y=x ^{-1}(x-y)$. Therefore, $$\left\| e-x^{-1}y \right\| \leq \left\| x^{-1} \right\| \left\| x-y \right\| <1$$Therefore, from Lemma 2, $e-(e-x^{-1}y)=x^{-1}y\in G(A)$. Therefore, $y\in G(A)$. 
- **Remark**: $G(A)$ is an open subset of $A$ and multiplication and inversion are continuous on $G(A)$.
---


> [!lemma] Theorem 4 (Spectral Radius Formula)
> Let $A$ be a [[Banach Algebra|Banach algebra]] and $x\in A$. Then, 
> 1. $\text{Sp}_{A}(x)\subseteq \mathbb{C}$ is a  non-empty compact set and: 
> 2. it holds that$$r_{A}(x)=\max \{ \left| \lambda \right| :\lambda\in \text{Sp}_{A}(x) \}=\|x\|_{\text{sp}}$$

> [!proof]-
> Wlog we may assume that $A$ is unital.
> 1. **Show that $\text{Sp}_{A}(x)\subseteq B_{<r_{A}(x)}(0)$**:
>    Assume $\left| \lambda \right|>r_{A}(x)$. Then, $r_{A}(x) / \left| \lambda \right|<1$. By definition, we have: $$\frac{r_{A}(x)}{\left| \lambda \right| }=r_{A}\left( \frac{x}{\lambda} \right)$$ Therefore, $e-x / \lambda$ is invertible by Lemma 2. As $\lambda e$ is invertible as well, the product $\lambda e-x$ is invertible, i.e. $\lambda\notin \text{Sp}_{A}(x)$.
> 2. **Show that $\text{Sp}_{A}(x)$ is compact**:$$\text{Sp}_{A}(x)=\{ \lambda\in \mathbb{C}: x-\lambda e\in A \backslash G(A) \}$$Therefore, $\text{Sp}_{A}(x)$ is the inverse image of the closed subset $A \backslash G(A)$ under the continuous map $\lambda\mapsto x-\lambda e$. This proves that $\text{Sp}_{A}(x)$ is closed and bounded, i.e. compact.
> 3. **Show that $\text{Sp}_{A}(x)$ is non-empty**:
>    Recall $\rho_{A}(x):=\mathbb{C} \backslash \text{Sp}_{A}(x)$ is an open subset of $\mathbb{C}$. Then, for $\ell\in A^{*}$, we define: $$\begin{array}{cccc} {f:}&{\rho_{A}(x)}&\to&{\mathbb{C}}\\&{\lambda} &\mapsto & {\ell((\lambda e-x)^{-1})} \end{array}{}$$If $y,z\in G(A)$ and $y,z$ commute, then, $y,z,y^{-1},z^{-1}$ commute pairwise. Therefore, for $\lambda,\mu\in\rho_{A}(x)$: $$(\lambda e-x)(\mu e-x)\left( (\lambda e-x)^{-1}-(\mu e-x)^{-1} \right) =(\mu e-x)-(\lambda e-x)=(\mu-\lambda)e$$and $(\lambda e-x)^{-1}-(\mu e-x)^{-1}=-(\lambda-\mu)((\lambda e-x)(\mu e-x))^{-1}$. It follows that: $$f(\lambda)-f(\mu)=\ell((\lambda e-x)^{-1}-(\mu e-x)^{-1})=-(\lambda-\mu)\ell([(\lambda e-x)(\mu e-x)]^{-1})$$ If $\lambda\neq \mu$, then: $$\frac{f(\lambda)-f(\mu)}{\lambda-\mu}=-\ell([(\lambda e-x)(\mu e-x)]^{-1})$$As $\mu\mapsto \ell([(\lambda e-x)(\mu e-x)]^{-1})$ is continuous and $\lim_{ \mu \to \lambda }\frac{f(\lambda)-f(\mu)}{\lambda-\mu}=-\ell((\lambda e-x)^{-2})$ exists and $f:\rho_{A}(x)\to \mathbb{C}$ is holomorphic.
>    
>    Now assume that $\text{Sp}_{A}(x)$ is empty. If $\left| \lambda \right|>r_{A}(x)$, then by 1, $e-x / \lambda$ is invertible and $(e-x / \lambda)^{-1}=\sum_{n=0}^{\infty} (x / \lambda)^n$ is absolutely convergent. Then, $$(\lambda e-x)^{-1}=\sum_{n=0}^{\infty}\lambda^{-n-1}x^n$$and $$f(\lambda)=\ell((\lambda e-x)^{-1})=\sum_{n=0}^{\infty}\lambda^{-n-1}\ell(x^n)$$is absolutely convergent for $\left| \lambda \right|>r_{A}(x)$. 
>    
>    Say $\left| \lambda \right|>2\|x\|$. Then, $$f(\lambda)=\frac{1}{\lambda}\sum_{n=0}^{\infty}\ell\left( \left( \frac{x}{\lambda} \right)^n \right)$$and $\left| f(\lambda) \right|\leq \frac{1}{\left| \lambda \right|}\sum_{n=0}^{\infty}\left\| \ell \right\|\left\| \frac{x}{\lambda} \right\|^n< \frac{\left\| \ell \right\|}{\left| \lambda \right|}\sum_{n=0}^{\infty} \frac{1}{2^n}=2\left\| \ell \right\| / \left| \lambda \right|$. 
>    
>    Now, if $\text{Sp}_{A}(x)= \varnothing$, then $\rho_{A}(x)=\mathbb{C}$ and $f:\mathbb{C}\to \mathbb{C}$ is a bounded holomorphic function. Therefore, $f$ is constant and from $\left| f(\lambda) \right|<2\|\ell\| /\left| \lambda \right|$, we have $f=0$. Hence, $\ell((\lambda e-x)^{-1})=0$ for all $\ell\in A^{*}$, which means $(\lambda e-x)^{-1}=0$ but this would imply that $e=0$, which is a contradiction.
>  4. **Show that $\|x\|_{\text{sp}}=r_{A}(x)$**:
> 	    From 1, we have $\|x\|_{\text{sp}}\leq r_{A}(x)$. We proceed to show $r_{A}(x)\leq\|x\|_{\text{sp}}$. As $\text{Sp}_{A}(x)\subseteq B_{\leq \|x\|_{\text{sp}}}(0)$, we have that: 
> 	    
> 	   For $0<\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}$, define $g(\xi):=f( 1/ \xi)$. Therefore, $g$ on $\left\{  \xi\in \mathbb{C}:0<\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}  \right\}$ is holomorphic. Therefore, for $0<\left| \xi \right|< \frac{1}{r_{A}(x)}$, we get an absolutely convergent power series: $$g(\xi)=f\left(  \xi ^{-1} \right)=\sum_{n=0}^{\infty}\xi^{n+1}\ell(x^n)$$Therefore, $\lim_{ \xi \to 0 }g(\xi)=0$ and by the removable singularity theorem, $g$ is holomorphic and $\sum_{n=0}^{\infty}\xi^{n+1}\ell(x^n)$ is the Taylor expansion at $0$. 
> 	   
> 	   Therefore, the Taylor expansion converges absolutely in $\left\{  \xi\in \mathbb{C}:\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}  \right\}$, which implies for such $\xi$, $$\sup_{n\geq 1}\left| \ell(\xi^{n+1}x^n) \right|=\sup_{n\geq 1}\left| \xi^{n+1}\ell(x^n) \right| <+\infty$$Then, by [[Bounded Linear Map|Banach-Steinhaus]], $\sup_{n\geq 1}\left\| \xi^{n+1}x^n \right\|<+\infty$. Let $C(\xi):=\sup_{n\geq 1}\left\| \xi^n x^n \right\|<+\infty$. Then, $$\left| \xi \right| \left\| x^n \right\|^{1/n} \leq C(\xi)^{1/n}\xrightarrow{n\to \infty}1$$
> 	   But $\left| \xi \right|r_{A}(x)\leq 1$ for all $\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}$ and $r_{A}(x)\leq \frac{1}{\left| \xi \right|}$ for all $\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}$ which implies: $$r_{A}(x)\leq \|x\|_{\text{sp}}$$
---
> [!lemma] Corollary 5 (Guelfand-Mazur)
> If $A$ is a unital [[Banach Algebra]] in which every non-zero element is invertible. Then, $A\cong \mathbb{C}$ as Banach algebras.

> [!proof]-
> Let $x\in A$. Then, as $\text{Sp}_{A}(x)\neq \varnothing$, pick $\lambda\in \text{Sp}_{A}(x)$ and $x-\lambda e$ is not invertible. This means $x-\lambda e=0$ and $x=\lambda e$. 
> 
> So for each $x\in A$, there exists $\lambda(x)\in \mathbb{C}$ s.t. $x=\lambda(x)e$. $A$ is one-dimensional => $A\to \mathbb{C}$ is continuous by [[Bounded Linear Map|Proposition 2]]
---
##### Examples
> [!h] Example 1
> Let $A=\text{End}(V)$ where $V$ is a finite-dimensional $\mathbb{C}$-vector space. Then, for $T\in A$, $\text{Sp}_{A}(T)$ is the set of roots of the characteristic polynomial of $T$.
---
> [!h] Example 2
> Let $X$ be compact Hausdorff, then consider $A:=C(X)$ with $\|\cdot\|_{b}$. Then, for $f\in C(X)$, $$\text{Sp}_{A}(f)=\text{Im}(f)$$
---
