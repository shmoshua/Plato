#Definition #FunctionalAnalysis

> [!definition] 
> Fix a prime $p$. For $n\geq 1$ and , $A_{n}:= \mathbb{Z} / p^n\mathbb{Z}$ is a [[ring]] with $1$. These rings are connected by the surjective homomorphism: $$\begin{array}{cccc} {\Phi_{n}:}&{A_{n}}&\to&{A_{n-1}}\\&{x} &\mapsto & {x\mod p^{n-1}} \end{array}{}$$Then, the ring $\mathbb{Z}_{p}$ of ***$p$-adic integers*** is defied as: $$\mathbb{Z}_{p}:=\left\{  (x_{1},x_{2},\dots)\in\prod_{n\geq 1}^{}A_{n}:\Phi_{n}(x_{n})=x_{n-1}, \forall n\geq 2  \right\}$$
---
##### Properties
> [!lemma] Proposition 1
> $\mathbb{Z}_{p}$ forms a ring. 

> [!proof]-
> This follows from the fact that $\Phi_{n}$ is a ring homomorphism for all $n\geq 2$. 
> 
> For $x,y\in \mathbb{Z}_{p}$: $$\Phi_{n}(x_{n}+y_{n})=\Phi_{n}(x_{n})+\Phi_{n}(y_{n})=x_{n-1}+y_{n-1}$$
---
> [!lemma] Proposition 2
> 