#Definition #Algorithms #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an connected [[graph|undirected graph]] with weights $w: E\to \mathbb{R}_{\geq 0}$. A ***minimum spanning tree*** is given by: $$T^{*}\in \underset{ T\text{ spanning tree} }{ \arg\min }w(T)$$
---
##### Properties
> [!lemma] Lemma 1
> Let $G$ have unique edge weights and let $T$ be a MST of $G$.
> 1. $T$ is unique. -
> 2. For any cut $(S, V \backslash S)$, $e\in \arg\min_{e\in E(S , V \backslash S)}w(e)$ is in $T$.
> 3. For any cycle $C$, $e\in \arg\max_{e\in E(S , V \backslash S)}w(e)$ is not in $T$.

> [!proof]+
> We have:
> 1. Assume there exist $T_{1},T_{2}$ different MSTs for $G$. Let $e\in T_{1}$ that is not in $T_{2}$. Then, $T_{2}\cup \{ e \}$ contains a cycle $C$. We have the two cases:
> 	1. There is at least one edge $f\neq e$ in $C$ with $w(f)>w(e)$. Then, by removing $f$ from $T_{2}$ and adding $e$ instead, we have a spanning tree with less weight, which is a contradiction.
> 	2. For all edges $f\neq e\in C$, we have that $w(f)<w(e)$. Then, there exists one edge $f\neq e\in C$ that can replace $e$ in $T_{1}$ for a lower weight, which is a contradiction.
> 2. Assume we have a cut $(S, V\backslash S)$ with minimum edge $e$ s.t. $e\notin T$. Let $f\in T\cap E(S , V \backslash S)$. Then, we have that $w(e)<w(f)$ and $T\cup \{ e \} \backslash \{ f \}$ has a lower weight than $T$, which is a contradiction.
> 3. Similar to 2.

---
