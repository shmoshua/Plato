#Definition #FunctionalAnalysis 

> [!definition]
> For a [[Banach Space|Banach space]] $V$ and $T\in \mathcal{B}(V,V)$, for all $\alpha\in \mathbb{C}$, we define: $$V_{\alpha}:=\{ v\in V:T(v)=\alpha v \}$$Then, $V_{\alpha}$ is a closed subspace of $V$ and if $V_{\alpha}\neq \{ 0 \}$,
> 1. $\alpha$ is called an ***eigenvalue*** of $T$ and
> 2. $V_{\alpha}$ is called the ***eigenvectors*** of $T$.
---
##### Examples
- **Example of a bounded operator with no eigenvalues**: Let $\mathcal{H}:=L^2([0,1],\mathcal{L}^1)$ and define $$\begin{array}{cccc} {T:}&{\mathcal{H}}&\to&{\mathcal{H}}\\&{f} &\mapsto & {x\mapsto xf(x)} \end{array}{}$$Then, we can see that $T$ is bounded as: $$\left\| Tf \right\| _{2}^2=\int_{0}^{1} x^{2}\left| f(x) \right| ^{2} \, d\mathcal{L}^1(x)\leq \int_{0}^{1} \left| f(x) \right|^{2} \, d\mathcal{L}^1(x)=\left\| f \right\| _{2}^2  $$and self-adjoint, i.e. $T=T^{*}$ as: $$\braket{ Tf , g } =\int_{0}^{1} xf(x)g(x) \, d\mathcal{L}^1(x)= \braket{ f , Tg } $$However, $T$ has no eigenvalues: for any $\alpha\in \mathbb{C}$, $$\begin{align}xf(x)&=\alpha f(x)&\mathcal{L}^1\text{-a.e.}\\(x-\alpha)f(x)&=0&\mathcal{L}^1\text{-a.e.}\\f(x)&=0 & \mathcal{L}^1\text{-a.e.}\end{align}$$
  Therefore, $\mathcal{H}_{\alpha}=\{ 0 \}$. 
---