#Definition #FunctionalAnalysis 
> [!definition]
> Let $A$ be a commutative [[Banach algebra]]. An ideal $\mathfrak{a}\subseteq A$ is ***regular***, if there exists $u\in A$ s.t. $$ux-x\in \mathfrak{a},\quad\forall x\in A$$
- **Equivalent definition**: $\mathfrak{a}$ is regular if either $\mathfrak{a}=A$ or $\mathfrak{a}\subsetneq A$ and $A / \mathfrak{a}$ is [[C-Algebra|unital]].
---
##### Properties
> [!lemma] Proposition 1
> Let $A$ be a commutative Banach algebra and $\mathfrak{a}\subseteq A$ a proper regular ideal. Further, let $u\in A$ be a [[unit]] modulo $\mathfrak{a}$. Then, $$\|u-x\|\geq 1,\quad \forall x\in \mathfrak{a}$$

> [!proof]+
> Assume $x\in \mathfrak{a}$ s.t. $\|u-x\|<1$. Then, $$s:=\sum_{n=1}^{\infty}(u-x)^n$$converges absolutely.  Now, $u-x=s-s(u-x)=s-su+sx$
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
