#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a unital [[C-Algebra|$\mathbb{C}$-algebra]] and $x\in A$. Then, the ***spectrum*** of $x$ is:
> $$\text{Sp}_{A}(x):=\{ \lambda\in \mathbb{C}:x-\lambda e\notin G(A) \}$$
> If $A$ is non-unital, we define: $$\text{Sp}_{A}(x):=\text{Sp}_{A_{I}}(x)$$
- **Related definition**: The complement of a spectrum $\rho_{A}(x):=\mathbb{C} \backslash \text{Sp}_{A}(x)$ is called the ***resolvent set***.
---
##### Properties
> [!lemma] Theorem 1
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
> [!lemma] Corollary 2 (Guelfand-Mazur)
> If $A$ is a unital algebra in which every non-zero element is invertible. Then, $A\cong \mathbb{C}$.

> [!proof]-
> Let $x\in A$. Then, as $\text{Sp}_{A}(x)\neq \varnothing$, pick $\lambda\in \text{Sp}_{A}(x)$ and $x-\lambda e$ is not invertible. This means $x-\lambda e=0$ and $x=\lambda e$. 
> 
> So for each $x\in A$, there exists $\lambda(x)\in \mathbb{C}$ s.t. $x=\lambda(x)e$.
> $A$ is one-dimensional => $A\to \mathbb{C}$ is continuous.
---
##### Examples
> [!h] Example 1
> Let $A=\text{End}(V)$ where $V$ is a finite-dimensional $\mathbb{C}$-vector space. Then, for $T\in A$: 
> 1. $\text{Sp}_{A}(T)$ is the set of roots of the characteristic polynomial of $T$.
---
> [!h] Example 2
> Let $X$ be compact Hausdorff, then consider $A:=C(X)$ with $\|\cdot\|_{b}$. Then, for $f\in C(X)$, $$\text{Sp}_{A}(f)=\text{Im}(f)$$
---
