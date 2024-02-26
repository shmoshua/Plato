#Definition #FunctionalAnalysis 
> [!definition]
> Let $A$ be a commutative [[Banach algebra]]. An ideal $\mathfrak{a}\subseteq A$ is ***regular***, if there exists $u\in A$ s.t. $$ux-x\in \mathfrak{a},\quad\forall x\in A$$
- **Equivalent definition**: $\mathfrak{a}$ is regular if either $\mathfrak{a}=A$ or $\mathfrak{a}\subsetneq A$ and $A / \mathfrak{a}$ is [[C-Algebra|unital]].
---
##### Examples
> [!h] Example 1
> We have:
> 1. Any ideal in a unital Banach algebra is regular.
> 2. For an algebra homomorphism $\chi:A\to \mathbb{C}$, $\text{ker }\chi$ is regular. 

> [!proof]-
> We have: 
> 1. If $\text{ker } \chi\neq A$, then $\chi(A)=\mathbb{C}$ and we can pick $u\in A$ with $\chi(u)=1$. Then, $ux-x\in \text{ker }\chi$ for all $x\in A$.
---
> [!h] Example 2
> For a [[locally compact Hausdorff space]] $X$ and a closed subset $E\subseteq X$, we define: $$\mathfrak{E}:=\{ f\in C_{0}(X):f|_{E}=0 \}$$Then, 
> 1. $\mathfrak{E}$ is an ideal in $C_{0}(X)$.
> 2. $\mathfrak{E}$ is regular if and only if $E$ is compact. (Urysohn's lemma)