#Definition #Algebra

> [!definition]
> For a [[Field Extension|field extension]] $K:F$ and $\alpha\in K$ [[Algebraic and Transcendental Element|algebraic]] over $F$. The ***minimal polynomial*** of $\alpha$ over $F$ is the unique monic [[Integral Domain|irreducible]] polynomial $m_{\alpha,F}(x)\in F[X]$ that has $\alpha$ as a root.
- **Related definition**: The degree of $m_{\alpha,F}(x)$ is called the ***degree of $\alpha$ over $F$.***
---
##### Properties
![[Algebraic and Transcendental Element#^15dd97]]
![[Algebraic and Transcendental Element#^dd6eee|p]]

---
> [!lemma] Proposition 1
> Let $L:F$ be an extension and $\alpha$ is algebraic over $F$ and $L$. Then, $$m_{\alpha,L}(x)|m_{\alpha,F}(x)\quad \text{ in }L[X]$$

> [!proof]-
> As $m_{\alpha,F}(x)\in L[X]$ as well and $m_{\alpha,F}(\alpha)=0$, we have that $m_{\alpha,L}(x)|m_{\alpha,F}(x)$ in $L[X]$ by [[Algebraic and Transcendental Element|Proposition 2]].
---
> [!lemma] Theorem 2
> Let $K:F$ be a field extension and $\alpha\in K$ [[Algebraic and Transcendental Element|algebraic]] over $F$. Then, 
> 1. $F[\alpha]=F(\alpha)\cong F[X] / (m_{\alpha,F}(x))$
> 2. $[F(\alpha):F]=\deg m_{\alpha,F}=:n$
> 3. $\{ 1,\alpha,\dots,\alpha^{n-1} \}$ is a basis for $F(\alpha)$ over $F$.

> [!proof]+
> From [[Field Extension|Theorem 4]].
- **Corollary**: If $\alpha\in K$ is algebraic over $F$, then $[F(\alpha):F]<+\infty$.
---
##### Examples
> [!h] Example 1
> In $\mathbb{R}:\mathbb{Q}$, 
> 1. $m_{\sqrt{ 2 },\mathbb{Q}}(x)=x^{2}-2$ as it is monic irreducible and has $\sqrt{ 2 }$ as a root.
> 2. $m_{\sqrt{ 2 },\mathbb{R}}(x)=x-\sqrt{ 2 }$.
---
We have:
1. $K=\mathbb{Q},$ and $s_{0}=2\cos\left( \frac{2\pi}{5} \right)=e^{i 2\pi/5}+e^{-i 2\pi /5}$. Then, $$m_{s_{0}}=X^{2}+X-1$$with $\varphi$ as a root. Therefore, $$\cos\left( \frac{2\pi}{5} \right)=\frac{\varphi}{2}$$and $\text{gcd}(X^2+X-1,X)$ and get: $$\frac{1}{\overline{X}}=\overline{X+1},\quad \frac{1}{\varphi}=\varphi+1$$
3. $K=\mathbb{Q},s_{0}= 2\cos\left( \frac{2\pi}{7} \right)$ and $m_{s_{0}}=X^3+X^{2}-2X-1$. Then, $m_{s_{0}}$ is irreducible over $\mathbb{Q}$.
---
$$$$