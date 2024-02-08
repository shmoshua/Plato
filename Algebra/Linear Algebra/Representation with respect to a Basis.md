#Definition #LinearAlgebra #LST 

> [!definition]
> Let $(V,F)$ be a finite-dimensional linear space and $\{ b_{1} ,\dots,b_{n}\}$ be a [[Basis|basis]] of $V$. By definition, for any $x\in V$, there exists $\xi_{1},\dots,\xi_{n}\in F$ s.t. $$x=\sum_{i=1}^{n}\xi_{i}b_{i}$$
> The vector $\xi:=[\xi_{1},\dots,\xi_{n}]\in F^n$ is called the ***representation*** of $x$ with respect to $\{ b_{i} \}_{i=1}^n$.

---
##### Properties
> [!lemma] Fact Repr.1
> The representation of a given vector $x\in V$ with respect to a basis $\{ b_{1},\dots,b_{n} \}$ is unique.

>[!proof]-
> For a vector $x\in V$, assume there are two representations $\xi,\xi'$. Then,$$ \sum_{i=1}^n(\xi_i-\xi'_i)b_i=x-x=0 $$
> But from linear independence, for all $i$, $$ \xi_i-\xi_i'=0\Longrightarrow \xi_i=\xi'_i $$

---