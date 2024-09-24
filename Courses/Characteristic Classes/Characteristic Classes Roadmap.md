#CharacteristicClasses #Roadmap 

#### 1. Fiber Bundles, Homotopy Groups

Example 1: $\pi_{2}(S^2)\cong \mathbb{Z}$ and $\pi_{k}(S^3)\cong \pi_{k}(S^2)$ for all $k\geq 3$. $\pi_{n}(S^n)\cong \mathbb{Z}$.
**Example 2**: $\mathbb{C}P^1\subseteq \mathbb{C}P^2\subseteq\dots$ and define $\mathbb{C}P^\infty:=\bigcup_{n\geq 0}^{}\mathbb{C}P^n$. 
Claim: $\pi_{k}(\mathbb{C}P^\infty)=\begin{cases}\mathbb{Z}&\text{if k=2}\\\{ 0 \}&\text{otherwise}\end{cases}$

---
**Example (Homotopy Groups of Stiefel Manifold)**
Let $V_{m,n}:=\text{SO}(n) / \text{SO}(n-m)$ which is also the set of $m$-frames in $\mathbb{R}^n$.

> [!lemma] Proposition 1
> $\pi_{k}(V_{m,n})=0$ for $k<n-m$.

> [!proof]+
> We have: $$V_{m-1,n-1}\to V_{m,n}\to S^{n-1}$$
> $$\dots\to\pi_{k}(S^{n-1})\to \pi_{k-1}(V_{m-1,n-1})\to \pi_{k-1}(V_{m,n})\to \pi_{k-1}(S^{n-1})\to\dots $$However, $\pi_{k}(S^{n-1})=0$ whenever $k\leq(n-1)-1=n-2$, hence if $k\leq n-2$, then $$$$