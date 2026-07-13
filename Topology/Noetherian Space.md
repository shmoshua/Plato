#Definition #AlgebraicGeometry 

> [!definition]
> Let $X$ be a [[topological space]].
> 1. $X$ is ***Noetherian*** if there is no infinite strictly decreasing chain of closed subsets: $$X_{0}\supsetneq X_{1}\supsetneq \dots$$
---
##### Properties
> [!lemma] Proposition 1
> Every Noetherian space is compact.


> [!proof]-
> Let $\{ U_{i} \}_{i\in I}$ be an open cover of a Noetherian space $X$. Assume that there exists no finite subcover. Pick $U_{1}$ from the cover. Since there is no finite subcover, $U_{1}\neq X$. Let $V_{1}:= X \backslash U_{1}$. 
> 
> Then, there exists a point $U_{2}$ that covers a point in $V_{1}$. Then, $V_{2}:= V_{1}\backslash U_{2}$ gives us $V_{1}\supsetneq V_{2}$. Continuing this we can find a strictly decreasing chain of closed subsets which is a contradiction.

- **Corollary**: Every open subset of an affine variety is compact in the [[Zariski topology]].
---
##### Examples

> [!h] Example 1
> An affine [[variety]] $X$ is a Noetherian space.


> [!proof]-
> Let $X$ be an affine variety and let there be an infinite strictly decreasing chain of affine subvarieties: $$X_{0}\supsetneq X_{1}\supsetneq X_{2}\supsetneq\dots$$This induces an increasing chain: $$I(X_{0})\subsetneq I(X_{1})\subsetneq \dots$$which cannot exist as $A(X)$ is [[Noetherian and Artinian Module|Noetherian]].



Let $n\le \text{codim}_{X}(a)$, i.e. there exists a chain $\{ a \}\subseteq Y_{0}\subsetneq\dots \subsetneq Y_{n}\subseteq X$ of irreducible closed subsets. However, $Y_{n}=\bigcup_{i}^{}(X_{i}\cap Y_{n})$ is a union of closed sets in $Y_{n}$ and as $Y_{n}$ is irreducible, $Y_{n}=X_{i}\cap Y_{n}$ for some $i\in[r]$ and $Y_{n}\subseteq X_{i}$. Hence, our chain is also a chain of irreducible closed subsets in $\text{dim} X_{i}$. Hence, $n\le \max \text{dim} X_{i}$ where $a\in X_{i}$.

Conversely, let $a\in X_{i}$. If $n\le \text{dim} X_{i}$, then there exists a chain $\{ a \}\subseteq Y_{0}\subsetneq\dots \subsetneq Y_{n}\subseteq X_{i}$. As $X_{i}$ is closed, this is also a chain in $X$. Hence, $n\le \text{codim}_{X}(a)$.
