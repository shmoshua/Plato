#Definition #FunctionalAnalysis 
> [!definition]
> In a [[topological space]] $X$, a set $A\subseteq X$ is: 
> 1. ***meager*** or of ***first category***, if it is a countable union of [[Dense Subset|nowhere dense subsets]] of $X$. 
> 2. ***non-meager*** or of ***second category***, if it is not meager.
> 3. ***residual*** or ***generic***, if $X / A$ is meager.
---
##### Examples
**Meager Sets**
1. $\mathbb{Q}$ is meager in $\mathbb{R}$, as it is a countable union of points.
2. A complete non-empty metric space $X$ and any of its non-empty open subsets.
---
**Example of a generic set of measure 0**
Let $j \mapsto q_{j}$ denote the bijection from $\mathbb{N}\to \mathbb{Q}$. Then, we define: $$U_{j}:=\bigcup_{k\in\mathbb{N}}^{}(q_{k}-2^{-(j+k+1)},q_{k}+2^{-(j+k+1)})$$As $\mathbb{Q}\subseteq U_{j}$ for all $j$, $\bigcap_{j\geq 0}^{}U_{j}$ is dense in $\mathbb{R}$ and therefore generic. However, $$\mathcal{L}^1\left( \bigcap_{j\geq 0}^{}U_{j} \right)= \lim_{ j \to \infty }\mathcal{L}^1(U_{j})\leq \lim_{ j \to \infty } \sum_{k=0}^\infty 2^{-(j+k)}=\lim_{ j \to \infty } 2^{-(j-1)}=0 $$

---
