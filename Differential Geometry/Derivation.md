#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]] and $p\in M$. A ***derivation*** of $C^\infty(M)$ at $p$ is a map $\delta\in C^\infty(M)^{*}$ s.t. for all $f,g\in C^\infty(M)$, $$\delta(fg)=\delta(f)g(p)+f(p)\delta(g)$$
> Let $\text{Der}_{p}C^\infty(N)$ be the vector space of derivations at $p$.
---
##### Properties
> [!lemma] Lemma 1
> Let $M$ be a [[smooth manifold]] and $p\in M$. 

> [!lemma] Theorem 1
> Let $M$ be a [[smooth manifold]] and $p\in M$. $$\begin{array}{cccc} {}&{\text{T}_{p}M}&\to&{\text{Der}_{p}C^\infty(N)}\\&{v} &\mapsto & {\delta_{v}:f\mapsto d_{p}f(v)} \end{array}{}$$is a vector space isomorphism.

> [!proof]+
> Let $\sigma:\mathbb{R}\to \mathbb{R}$ where: $$\sigma(x):=\begin{cases}e^{-1/x^{2}}&x>0\\0&x\leq 0\end{cases}$$Then, $\sigma\in C^\infty(\mathbb{R})$