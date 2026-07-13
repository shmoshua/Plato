#Definition #AlgebraicGeometry 

> [!definition]
> A ***ringed space*** is a [[topological space]] $X$ together with a [[sheaf]] $\mathcal{O}_{X}$ of rings, called the ***structure sheaf***.
- **Related definition**: Let $f:X\to Y$ be a map of ringed spaces.
	1. For any map $\varphi:U\to K$ where $U$ is open, $f^{*}\varphi:=\varphi \circ f:f^{-1}(U)\to K$ is the ***pullback*** of $\varphi$ by $f$.
	2. $f$ is the ***morphism of ringed spaces*** if it is continuous and if for all open $U\subseteq Y$ and $\varphi\in \mathcal{O}_{Y}(U)$, we have $f^{*}\varphi\in \mathcal{O}_{X}(f^{-1}(U))$. In other words, $$f^{*}:\mathcal{O}_{Y}(U)\to \mathcal{O}_{X}(f^{-1}(U)),\quad \varphi\mapsto f^{*}\varphi$$is a $K$-algebra homomorphism.
	3. $f$ is an ***isomorphism*** if it has an inverse morphism.
- **Remark**: The composition and restriction of morphisms is a morphism.
---
##### Properties
> [!lemma] Lemma 1 (Gluing Property for Morphisms)
> Let $f:X\to Y$ be a morphism of ringed s
> 