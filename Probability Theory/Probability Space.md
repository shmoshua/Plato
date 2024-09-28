#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{F})$ be a [[Sigma Algebra|measurable space]]. 
> 1. A [[positive measure]] $\mathbb{P}:\mathcal{F}\to[0,+\infty]$ is a ***probability measure*** if $\mathbb{P}(\Omega)=1$. 
> 2. A ***probability space*** is a tuple $(\Omega,\mathcal{F},\mu)$.

^815b6d

- **Related definition**: A ***random variable*** is a map $X:(\Omega,\mathcal{F},\mu)\to R$ is a [[measurable function]] from a probability space to a measurable space.
- **Related definition**: A ***cumulative distribution function*** $F$ of a real random variable $X$ is a function $F:\mathbb{R}\to[0,1],t\mapsto \text{P}(X\leq t)$.
- **Related definition**: An ***extension*** of a probability space $(\Omega,\mathcal{F},\mu)$ is another probability space $(\Omega',\mathcal{F',\mu'})$ with a surjective [[Measurable Function|measurable map]] $\pi:\Omega'\to\Omega$ s.t. $\mu'(\pi ^{-1}(E))=\mu(E)$ for all $E\in \mathcal{F}$.
---
##### Properties

> [!lemma] Theorem 1
> Let $(\Omega,\mathcal{F},\mu)$ be a probability space with $(E_{n})_{n}$ events. Then,
> 1. **monotonicity**: for events $E,F\in \Sigma$ with $E\subseteq F$, $\text{P}\mathbb{}(E)\leq \text{P}(F)$.
> 2. **subadditivity**: $\text{P}\left( \bigcup_{n=1}^{\infty}E_{n} \right)\leq \sum_{n=1}^{\infty}\text{P}(E_{n})$.
> 3. **continuity from above**: If $(E_{n})_{n}$ is increasing, then $\text{P} \left( \bigcup_{n=1}^{\infty}E_{n} \right) =\lim_{ n \to \infty } \text{P}(E_{n})$
> 4. **continuity from below**: If $(E_{n})_{n}$ is decreasing. then $\text{P} \left( \bigcap_{n=1}^{\infty}E_{n} \right) =\lim_{ n \to \infty } \text{P}(E_{n})$.

> [!proof]-
> From [[Measure Space|Theorem 1]].
---
> [!lemma] Lemma 2 (Properties of CDF)
> Let $F$ be a cumulative distribution function of a real random variable $X$. Then, 
> 1. $F$ is non-decreasing.
> 2. $\lim_{ t \to -\infty }F(t)=0$ and $\lim_{ t \to +\infty }F(t)=1$.
> 3. $F$ is right-continuous, i.e. $F(t)=\lim_{ s \to t^+ }F(s)$ for all $t\in \mathbb{R}$. 
> 4. $\lim_{ s \to t^- }F(s)=\text{P}(X<t)$ for all $t\in \mathbb{R}$.

> [!proof]-
> We have that:
> 1. Let $s\leq t$. Then, $F(s)=\text{P}(X\leq s)\leq \text{P}(X\leq t)=F(t)$ by $\{ X\leq s \}\subseteq \{ X \leq t \}$ and monotonicity.
> 2. We have that: $$\lim_{ t \to -\infty } F(t)=\lim_{ n \to \infty } F(-n)=\lim_{ n \to \infty } \text{P}(X \leq-n)=\text{P}\left( \bigcap_{n=1}^{\infty}\{ X\leq-n \} \right) =\text{P}(\varnothing)=0$$and $$\lim_{ t \to +\infty } F(t)=\lim_{ n \to \infty } F(n)=\lim_{ n \to \infty } \text{P}(X\leq n)=\text{P}\left( \bigcup_{n=1}^{\infty}\{ X\leq n \} \right)=\text{P}(\Omega)=1 $$
> 3. We have that: $$\lim_{ s \to t^+ } F(s)=\lim_{ n\to \infty }F\left( t+\frac{1}{n} \right)=\lim_{ n \to \infty } \text{P}\left( X\leq t+\frac{1}{n} \right)=\text{P}\left( \bigcap_{n=1}^{\infty}\left\{  X\leq t+\frac{1}{n}  \right\} \right) =F(t) $$
> 4. We have that: $$\lim_{ s \to t^- } F(s)=\lim_{ n \to \infty } F\left( t-\frac{1}{n} \right)=\text{P}\left( \bigcup_{n=1}^{\infty}\left\{  X\leq t-\frac{1}{n}  \right\} \right)=\text{P}(X<t)$$

- **Corollary**: $\text{P}(X=t)=F(t)-\lim_{ s \to t^- }F(s)$ and $F$ is continuous if and only if $\text{P}(X=t)=0$ for all $t\in \mathbb{R}$. 