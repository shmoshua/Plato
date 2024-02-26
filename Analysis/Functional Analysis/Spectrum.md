#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a unital [[C-Algebra|$\mathbb{C}$-algebra]] and $x\in A$. Then, the ***spectrum*** of $x$ is:
> $$\text{Sp}_{A}(x):=\{ \lambda\in \mathbb{C}:x-\lambda e\notin G(A) \}$$
> If $A$ is non-unital, we define: $$\text{Sp}_{A}(x):=\text{Sp}_{A_{I}}(x)$$
- **Related definition**: The complement of a spectrum $\rho_{A}(x):=\mathbb{C} \backslash \text{Sp}_{A}(x)$ is called the ***resolvent set***.
---
##### Properties
> [!lemma] Theorem 1
> Let $A$ be a [[Banach algebra]] and $x\in A$. Then, $\text{Sp}_{A}(x)\subseteq \mathbb{C}$ is a  non-empty compact set and: $$r_{A}(x)=\max \{ \left| \lambda \right| :\lambda\in \text{Sp}_{A}(x) \}=\|x\|_{\text{sp}}$$

> [!proof]+
> Wlog we may assume that $A$ is unital.
> 1. **Show that $\text{Sp}_{A}(x)\subseteq \{ \lambda\in \mathbb{C}:\left| \lambda \right|\leq r_{A}(x) \}$**:
>    Assume $\left| \lambda \right|>r_{A}(x)$. Then, $r_{A}(x) / \left| \lambda \right|<1$. By definition, we have: $$\frac{r_{A}(x)}{\left| \lambda \right| }=r_{A}\left( \frac{x}{\lambda} \right)$$ Therefore, $e-x / \lambda$ is invertible by [[Spectral Radius|Lemma 2]]. As $\lambda e$ is invertible as well, the product $\lambda e-x$ is invertible, i.e. $\lambda\notin \text{Sp}_{A}(x)$.
> 2. **Show that $\text{Sp}_{A}(x)$ is compact**:$$\text{Sp}_{A}(x)=\{ \lambda\in \mathbb{C}: x-\lambda e\in A \backslash G(A) \}$$Therefore, $\text{Sp}_{A}(x)$ is the inverse image of the closed subset $A \backslash G(A)$ under the continuous map $\lambda\mapsto x-\lambda e$. This proves that $\text{S}$
---
##### Examples
> [!h] Example 1
> Let $A=\text{End}(V)$ where $V$ is a finite-dimensional $\mathbb{C}$-vector space. Then, for $T\in A$: 
> 1. $\text{Sp}_{A}(T)$ is the set of roots of the characteristic polynomial of $T$.
---
> [!h] Example 2
> Let $X$ be compact Hausdorff, then consider $A:=C(X)$ with $\|\cdot\|_{b}$. Then, for $f\in C(X)$, $$\text{Sp}_{A}(f)=\text{Im}(f)$$
---
