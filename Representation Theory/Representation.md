#Definition #RepresentationTheory 

> [!definition]
> A ***representation*** of an [[associative algebra]] $A$ is a tuple $(\rho,V)$ where:
> 1. $V$ is a [[vector space]].
> 2. $\rho:A\to \text{End}(V)$ is an [[algebra homomorphism]].
- **Remark**: A representation is also called a ***left $A$-module***. A ***right $A$-module*** is a vector space $V$ equipped with an antihomomorphism $\rho:A\to \text{End}(V)$, i.e. $\rho(ab)=\rho(b)\rho(a)$ and $\rho(1_{A})=\text{id}_{V}$.
- **Notation**: For $a\in A$ and $v\in V$, $av:=\rho(a)v$. Therefore, algebra homomorphism can be written as $(ab)v=a(bv)$.
- **Remark**: If $A$ is commutative, a left $A$-module is equivalent to a right $A$-module; we just call them $A$-modules.
- **Related definition**: A ***subrepresentation*** of representation $V$ is a subspace $W\subseteq V$ which is $A$-invariant, i.e. $\rho(a)W\subseteq W$ for all $a\in A$. Equivalently, $W$ is called an ***invariant subspace***.
- **Related definition**: A representation $V\neq 0$ of $A$ is ***irreducible*** if the only subrepresentations of $V$ are $(0)$ and $V$.
- **Related definition**: For two $A$-representations $V_{1},V_{2}$, the ***direct sum*** of $V_{1}$ and $V_{2}$ is a representation of $A$ given as $a(v_{1}\oplus v_{2})=a(v_{1})\oplus a(v_{2})$
- **Related definition**: A representation $0\neq V$ of $A$ is called ***indecomposable*** if it's not isomorphic to a direct sum of two non-zero representations.
---
##### Properties
> [!lemma] Proposition 1
> A non-zero finite-dimensional representation $V$ of an algebra $A$ has an irreducible subrepresentation.

> [!proof]-
> If $V$ has no proper non-trivial subrepresentation, then we are done and $V$ is irreducible. Otherwise, there exists a proper non-trivial subrepresentation $W$ and it holds that $0<\text{dim }W<\text{dim }V$. Continuing with $W$ has to stop in finite number of steps. Therefore, there exists an irreducible subrepresentation.
- **Remark**: This does not hold for infinite-dimensional representations, e.g. $A=\mathbb{C}[X]$ with the regular representation. Then, every non-zero element generates a subrepresentation isomorphic to $A$.
---
##### Examples
> [!h] Example 1
> Following are representations: 
> 1. $V=0$.
> 2. ***Regular representation***: $V=A$ and $\rho:A\to \text{End}(A)$ with: $$\rho(a)b=ab$$
> 3. $A=K$ with $\rho(k)v=kv$. Then, $V$ is a $K$-vector space.
---
> [!h] Example 2
> For any representation $V$, $(0)$ and $V$ are subrepresentations.
---
> [!h] Example 3 (Quotient representation)
> For a representation $V$ and a subrepresentation $W$, the ***quotient representation*** is defined as $V / W$ where: $$\rho_{V / W}(a)\pi(x):=\pi(\rho_{V}(a)x)$$
> As any left ideal $I\subseteq A$ is a subrepresentation of the regular representation, $A / I$ is a representation of $A$.

> [!proof]-
> We have: $$\rho_{V / W}(ab)\pi(x)=\pi(\rho_{V}(ab)x)=\pi(\rho_{V}(a)\rho_{V}(b)x)=\rho_{V/W}(a)\pi(\rho_{V}(b)x)=\rho_{V/W}(a)\rho_{V / W}(b)\pi(x)$$
---
> [!h] Example 4
> Let $A:=K[X_{1},\dots,X_{n}]$ and let $I\neq A$ be any ideal in $A$ containing all homogeneous polynomials of degree $\geq N$. Show that $A / I$ is an indecomposable representation of $A$.

---
