#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach algebra]]. A ***character*** of $A$ is a non-trivial [[C-Algebra|$\mathbb{C}$-algebra]] homomorphism $\chi:A\to \mathbb{C}$. Then, the ***Guelfand spectrum*** $\hat{A}$ of $A$ is defined as the set of characters of $A$.
- **Remark**: If a $\mathbb{C}$-algebra $A$ has a unit $e$, then for any $\mathbb{C}$-algebra homomorphism $\varphi:A\to \mathbb{C}$, $\varphi(e)=1$.
- **Remark**: GIven any $\mathbb{C}$-algebra homomorphism $\varphi:A\to \mathbb{C}$, we can define: $$\begin{array}{cccc} {\varphi_{I}:}&{A\times \mathbb{C}}&\to&{\mathbb{C}}\\&{(x,\lambda)} &\mapsto & {\varphi(x)+\lambda} \end{array}{}$$Then, $\hat{A}_{I}=\{ \varphi_{I}:\varphi\in \hat{A} \}\cup \{ \varphi_{\infty} \}$ where $\varphi_{\infty}(x,\lambda)=\lambda$. One also often denotes $\hat{A}_{I}=\hat{A}\cup \{ \varphi_\infty \}$.
---
##### Properties
> [!lemma] Proposition 1
> For every $\varphi\in \hat{A}$ we have: $$\left| \varphi(x) \right| \leq\|x\|_{\text{sp}}\quad \forall x\in A$$ In particular, $\varphi\in A^{*}$ with $\left\| \varphi \right\|\leq 1$ with equality if $A$ is unital with $\|e\|=1$ for the unit.

> [!proof]-
> Due to the remark, we may assume that $A$ is unital. If $\left| \lambda \right|>\|x\|_{\text{sp}}$.  Then, $x-\lambda e$ is invertible. But then if $y\in A$ is the inverse of $x-\lambda e$, we have: $$y(x-\lambda e)=e\implies\varphi(y)\varphi(x-\lambda e)=\varphi(e)=1$$which means $\varphi(x-\lambda e)\neq 0$ and $\varphi(x)\neq\lambda$. Therefore, $\left| \varphi(x) \right|\leq \|x\|_{\text{sp}}$.
> 
> Further, as $\|x\|_{\text{sp}}\leq\|x\|$, $\left\| \varphi \right\|\leq 1$. If $\|e\|=1$, then since $\varphi(e)=1=\|e\|$, $\|\varphi\|=1$.