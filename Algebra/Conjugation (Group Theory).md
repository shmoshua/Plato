#Definition #Algebra

> [!definition]
> The ***conjugation*** is defined by the [[Group Action|group action]] $G \curvearrowright G$, s.t. 
> $$a \circ  x=ax  a^{-1}$$
- $[x]=\{ axa^{-1}:a\in G \}$.
- $\text{St}_{G}(x)=\{ a\in G:ax=xa \}=$ [[Centralizer and Normalizer|$Z_{G}(x)$]].
- $\left| [x] \right|=[G:\text{St}_{G}(x)]$. 
- $x$ is a [[Fixed Point of a Group|fixed point]] $\iff$ $x\in$ [[Center of a group|$Z(G)$]].
---
##### Properties
> [!lemma] Proposition 1
> Let $[x_{ 1}],\dots,[x_{n}]$ be $n$ different conjugation classes with more than one element. Then,
> $$|G| = \left| Z(G) \right| +\sum_{i=1}^{n}\left| [x_{i}] \right| =|Z(G)|+\sum_{i=1}^{n}[G:Z_{G}(x_{i})]$$ 
> where $Z(G)$ is the union of conjugation classes with 1 element.

>[!proof]-
> We have that $a\in Z(G)\iff |[a]|=1$. Further, $G$ can be decomposed into pairwise disjoint conjugation classes.
---
##### Examples

