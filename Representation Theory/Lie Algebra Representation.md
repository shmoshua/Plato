#Definition #RepresentationTheory 

> [!definition]
> For a [[Lie algebra]] $\mathfrak{g}$, its ***Lie algebra representation*** is a vector space $V$ and a Lie-algebra homomorphism $\rho:\mathfrak{g}\to \text{End}(V)$, i.e. $$\rho([a,b])=[\rho(a),\rho(b)]=\rho(a)\rho(b)-\rho(b)\rho(a)$$
- **Related definition**: The ***tensor product*** of two Lie algebra representations $V,W$ is $V\otimes W$ with: $$\rho_{V\otimes W}(x)=\rho_{V}(x)\otimes \text{id}+\text{id}\otimes \rho_{W}(x)$$
- **Related definition**: For a Lie algebra representation $V$ of $\mathfrak{g}$, the ***dual representation*** is the dual space $V^{*}$ with $\rho_{V^{*}}(x)=-\rho_{V}(x)^{*}$.
---
##### Properties
> [!lemma] Theorem 1
> For a Lie algebra $\mathfrak{g}$, a Lie algebra representation $V$ is equivalent to the associative algebra representation of the [[universal enveloping algebra]] $\mathcal{U}(\mathfrak{g})$ of $\mathfrak{g}$.
---
##### Examples
> [!h] Example 1
> We have:
> 1. $V=0$ is a Lie algebra representation of any $\mathfrak{g}$.
> 2. For any vector space $V$, $\rho=0$ is a representation.
---
> [!h] Example 2 (Adjoint Representation)
> The ***adjoint representation*** is $V=\mathfrak{g}$ with $ab=[a,b]$. Then, $$\rho([a,b])c=[[a,b],c]=-[[b,c],a]-[[c,a],b]=-[\rho(b)c,a]+[\rho(a)c,b]=\rho(a)\rho(b)c-\rho(b)\rho(a)c$$given by the Jacobi identity, i.e. the Jacobi identity is equivalent to the existence of the adjoint representation.