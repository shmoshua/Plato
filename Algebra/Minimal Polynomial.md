#Definition #Algebra

> [!definition]
> For [[Extension Field|field extension]] $K:F$ and $\alpha\in K$ and [[Algebraic and Transcendental Number|algebraic]]. Then, the unique monic [[Integral Domain|irreducible]] polynomial $m_{\alpha,F}(x)\in F[X]$ that has $\alpha$ as a root is called the ***minimal polynomial of $\alpha$ over $F$***.
- **Related definition**: The degree of $m_{\alpha,F}(x)$ is called the ***degree of $\alpha$ over $F$.***
---
##### Properties
> [!lemma] Proposition 1
> Let $L:F$ be an extension and $\alpha$ is algebraic over $F$ and $L$. Then, $$m_{\alpha,L}(x)|m_{\alpha,F}(x)\quad \text{ in }L[X]$$

> [!proof]-
> As $m_{\alpha,F}(x)\in L[X]$ as well and $m_{\alpha,F}(\alpha)=0$, we have that $m_{\alpha,L}(x)|m_{\alpha,F}(x)$ in $L[X]$ by [[Algebraic and Transcendental Number|Proposition 1]].

---
##### Examples
1. $K=\mathbb{Q}, L=\mathbb{R},\mathbb{C}$ and $s_{0}=\sqrt{ 2 }$. Then, $$m_{\sqrt{ 2 }}=X^{2}-2$$and $$\mathbb{Q}[X] / (X^2-2)\cong \mathbb{Q}[\sqrt{ 2 }]$$
2. $K=\mathbb{Q},$ and $s_{0}=2\cos\left( \frac{2\pi}{5} \right)=e^{i 2\pi/5}+e^{-i 2\pi /5}$. Then, $$m_{s_{0}}=X^{2}+X-1$$with $\varphi$ as a root. Therefore, $$\cos\left( \frac{2\pi}{5} \right)=\frac{\varphi}{2}$$and $\text{gcd}(X^2+X-1,X)$ and get: $$\frac{1}{\overline{X}}=\overline{X+1},\quad \frac{1}{\varphi}=\varphi+1$$
3. $K=\mathbb{Q},s_{0}= 2\cos\left( \frac{2\pi}{7} \right)$ and $m_{s_{0}}=X^3+X^{2}-2X-1$. Then, $m_{s_{0}}$ is irreducible over $\mathbb{Q}$.
---
$$$$