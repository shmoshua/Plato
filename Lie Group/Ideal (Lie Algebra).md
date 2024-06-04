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
> Let $G$ be a [[Lie group]].  
> 1. Let $N\leq G$ a closed subgroup with Lie algebra $\mathfrak{n}\subseteq \mathfrak{g}$. If $N\unlhd G$, then $\mathfrak{n}$ is an ideal of $\mathfrak{g}$.
> 2. Let $G,N$ be connected with $\mathfrak{n}\leq \mathfrak{g}$ as an ideal. Then, $N\unlhd G$.

> [!proof]+
> If $N\unlhd G$, then for any $g\in G$, $\alpha_{g}:N\to N$ and $\text{Ad}(g):\mathfrak{n}\to \mathfrak{n}$. Therefore, for any $x\in \mathfrak{g}$, Then, for $$[x,y]=\text{ad}(x)y=d_{e}\text{Ad}(x)y=$$
> 
> As $N\leq G$ is closed, 
> 
> we have that by [[Lie Group|Cartan's Theorem Corollary]], $\mathfrak{n}:=\{ x\in \mathfrak{g}:\exp(tx)\in N,\forall t\in \mathbb{R} \}$. Then, for $x\in \mathfrak{n}$ and $y\in \mathfrak{g}$,   $$\exp(sy)\exp(tx)\exp(-sy)=\exp(\text{Ad}(\exp(sy))(tx))=\exp(\exp(\text{ad}(sy))(tx))\in N$$
> 
> We have that for $a\in \mathfrak{g}$ and $b\in \mathfrak{n}$, $$\begin{align}\exp(t[a,b])&=\exp(  \text{ad}(a)(tb) ) \\&=\exp(d_{e}\text{Ad}(a)(tb))\\&=\left. \frac{d}{ds} \right| _{s=0}\exp(\text{Ad}(\exp(sa))(tb))\\&=\left. \frac{d}{ds} \right| _{s=0}\exp(sa)\exp(tb)\exp(-sa)\end{align}$$
---
##### Examples
> [!h] Example 1 (Kernel)
> For any Lie algebra homomorphism $\varphi:\mathfrak{g}_{1}\to \mathfrak{g}_{2}$, 
> 1. $\text{ker }\varphi$ is an ideal of $\mathfrak{g}_{1}$.

> [!proof]-
> We have for $a\in \mathfrak{g}_{1}$ and $b\in \text{ker }\varphi$:
> $$\varphi([a,b])=[\varphi(a),\varphi(b)]=[\varphi(a),0]=0$$