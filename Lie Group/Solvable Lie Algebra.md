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