#Definition #LieGroups 

> [!definition]
> Let $G$ be a [[Lie group]]. A pair $(H,\varphi)$ is a ***Lie subgroup*** of $G$ if:
> 1. $H$ is a Lie group and
> 2. $\varphi:H\to G$ is an injective Lie group homomorphism that is also an [[Differential|immersion]].
- **Remark**: As $\varphi$ is an injective immersion, $\varphi(H)$ is an [[Submanifold|immersed submanifold]] of $G$. 
- **Remark**: Often we identify $(H,\varphi)$ with $\varphi(H)\leq G$.
- **Related definition**: Two Lie subgroups $(H_{1},\varphi_{1})$ and $(H_{2},\varphi_{2})$ are ***equivalent***, if there exists a Lie group isomorphism $\alpha:H_{1}\to H_{2}$ s.t. $\varphi_{2}\circ\alpha=\varphi_{1}$. 
---
##### Properties
> [!lemma] Theorem 1 (Lie group Lie algebra Correspondence)
> Let $G$ be a [[Lie group]] with [[Lie algebra]] $\mathfrak{g}$. For any Lie subalgebra $\tilde{\mathfrak{h}}\subseteq \mathfrak{g}$, 
> 1. there exists a unique (up to equivalence) [[Connected Space|connected]] Lie subgroup $(H,\varphi)$ of $G$ with Lie algebra $\mathfrak{h}$ s.t. $d_{e}\varphi(\mathfrak{h})=\tilde{\mathfrak{h}}$.