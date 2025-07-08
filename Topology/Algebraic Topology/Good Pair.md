#Definition #AlgebraicTopology 

> [!definition]
> A pair of [[Topological Space|topological spaces]] $(X,A)$ is ***good*** if:
> 1. $\varnothing\neq A\subseteq X$ and $A$ is closed in $X$ s.t.
> 2. there exists a neighborhood $A\subseteq N\subseteq X$ s.t. $A$ is a [[Retract|strong deformation retract]] of $N$.

^d83b17

---
> [!lemma] Theorem 1
> Let $(X,A)$ be a good pair. Let $q:(X,A)\to(X / A,*)$ be the quotient map. 
> 1. $q_{*}:H_{*}(X,A;G)\to H_{*}(X / A,*;G)$ is an isomorphism, i.e. $$H_{*}(X, A ; G)\cong H_{*}(X / A,*;G)\cong \tilde{H}_{*}(X/ A;G)$$

^248625

> [!proof]+
> We will omit $G$ from the notation of the proof. As $(X,A)$ is a good pair, we have $A\subseteq N\subseteq X$ in the definition. Consider: $$h:(X \backslash A,N \backslash A)\to(X / A\backslash \{ * \}, N / A \backslash \{ * \})$$ the map induced by $q$. Then, 
> 1. $h$ is a homeomorphism. Indeed, $h$ is bijective. To check the continuity, let $U$ be an open set in $X  / A \backslash \{ * \}$. Then, either $U\subseteq X \backslash A$ is open or $U\sqcup A \subseteq X$ is open. In any case, $h^{-1}(U)=U \backslash A$, which is open in $X \backslash A$. The converse is analogous.
> 
> Hence, consider the commutative diagram: $$\begin{CD}H_{n}(X,A)@>i_{*}>> H_{n}(X,N)@<\cong<< H_{n}(X \backslash A,N \backslash A)\\@Vq_{*}VV@Vq_{*}VV@Vh_{*}VV\\H_{n}(X / A,*)@>>\tilde{i}_{*}> H_{n}(X / A, N / A)@<<\cong< H_{n}((X / A) \backslash *, (N / A)\backslash *)\end{CD}$$where the isomorphisms are given by excisions. As $h$ is a homeomorphism, $h_{*}$ is an isomorphism and the middle downward map is an isomorphism. Now, we have that from LES: $$\begin{CD}H_{n}(A)@>>>H_{n}(X)@>>>H_{n}(X, A)@>>>H_{n-1}(A)@>>>H_{n-1}(X)\\@V\cong VV@V\text{id}VV@Vi_{*}VV@V\cong VV@V\text{id}VV\\H_{n}(N)@>>>H_{n}(X)@>>>H_{n}(X, N)@>>>H_{n-1}(A)@>>>H_{n-1}(X)\end{CD}$$where the isomorphism comes from the fact that $N$ is a deformation retract and hence a homotopy equivalence. (See [[Homology Theory|Lemma 1.3]]) Hence, by [[Exact Sequence|5-Lemma]], $i_{*}$ is an isomorphism.
> 
> Similarly, $$\begin{CD}H_{n}(*)@>>>H_{n}(X / A)@>>>H_{n}(X / A, *)@>>>H_{n-1}(*)@>>>H_{n-1}(X / A)\\@V\cong VV@V\text{id}VV@Vi_{*}VV@V\cong VV@V\text{id}VV\\H_{n}(N / A)@>>>H_{n}(X / A)@>>>H_{n}(X / A, N / A)@>>>H_{n-1}(N / A)@>>>H_{n-1}(X / A)\end{CD}$$
> as $N / A$ is contractible. Hence, $\tilde{i}_{*}$ is an isomorphism and $q_{*}:H_{n}(X / A)\to H_{n}( X / A, *)$ is an isomorphism.
> 
> 

^db47d0

---
##### Examples
> [!h] Example 1
> We have that:
> 1. A [[CW-complex]] $X$ and a subcomplex $A$ build a good pair.

^0d0ef3

---