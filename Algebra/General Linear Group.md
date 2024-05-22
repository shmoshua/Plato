#Definition #Algebra

> [!definition]
> Let $K$ be a field. The ***general linear group*** for $n\in \mathbb{N}$, denoted as $(\text{GL}(n,K),\cdot)$ is defined as: $$\text{GL}(n,K):=\{  A\in \text{M}(n,K):\det(A)\neq 0 \}$$
> where $\text{M}(n,K)$ is the set of all $n\times n$ matrices with elements in $K$ as entries.

- $\text{GL}(1,\mathbb{R})\cong (\mathbb{R}^*,\cdot)$ which means $\text{GL}(1)$ is abelian.
- For $n>1$, $\text{GL}(n,\mathbb{R})$ is non-abelian as matrix multiplications don't commute.
---
##### Properties
> [!lemma] Proposition 1
> Consider the injection: $$\begin{array}{cccc} {\Psi:}&{\text{GL}(n,\mathbb{R})}&\to&{\text{Homeo}(\mathbb{R}^n)}\\&{A} &\mapsto & {(x\mapsto Ax)} \end{array}{}$$Then, 
> 1. $\Psi(\text{GL}(n,\mathbb{R}))\subseteq \text{Homeo}(\mathbb{R}^n)$ is closed w.r.t. [[compact-open topology]].
> 2. the induced subspace topology coincides with the euclidean topology on $\text{GL}(n,\mathbb{R})$.

> [!proof]-
> We have: 
> 1. We can characterize: $$\Psi(\text{GL}(n,\mathbb{R}))=\{ f\in \text{Homeo}(\mathbb{R}^n): f(\lambda a+b)=\lambda f(a)+f(b), \forall\lambda,a,b\in \mathbb{R} \}$$Then, for $\lambda,a,b\in \mathbb{R}$, the evaluation map $f\mapsto f(\lambda a+b)-\lambda f(a)-f(b)$ is continuous and therefore, $$\Psi(\text{GL}(n,\mathbb{R}))=\bigcap_{\lambda,a,b\in \mathbb{R}}^{}\text{ker }\text{ev}_{\lambda,a,b}$$is a closed set.
---

