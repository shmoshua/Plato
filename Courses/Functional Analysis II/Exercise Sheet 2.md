#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $X$ be a [[locally compact Hausdorff space]]. Compute the spectrum $\text{Sp}_{C_{0}(X)}(f)$ for each $f\in C_{0}(X)$.

Let $f\in C_{0}(X)$. Firstly, if $X$ is compact, then $C_{0}(X)$ is unital with unit $1$. Then, for $\lambda\in \mathbb{C}$, $f-\lambda$ is not invertible, if and only if $0\in (f-\lambda)(X)$. This is equivalent to $\lambda\in f(X)$ and therefore, $$\text{Sp}_{C_{0}(X)}(f)=f(X)$$
Now, assume that $X$ is not compact, i.e. $C_{0}(X)$ is non-unital. Then, $$\text{Sp}_{C_{0}(X)}(f)=\text{Sp}_{C_{0}(X)_{I}}((f,0))=\{ \lambda\in \mathbb{C}: (f,-\lambda)\notin G(C_{0}(X)_{I}) \}$$Then, $$(f,-\lambda)^{-1}=\left( \frac{1}{\lambda(f-\lambda )}f,-\frac{1}{\lambda} \right) $$Therefore, $(f,-\lambda)$ is not invertible if and only if $\lambda=0$ or $\lambda\in f(X)$. Therefore, $\text{Sp}_{C_{0}(X)}(f)=f(X)\cup \{ 0 \}$.

---
> [!def] Problem 2
> Let $\Gamma$ be an abelian group and $A:=\ell^1(\Gamma)$ with convolution product. Compute the Guelfand spectrum $\hat{A}$ of $A$ as a set.

We will show that: $$\begin{array}{cccc} {J:}&{\Gamma}&\to&{\widehat{\ell^1(\Gamma)}}\\&{\gamma} &\mapsto & {\text{ev}_{\gamma}} \end{array}{}$$is a bijection.

1. **Showing that $J$ is well-defined**:
	We show that 


