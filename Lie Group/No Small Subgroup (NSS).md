#Definition #LieGroups 

> [!definition]
> A ***topological group*** $G$ is said to have ***no small subgroup (NSS)*** if there exists a neighborhood $U\ni e$ s.t. $U$ contains no non-trivial subgroup of $G$.
---
##### Examples
> [!h] Example 1 (Groups with small subgroups)
> Let $(G_{n})_{n}$ be a sequence of topological groups. Then, $G:=\prod_{n\geq 1}^{}G_{n}$ is a topological group. 
> 1. For any $U\ni e$, there exists finite $J\subseteq \mathbb{N}$ s.t. $$\prod_{n\in J}^{}U_{n}\times\prod_{n\notin J}^{}G_{n}\subseteq U$$where $e\in U_{n}\subseteq G_{n}$ open. 
> 2. By taking $\prod_{n\in J}^{}\{ e \}\times \prod_{n\notin J}^{}G_{n}\leq G$, $G$ is not NSS.
---
