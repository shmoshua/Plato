#Definition #MeasureTheory 

> [!definition] 
> For a [[Measure|measure]] $\mu:\mathcal{ P}(X)\to [0,+\infty]$ and a [[Sigma Algebra|$\sigma$-algebra]] $\Sigma$ of all [[Measurable Set|$\mu$-measurable sets]], the tuple $(X,\Sigma,\mu)$ is called a ***measure space***.
---
##### Properties
> [!lemma] Theorem 1
> Let $(X,\Sigma,\mu)$ be a measure space and $(A_{n})_{n}\subseteq \Sigma$, then:
> 1. **$\sigma$-additivity** of $\mu$: If $(A_{n})_{n}$ is disjoint, $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) =\sum_{n=1}^{\infty}\mu(A_{n})$$
> 2. **Continuity from above**: If $(A_{n})_{n}$ is increasing, then $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) =\lim_{ n \to \infty } \mu(A_{n})$$
> 3. **Continuity from below**: If $(A_{n})_{n}$ is decreasing and $\mu(A_{1})<+\infty$, then $$\mu \left( \bigcap_{n=1}^{\infty}A_{n} \right) =\lim_{ n \to \infty } \mu(A_{n})$$

> [!proof]-
> We see that:
> 1. We have $\mu \left( B\cap \bigcup_{n=1}^{m}A_{n} \right)=\sum_{n=1}^{m}\mu(B\cap A_{n})$. By taking $B=X$, we have $\mu \left( \bigcup_{n=1}^{m}A_{n} \right)=\sum_{n=1}^{m}\mu(A_{n})$. Then, $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) \geq \lim_{ m \to \infty } \mu \left( \bigcup_{n=1}^{m}A_{n} \right) =\lim_{ m \to \infty } \sum_{n=1}^{m}\mu(A_{n})=\sum_{n=1}^{\infty}\mu(A_{n}) \geq \mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) $$
> 2. Consider $(\tilde{ A}_{n})_{n}$ where $\tilde{ A}_{n}:=A_{n} \backslash A_{n-1}$. Then, $(\tilde{ A}_{n})_{n}$ is disjoint and $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) =\mu \left( \bigcup_{n=1}^{\infty}\tilde{ A}_{n} \right) =\sum_{n=1}^{\infty}\mu(\tilde{A}_{n})=\lim_{ m \to \infty } \sum_{n=1}^{m}\mu(\tilde{ A}_{n})=\lim_{ m \to \infty } \mu(A_{m})$$
> 3. Consider $(\tilde{ A}_{n})_{n}$ where $\tilde{ A}_{n}:=A_{1} \backslash A_{n}$. Then, $(\tilde{ A}_{n})_{n}$ is increasing and $$\begin{align}\mu(A_{1})-\lim_{ n \to \infty } \mu(A_{n})&=\lim_{ n \to \infty } \mu(\tilde{ A}_{n})=\mu \left( \bigcup_{n=1}^{\infty}\tilde{A}_{n} \right) \\&=\mu \left( \bigcup_{n=1}^{\infty}(A_{1}\backslash A_{n}) \right)=\mu \left( A_{1} \backslash \bigcap_{n=1}^{\infty}A_{n} \right) =\mu(A_{1})-\mu \left( \bigcap_{n=1}^{\infty}A_{n} \right)  \end{align}$$
> which proves our statement, only if $\mu(A_{1})<\infty$.

- **Remark**: If $\mu(A_{1})=+\infty$, for counting measure $\mu$, $(\mathbb{N},\mathcal{ P}(\mathbb{N}), \mu)$ is a measure space. If we let $A_{n}:=\{ m\in \mathbb{N}:m \geq n \}$, then $(A_{n})_{n}$ is decreasing. But, $$\mu \left( \bigcap_{n=1}^{\infty}A_{n} \right) =\mu(\varnothing)=0 \neq +\infty=\lim_{ n \to \infty } \mu(A_{n})$$
---
> [!lemma] Theorem 2 (Upper and lower semicontinuity of measures)
> For a $\sigma$-algebra $\Sigma$ on $X$, an $\sigma$-additive function $\mu:\Sigma\to[0,+\infty]$ and $\{ A_{n} \}_{n}\subseteq \mathcal{P}(X)$, 
> 1. $\mu(\liminf_{ n \to \infty }A_{n})\leq \liminf_{ n \to \infty }\mu(A_{n})$
> 2. if $\mu(X)<+\infty$, $\limsup_{ n \to \infty }\mu(A_{n})\leq \mu(\limsup_{ n \to \infty }A_{n})$

> [!proof]-
> We define $B_{n}:=\bigcap_{j=n}^{\infty}A_{j}$. Then, $B_{n}\subseteq B_{n+1}$. If we further define:
    > 1. $\widetilde{B}_0:=B_0$
    > 2. $\widetilde{B}_1:=B_1\backslash B_0$
    > 3. $\widetilde{B}_k:=B_k\backslash B_{k-1}$
    >
> then we have $\bigcup _kB_k=\bigcup _k\widetilde{B}_k$ and consequently,
> $$ \begin{aligned} \mu\left(\liminf_{n\to\infty}A_n \right) =\sum_{k=0}^\infty \mu\left(\widetilde{B}_k \right) =\lim_{N\to \infty }\sum_{k=1}^N\left(\mu(B_k)-\mu(B_{k-1})\right)+\mu(B_0) =\lim_{N\to \infty }\mu(B_N)\end{aligned} $$
> Furthermore, $B_N=\bigcap _{n=N}^\infty A_n\subseteq A_m$ for any $m\ge N$ and consequently $\mu(B_N)\le \mu(A_m)$ for any $m\ge N$. Therefore,$$ \begin{aligned} \mu\left(\liminf_{n\to\infty}A_n \right)=\lim_{N\to \infty }\mu(B_N)\le \lim_{N\to \infty }\left(\inf_{n\ge N}\mu(A_n)\right)=\liminf_{N\to \infty}\mu(A_N)\end{aligned} $$
> 
> For 2, we have that: 
> $$\liminf_{ n \to \infty } X\backslash A_{n}=\bigcup_{n=1}^{\infty}\bigcap_{m=n}^{\infty}X \backslash A_{n}=X \backslash \limsup_{ n \to \infty } A_{n}$$
> $$\mu(X)-\mu \left( \limsup_{ n \to \infty } A_{n} \right) =\mu \left( \liminf_{ n \to \infty } X\backslash A_{n} \right) \leq \liminf_{ n \to \infty } \mu(X \backslash A_{n})=\mu(X)-\limsup_{ n \to \infty } \mu(A_{n})$$Therefore, $$\limsup_{ n \to \infty } \mu(A_{n})\leq \mu \left( \limsup_{ n \to \infty } A_{n} \right) $$
---