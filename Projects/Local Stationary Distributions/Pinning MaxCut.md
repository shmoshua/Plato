> [!outlook] Setup
> Let $G:=(V,E)$ be triangle-free with $\Delta(G)\leq d$. We define $\mu_{\beta}\in \Delta(\{ \pm 1 \}^n)$ s.t.: $$\mu_{\beta}(x)\propto \exp \left( -\beta x^\top A x \right) $$

---
Pick a uniformly random vertex $v$

---
##### Pinning Independent Sets
> [!lemma] Lemma 1
> Let $\mu$ be the uniform measure over independent sets of $G$. We define: $$\phi_{v}:\{ 0,1 \}^n\to \mathbb{R},\quad x\mapsto d \cdot x_{v}+\sum_{u\in N(v)}^{}x_{u}$$Then, for every pinning $\tau\in \{ 0,1 \}^\overline{N[v]}$, we have that: $$\mathbb{E}_{x\sim \mu}[\phi_{v}(x)|x_{\overline{N[v]}}=\tau]\geq \frac{\log d}{2}$$

> [!proof]-
> Let $S\subseteq N(v)$ denote the neighbors of $v$ that are not adjacent to any vertex in $\tau$, and $k:= \left| S \right|$.  Hence, $$\mathbb{E}_{x\sim \mu}[\phi_{v}(x)|x_{\overline{N[v]}}=\tau]=\frac{d}{2^k+1}+\frac{k}{2}\frac{2^k}{2^k+1}$$