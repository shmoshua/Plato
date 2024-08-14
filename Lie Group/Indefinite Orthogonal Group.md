#Definition #LieGroups 

> [!definition]
> For $p,q\geq 1$, the ***indefinite orthogonal group*** is given as: $$\text{O}(p,q):=\left\{ A\in \text{GL}(p+q,\mathbb{R}):A^\top \begin{bmatrix}-I_{p}&\\&I_{{q}}\end{bmatrix}A=\begin{bmatrix}-I_{p}&\\&I_{{q}}\end{bmatrix}\right\}$$
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\text{O}(p,q)\leq \text{GL}(p+q,\mathbb{R})$ is a closed [[Topological Group|topological subgroup]].
> 2. $\text{O}(p,q)$ is compact if and only if $p=0$ or $q=0$.
> 3. $\text{O}(p,q)$ is a [[Submanifold|regular $\frac{n(n-1)}{2}$-submanifold]] of $\text{GL}(n,\mathbb{R})$ for $n=p+q$.
> 4. $\text{O}(p,q)$ is a [[Lie group]].

> [!proof]-
> We have:
> 1. [[Topological Group|Example 6]]
> 2. [[Locally Compact Group|Example 4]]
> 3. [[Submanifold|Example 1]]
> 4. [[Lie Group|Example 6]]

---
##### Examples
> [!h] Example 1
> The connected component of $\text{O}(1,1)\subseteq \text{GL}(2,\mathbb{R})$ containing $\text{id}$ is homeomorphic to $\mathbb{R}$.

> [!proof]-
> Let $\begin{bmatrix}a&b\\ c&d\end{bmatrix}\in \text{O}(1,1)$. Then, $a^2-1=c^2$ and $b^2+1=d^2$ with $ab=cd$. Then, we have: $$c^2d^2-b^2 =c^2b^2,\quad c^2d^2+a^2=a^2d^2$$and $1=d^2-b^2=b^2 /c^2$ and $1=a^2-c^2=a^2 /d^2$. We have that: $$\text{O}(1,1)=\left\{ \begin{bmatrix}a&b\\b&a\end{bmatrix}\in \text{GL}(2,\mathbb{R}): a^2-b^2=1 \right\}\cup\left\{ \begin{bmatrix}a&b\\-b&-a\end{bmatrix}\in \text{GL}(2,\mathbb{R}): a^2-b^2=1 \right\}$$
---