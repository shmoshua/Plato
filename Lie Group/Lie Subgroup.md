#Definition #LieGroups 

> [!definition]
> Let $G$ be a [[Lie group]]. A pair $(H,\varphi)$ is a ***Lie subgroup*** of $G$ if:
> 1. $H$ is a Lie group and
> 2. $\varphi:H\to G$ is an injective Lie group homomorphism that is also an [[Immersion|immersion]].
- **Remark**: As $\varphi$ is an injective immersion, $\varphi(H)$ is an [[Submanifold|immersed submanifold]] of $G$. 
- **Remark**: Often we identify $(H,\varphi)$ with $\varphi(H)\leq G$.
- **Related definition**: Two Lie subgroups $(H_{1},\varphi_{1})$ and $(H_{2},\varphi_{2})$ are ***equivalent***, if there exists a Lie group isomorphism $\alpha:H_{1}\to H_{2}$ s.t. $\varphi_{2}\circ\alpha=\varphi_{1}$. 
---
##### Properties
> [!lemma] Theorem 1 (Lie group Lie algebra Correspondence)
> Let $G$ be a [[Lie group]] with [[Lie algebra]] $\mathfrak{g}$. For any Lie subalgebra $\tilde{\mathfrak{h}}\subseteq \mathfrak{g}$, 
> 1. there exists a unique (up to equivalence) [[Connected Space|connected]] Lie subgroup $(H,\varphi)$ of $G$ with Lie algebra $\mathfrak{h}$ s.t. $d_{e}\varphi(\mathfrak{h})=\tilde{\mathfrak{h}}$.

> [!proof]-
> Let's define a [[smooth distribution]] on $G$ by setting: $$\mathcal{D}_{g}:=\{ v^L_{g}:v\in \tilde{\mathfrak{h}} \}\subseteq \text{T}_{g}G$$Then, $\mathcal{D}$ is smooth as for any basis $v_{1},..,v_{d}\in \tilde{ \mathfrak{h}}$, $v_{1}^L,\dots,v_{d}^L$ forms a local basis of $\mathcal{D}$ at each point. $\mathcal{D}$ is also involutive as $\tilde{\mathfrak{h}}$ is a Lie subalgebra and closed under bracket.
> 
> Then, by [[Smooth Distribution|Theorem 2]], let $(H,\varphi)$ be the unique maximal integral submanifold of $\mathcal{D}$ through $e$. Hence, by construction, for any $g\in \varphi(H)$, $(H,L_{g^{-1}}\circ\varphi)$ is an integral submanifold of $\mathcal{D}$ through $e$. By uniqueness, we have that $L_{g^{-1}}(\varphi(H))\subseteq\varphi(H)$. In other words, for $g,g'\in \varphi(H)$, $g^{-1}g'\in \varphi(H)$ and $\varphi(H)\leq G$.
> 
> Therefore, we can endow $H$ with a group structure s.t. $\varphi:H\to G$ is a smooth homomorphism. This shows that $(H,\varphi)$ is a connected Lie subgroup.
> 
> Lastly, for $v\in \mathfrak{h}$, $$d_{e}\varphi (\mathfrak{h})=\mathcal{D}_{\varphi(e)}=\{ v^L_{\varphi(e)}:v \in \tilde{\mathfrak{h}} \}=\tilde{\mathfrak{h}}$$
---
> [!lemma] Theorem 2
> For a Lie subgroup $(H,\varphi)$ of $G$, TFAE:
> 1. $\varphi$ is an [[Submanifold|embedding]], i.e. an injective immersion that is also a homeomorphism to its image.
> 2. $\varphi(H)$ is closed in $G$.
- **Remark**: This is not true for general submanifolds. There exist closed submanifolds that are not embedded.
---
