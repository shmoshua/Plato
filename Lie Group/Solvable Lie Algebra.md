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

> [!proof]-
> We have:
> 1. for $\delta\in \text{Der}(\mathfrak{g})$, $\delta([x,y])=[\delta(x),y]+[x,\delta(y)]\in [\mathfrak{g},\mathfrak{g}]$.
> 2. $\mathfrak{g}^{(1)}$ is an ideal in $\mathfrak{g}$ by construction. Then, for $\mathfrak{g}^{(\ell)}$, as $\mathfrak{g}^{(\ell-1)}$ is an ideal by induction hypothesis and $\mathfrak{g}^{(\ell)}=[\mathfrak{g}^{(\ell-1)},\mathfrak{g}^{(\ell-1)}]$ is a characteristic ideal in $\mathfrak{g}^{(\ell-1)}$ by 1, we have by [[Ideal (Lie Algebra)|Lemma 3]] $\mathfrak{g}^{(\ell)}$ is an ideal in $\mathfrak{g}$.
> 3. We have that: $\pi(\mathfrak{g}^{(1)})=\pi(\mathfrak{g})^{(1)}$. The rest is obvious.
> 4. We have $\mathfrak{g} / \mathfrak{n}$ is abelian if and only if $(0)=[\mathfrak{g} / \mathfrak{n},\mathfrak{g} / \mathfrak{n}]=[p(\mathfrak{g}),p(\mathfrak{g})]=p(\mathfrak{g}^{(1)})$ and $\mathfrak{g}^{(1)}\subseteq \mathfrak{n}$.
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
> 2. if $\mathfrak{h}\unlhd \mathfrak{g}$, then $\mathfrak{g}$ is solvable if and only if $\mathfrak{h}$ and $\mathfrak{g / h}$ are.

> [!proof]+
> We have:
> 1. Notice that $\mathfrak{h}^{(1)}\leq \mathfrak{g}^{(1)}$
---
##### Examples
> [!h] Example 1
> Let $\mathfrak{g}$ be the space of all $n\times n$ upper triangular matrices. Then, 
> 1. $\mathfrak{g}^{(1)}$ is the space of all $n\times n$ upper triangular matrices with zero diagonal.
> 2. $\mathfrak{g}^{(n)}=(0)$ and $\text{sol}(\mathfrak{g})=n$.
