#Definition #RepresentationTheory 
> [!definition]
> Let $V_{1},V_{2}$ be two [[Representation|representations]] of an [[associative algebra]] $A$. A ***homomorphism*** or an ***intertwining operator*** $\phi:V_{1}\to V_{2}$ is a linear operator s.t. $$\phi(av)=a\phi(v),\quad\forall a\in A,v\in V_{1}$$
- **Related definition**: $\text{Hom}_{A}(V_{1},V_{2})$ denotes the space of all homomorphisms between $V_{1},V_{2}$.
- **Related definition**: A homomorphism $\phi$ is a ***representation isomorphism***, if it is a vector space isomorphism. Then, $V_{1}$ and $V_{2}$ are called ***isomorphic***.
---
##### Properties
> [!lemma] Proposition 1
> Let $\phi:V_{1}\to V_{2}$ be a representation isomorphism. Then, $\phi ^{-1}$ is also a  representation isomorphism.

> [!proof]-
> We have that for all $a\in A$ and $v\in V_{2}$, $$\phi (a\phi ^{-1}(v))=a\phi(\phi ^{-1}(v))=av=\phi(\phi ^{-1}(av))$$Therefore, $a\phi ^{-1}(v)=\phi ^{-1}(av)$.
---
> [!lemma] Proposition 2
> For any $\phi\in \text{Hom}_{A}(V_{1},V_{2})$, 
> 1. $\text{ker }\phi$ is a [[Representation|subrepresentation]] of $V_{1}$ and
> 2. $\text{im }\phi$ is a [[Representation|subrepresentation]] of $V_{2}$.

> [!proof]-
> We have that for all $a\in A$ and $x\in \text{ker }\phi$ $$\phi(ax)=a\phi(x)=0$$Therefore, $ax\in\text{ker }\phi$. Similarly, for all $a\in A$ and $x\in V_{1}$, $$\phi(ax)=a\phi(x)$$and therefore, $a\phi(x)\in \text{Im }\phi$. 
---
> [!lemma] Proposition 3 (Schur's Lemma)
> Let $V_{1},V_{2}$ be representations of $A$ over any field $K$ (not necessarily [[Algebraic Closure|algebraically closed]]). Further $\phi:V_{1}\to V_{2}$ be a non-trivial representation homomorphism. Then, 
> 1. if $V_{1}$ is irreducible, $\phi$ is injective.
> 2. if $V_{2}$ is irreducible, $\phi$ is surjective.
> 3. if both $V_{1}$ and $V_{2}$ are irreducible, $\phi$ is an isomorphism.

> [!proof]-
> We have: 
> 1. $\text{ker }\phi$ is a subrepresentation of $V_{1}$, but as $\phi$ is non-trivial, $\text{ker }\phi=(0)$.
> 2. $\text{Im }\phi$ is a subrepresentation of $V_{2}$ but as $\phi$ is non-trivial, $\text{Im }\phi=V_{2}$.
---
> [!lemma] Proposition 4 (Schur's Lemma for Algebraically Closed Fields)
> Let $V$ be a finite-dimensional irreducible representation of an associative algebra $A$ over an [[Algebraic Closure|algebraically closed]] field $K$. Then, $$\text{Hom}_{A}(V)=K\cdot \text{id}_{\mathcal{H}}$$ 

> [!proof]-
> Let $\lambda$ be an eigenvalue of $\phi$, which exists as $K$ is algebraically closed. Then, $\phi-\lambda \text{id}_{V}\in \text{Hom}_{A}(V)$, however, it is not an isomorphism as $\det(\phi-\lambda \text{id}_{V}) =0$. Therefore, by Proposition 3, $\phi-\lambda \text{id}_{V}=0$.
- **Remark**: If $K=\mathbb{R}$, the statement is false. Consider $A=\mathbb{C}$ and $V=A$.
---
> [!lemma] Corollary 5 (Commutative Algebra have only 1-dimensional irreducible representation)
> Let $A$ be a [[Associative Algebra|commutative algebra]] over algebraically closed $K$. Then, every irreducible finite-dimensional representation $V$ of $A$ is $1$-dimensional.

> [!proof]-
> Let $V$ be irreducible. For any $a\in A$, $\rho(a)\in \text{Hom}_{A}(V)$, as: $$\rho(a)\rho(b)v=\rho(ab)v=\rho(ba)v=\rho(b)\rho(a)v$$Therefore, by Schur's lemma, $\rho(a)$ is a scalar operator for all $a\in A$. Hence, every subspace of $V$ is a subrepresentation. But $V$ is irreducible, so 0 and $V$ are the only subspaces of $V$. This means that $\text{dim }V=1$.

- **Remark**: Any $1$-dimensional representation $V$ is automatically irreducible.
---
##### Examples
> [!h] Example 1
> Let $A=K$. Then, representations of $A$ are $K$-vector spaces. Therefore, $V=A$ is the only irreducible and only indecomposable representation.
---
> [!h] Example 2
> Let $A:=K[X]$. As $A$ is commutative, by Corollary 5, the irreducible representations of $A$ are $1$-dimensional. Therefore, they are defined as: $(K,\rho_{\lambda})$ where $$\begin{array}{cccc} {\rho_{\lambda}:}&{K[X]}&\to&{K}\\&{p} &\mapsto & {p(\lambda)} \end{array}{}$$These representations are pairwise non-isomorphic.
---
> [!h] Example 3
> Let $A:=K[G]$ where $G$ is a group. Then, the representations coincide with [[Group Representation|group representations]].
---
> [!h] Example 4 (Central Character)
> Let $A$ be an algebra over $K$ (algebraically closed). 
> 1. For an irreducible finite-dimensional representation $V$ of $A$, then for any $z\in Z(A)$, $z$ acts  in $V$ by multiplication by some scalar $\chi_{V}(z)\in K$. This defines a homomorphism: $\chi_{V}:Z(A)\to K$.
> 2. Show that if $V$ is an indecomposable finite-dimensional representation of $A$, then for any $z\in Z(A)$, the operator $\rho(z)$ by which $z$ acts in $V$ has only one eigenvalue $\chi_{V}(z)$.
> 3. Does $\rho(z)$ in 2 have to be a scalar operator?

> [!proof]+
> We have:
> 1. for $z\in Z(A)$ and $a\in A$, $$\rho(z)\rho(a)v=\rho(za)v=\rho(az)v=\rho(a)\rho(z)v$$Then, $\rho(z)\in \text{Hom}_{A}(V)$ and therefore is scalar. Let the scalar be $\chi_{V}(z)$. Then, $$\chi_{V}(z_{1}z_{2})=$$