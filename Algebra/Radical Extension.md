#Definition #Algebra 

> [!definition]
> A [[field extension]] $L:K$ is ***radical*** if $L=K(\alpha_{1},\dots,\alpha_{m})$ where for each $i=1,\dots,m$, there exists an integer $n_{i}\in\mathbb{Z}$ s.t. $\alpha_{i}^{n_{i}}\in K(\alpha_{1},\dots,\alpha_{i-1})=:K_{i-1}$.
> 
> In other words, there exists a chain of intermediate fields: $$K=K_{0}\subseteq K_{1}\subseteq\dots \subseteq K_{m}=L$$s.t. $K_{i-1}(\alpha_{i})=K_{i}$ where $\alpha_{i}^{n_{i}}\in K_{i-1}$.
- **Related definition**: $\alpha_{i}$ form a ***radical sequence*** for $L:K$.
- **Related definition**: A polynomial $f\in K[X]$ is ***solvable by radicals*** if there exists a radical extension $M:K$ s.t. $f$ splits in $M[X]$, i.e. $L_{f}\subseteq M$.
---
##### Properties
> [!lemma] Theorem 1
> Let $K$ be a field with $\text{char }K=0$ and $L$ a finite [[normal extension]] of $K$. Then, the following are equivalent:
> 1. there exists $M:L$ s.t. $M:K$ is radical.
> 2. $\text{Gal}(L:K)$ is [[Solvable Group|solvable]].