#Definition #Algebra

> [!definition]
> For [[Field]] $K\subseteq L$ and $s_{0}\in L$ and [[Algebraic and Transcendental Number|algebraic]] s.t. $$K[X] / (m_{s_{0}})\cong K[s_{0}]$$then, $m_{s_{0}}$ is called the ***minimal polynomial*** of $s_{0}$ over $K$.
---
##### Properties
> [!lemma] Proposition 1
> If $\text{char}(K)=0$, then $K[X] / (m_{s_{0}})$ is a field.

> [!proof]-
> We first show that $(m_{s_{0}})$ is [[Maximal Ideal|maximal]]. For every $p\in K[X]$, we have either $p\in (m_{s_{0}})$ or $(p,m_{s_{0}})=K[X]$. Therefore, $K[X] / (m_{s_{0}})$ is a field.
---
##### Examples
1. $K=\mathbb{Q}, L=\mathbb{R},\mathbb{C}$ and $s_{0}=\sqrt{ 2 }$. Then, $$m_{\sqrt{ 2 }}=X^{2}-2$$and $$\mathbb{Q}[X] / (X^2-2)\cong \mathbb{Q}[\sqrt{ 2 }]$$
2. $K=\mathbb{Q},$ and $s_{0}=2\cos\left( \frac{2\pi}{5} \right)=e^{i 2\pi/5}+e^{-i 2\pi /5}$. Then, $$m_{s_{0}}=X^{2}+X-1$$with $\varphi$ as a root. Therefore, $$\cos\left( \frac{2\pi}{5} \right)=\frac{\varphi}{2}$$and $\text{gcd}(X^2+X-1,X)$ and get: $$\frac{1}{\overline{X}}=\overline{X+1},\quad \frac{1}{\varphi}=\varphi+1$$
3. $K=\mathbb{Q},s_{0}= 2\cos\left( \frac{2\pi}{7} \right)$ and $m_{s_{0}}=X^3+X^{2}-2X-1$. Then, $m_{s_{0}}$ is irreducible over $\mathbb{Q}$.
---
$$$$