#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***second countable*** if $X$ has a countable [[Base of Topology|base]].
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a second countable space. Then, 
> 1. $X$ is [[Separable Space|separable]].

> [!proof]-
> Let $\{ U_{n} \}_{n}$ be the countable base. Then, we wlog assume that $U_{n}$ is non-empty and choose $x_{n}\in U_{n}$ and let $D:=\{ x_{n} \}_{n}$. We show that $D$ is dense in $X$.
> 
>  Let $V\subseteq X$ open. Then, there exists $U_{n}\subseteq V$ and $x_{n}\in V\cap D$. Therefore, $D$ is dense and countable.
---
##### Examples
> [!h] Example 1
> $\mathbb{R}^n$ is second countable with: $$\mathcal{B}:=\{ B_{<r}(x):x\in \mathbb{Q}^n,r\in \mathbb{Q} \}$$ as basis.
---
