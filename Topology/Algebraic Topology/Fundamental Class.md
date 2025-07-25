#Definition #AlgebraicTopology 

> [!definition]
> Let $R$ be a [[ring]]. Let $M^n$ be a [[Orientable Double Cover|$R$-oriented]] [[Topological Manifold|manifold]] with $R$-orientation $\mu$
> 1. the ***fundamental class***  of $M$ is an element $[M]\in H_{n}(M;R)$ s.t. $$L_{x}([M])=\mu_{x},\quad \forall x\in M$$

^5be81b

---
##### Properties

> [!lemma] Proposition 1 (Existence of Fundamental Classes)
> Let $M^n$ be a compact connected $R$-orientable manifold with $R$-orientation $\mu$, 
> 1. there exists $a_{x}\in H_{n}(M;R)$ with $L_{x}(a_{x})=\mu_{x}$ for all $x\in M$ s.t. for a ball chart $B\subseteq M$, and $x,y\in B$ we have that $a_{x}=a_{y}$.
> 2. there exists $a\in H_{n}(M;R)$ s.t. $L_{x}(a)=\mu_{x}$ for all $x\in M$ where $a$ is a generator of $H_{n}(M;R)$ which is a rank 1 free $R$-module.
> 3. there is a bijection: $$\{ R\text{-orientations of }M \}\leftrightarrow  \{ \text{generators of the }R\text{-module }H_{n}(M;R)\cong R \}$$i.e. $[M]$ exists.

^28f05d

> [!proof]-
> We have that:
> 1. From [[Orientable Double Cover|Theorem 4.1]], $L_{x}$ is an isomorphism and $a_{x}\in H_{n}(M;R)$ exists that is also a generator. If $y$ lies in the same ball chart $B$, consider the commutative diagram: 
> 	```tikz 
> 	\usepackage{tikz-cd} \begin{document} \begin{tikzcd} & {H_n(M;R)} \\ {H_n(M|x;R)} & {H_n(M|B;R)} & {H_n(M|y;R)} \arrow["{L_x,\cong}"', from=1-2, to=2-1] \arrow["\cong", from=1-2, to=2-2] \arrow["{\cong, L_y}", from=1-2, to=2-3] \arrow["\cong"', from=2-1, to=2-2] \arrow["\cong", from=2-3, to=2-2] \end{tikzcd}\end{document}
> 	```
>   There it commutes as the isomorphisms are all induced by inclusions. Hence, $$a_{x}=L^{-1}_{x}(\mu_{x})=L^{-1}_{x}(L_{x}L_{y}^{-1}(\mu_{y}))=L^{-1}_{y}(\mu_{y})=a_{y}$$
> 2. As $M$ is connected, it is path connected and for any two points $x,y\in M$ we can find a path and ball charts s.t. using 1 we can show that $a_{x}=a_{y}=: a$. Also $a$ is trivially a generator.
> 3. For a generator $a$, we have that $x\mapsto L_{x}(a)$ is an $R$-orientation.

^40b4cb

---
> [!lemma] Proposition 2
> Let $M^n$ be a manifold and $a\in H_{n}(M;R)$.
> 1. if $L_{x}(a)\neq 0$  for all $x\in M$, $M$ is compact.
> 2. if $[M]$ exists, then $M$ is compact.

^a34de3

> [!proof]-
> We have that:
> 1. Let $a=[c]$ for $c\in S_{n}(M;R)$. We claim that $\text{im}(c)=M$. Assume otherwise. Then, there exists $x_{0}\in M$ s.t. $x_{0}\notin \text{im}(c)$. Then, $$L_{x_{0}}([c])\in H_{n}(M|x_{0};R)$$has to be 0 as $\text{im }c\subseteq M \backslash x_{0}$ which is a contradiction.
>    
>    Therefore, $M=\text{im }c$ which is compact as $\Delta^n$ is.

^5e3b91

---
> [!lemma] Theorem 3 (Poincaré Duality)
> Let $M^n$ be a compact $R$-oriented manifold with fundamental class $[M]\in H_{n}(M;R)$. Then, 
> 1. the ***Poincaré duality***, i.e. the map: $$\text{PD}: H^k(M;R)\to H_{n-k}(M;R),\quad \alpha\mapsto \alpha \cap[M]$$is an isomorphism of $R$-modules.