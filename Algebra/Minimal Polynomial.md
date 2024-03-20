#Definition #Algebra

> [!definition]
> For [[Extension Field|field extension]] $K:F$ and $\alpha\in K$ and [[Algebraic and Transcendental Number|algebraic]] over $F$. Then, the unique monic [[Integral Domain|irreducible]] polynomial $m_{\alpha,F}(x)\in F[X]$ that has $\alpha$ as a root is called the ***minimal polynomial of $\alpha$ over $F$***.
- **Related definition**: The degree of $m_{\alpha,F}(x)$ is called the ***degree of $\alpha$ over $F$.***
---
##### Properties
> [!lemma] Proposition 1
> Let $L:F$ be an extension and $\alpha$ is algebraic over $F$ and $L$. Then, $$m_{\alpha,L}(x)|m_{\alpha,F}(x)\quad \text{ in }L[X]$$

> [!proof]-
> As $m_{\alpha,F}(x)\in L[X]$ as well and $m_{\alpha,F}(\alpha)=0$, we have that $m_{\alpha,L}(x)|m_{\alpha,F}(x)$ in $L[X]$ by [[Algebraic and Transcendental Number|Proposition 1]].
---
> [!lemma] Theorem 2
> Let $K:F$ be a field extension and $\alpha\in K$ [[Algebraic and Transcendental Number|algebraic]] over $F$. Then, 
> 1. $F[\alpha]=F(\alpha)\cong F[X] / (m_{\alpha,F}(x))$
> 2. $[F(\alpha):F]=\deg m_{\alpha,F}=:n$
> 3. $\{ 1,\alpha,\dots,\alpha^{n-1} \}$ is a basis for $F(\alpha)$ over $F$.

> [!proof]-
> From [[Extension Field|Theorem 4]]
---
> [!lemma] Proposition 3
> Let $K:F$ and $\alpha\in K$. The following are equivalent:
> 1.  $\alpha$ is algebraic over $F$. 
> 2. $[F(\alpha):F]<+\infty$

> [!proof]-
> (1=>2) holds from Theorem 2. For the converse, suppose that $[F(\alpha):F]=n$. Then, $$1,\alpha,\dots,\alpha^n$$are linearly dependent and there exists $b_{0},\dots,b_{n}\in F$ not all zero, s.t. $$b_{0}+b_{1}\alpha+\dots+b_{n}\alpha^n=0$$By defining $g(x):=b_{0}+b_{1}x+\dots+b_{n}x^n\in F[X]$, we have that $\alpha$ is algebraic over $F$. 
---
##### Examples
1. $K=\mathbb{Q}, L=\mathbb{R},\mathbb{C}$ and $s_{0}=\sqrt{ 2 }$. Then, $$m_{\sqrt{ 2 }}=X^{2}-2$$and $$\mathbb{Q}[X] / (X^2-2)\cong \mathbb{Q}[\sqrt{ 2 }]$$
2. $K=\mathbb{Q},$ and $s_{0}=2\cos\left( \frac{2\pi}{5} \right)=e^{i 2\pi/5}+e^{-i 2\pi /5}$. Then, $$m_{s_{0}}=X^{2}+X-1$$with $\varphi$ as a root. Therefore, $$\cos\left( \frac{2\pi}{5} \right)=\frac{\varphi}{2}$$and $\text{gcd}(X^2+X-1,X)$ and get: $$\frac{1}{\overline{X}}=\overline{X+1},\quad \frac{1}{\varphi}=\varphi+1$$
3. $K=\mathbb{Q},s_{0}= 2\cos\left( \frac{2\pi}{7} \right)$ and $m_{s_{0}}=X^3+X^{2}-2X-1$. Then, $m_{s_{0}}$ is irreducible over $\mathbb{Q}$.
---
$$$$