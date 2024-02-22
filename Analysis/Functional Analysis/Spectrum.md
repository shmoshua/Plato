#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a unital [[C-Algebra|$\mathbb{C}$-algebra]] and $x\in A$. Then, the ***spectrum*** of $x$ is:
> $$\text{Sp}_{A}(x):=\{ \lambda\in \mathbb{C}:x-\lambda e\notin G(A) \}$$
> If $A$ is non-unital, we define: $$\text{Sp}_{A}(x):=\text{Sp}_{A_{I}}(x)$$
- **Related definition**: The complement of a spectrum $\rho_{A}(x):=\mathbb{C} \backslash \text{Sp}_{A}(x)$ is called the ***resolvent set***.
---
##### Properties
> [!lemma] Theorem 1
> Let $A$ be a [[Banach algebra]] and $x\in A$. Then, $\text{Sp}_{A}(x)\subseteq \mathbb{C}$ is a  non-empty compact set and: $$r_{A}(x)=\max \{ \left| \lambda \right| :\lambda\in \text{Sp}_{A}(x) \}$$
---
##### Examples
> [!h] Example 1
> Let $A=\text{End}(V)$ where $V$ is a finite-dimensional $\mathbb{C}$-vector space. Then, for $T\in A$: 
> 1. $\text{Sp}_{A}(T)$ is the set of roots of the characteristic polynomial of $T$.
---
> [!h] Example 2
> Let $X$ be compact Hausdorff, then consider $A:=C(X)$ with $\|\cdot\|_{b}$. Then, for $f\in C(X)$, $$\text{Sp}_{A}(f)=\text{Im}(f)$$
---
