> [!outlook] Setup
> Let $G:=(V,E)$ be triangle-free with $\Delta(G)\leq d$. We define $\mu_{\beta}\in \Delta(\{ \pm 1 \}^n)$ s.t.: $$\mu_{\beta}(x)\propto \exp \left( -\beta x^\top A x \right) $$

---
Pick a uniformly random vertex $v$
> [!lemma] Theorem 1
> Let $G$ be a triangle free graph with $\Delta(G)\leq d$. Let $x$ be a max-cut in $G$ that arises from Glauber dynamics run for $\text{poly}(n)$. Then, 
> 1. the expected size is at least $\frac{1}{2}+\Omega\left( \frac{1}{\sqrt{ d }} \right)$.

> [!proof]-
> We want to show that: $$\mathbb{E}_{t\sim [0,T]}\mathbb{E}_{x\sim{\nu_{t}}}\text{Cut}(x)\geq \left( \frac{1}{2}+\Omega \left( \frac{1}{\sqrt{ d }} \right)  \right)m$$However, $$\text{Cut}(x)=$$
> Our goal is: $$\mathbb{E}_{t\sim [0,T]}\mathbb{E}_{\nu_{t}}[x_{u}x_{v}]\leq -\Omega\left( \frac{1}{\sqrt{ d }} \right)$$
---
Let $$\phi_{v}(x):=-x_{v}\sum_{u\sim v}^{}x_{u}$$Then, $$n \mathbb{E}_{v\sim V}[\phi_{v}(x)]=-2\sum_{uv\in E} x_{u}x_{v}$$

Let $e(u,\tau^+)$ and $e(u,\tau^-)$ denote the number of edges between $u$ to $\tau^+$ and $\tau^-$. Let $S:= \{ u\in N(v): e(u,\tau^+)=e(u,\tau^-) \}$ and $k:= \left| S \right|$.
1. If $d(v)$ is odd, $v$'s spin is always determined by the rest. In this case, $$\mathbb{E}_{x\sim \pi_{\beta}}[\phi_{v}(x)|x_{\overline{N[v]}}=\tau]=$$
 
If $e$

Then, for $k:= \left| S \right|$
1. if $k$ is odd, it can't happen $$\mathbb{E}_{x\sim \pi}[\phi_{v}(x)|x_{\overline{N[v]}}=\tau]=$$

---
##### Pinning Independent Sets
> [!lemma] Lemma 1
> Let $\mu$ be the uniform measure over independent sets of $G$. We define: $$\phi_{v}:\{ 0,1 \}^n\to \mathbb{R},\quad x\mapsto d \cdot x_{v}+\sum_{u\in N(v)}^{}x_{u}$$Then, for every pinning $\tau\in \{ 0,1 \}^\overline{N[v]}$, we have that: $$\mathbb{E}_{x\sim \mu}[\phi_{v}(x)|x_{\overline{N[v]}}=\tau]\geq \frac{\log d}{2}$$

> [!proof]-
> Let $S\subseteq N(v)$ denote the neighbors of $v$ that are not adjacent to any vertex in $\tau$, and $k:= \left| S \right|$.  Hence, $$\mathbb{E}_{x\sim \mu}[\phi_{v}(x)|x_{\overline{N[v]}}=\tau]=\frac{d}{2^k+1}+\frac{k}{2}\frac{2^k}{2^k+1}$$

