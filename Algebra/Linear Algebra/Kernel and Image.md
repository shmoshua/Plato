#Definition #LST #LinearAlgebra 

> [!definition]
> Let $\mathcal{A}:U\to V$ be linear. The ***null space*** of $\mathcal{A}$ is the set 
> $$\text{Null}(\mathcal{A}):=\{ u\in U | \mathcal{A}(u)=\theta_{V} \}\subseteq U$$
> and the ***range space*** of $\mathcal{A}$ is the set $$\text{Range}(\mathcal{A}):=\{ v\in V: \exists u\in U:v=\mathcal{A}(u) \}\subseteq V$$

- **Remark**: Null spaces are [[Vector Subspace| linear subspaces]] of $(U,F)$ and range spaces are linear subspaces of $(V,F)$.
---
##### Properties
> [!lemma] Theorem NullRange.1
> Let $\mathcal{A}:U \to V$ be a linear map and let $b\in V$.
> 1. $\mathcal{A}$ is surjective, if and only if $\text{Range}(\mathcal{A})=V$.
> 2. If $b\in \text{Range}(\mathcal{A})$ and for some $u_{0}\in U$ we have $\mathcal{A}(u_{0})=b$, then for all $u\in U$: $$\mathcal{A}(u)=b \iff u=u_{0}+z$$ where $z\in \text{Null}(\mathcal{A})$.
> 3. If $b\in \text{Range}(\mathcal{A})$, there exists a unique $u\in U$ s.t. $\mathcal{A}(u)=b$ if and only if $\text{Null}(\mathcal{A})=\{ \theta_{U} \}$, i.e. $\mathcal{A}$ is injective if and only if $\text{Null}(\mathcal{A})=\{ \theta_{U} \}$.

> [!proof]-
> We have:
> 1. Follows from the definition.
> 2. =>: Let $\mathcal{A}(u)=b$. Then, $\mathcal{A}(u-u_{0})=\mathcal{A}(u)-\mathcal{A}(u_{0})=b-b=\theta_{V}$. Therefore, $z:=u-u_{0}\in \text{Null}(\mathcal{A})$.
>    <=: Let $z\in \text{Null}(\mathcal{A})$. Then, $\mathcal{A}(u)=\mathcal{A}(u_{0})+\mathcal{A}(z)=b+\theta_{V}=b$
> 3. Follows from 2.
---
