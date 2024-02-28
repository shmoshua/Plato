#Definition #DifferentialGeometry 

> [!definition]
> A ***topological manifold $M$ of dimension $m$*** is a [[topological space]] that is:
> 1. [[Hausdorff Space|Hausdorff]] $(T_{2})$ 
> 2. **second countable**: the topology admits a countable basis $\mathcal{B}=\{ U_{n} \}_{n}$
> 3. **locally homeomorphic to $\mathbb{R}^m$**: every point $p\in M$ admits an open neighborhood $U\subseteq M$ s.t. $\varphi :U\to \varphi(U)\subseteq\mathbb{R}^m$ is a [[homeomorphism]].
- **Related definition**: In a topological manifold $M$, we have:
  1. a ***chart*** $(U,\varphi)$
	2. the ***coordinate neighborhood*** $U$ of $\varphi$.
	3. the ***coordinate space*** $\varphi(U)$ of $\varphi$.
	4. the ***atlas*** $\{ \varphi_{i},U_{i} \}_{i}$ if $M=\bigcup_{i\in I}^{}U_{i}$.
- **Related definition**: Let $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})$ be two charts s.t. $U_{\alpha}\cap U_{\beta}\neq \varnothing$. Then, 
- **Related definition**: Two charts $(\phi,U),(\psi,V)$ are ***compatible***, if $\phi \circ\psi ^{-1}:\psi(U\cap V)\to \phi(U\cap V)$ is a [[Diffeomorphism|smooth diffeomorphism]].
---
##### Examples
> [!h] Example 1
> The following are topological manifolds:
> 1. A countable discrete space $X$ is a zero-dimensional topological manifold.
> 1. $\mathbb{R}^m$ or a non-empty open set $U\subseteq \mathbb{R}^m$ is a manifold of dimension $m$.
> 2. $S^n:=\left\{  (x_{1},\dots,x_{n+1})\in \mathbb{R}^{n+1}:\sum_{i=1}^{n+1}x_{i}^{2}=1 \right\}$