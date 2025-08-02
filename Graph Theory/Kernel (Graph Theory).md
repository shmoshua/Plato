#Definition #GraphTheory 

> [!definition]
> Let $G$ be a [[Graph|digraph]].
> 1. A ***kernel*** of $G$ is an independent set $S$ s.t. for every $v\notin S$, there exists $u\in S$ with $u\to v\in G$.

- **Related definition**: $G$ is ***kernel-perfect*** if every induced subdigraph of $G$ has a kernel.

---
> [!lemma] Proposition 1
> Let $D$ be a kernel-perfect orientation of $G$. Then,
> 1. $G$ is $(d^-_{D}+1)$-choosable.

> [!proof]-
> We show this via induction over $n$.
> 1. If $n=1$, the claim is trivial.
> 2. Let $n\geq 2$ and let $L(x)$ be a list s.t. $\left| L(x) \right|\geq 1+d^-_{D}(x)$ for all $x\in V(G)$. Let $c$ be some color. Consider $U:=\{ v:c\in L(v) \}$. Then, there is a kernel $S$ of $D[U]$. Now, assign $c$ to all of $S$, which is valid as $S$ is an independent set. Delete $c$ from $L(v)$ from each of the $U \backslash S$. 
>    
>    We have that $D \backslash S$ is a kernel perfect orientation of $G \backslash S$. Hence, by induction, $G \backslash S$ is $(d^-_{D / S}+1)$-choosable. Hence, we can have a valid list coloring on $G \backslash S$ as we also have that the in-degree decreases by 1 for all vertices in $D \backslash S$. This proves the claim. 