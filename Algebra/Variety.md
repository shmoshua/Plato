#Algebra #Definition 

> [!definition]
> Let $K$ be a [[field]] and $S\subseteq K[x_{1},\dots,x_{n}]$. Then, $$V(S):=\{  x\in \mathbb{A}_{K}^n:f(x)=0, \forall f\in S \}\subseteq \mathbb{A}_{K}^n$$is called the ***zero locus*** of $S$, where $\mathbb{A}_{K}^n$ is the [[affine space]] over $K$. Subsets of $\mathbb{A}_{K}^n$ like these are called ***varities***.

^1a7b97

- **Related definition**: For any $X\subseteq \mathbb{A}_{K}^n$, the ***ideal*** of $X$ is defined as:$$I(X):=\{  f\in K[x_{1},\dots,x_{n}]:f(x)=0,\forall x\in X \}$$ ^d9dae1

---
##### Properties
> [!lemma] Proposition 1
> For $X\subseteq \mathbb{A}_{K}^n$, 
> 1. $I(X)\unlhd K[x_{1},\dots,x_{n}]$.

^35d70d

> [!proof]-
> We have:
> 1. for any $f\in I(X)$ and $g\in K[x_{1},\dots,x_{n}]$, $fg(x)=0$ for $x\in X$. Further, $I(X)$ is an additive subgroup.

^c6655d

---
##### Examples 
> [!h] Example 1
> We have:
> 1. $\varnothing$ and $\mathbb{A}_{K}^n$ are varieties as $V(1)$ and $V(0)$.
> 2. $V(x_{1}^{2}+x_{2}^{2}+1)\subseteq \mathbb{A}_{\mathbb{R}}^{2}$ is the unit circle.
> 3. $V(x_{1}x_{3},x_{2}x_{3})\subseteq \mathbb{A}_{\mathbb{R}}^3$ is the $x_{1}x_{2}$-plane.

^d6893c

---
##### Non-Examples
> [!h] Non-Example 1
> We have:
> 1. $\mathbb{Z}\subseteq \mathbb{A}_{\mathbb{C}}^1$ is not a variety.

^cde87b

> [!proof]+
> We have:
> 1. $I(\mathbb{Z})=(0)$ by Liouville's theorem. However, $V(0)=\mathbb{A}_{\mathbb{C}}^1$.

^cc24f3

