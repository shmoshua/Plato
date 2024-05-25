#Definition #LieGroups 

> [!definition]
> Let $G$ be a [[topological group]] and $X$ a [[topological space]]. $X$ is a ***homogeneous space*** of $G$ if there exists a continuous [[Group Action|transitive group action]] $G\times X\to X$.
- **Related definition**: A subset $Y\subseteq X$ is ***$G$-invariant***  if for any $y\in Y$ and $g\in G$, $gy\in Y$.
- **Notation**: The [[Orbit and Stablizer|stabilizer]] $\text{Stab}_{G}(x)$ is also denoted as $G_{x}$.
---
##### Properties

> [!lemma] Proposition 1
> For a topological group $G$ and its homogeneous space $X$, 
> 1. for $x\in X$, the $G$-map: $$G/G_{x}\to X,\quad g\cdot G_{x}\mapsto gx$$is an isomorphism of $G$-spaces, i.e. it is a bijection that commutes with the action. ($G_{x}$ denotes the stabilizer $\text{Stab}_{G}(x):=\{ g\in G:gx=x \}$)
> 2. the $G$-map is continuous.
> 3. If $G$ is LCH and second countable and $X$ is LCH, then the bijection is a homeomorphism.

> [!proof]+
> We have:
> 1. Let $\Psi$ denote the map. Then, it is well-defined: for $g,h\in G$ with $g^{-1}h\in G_{x}$, $$hx=g g^{-1}hx=gx$$Then, it is injective as if $gx=hx$, then $g^{-1}hx=x$ and $g^{-1}h\in G_{x}$. Therefore, $gG_{x}=hG_{x}$. It is surjective as for any $y\in X$, there exists $g\in G$ s.t. $gx=y$ by transitivity of the group action.
>    
>    Lastly, it commutes with the $G$-action as: $$h\Psi(gG_{x})=hgx=\Psi(hgG_{x})$$
> 2. Consider $\Phi:G\to X,g\mapsto gx$, which is continuous as the group action is continuous. As $\Phi=\Psi \circ p$, $\Psi$ is continuous.
> 3. 
---
> [!lemma] Lemma 2
> Let $G$ be a topological group, $X$ a topological space and $\mu:G\times X\to X$ a continuous transitive group action. Then,
> 1. if $G$ is compact, then $X$ is compact.
> 2. if $G$ is connected, then $X$ is connected.

> [!proof]-
> Let $x\in X$. Then, from the transitivity, $\mu(G\times \{ x \})=X$. As $G\times \{ x \}$ is compact and connected if $G$ is compact and connected, $X$ is compact and connected.
> 
---