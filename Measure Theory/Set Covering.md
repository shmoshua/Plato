#Definition #MeasureTheory 

> [!Definition]
> A set $\mathcal{K}\subseteq \mathcal{P}(X)$ is a (set) ***covering*** of $X$, if:
> 1. $\varnothing\in \mathcal{K}$,
> 2. there exists $(K_{i})_{i}\subseteq \mathcal{K}$ s.t. $X=\bigcup_{i=1}^{\infty}K_{i}$.
- **Remark**: every [[Measure Theory/Algebra|algebra]] $\mathcal{A}\subseteq \mathcal{P}(X)$ is a covering of $X$.
- **Related Definition**: A covering $\mathcal{K}$ is ***open*** if all sets in $\mathcal{K}$ are open.
---
##### Properties

> [!lemma] Theorem 1
> For a covering $\mathcal{K}$ of $X$, and a function $\lambda:\mathcal{K} \to[0,+\infty]$ with $\lambda(\varnothing)=0$, we define $\mu:\mathcal{P}(X)\to[0,+\infty]$ as follows:
> $$\mu(A)=\text{inf}\left\{  \left.\sum_{n=1}^{\infty}\lambda(A_{n})  \right|A_{n}\in \mathcal{K},A\subseteq \bigcup_{n=1}^{\infty}A_{n}\right\}$$
> Then, $\mu$ is a [[Measure|measure]].

> [!proof]-
> Firstly, trivially we have $\mu(\varnothing)=0$. 
> 
> Now, for $A\subseteq \bigcup_{i=1}^{\infty}A_{i}$, we need to show that $\mu(A)\leq \sum_{i=1}^{\infty}\mu(A_{i})$.
> 
> If $\sum_{i=1}^{\infty}\mu(A_{i})=\infty$, then this trivially holds. If $\sum_{i=1}^{\infty}\mu(A_{i})<\infty$, then $\mu(A_{i})<\infty$ for all $i$. By the definition of infimum, for any $\varepsilon > 0$ and $i\geq 1$, there exists $(K_{ij})_{j}\subseteq\mathcal{K}$ s.t. $A_{i}\subseteq \bigcup_{j=1}^{\infty}K_{ij}$ and $$\sum_{j=1}^{\infty}\lambda(K_{ij})\leq \mu(A_{i})+ \frac{\varepsilon}{2^i}$$
> It is clear that $A=\bigcup_{i=1}^{\infty}A_{i}\subseteq \bigcup_{i,j=1}^{\infty}K_{i,j}$. By definition, 
> $$\mu(A) \leq \sum_{i,j=1}^{\infty}\lambda(K_{ij})\leq \sum_{i=1}^{\infty}\mu(A_{i})+\varepsilon$$
> As this holds for any $\varepsilon>0$, we have that $\mu(A)\leq \sum_{i=1}^{\infty}\mu(A_{i})$.
---
