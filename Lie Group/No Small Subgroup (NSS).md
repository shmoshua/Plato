#Definition #LieGroups 

> [!definition]
> A [[topological group]] $G$ is said to have ***no small subgroups (NSS)*** if there exists a neighborhood $U\ni e$ s.t. $U$ contains no non-trivial subgroup of $G$.
---
> [!lemma] Theorem 1 (Hilbert, 5th Problem)
> Let $G$ be a connected, locally compact topological group. Then, the following are equivalent:
> 1. $G$ is a [[Lie group]].
> 2. $G$ has no small subgroups.
---
##### Examples
> [!h] Example 1 (Groups with small subgroups)
> Let $(G_{n})_{n}$ be a sequence of topological groups. Then, $G:=\prod_{n\geq 1}^{}G_{n}$ is a topological group. 
> 1. For any $U\ni e$, there exists finite $J\subseteq \mathbb{N}$ s.t. $$\prod_{n\in J}^{}U_{n}\times\prod_{n\notin J}^{}G_{n}\subseteq U$$where $e\in U_{n}\subseteq G_{n}$ open. 
> 2. By taking $\prod_{n\in J}^{}\{ e \}\times \prod_{n\notin J}^{}G_{n}\leq G$, $G$ is not NSS.
---
> [!h] Example 2 (Lie Groups)
> [[Lie Group|Lie groups]] have no small subgroups.

> [!proof]-
> By the exponential map, we have an open neighborhood $U\ni 0$ in $\mathfrak{g}$ s.t. $\exp:U\to \exp(U)$ is a diffeomorphism. Modulo taking a bounded subset, we may assume that $U$ is bounded and non-zero. Then, $\exp\left( \frac{1}{2}U \right)$ is an open neighborhood of $e$. 
> 
> Assume $\exp\left( \frac{1}{2}U \right)$ contains a non-trivial subgroup of $G$. Then, there exists $v\in \frac{1}{2}U \backslash\{ 0 \}$. Then, there also exists $n\in \mathbb{N}$ s.t. $2^nv\in \frac{1}{2}U$ but $2^{n+1}v\in U \backslash\frac{1}{2}U$. By the exponential map, we have that: $$\exp(2^{n+1}v)=\exp(v)^{2^{n+1}}\notin \exp\left( \frac{1}{2}U \right)$$which is a contradiction.
---
