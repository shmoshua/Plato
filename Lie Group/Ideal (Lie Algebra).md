#Definition #LieGroups 

> [!definition]
> For a [[Lie algebra]] $\mathfrak{g}$, an ***ideal*** $\mathfrak{n}$ of $\mathfrak{g}$ is a vector subspace of $\mathfrak{g}$ s.t. $$[a,b]\in \mathfrak{n},\quad \forall a\in\mathfrak{g},b\in \mathfrak{n}$$
- **Remark**: An ideal $\mathfrak{n}$ is a Lie subalgebra.
---
##### Properties
> [!lemma] Proposition 1
> Let $\mathfrak{n}$ be an ideal of $\mathfrak{g}$. Then, 
> 1. $\mathfrak{g} / \mathfrak{n}$ can be endowed a Lie algebra structure.
> 2. $\pi:\mathfrak{g}\to \mathfrak{g} / \mathfrak{n}$ is a Lie algebra homomorphism with $\text{ker }\pi=\mathfrak{n}$.

> [!proof]-
> We have that:
> 1. Define $[a+\mathfrak{n},b+\mathfrak{n}]:=[a,b]+\mathfrak{n}$. This is well-defined as, if we have $a_{1}+\mathfrak{n}=a_{2}+\mathfrak{n}$ and $b_{1}+\mathfrak{n}=b_{2}+\mathfrak{n}$, then: $$[a_{1},b_{1}]-[a_{2},b_{2}]=\underbrace{ [a_{1}-a_{2},b_{1}] }_{ \in \mathfrak{n} }+\underbrace{ [a_{2},b_{1}-b_{2}] }_{ \in \mathfrak{n} }\in \mathfrak{n}$$Further, $[b+\mathfrak{n},a+\mathfrak{n}]=[b,a]+\mathfrak{n}=-[a,b]+\mathfrak{n}=-[a+\mathfrak{n},b+\mathfrak{n}]$. This proves the statement.
> 2. Shown in 1 with: $$\text{ker }\pi=\{ v\in \mathfrak{g}:v+\mathfrak{n}=\mathfrak{n} \}=\mathfrak{n}$$
---
> [!lemma] Proposition 2
> Let $G$ be a [[Lie group]]. Let $N\leq G$ a closed subgroup with Lie algebra $\mathfrak{n}\subseteq \mathfrak{g}$. 
> 1. If $N\unlhd G$, then $\mathfrak{n}$ is an ideal of $\mathfrak{g}$.
> 2. If $G,N$ are connected with $\mathfrak{n}\leq \mathfrak{g}$ as an ideal. Then, $N\unlhd G$.

> [!proof]-
> We have:
> 1. If $N\unlhd G$, then for any $g\in G$, $\alpha_{g}:N\to N$ and $\text{Ad}(g):\mathfrak{n}\to \mathfrak{n}$. Therefore, for any $x\in \mathfrak{g}$, Then, for $x\in \mathfrak{g}$ and $y\in \mathfrak{n}$, $$[x,y]=\text{ad}(x)y=d_{e}\text{Ad}(x)y=d_{e}\text{Ad}(d_{0}\exp(x))y=d_{0}\text{Ad}(\exp(x))y\in \mathfrak{n}$$since $\text{Ad}(\exp(x)):\mathfrak{n}\to \mathfrak{n}$. 
> 2. As $\mathfrak{n}$ is an ideal, $\text{ad}(x)$ leaves $\mathfrak{n}$ invariant for all $x\in \mathfrak{g}$. Then, $\text{Ad}(\exp(x))=\exp(\text{ad}(x))$ leaves $\mathfrak{n}$ invariant for all $x\in \mathfrak{g}$. Therefore, for any $x\in \mathfrak{g}$ and $y\in \mathfrak{n}$, $\text{Ad}(\exp(x))y\in \mathfrak{n}$ and from [[Lie Group|Cartan's Theorem corollary]], $$\exp(x)\exp(y)\exp(-x)=\alpha_{\exp(x)}\exp(y)=\exp(\text{Ad}(\exp(x))y)\in N$$As $G$ and $N$ are connected, by [[Topological Group|Proposition 2.4]], $N\unlhd G$. 
> 
---
##### Examples
> [!h] Example 1 (Kernel)
> For any Lie algebra homomorphism $\varphi:\mathfrak{g}_{1}\to \mathfrak{g}_{2}$, 
> 1. $\text{ker }\varphi$ is an ideal of $\mathfrak{g}_{1}$.

> [!proof]-
> We have for $a\in \mathfrak{g}_{1}$ and $b\in \text{ker }\varphi$:
> $$\varphi([a,b])=[\varphi(a),\varphi(b)]=[\varphi(a),0]=0$$