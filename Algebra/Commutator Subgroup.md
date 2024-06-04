#Definition #Algebra #LieGroups 

> [!definition]
> Let $G$ be a [[group]]. For $g,h\in G$, the ***commutator*** is defined as $[g,h]=g^{-1}h^{-1}gh\in G$. Then, the ***commutator subgroup*** of $G$ is defined as: $$[G,G]:=\left\langle [g,h]:g,h\in G \right\rangle\leq G$$
- ***Related definition***: A ***derived series*** of a group $G$ is $(G^{(i)})_{i}$ where $G^{(0)}=G$ and $G^{(i+1)}=[G^{(i)},G^{(i)}]$.
---
##### Properties
> [!lemma] Lemma 1
> We have:
> 1. Let $\pi:G\to H$ be a [[group homomorphism]]. Then, $\pi(G^{(i)})=\pi(G)^{(i)}$.
> 2. For $N\unlhd G$, $G / N$ is abelian if and only if $[G,G]\leq N$.
> 3. $[G,G]\unlhd G$

> [!proof]-
> We have:
> 1. Follows from $\pi([g,h])=[\pi(g),\pi(h)]$. Therefore, $\pi(G^{(1)})=\pi(G)^{(1)}$ and the statement follows.
> 2. Let $N\unlhd G$ and $\pi:G\to G / N$ the canonical projection. If it is abelian, then: $$\pi([G,G])=[\pi(G),\pi(G)]=[G / N,G / N]=\{ N \}$$Therefore, $[G,G]\leq N$. Conversely, if $[G,G]\leq N$, then: $[G /N, G / N]=\{ N \}$ and $G / N$ is abelian.
> 3. We have that for $g,h\in G$ and $x\in G$, $$x[g,h]x ^{-1}=xg^{-1}h^{-1}ghx ^{-1}=[x ^{-1},g][g,hx ^{-1}]\in [G,G]$$ 
---
> [!lemma] Lemma 2
> Let $G$ be a topological group. If $G$ is connected, then 
> 1. $[G,G]$ is connected and
> 2. $G^{(i)}$ is connected for all $i\geq 1$.

> [!proof]-
> As $G\times G\to G,(g,h)\mapsto[g,h]$ is a continuous map, $V:=\{ [g,h]:g\in G,h\in G \}$ is connected. Then, $V^n$ is also connected and as $e\in V^n$ for all $n\geq 1$, $$[G,G]=\bigcup_{n\geq 1}^{}V^n$$is connected.
---
