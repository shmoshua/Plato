#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a unital [[C-Algebra|$\mathbb{C}$-algebra]] and $x\in A$. Then, the ***spectrum*** of $x$ is:
> $$\text{Sp}_{A}(x):=\{ \lambda\in \mathbb{C}:x-\lambda e\notin G(A) \}$$
> If $A$ is non-unital, we define: $$\text{Sp}_{A}(x):=\text{Sp}_{A_{I}}(x)$$
- **Related definition**: The complement of a spectrum $\rho_{A}(x):=\mathbb{C} \backslash \text{Sp}_{A}(x)$ is called the ***resolvent set***.
- **Related definition**: In a [[Banach algebra]], for $x\in A$, define $r_{A}(x):=\inf_{n\geq 1}\left\| x^n \right\|^{1/n}$.
- **Related definition**: In a [[Banach algebra]], for $x\in A$, the ***spectral radius*** is defined as:$$\|x\|_{\text{sp}}:=\max\{ \left| \lambda \right| :\lambda\in \text{Sp}_{A}(x) \}$$
---
##### Properties
> [!lemma] Proposition 1 
> Let $A$ be a [[Banach algebra]]. For $x\in A$, we have that:
> 1. $r_{A}(x)$ is well-defined.
> 2. $r_{A}(x)=\lim_{ n \to \infty }\left\| x^n \right\|^{1/n}$

> [!proof]-
> We will prove this for a general function $f:\mathbb{N}^{*}\to \mathbb{R}_{>0}$ then the statement follows by taking $f(x)=\|x^n\|$. 
> 1. **Showing the well-definedness**:
> 	Assume $f(n+m)\leq f(n)f(m)$ for all $n,m\geq 1$. Then,  $\lim_{ n \to \infty }f(n)^{1/n}$ exists and equals $\inf\{ f(n)^{1/n}:n\geq 1 \}$.
> 2. **Showing the inequality**:
> 	If $f(1)=0$, then $f(n)=0$ for all $n\geq 1$ and the statement trivially holds. Therefore, assume that $f(1)>0$. 
> 	
> 	Let $r:=\text{inf}\{ f(n)^{1/n} :n\geq 1\}\geq 0$. Further, let $\varepsilon>0$ and $k\geq 1$ s.t. $f(k)^{1/k}<r+\varepsilon$. It is sufficient to show that: $\limsup_{ n \to \infty } f(n)^{1/n}\leq r$ from which it follows that: $$r\leq\liminf_{ n \to \infty } f(n)^{1 /n}\leq \limsup_{ n \to \infty } f(n)^{1/n}\leq r$$ Now, let $n>k$ and $n:=ak+b$ where $a\geq 1$ and $0\leq b<k$. Then, $$f(n)^{1/n}=f(ak+{b})^{1/n}\leq f(ak)^{1/n}f(b)^{1/n}\leq f(k)^{a/n}f(1)^{b/n}=(f(k)^{1/k})^{1-b/n}f(1)^{b/n}\to f(k)^{1/k}$$Therefore, $$\limsup_{ n \to \infty } f(n)^{1/n}\leq f(k)^{1/k}<r+\varepsilon$$As $\varepsilon$ was arbitrary, this concludes the proof.
---
> [!lemma] Lemma 2
> Let $A$ be a unital [[Banach algebra]] and $x\in A$ with $r_{A}(x)<1$. Then, 
> 1. $e-x$ is invertible and
> 2. $(e-x)^{-1}=\sum_{n=0}^{\infty}x^n$ where $x^0=e$, as an absolutely convergent series.

> [!proof]-
> We have: 
> 1. **Showing the series is absolutely convergent**: 
>    Pick $r_{A}(x)<q<1$. Then, as $r_{A}(x)=\lim_{ n \to \infty }\|x^n\|^{1/n}$, there exists $N\geq 1$ such that $\|x^n\|^{1/n}\leq q$ for all $n\geq N$, i.e. $\|x^n\|\leq q^n$. Therefore, $$\sum_{n=0}^{\infty}\left\| x^n \right\| \leq \sum_{n=0}^{\infty}q^n= \frac{1}{1-q}$$is absolutely convergent. (hence convergent)
>2. **Showing that it is the inverse**:
>   We have: $$(e-x)\sum_{n=0}^{\infty}x^n=\sum_{n=0}^{\infty}x^n-\sum_{n=1}^{\infty}x^n=e$$
- **Corollary**: If $\|x\|<1$, then $r_{A}(x)\leq\|x\|<1$ and the same result holds.
---
> [!lemma] Lemma 3
> Let $A$ be a unital [[Banach algebra]]. Then, it holds that:
> 1. the map $G(A)\to G(A), y\mapsto y^{-1}$ is [[Lipschitz Function|Lipschitz continuous]] in some neighborhood of every $x\in G(A)$. More precisely, if $\left\| y-x \right\| \leq \frac{1}{2}\left\|x ^{-1} \right\| ^{-1}$, then: $$\left\| y^{-1}-x ^{-1} \right\| \leq 2\left\|  x ^{-1} \right\|^2 \left\| y-x \right\| $$
> 3. For $x\in G(A)$, if $y\in A$ satisfies $\left\| y-x \right\|<\left\| x ^{-1} \right\|^{-1}$, then $y\in G(A)$. 

> [!proof]-
> We have
> 1. $(y^{-1}-x ^{-1})=y^{-1}(x-y) x ^{-1}$ and: $$\left\| y^{-1} \right\| -\left\| x ^{-1} \right\|\leq \left\| y^{-1}-x ^{-1} \right\| \leq \left\| y^{-1} \right\|\left\| x-y \right\| \left\| x ^{-1} \right\| \leq \frac{1}{2}\left\| y^{-1} \right\|  $$Therefore, $\left\| y^{-1} \right\|\leq 2\left\| x ^{-1} \right\|$ and $\left\| y^{-1}-x ^{-1} \right\|\leq 2\left\| x ^{-1} \right\|^2\left\| x-y \right\|$
> 2. We have: $e-x ^{-1}y=x ^{-1}(x-y)$. Therefore, $$\left\| e-x^{-1}y \right\| \leq \left\| x^{-1} \right\| \left\| x-y \right\| <1$$Therefore, from Lemma 2, $e-(e-x^{-1}y)=x^{-1}y\in G(A)$. Therefore, $y\in G(A)$. 
- **Remark**: $G(A)$ is an open subset of $A$ and multiplication and inversion are continuous on $G(A)$.
---


> [!lemma] Theorem 4 (Spectral Radius Formula)
> Let $A$ be a [[Banach algebra]] and $x\in A$. Then, $\text{Sp}_{A}(x)\subseteq \mathbb{C}$ is a  non-empty compact set and: $$r_{A}(x)=\max \{ \left| \lambda \right| :\lambda\in \text{Sp}_{A}(x) \}=\|x\|_{\text{sp}}$$

> [!proof]-
> Wlog we may assume that $A$ is unital.
> 1. **Show that $\text{Sp}_{A}(x)\subseteq \{ \lambda\in \mathbb{C}:\left| \lambda \right|\leq r_{A}(x) \}$**:
>    Assume $\left| \lambda \right|>r_{A}(x)$. Then, $r_{A}(x) / \left| \lambda \right|<1$. By definition, we have: $$\frac{r_{A}(x)}{\left| \lambda \right| }=r_{A}\left( \frac{x}{\lambda} \right)$$ Therefore, $e-x / \lambda$ is invertible by [[Spectral Radius|Lemma 2]]. As $\lambda e$ is invertible as well, the product $\lambda e-x$ is invertible, i.e. $\lambda\notin \text{Sp}_{A}(x)$.
> 2. **Show that $\text{Sp}_{A}(x)$ is compact**:$$\text{Sp}_{A}(x)=\{ \lambda\in \mathbb{C}: x-\lambda e\in A \backslash G(A) \}$$Therefore, $\text{Sp}_{A}(x)$ is the inverse image of the closed subset $A \backslash G(A)$ under the continuous map $\lambda\mapsto x-\lambda e$. This proves that $\text{Sp}_{A}(x)$ is closed and bounded, i.e. compact.
> 3. **Show that $\text{Sp}_{A}(x)$ is non-empty**:
>    Recall $\rho_{A}(x):=\mathbb{C} \backslash \text{Sp}_{A}(x)$ is an open subset of $\mathbb{C}$. For $\ell\in A^{*}$, we define: $$\begin{array}{cccc} {f:}&{\rho_{A}(x)}&\to&{\mathbb{C}}\\&{\lambda} &\mapsto & {\ell((\lambda e-x)^{-1})} \end{array}{}$$For $\lambda,\mu\in \rho_{A}(x)$, we have: $$f(\lambda)-f(\mu)=\ell((\lambda e-x)^{-1}-(\mu e-x)^{-1})$$If $y,z\in G(A)$ and $y,z$ commute. Then, $y,z,y^{-1},z^{-1}$ commute pairwise. Therefore, $$(\lambda e-x)(\mu e-x)\left( (\lambda e-x)^{-1}-(\mu e-x)^{-1} \right) =(\mu e-x)-(\lambda e-x)=(\mu-\lambda)e$$It follows that $(\lambda e-x)^{-1}-(\mu e-x)^{-1}=-(\lambda-\mu)((\lambda e-x)(\mu e-x))^{-1}$ and: $$f(\lambda)-f(\mu)=-(\lambda-\mu)\ell([(\lambda e-x)(\mu e-x)]^{-1})$$If $\lambda\neq \mu$, then: $$\frac{f(\lambda)-f(\mu)}{\lambda-\mu}=-\ell([(\lambda e-x)(\mu e-x)]^{-1})$$As $\mu\mapsto \ell([(\lambda e-x)(\mu e-x)]^{-1})$ is continuous and $\lim_{ \mu \to \lambda }\frac{f(\lambda)-f(\mu)}{\lambda-\mu}=-\ell((\lambda e-x)^{-2})$ exists and $f:\rho_{A}(x)\to \mathbb{C}$ is holomorphic.
>    
>    If $\left| \lambda \right|>r_{A}(x)$, then $e-x / \lambda$ is invertible and $(e-x / \lambda)^{-1}=\sum_{n=0}^{\infty} (x / \lambda)^n$ is absolutely convergent. Then, $$(\lambda e-x)^{-1}=\sum_{n=0}^{\infty}\lambda^{-n-1}x^n$$and $$f(\lambda)=\ell((\lambda e-x)^{-1})=\sum_{n=0}^{\infty}\lambda^{-n-1}\ell(x^n)$$is absolutely convergent for $\left| \lambda \right|>r_{A}(x)$. 
>    
>    Say $\left| \lambda \right|>2\|x\|$. Then, $$f(\lambda)=\frac{1}{\lambda}\sum_{n=0}^{\infty}\ell\left( \left( \frac{x}{\lambda} \right)^n \right)$$and $\left| f(\lambda) \right|\leq \frac{1}{\left| \lambda \right|}\sum_{n=0}^{\infty}\left\| \ell \right\|\left\| \frac{x}{\lambda} \right\|^n< \frac{\left\| \ell \right\|}{\left| \lambda \right|}\sum_{n=0}^{\infty} \frac{1}{2^n}=2\left\| \ell \right\| / \left| \lambda \right|$. 
>    
>    Now, if $\text{Sp}_{A}(x)= \varnothing$, then $\rho_{A}(x)=\mathbb{C}$ and $f:\mathbb{C}\to \mathbb{C}$ is a bounded holomorphic function. Therefore, $f$ is constant and $f=0$. Hence, $\ell((\lambda e-x)^{-1})=0$ for all $f\in A^{*}$, which means $(\lambda e-x)^{-1}=0$ but this would imply that $e=0$, which is a contradiction.
>  4. **Show that $\|x\|_{\text{sp}}=r_{A}(x)$**:
> 	    From 1, we have $\|x\|_{\text{sp}}\leq r_{A}(x)$. We proceed to show $r_{A}(x)\leq\|x\|_{\text{sp}}$. As $\text{Sp}_{A}(x)\subseteq B_{\leq \|x\|_{\text{sp}}}(0)$, we have that: 
> 	    
> 	   For $0<\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}$, define $g(\xi):=f( 1/ \xi)$. Therefore, $g$ on $\left\{  \xi\in \mathbb{C}:0<\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}  \right\}$ is holomorphic. Therefore, for $0<\left| \xi \right|< \frac{1}{r_{A}(x)}$, we get an absolutely convergent power series: $$g(\xi)=f\left(  \xi ^{-1} \right)=\sum_{n=0}^{\infty}\xi^{n+1}\ell(x^n)$$Therefore, $\lim_{ \xi \to 0 }g(\xi)=0$ and by the removable singularity theorem, $g$ is holomorphic and $\sum_{n=0}^{\infty}\xi^{n+1}\ell(x^n)$ is the Taylor expansion at $0$. 
> 	   
> 	   Therefore, the Taylor expansion converges absolutely in $\left\{  \xi\in \mathbb{C}:\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}  \right\}$, which implies for such $\xi$, $$\sup_{n\geq 1}\left| \ell(\xi^{n+1}x^n) \right|=\sup_{n\geq 1}\left| \xi^{n+1}\ell(x^n) \right| <+\infty$$Then, by [[Bounded Linear Map|Banach-Steinhaus]], $\sup_{n\geq 1}\left\| \xi^{n+1}x^n \right\|<+\infty$. Let $C(\xi):=\sup_{n\geq 1}\left\| \xi^n x^n \right\|<+\infty$. Then, $$\left| \xi \right| \left\| x^n \right\|^{1/n} \leq C(\xi)^{1/n}\xrightarrow{n\to \infty}1$$
> 	   But $\left| \xi \right|r_{A}(x)\leq 1$ for all $\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}$ and $r_{A}(x)\leq \frac{1}{\left| \xi \right|}$ for all $\left| \xi \right|< \frac{1}{\|x\|_{\text{sp}}}$ which implies: $$r_{A}(x)\leq \|x\|_{\text{sp}}$$
---
> [!lemma] Corollary 5 (Guelfand-Mazur)
> If $A$ is a unital algebra in which every non-zero element is invertible. Then, $A\cong \mathbb{C}$.

> [!proof]-
> Let $x\in A$. Then, as $\text{Sp}_{A}(x)\neq \varnothing$, pick $\lambda\in \text{Sp}_{A}(x)$ and $x-\lambda e$ is not invertible. This means $x-\lambda e=0$ and $x=\lambda e$. 
> 
> So for each $x\in A$, there exists $\lambda(x)\in \mathbb{C}$ s.t. $x=\lambda(x)e$.
> $A$ is one-dimensional => $A\to \mathbb{C}$ is continuous.
---
##### Examples
> [!h] Example 1
> Let $A=\text{End}(V)$ where $V$ is a finite-dimensional $\mathbb{C}$-vector space. Then, for $T\in A$, $\text{Sp}_{A}(T)$ is the set of roots of the characteristic polynomial of $T$.
---
> [!h] Example 2
> Let $X$ be compact Hausdorff, then consider $A:=C(X)$ with $\|\cdot\|_{b}$. Then, for $f\in C(X)$, $$\text{Sp}_{A}(f)=\text{Im}(f)$$
---
