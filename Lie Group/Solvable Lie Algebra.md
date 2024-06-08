#Definition #LieGroups 

> [!definition]
> A [[Lie algebra]] $\mathfrak{g}$ is ***solvable*** if there exists a sequence: $$\mathfrak{g}=\mathfrak{g}_{0}\supseteq \mathfrak{g}_{1}\supseteq\dots \supseteq\mathfrak{g}_{r}=(0)$$s.t. $\mathfrak{g}_{i}$ is an ideal in $\mathfrak{g}_{i-1}$ and $\mathfrak{g}_{i-1} /\mathfrak{g}_{i}$ is an abelian Lie algebra.
- **Related definition**: The ***commutator subalgebra*** of $\mathfrak{g}$ is defined as: $[\mathfrak{g},\mathfrak{g}]:=\text{span}\{ [x,y]:x,y\in \mathfrak{g} \}$.
- **Related definition**: $(\mathfrak{g}^{(\ell)})_{\ell}$ is called the ***derived series*** where $\mathfrak{g}^{(\ell)}:=[\mathfrak{g}^{(\ell-1)},\mathfrak{g}^{(\ell-1)}]$ and $\mathfrak{g}^{(0)}:=\mathfrak{g}$. 
---
##### Properties
> [!lemma] Lemma 1
> We have that:
> 1. $[\mathfrak{g},\mathfrak{g}]$ is a [[Ideal (Lie Algebra)|characteristic ideal]] in $\mathfrak{g}$. 
> 2. $\mathfrak{g}^{(\ell)}$ is an ideal in $\mathfrak{g}$ for all $\ell\geq 1$.
> 3. for a Lie algebra homomorphism $\pi:\mathfrak{g}\to \mathfrak{h}$, $\pi(\mathfrak{g}^{(i)})=\pi(\mathfrak{g})^{(i)}$.
> 4. for $\mathfrak{n}\unlhd \mathfrak{g}$, $\mathfrak{g} / \mathfrak{n}$ is abelian if and only if $\mathfrak{n}\geq \mathfrak{g}^{(1)}$.
> 5. for solvable ideals $\mathfrak{a},\mathfrak{b}\unlhd \mathfrak{g}$, $\mathfrak{a}+\mathfrak{b}\unlhd \mathfrak{g}$.

> [!proof]-
> We have:
> 1. for $\delta\in \text{Der}(\mathfrak{g})$, $\delta([x,y])=[\delta(x),y]+[x,\delta(y)]\in [\mathfrak{g},\mathfrak{g}]$.
> 2. $\mathfrak{g}^{(1)}$ is an ideal in $\mathfrak{g}$ by construction. Then, for $\mathfrak{g}^{(\ell)}$, as $\mathfrak{g}^{(\ell-1)}$ is an ideal by induction hypothesis and $\mathfrak{g}^{(\ell)}=[\mathfrak{g}^{(\ell-1)},\mathfrak{g}^{(\ell-1)}]$ is a characteristic ideal in $\mathfrak{g}^{(\ell-1)}$ by 1, we have by [[Ideal (Lie Algebra)|Lemma 3]] $\mathfrak{g}^{(\ell)}$ is an ideal in $\mathfrak{g}$.
> 3. We have that: $\pi(\mathfrak{g}^{(1)})=\pi(\mathfrak{g})^{(1)}$. The rest is obvious.
> 4. We have $\mathfrak{g} / \mathfrak{n}$ is abelian if and only if $(0)=[\mathfrak{g} / \mathfrak{n},\mathfrak{g} / \mathfrak{n}]=[p(\mathfrak{g}),p(\mathfrak{g})]=p(\mathfrak{g}^{(1)})$ and $\mathfrak{g}^{(1)}\subseteq \mathfrak{n}$.
> 5. Of coure, $\mathfrak{a}+\mathfrak{b}$ is a vector subspace of $\mathfrak{g}$. Further for any $a\in \mathfrak{a},b\in \mathfrak{b},x\in \mathfrak{g}$, $$[x,a+b]=[x,a]+[x,b]\in \mathfrak{a}+\mathfrak{b}$$
---
> [!lemma] Lemma 2
> $\mathfrak{g}$ is solvable if and only if $\mathfrak{g}^{(r)}=(0)$ for some $r\geq 1$. 

> [!proof]-
> We have:
> - (2=>1): Then, from Lemma 1.1, $\mathfrak{g}^{(i+1)}\unlhd \mathfrak{g}^{(i)}$ and $\mathfrak{g}^{(i)} / \mathfrak{g}^{(i+1)}$ is abelian. Therefore, $\mathfrak{g}^{(r)}\unlhd \dots\unlhd \mathfrak{g}^{(0)}$ is the desired sequence and $\mathfrak{g}$ is solvable.
> - (1=>2): Assume $\mathfrak{g}$ is solvable and we have a sequence $\{ e \}=\mathfrak{g}_{r}\unlhd \dots\unlhd \mathfrak{g}_{0}=\mathfrak{g}$. We claim that $\mathfrak{g}^{(i)}\leq \mathfrak{g}_{i}$. We will show this by induction. $\mathfrak{g}^{(0)}=\mathfrak{g}\leq \mathfrak{g}=\mathfrak{g}_{0}$ holds automatically. For $i\geq 1$, by Lemma 1, $$\mathfrak{g}_{i}\geq \mathfrak{g}_{i-1}^{(1)}\geq (\mathfrak{g}^{(i-1)})^{(1)}=\mathfrak{g}^{(i)}$$Therefore, $\mathfrak{g}^{(r)}\leq \mathfrak{g}_{r}=(0)$.
- **Related definition**: The ***solvability length*** of $\mathfrak{g}$ is $\text{sol}(\mathfrak{g}):=\min\{ r\geq 1:\mathfrak{g}^{(r)}=(0)\}$.
---
> [!lemma] Lemma 3
> We have:
> 1. if $\mathfrak{h}\leq \mathfrak{g}$, then $\mathfrak{h}$ is solvable if $\mathfrak{g}$ is.
> 2. if $\mathfrak{h}\unlhd \mathfrak{g}$, then $\mathfrak{g}$ is solvable if and only if $\mathfrak{h}$ and $\mathfrak{g / h}$ are. In which case, we have: $$\text{sol}(\mathfrak{g})\leq \text{sol}(\mathfrak{h})+\text{sol}(\mathfrak{g} / \mathfrak{h})$$

> [!proof]-
> We have:
> 1. Notice that $\mathfrak{h}^{(1)}\leq \mathfrak{g}^{(1)}$. Therefore, $\mathfrak{h}^{(i)}\leq \mathfrak{g}^{(i)}$ for all $i\geq 1$ and from Lemma 2, we have $\mathfrak{h}^{(r)}\leq\mathfrak{g}^{(r)}=(0)$ for some $r\geq 1$. This proves that $\mathfrak{h}$ is solvable.
> 2. Let $\pi:\mathfrak{g}\to \mathfrak{g} / \mathfrak{h}$ be the canonical projection. Then, $\pi(\mathfrak{g}^{ (i)})=(\mathfrak{g} / \mathfrak{h})^{(i)}$ by Lemma 1.3 and $\mathfrak{h}^{(i)}\leq \mathfrak{g}^{(i)}$. Therefore, if $\mathfrak{g}$ is solvable, then $\mathfrak{h}$ and $\mathfrak{g} / \mathfrak{h}$ are.
>    
>    Conversely, let $m\geq 1$ with $(0)=(\mathfrak{g} / \mathfrak{h})^{(m)}=\pi(\mathfrak{g}^{(m)})$. Then, $\mathfrak{g}^{(m)}\leq \mathfrak{h}$ and if $\mathfrak{h}^{(r)}=(0)$, then $\mathfrak{g}^{(m+r)}\leq \mathfrak{h}^{(r)}=(0)$.
---
> [!lemma] Theorem 4 (Solvable Lie groups and Lie algebras)
> Let $G$ be a connected Lie group. Then, TFAE:
> 1. $\mathfrak{g}$ is solvable.
> 2. $G$ is a solvable group.

> [!proof]-
> We have:
> 1. (2=>1): By [[Solvable Group|Theorem 1]], there exists: $$\{ e \}=G_{r}\unlhd \dots\unlhd G_{0}=G$$where $G_{i} / G_{i+1}$ is abelian and $G_{i}$ are closed connected. By [[Lie Group|closed subgroup theorem]], $G_{i}$ are Lie groups and let $\mathfrak{g}_{i}$ be their respective Lie algebras. By [[Ideal (Lie Algebra)|Proposition 2]], $\mathfrak{g}_{i}\unlhd \mathfrak{g}_{i-1}$. Then, by [[Lie Group|Quotient Manifold Theorem corollary]], $\text{Lie}(G_{i-1} / G_{i})=\mathfrak{g}_{i-1} / \mathfrak{g}_{i}$ and as $G_{i-1} / G_{i}$ is connected as a continuous image, by [[Lie Algebra|Proposition 4]], $\mathfrak{g}_{i-1} / \mathfrak{g}_{i}$ is abelian and $\mathfrak{g}$ is solvable.
> 2. (1=>2): We prove by induction on $r:=\text{sol}(\mathfrak{g})$. If $r=1$, then $\mathfrak{g}$ is abelian and as $G$ is connected by [[Lie Algebra|Proposition 4]], $G$ is abelian and $\text{sol}(G)=1$. 
>    
>    If $r\geq 2$, then $(0)\neq \mathfrak{g}^{(r-1)}\unlhd \mathfrak{g}$ by Lemma 1.2. Then, by [[Ideal (Lie Algebra)|Proposition 2.2]], $\exp(\mathfrak{g}^{(r-1)})\unlhd G$. Moreover, as $\mathfrak{g}^{(r-1)}$ is abelian, $\exp(\mathfrak{g}^{(r-1)})$ is abelian too by [[Lie Algebra|Proposition 4]]. Then, its closure $N:=\overline{\exp(\mathfrak{g}^{(r-1)})}$ is also normal, abelian and connected by [[Topological Group|Proposition 2.1]] and [[Connected Space|Lemma 2.1]]. Then, $\mathfrak{n}\unlhd\mathfrak{g}$ by [[Ideal (Lie Algebra)|Proposition 2.1]] and it is clear that $\mathfrak{g}^{(r-1)}\leq \mathfrak{n}$. Therefore, $\text{sol}(\mathfrak{n})\leq r-1$. As the Lie algebra of $G / N$ is $\mathfrak{g} / \mathfrak{n}$, we can prove that $G$ is solvable by the inverse image of $\pi:G\to G / N$, similarly to the proof of  [[Solvable Group|Solvable Topological Group Theorem 1]].
---
> [!lemma] Theorem 5 (Lie, 1st)
> Let $\mathfrak{g}$ be a solvable Lie algebra. Further, let $\rho:\mathfrak{g}\to \mathfrak{gl}(V)$ be a [[Lie group representation]] to a finite dimensional complex vector space $V$. Then, 
> 1. there exists a basis of $V$ s.t. $\rho(x)$ is upper triangular w.r.t. the basis for all $x\in \mathfrak{g}$.

> [!proof]-
> Analogous to [[Lie Group|1st Theorem of Lie]].
---
##### Examples
> [!h] Example 1
> Let $\mathfrak{g}$ be the space of all $n\times n$ upper triangular matrices. Then, 
> 1. $\mathfrak{g}^{(1)}$ is the space of all $n\times n$ upper triangular matrices with zero diagonal.
> 2. $\mathfrak{g}^{(n)}=(0)$ and $\text{sol}(\mathfrak{g})=n$.
---
> [!h] Example 2 (Nilpotent Lie Algebras are solvable)
> Let $\mathfrak{g}$ be a nilpotent Lie algebra. Then, 
> 1. $\mathfrak{g}^{(k)}\leq C^k(\mathfrak{g})$ for all $k\geq 1$. 
> 2. $\mathfrak{g}$ is solvable.

^5ae9c5

> [!proof]-
> We have that: 
> 1. $\mathfrak{g}^{(1)}=[\mathfrak{g},\mathfrak{g}]\subseteq C^1(\mathfrak{g})$ and $$\mathfrak{g}^{(k)}=[\mathfrak{g}^{(k-1)},\mathfrak{g}^{(k-1)}]\subseteq[\mathfrak{g},\mathfrak{g}^{(k-1)}]\subseteq[\mathfrak{g},C^{k-1}(\mathfrak{g})]=C^k(\mathfrak{g})$$
> 2. By [[Nilpotent Lie Algebra|Propsotion 2]] and Lemma 2, as $\mathfrak{g}^{(r)}\leq C^r(\mathfrak{g})=(0)$ for some $r\geq 1$. 

^dc3d92

---
