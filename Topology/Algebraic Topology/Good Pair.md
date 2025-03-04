#Definition #AlgebraicTopology 

> [!definition]
> A pair of [[Topological Space|topological spaces]] $(X,A)$ is ***good*** if:
> 1. $\varnothing\neq A\subseteq X$ and $A$ is closed in $X$ s.t.
> 2. there exists a neighborhood $A\subseteq N\subseteq X$ s.t. $A$ is a [[Retract|strong deformation retract]] of $N$.

---
> [!lemma] Theorem 1
> Let $(X,A)$ be a good pair. Let $q:(X,A)\to(X / A,*)$ be the quotient map. 
> 1. $q_{*}:H_{*}(X,A;G)\to H_{*}(X / A,*;G)$ is an isomorphism, i.e. $$H_{*}(X, A ; G)\cong H_{*}(X / A,*;G)\cong \tilde{H}_{*}(X/ A;G)$$

> [!proof]+
> We will omit $G$ from the notation of the proof. As $(X,A)$ is a good pair, we have $A\subseteq N\subseteq X$ in the definition. Consider: $$h:(X \backslash A,N \backslash A)\to(X / A\backslash \{ * \}, N / A \backslash \{ * \})$$ the map induced by $q$. 
---
##### Examples
> [!h] Example 1
> We have that:
> 1. A [[CW-complex]] $X$ and a subcomplex $A$ builds a good pair.