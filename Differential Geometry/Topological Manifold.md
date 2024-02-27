#Definition #DifferentialGeometry 

> [!definition]
> A ***topological manifold $M$ of dimension $m$*** is a 2nd-countable [[Hausdorff space]] s.t. for all $p\in M$, there exists an open neighborhood $U\subseteq M$ s.t. $\varphi :U\to \varphi(U)\subseteq\mathbb{R}^m$ is a [[homeomorphism]].
- **Related definition**: $(\varphi,U)$ is called a ***chart*** and $\{ \varphi_{i},U_{i} \}_{i}$ is called an ***atlas*** if $M=\bigcup_{i\in I}^{}U_{i}$.
- **Related definition**: Two charts $(\phi,U),(\psi,V)$ are ***compatible***, if $\phi \circ\psi ^{-1}:\psi(U\cap V)\to \phi(U\cap V)$ is a [[Diffeomorphism|smooth diffeomorphism]].
---
##### Examples
> [!h] Example 1
> The following are topological manifolds:
> 1. $\mathbb{R}^m$ or a non-empty open set $U\subseteq \mathbb{R}^m$ is a manifold of dimension $m$.
> 2. $\mathbb{S}^n:=\left\{  (x_{1},\dots,x_{n+1})\in \mathbb{R}^{n+1}:\sum_{i=1}^{n+1}x_{i}^{2}=1 \right\}$