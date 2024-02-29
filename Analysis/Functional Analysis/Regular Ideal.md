#Definition #FunctionalAnalysis 
> [!definition]
> Let $A$ be a commutative [[Banach algebra]]. An ideal $\mathfrak{a}\subseteq A$ is ***regular***, if there exists $u\in A$ s.t. $$ux-x\in \mathfrak{a},\quad\forall x\in A$$
- **Equivalent definition**: $\mathfrak{a}$ is regular if either $\mathfrak{a}=A$ or $\mathfrak{a}\subsetneq A$ and $A / \mathfrak{a}$ is [[C-Algebra|unital]].
---
##### Properties
> [!lemma] Proposition 1
> Let $A$ be a commutative Banach algebra and $\mathfrak{a}\subseteq A$ a proper regular ideal. Further, let $u\in A$ be a unit modulo $\mathfrak{a}$. Then, $$\|u-x\|\geq 1,\quad \forall x\in \mathfrak{a}$$

> [!proof]-
> Assume $x\in \mathfrak{a}$ s.t. $\|u-x\|<1$. Then, $$s:=\sum_{n=1}^{\infty}(u-x)^n$$converges absolutely.  Now, $u-x=s-s(u-x)=\underbrace{ s-su }_{\in \mathfrak{a} }+\underbrace{ sx }_{ \in \mathfrak{a} }\in \mathfrak{a}$. Therefore, $u\in \mathfrak{a}$ and $A  / \mathfrak{a}= (0)$This implies that $\mathfrak{a}=A$, which is a contradiction. 
---
> [!lemma] Proposition 2
> Let $\mathfrak{a}\subseteq A$ be regular and $\mathfrak{a}\subseteq \mathfrak{b}\subseteq A$ also an ideal. Then, $\mathfrak{b}$ is regular as well. 

> [!proof]-
> There exists $u\in A$ s.t. $ux-x\in \mathfrak{a}\subseteq \mathfrak{b}$ for all $x\in A$.
---
> [!lemma] Corollary 3
> We have: 
> 1. $\mathfrak{a}\subsetneq A$ is proper and regular, then $\overline{\mathfrak{a}}\subsetneq A$ is proper and regular.
> 2. $\mathfrak{a}\subseteq A$ is [[Maximal Ideal|maximal]] regular, then $\mathfrak{\overline{a}}=\mathfrak{a}$.

> [!proof]-
> We have: 
> 1. If $\mathfrak{a}\subseteq A$ is an ideal, $\overline{\mathfrak{a}}$ is an ideal due to the continuity of algebraic operations. Further, $\overline{\mathfrak{a}}$ is regular from Proposition 2. 
> 2. If $\mathfrak{a}=A$, then $\mathfrak{\overline{a}}=A$. Otherwise, $\mathfrak{a}\subseteq A$ is proper and regular. Therefore, $\overline{\mathfrak{a}}$ is proper and regular, but by the maximality, $\mathfrak{\overline{a}}=\mathfrak{a}$.
---
> [!lemma] Lemma 4
> Every regular and proper ideal $\mathfrak{a}\subseteq A$ is contained in some maximal regular ideal.

> [!proof]-
> Let $u\in A$ be a unit modulo $\mathfrak{a}$. For ideals $\mathfrak{a}\subseteq \mathfrak{b}\subseteq A$, the following are equivalent:
> 1. $\mathfrak{b}\subsetneq A$
> 2. $u\notin \mathfrak{b}$
> 
> Therefore, $$\mathcal{L}:=\{ \mathfrak{b}\subseteq A:\mathfrak{a}\subseteq \mathfrak{b}\subseteq A,\mathfrak{b}\text{ is an ideal}, u\notin \mathfrak{b} \}$$Let $\mathcal{K}\subseteq \mathcal{L}$ be a totally ordered subset in $\mathcal{L}$. Then, define $\mathfrak{L}:=\bigcup_{\mathfrak{b}\subseteq \mathcal{K}}^{}\mathfrak{b}\supseteq\mathfrak{a}$. Since $\mathcal{K}$ is totally ordered, $\mathfrak{L}$ is an ideal of $A$. Also, it is proper as otherwise, $u\in \mathfrak{L}$ which means $u\in \mathfrak{b}$ for some $\mathfrak{b}\in \mathcal{L}$, a contradiction. 
> 
> Therefore, by [[Axiom of Choice|Zorn's lemma]], $\mathcal{L}$ has a maximal element. 
---
> [!lemma] Corollary 5
> Let $A$ be a unital commutative Banach algebra. If $x\in A$ is not invertible, then $x$ is contained in a maximal ideal.

> [!proof]-
> Let $e\in A$ be the identity and consider the proper ideal $Ax$. Then, $e\notin Ax$, so $Ax$ is regular. Therefore, by Lemma 4, there exists a maximal regular ideal $\mathfrak{m}$ s.t. $x\in \mathfrak{m}.$
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
