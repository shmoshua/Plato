#Definition #Topology 

> [!definition]
> Let $X$ be a [[topological space]] and $\sim$ an [[equivalence relation]]. Let $X /_{\sim}$ be the set of equivalence classes and $\pi:X \to X /_{\sim}$ the canonical projection. The ***quotient topology*** on $X /_{\sim}$ has $U\subseteq X / _\sim$ if and only if $\pi ^{-1}(U)\subseteq X$ is open.
- **Remark**: As $X / _\sim$ is a continuous image of $X$, $X /_{\sim}$ inherits the compactness of connectedness of $X$.
---
##### Properties
> [!lemma] Lemma 1
> A map $f:X/_{\sim}\to Y$ is continuous if and only if $f\circ\pi:X\to Y$ is continuous.

> [!proof]-
> We have that $\pi$ is continuous by definition. Therefore, if $f$ is continuous, $f\circ\pi$ is continuous.
> 
> Conversely, assume that $f\circ\pi$ is continuous and let $U\subseteq Y$ be open. Then, $\pi ^{-1}(f^{-1}(U))$ is open and thereby $f^{-1}(U)$ is open.
---
##### Examples
> [!h] Example 1
> Consider the following equivalence relation on $\mathbb{R}$: $$x\sim y \iff x-y\in \mathbb{Z}$$Then, $\mathbb{R} / \mathbb{Z}\cong S^1$.

> [!proof]+
> 
---