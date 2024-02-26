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

> [!proof]+
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
>  4. Show that $\|x\|_{\text{sp}}=r_{A}(x)$
---
##### Examples
> [!h] Example 1
> Let $A=\text{End}(V)$ where $V$ is a finite-dimensional $\mathbb{C}$-vector space. Then, for $T\in A$: 
> 1. $\text{Sp}_{A}(T)$ is the set of roots of the characteristic polynomial of $T$.
---
> [!h] Example 2
> Let $X$ be compact Hausdorff, then consider $A:=C(X)$ with $\|\cdot\|_{b}$. Then, for $f\in C(X)$, $$\text{Sp}_{A}(f)=\text{Im}(f)$$
---
