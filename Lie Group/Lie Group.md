#Definition #LieGroups 

> [!definition]
> A ***Lie group*** is a [[topological group]] $G$ endowed with a [[Smooth Manifold|smooth manifold structure]] s.t. 
> 1. the multiplication $m:G\times G\to G$ is smooth and
> 2. the inverse $i:G\to G$ is smooth.
- **Related defintion**: For Lie groups $G,H$, a ***Lie group homomorphism*** is a smooth group homomorphism $G\to H$. It is a ***Lie group isomorphism*** if it's bijective and the inverse is also a Lie group homomorphism. 
---
##### Properties
> [!lemma] Proposition 1
> For a Lie group $G$ and a subgroup $H\leq G$ that is also a [[submanifold|regular submanifold]], 
> 1. $H$ is a Lie group with smooth structure induced by $\{ (U\cap H,\varphi|_{U\cap H}) \}$.
> 2. $H$ is closed in this case.

> [!proof]+
> We have that $H\leq G$ and by [[Topological Group|Proposition 2.1]], $\overline{H}\leq G$. 
> 1. **Claim: every $p\in H$ has a neighborhood $V\subseteq G$ s.t. $H$ is closed in $V$, i.e. $H\cap V=\overline{H}\cap V$.**
> 	Fix $p\in H$. Let $(U,\varphi)$ be a chart at $p$. Then, $\varphi|_{H}:U\cap H\to \mathbb{R}^n$ is a chart of $p$ in $H$. Let $h:=\varphi \circ\varphi|_{H}^{-1}$. Let further $B:=B_{<1}(0)\subseteq \mathbb{R}^n$. Then, $h(B)$ is open in $\varphi(N)$ and there exists $W\subseteq \mathbb{R}^{m}$ open s.t. $W\cap \varphi(N)=h(B)$. As $\overline{B}$ is compact, $h(\overline{B})$ is compact and hence closed. Then, $$h(B)\subseteq W\cap h(\overline{B}) \subseteq W\cap\varphi(N)=h(B)$$Therefore, $W\cap h(\overline{B})=W\cap\varphi(N)$ and $V:=\varphi ^{-1}(W)\subseteq G$ is a neighborhood of $p$ s.t. $V$
> 
> By Lemma, every ℎ∈𝐻ℎ∈� has a neighborhood 𝑉⊂𝐺�⊂� so that 𝐻∩𝑉=𝐻⎯⎯⎯⎯⎯⎯∩𝑉�∩�=�¯∩�. By part (1), the diffeomorphism given by right multiplication by 𝑥� sends this set to 𝐻𝑥∩𝑉𝑥=𝐻⎯⎯⎯⎯⎯⎯∩𝑉𝑥��∩��=�¯∩��, which is contained in 𝐻𝑥�� and is open in 𝐻⎯⎯⎯⎯⎯⎯�¯; this shows that 𝐻𝑥�� is open.
---
##### Examples
> [!h] Example 1
> A discrete group is a Lie group if and only if it is countable, in which case the dimension is $0$.

> [!proof]-
> If it is not countable, then it is not second countable.
---
> [!h] Example 2
> We have the following Lie groups:
> 1. $(\mathbb{R}^n,+)$
> 2. $(\mathbb{R}^\times,\cdot),(\mathbb{C}^\times,\cdot)$
> 3. $\text{GL}(n,\mathbb{R})$ is a $n^2$ dimensional Lie group with the multiplication as polynomial and inversion as rational.
> 4. $\text{GL}(n,\mathbb{C})$ is a $n^2$ dimensional Lie group with the multiplication as polynomial and inversion.
---
> [!h] Example 3
> $\text{Homeo}(X)$ is generally not a Lie group as it is not locally compact generally, but topological manifolds are.
---
> [!h] Example 4
> For a [[proper metric space]] $X$, 
> 1. $\text{Iso}(X)$ can be a Lie group but not always.
> 2. $\text{Iso}(\mathbb{R}^n)$ is a Lie group w.r.t. the euclidean distance.
> 3. $\text{Iso}(M)$ is a Lie group for a [[Riemannian manifold]] $M$.
---
> [!h] Example 5
> From [[Submanifold|Example 1]] and Proposition 1,
> 1. $\text{SL}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a Lie group.
> 2. $\text{O}(n,\mathbb{R})\leq \text{GL}(n,\mathbb{R})$ is a Lie group.
> 3. $\text{O}(p,q,\mathbb{R})\leq \text{GL}(p+q,\mathbb{R})$ is a Lie group.
> 4. $\text{SL}(n,\mathbb{C})\leq \text{GL}(n,\mathbb{C})$ is a Lie group.
> 5. $\text{U}(n,\mathbb{C})\leq \text{GL}(n,\mathbb{C})$ is a Lie group.
---
