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

> [!proof]-
> We have: $$V_{m-1,n-1}\to V_{m,n}\to S^{n-1}$$
> $$\dots\to\pi_{k}(S^{n-1})\to \pi_{k-1}(V_{m-1,n-1})\to \pi_{k-1}(V_{m,n})\to \pi_{k-1}(S^{n-1})\to\dots $$However, $\pi_{k}(S^{n-1})=0$ whenever $k\leq(n-1)-1=n-2$, hence if $k\leq n-2$, then $$$$

---
> [!lemma] Proposition 2
> $V_{m}:=\bigcup_{n\geq m}^{}V_{m,n}$ is weakly contractible, i.e. $\pi_{c}(V_{m})$ is trivial for $c\geq 1$. 

> [!proof]-
> Consider $f:S^k\to V_{m}$. Then, as $S^k$ is compact, so is $f(S^k)$ and $f(S^k)=V_{m,n}$ for some $n$.Therefore, $f:S^k\to V_{m,n}\subseteq V_{m,N}$ where $N-m\geq k$. Therefore, $f:S^k\to V_{m,N}$ is null-homotopic.
---
> [!lemma] Theorem (Whitehead)
> Let $f:X\to Y$ be a continuous map between two connected CW-complexes s.t. $f_{*}:\pi_{n}(X,x_{0})\to \pi_{n}(Y,f(x_{0}))$ is an isomorphism. Then,
> 1. $f$ is a homotopy equivalence.
- **Corollary**: If $X$ is a connected CW-complex with $\pi_{n}(X)=0$ for $n\geq 1$. Then $X$ is contractible.
---
#### 2. Principal $G$-bundles
![[Topological Group#^de795b]]

---
> [!def] Definition
ø