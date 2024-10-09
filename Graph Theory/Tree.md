#Definition #GraphTheory 

> [!definition]
> A ***tree*** is an acyclic [[Path|connected]] [[graph]].

- **Related definition**: For a tree $T=(V,E)$, any vertex $v\in V$ with $d(v)=1$ is called  a ***leaf***.

---
##### Properties
> [!lemma] Theorem 1
> Let $G=(V,E)$ be a non-empty graph. TFAE:
> 1. $G$ is a tree.
> 2. $G$ is connected and $\left| E \right|=\left| V \right|-1$.
> 3. $G$ is acyclic and $\left| E \right|=\left| V \right|-1$
> 4. for all $x,y\in V$ there exists exactly one $(x,y)$-path.

> [!proof]+
> We have:
> 1. (1=>2): $G$ is connected by definition. 
---
> [!lemma] Lemma 1
> Let $T=(V,E)$ be a finite tree with $\left| V \right|\geq 2$. Then, 
> 1. $T$ has at least 2 leaves.
> 2. for any leaf $v\in V$, $T \backslash \{ v \}$ is also a tree.

> [!proof]+
> We have that:
> 1. 