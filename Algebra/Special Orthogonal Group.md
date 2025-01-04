#Definition #Algebra

> [!definition]
> The ***special orthogonal group*** for $n\in \mathbb{N}$, denoted as $\text{SO}(n)$ is defined as: $$\text{SO}(n):=\{  A\in \text{O}(n):\det(A)=1 \}$$
> where $\text{O}(n)$ is the [[Orthogonal Group| orthogonal group]].

- $\text{SO}(1)\cong (\{ 1 \},\cdot)$ which means $\text{SO}(1)$ is abelian.
- $\text{SO}(2)$ only has matrices of the following form: $$\begin{bmatrix}
\cos\alpha&-\sin\alpha\\ \sin\alpha&\cos\alpha
\end{bmatrix}$$for some $\alpha\in \mathbb{R}$. Therefore, $\text{SO}(2)$ only contains rotations and is therefore abelian. This means, $\text{SO}(2)\cong\mathbb{U}$.

---
##### Properties

> [!lemma] Theorem 1
> We have that:
> 1. $\text{SO}(n)$ is a [[topological group]].
> 2. $\text{SO}(n)$ is a [[Lie group]].
> 3. $\text{SO}(n)$ is [[Connected Space|connected]].
> 4. $\text{SO}(n)$ is [[Path-Connected Space|path-connected]].

> [!proof]-
> We have:
> 1. Let $\text{SO}(n)\leq \text{GL}(n,\mathbb{R})$. Then, for $A,B\in \text{SO}(n)$, $\det(AB)=\det(A)\det(B)=1$ and $AB\in \text{SO}(n)$. Further, $\det(A^{-1})=1$ and $A^{-1}\in \text{SO}(n)$. Hence, $\text{SO}(n)$ is a closed subgroup of $\text{GL}(n,\mathbb{R})$.
> 2. As $\text{GL}(n,\mathbb{R})$ is a Lie group, it holds by Cartan's closed subgroup theorem.
> 3. By [[Topological Group|connected topological group Lemma 2]], we show that by induction. First, $\text{SO}(1)=\{ 1 \}$ and is connected. Then, we have for $n\geq 2$, $S^{n-1}$ is homeomorphic to $\text{SO}(n) / \text{SO}(n-1)$. Hence, as $S^{n-1}$ and $\text{SO}(n-1)$ are connected, so is $\text{SO}(n)$.
> 4. Every connected topological manifold is path-connected.

---
> [!lemma] Theorem 2
> $S^n$ is homeomorphic to $\text{SO}(n+1) / \text{SO}(n)$.

> [!proof]-
> See [[Homogeneous Space|Example 1]].

---
