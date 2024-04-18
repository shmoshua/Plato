#Definition #FunctionalAnalysis

> [!definition] 
> Fix a prime $p$. For $n\geq 1$ and , $A_{n}:= \mathbb{Z} / p^n\mathbb{Z}$ is a [[ring]] with $1$. These rings are connected by the surjective homomorphism: $$\begin{array}{cccc} {\Phi_{n}:}&{A_{n}}&\to&{A_{n-1}}\\&{x} &\mapsto & {x\mod p^{n-1}} \end{array}{}$$Then, the ring $\mathbb{Z}_{p}$ of ***$p$-adic integers*** is defied as: $$\mathbb{Z}_{p}:=\left\{  (x_{1},x_{2},\dots)\in\prod_{n\geq 1}^{}A_{n}:\Phi_{n}(x_{n})=x_{n-1}, \forall n\geq 2  \right\}$$
- **Related definition**: Let $\varepsilon_{n}:\mathbb{Z}_{p}\to A_{n},x\mapsto x_{n}$ denote the evaluation map.
---
##### Properties
> [!lemma] Proposition 1
> For $\mathbb{Z}_{p}$, it holds that:
> 1. $\mathbb{Z}_{p}$ forms a ring. 
> 2. $\mathbb{Z}_{p}$ is compact Hausdorff.
> 3. $(\mathbb{Z}_{p},+)$ is a compact [[topological group]].

> [!proof]-
> This follows from the fact that $\Phi_{n}$ is a ring homomorphism for all $n\geq 2$. 
> 
> For $x,y\in \mathbb{Z}_{p}$: $$\Phi_{n}(x_{n}+y_{n})=\Phi_{n}(x_{n})+\Phi_{n}(y_{n})=x_{n-1}+y_{n-1}$$.
> Endow $A_{n}$ with the discrete topology. As $A_{n}$ is finite, it is compact and by Tychonoff, $\prod_{n\geq 1}^{}A_{n}$ is compact Hausdorff w.r.t. the product topology. Then, $$F_{n}:=\left\{  x\in \prod_{n\geq 1}^{}A_{n}:\Phi_{n}(x_{n})=x_{n-1}  \right\}$$is closed and $\mathbb{Z}_{p}=\bigcap_{{n\geq 2}}^{}F_{n}$ is closed and a compact Hausdorff space.
---
> [!lemma] Proposition 2
> We have:
> 1. $\varepsilon_{n}$ is surjective.
> 2. $\text{ker }\varepsilon_{n}=p^n\mathbb{Z}_{p}$
> 3. Multiplication by $p^n$ is injective.

> [!proof]- Proof (Incomplete)
> For $m\in A_{n-1}$, we have that: $$\varepsilon_{n}(m\cdot 1)=m$$
> Let $x\in \mathbb{Z}_{p}$ and assume $px=(px_{n})_{n\geq 1}=(0)_{n\geq 1}$. 
> Since $px_{1}=0$ 
---
> [!lemma] Proposition 3
> We have:
> 1. $x\in \mathbb{Z}_{p}$ is invertible if and only if $x\notin p\mathbb{Z}_{p}$

> [!proof]+
> If $x$ is invertible, then $\varepsilon_{1}(x)$ is invertible. Therefore, $x\notin \text{ker }\varepsilon_{1}=p\mathbb{Z}_{p}$. Conversely, if $x\notin p\mathbb{Z}_{p}$, then $x_{n}\notin p A_{n}$, so there exists $y_{n}\in A_{n}$ s.t. $x_{n}y_{n}=1_{A_{n}}$. 
> 