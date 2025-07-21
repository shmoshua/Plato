#Definition #AlgebraicTopology 

> [!definition]
> Let $R$ be a [[ring]]. Let $M^n$ be a compact connected [[Orientable Double Cover|$R$-oriented]] [[Topological Manifold|manifold]] with $R$-orientation $\mu$
> 1. the ***fundamental class***  of $M$ is an element $[M]\in H_{n}(M;R)$ s.t. $$L_{x}([M])=\mu_{x},\quad \forall x\in M$$

---
##### Properties

> [!lemma] Proposition 1 (Existence of Fundamental Classes)
> Let $M^n$ be a compact connected $R$-orientable manifold with $R$-orientation $\mu$, 
> 1. there exists $a_{x}\in H_{n}(M;R)$ with $L_{x}(a_{x})=\mu_{x}$ for all $x\in M$ s.t. for a ball chart $B\subseteq M$, and $x,y\in B$ we have that $a_{x}=a_{y}$.
> 2. there exists $a\in H_{n}(M;R)$ s.t. $L_{x}(a)=\mu_{x}$ for all $x\in M$ where $a$ is a generator of $H_{n}(M;R)$ which is a rank 1 free $R$-module.
> 3. there is a bijection: $$\{ R\text{-orientations of }M \}\leftrightarrow  \{ \text{generators of the }R\text{-module }H_{n}(M;R)\cong R \}$$

> [!proof]+
> We have that:
> 1. From [[Orientable Double Cover|Theorem 4.1]], $L_{x}$ is an isomorphism and $a_{x}\in H_{n}(M;R)$ exists that is also a generator. If $y$ lies in the same ball chart $B$, consider the commutative diagram: 