#Definition #FunctionalAnalysis 

> [!definition]
> For a $\mathbb{R}$-vector space $E$, a subset $A\subseteq E$ is ***absorbant*** if for all $v\in E$, there exists $\alpha>0$ s.t.$$v\in \lambda A$$for all $\left| \lambda \right|\geq \alpha$.
---
##### Properties
> [!lemma] Lemma 1
> If $E$ is a [[topological vector space]] and $U\subseteq E$ is open, if $0\in U$, then $U$ is absorbant.

> [!proof]-
> Let $v\in E$, then $t\mapsto t\cdot v$ is continuous, especially at $t=0$. Therefore, there exists $\varepsilon>0$ s.t. $t\cdot v\in U$ for all $t\in[-\varepsilon,\varepsilon]$. In other words, $$\left| t \right| \leq \varepsilon \implies v\in \frac{1}{t}U$$We can rewrite this by $\lambda=\frac{1}{t}$ into: $$\left| \lambda \right| \geq \frac{1}{\varepsilon}\implies v\in \lambda U$$
---
##### Examples
1. The unit disk $B_{\leq 1}(0)$ in $\mathbb{R}^{2}$ is absorbant.