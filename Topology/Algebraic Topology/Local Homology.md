#Definition #AlgebraicTopology 

> [!definition]
> Let $M$ be a $n$-dimensional [[Topological Manifold|manifold]]. For $x\in M$ and a chart $\varphi:\mathbb{R}^n\to U_{x}\subseteq M$. 
> 1. the ***local homology*** of $M$ at $x$ is given by $H_{*}(M,M \backslash \{ x \})$. 
> 2. the ***local homology*** of $M$ at $A$ is given by $H_{*}(M,M \backslash A)$.

^7e9800

- **Notation**: For $A\subseteq M$, $H_{i}(M|A;G):=H_{i}(M, M \backslash A;G)$. ^482cae
- **Related definition**: A ***local orientation*** of $M$ at $x$ is a choice of the generator $\mu_{x}\in H_{n}(M, M \backslash x)$ ^152444
---
##### Properties
> [!lemma] Proposition 1
> Let $M^n$ be a manifold and $x\in M$ with a chart $\varphi:\mathbb{R}^n\to U_{x}\subseteq M$. Then, 
> 1. we have that:
> $$H_{i}(M,M \backslash \{ x \})\cong\begin{cases}0&i\neq n\\ \mathbb{Z}&i=n\end{cases}$$via an isomorphism $\rho_{\varphi}:H_{i}(M,M \backslash \{ x \})\to \mathbb{Z}$ that depends on $\varphi$.
> 2. for a linear homeomorphism $\tau:\mathbb{R}^n\to \mathbb{R}^n$, $\rho_{\varphi \circ\tau}=\text{sgn}(\det \tau)\cdot\rho_{\psi}$.

^78bcb9

> [!proof]-
> We have that:
> 1. Note that by excision, $$H_{i}(M,M \backslash \{ x \})\cong H_{i}(M\backslash (M \backslash U_{x}), (M \backslash \{ x  \})\backslash (M \backslash U_{x}))=H_{i}(U_{x}, U_{x} \backslash x)$$then: $$H_{i}(U_{x}, U_{x} \backslash \{ x \})\xrightarrow{ (\varphi ^{-1})_{*} }H_{i}(\mathbb{R}^n,\mathbb{R} \backslash \{ \varphi ^{-1}(x) \})$$is an isomorphism. Now, via the connecting homomorphism, we have from the LES: $$\dots\to \underbrace{ \tilde{H}_{i}(\mathbb{R}^n) }_{ =0 }\to H_{i}(\mathbb{R}^n, \mathbb{R}^n \backslash *)\to \tilde{H}_{i-1}(\mathbb{R} ^n \backslash *)\to \underbrace{ \tilde{H}_{i-1}(\mathbb{R}^n) }_{ =0 }\to \cdots$$Therefore, $H_{i}(M,M \backslash \{ x \})\cong \tilde{H}_{i-1}(\mathbb{R}^n \backslash *)\cong \tilde{H}_{i-1}(S^{n-1})\cong \begin{cases}0&i\neq n\\\mathbb{Z}&i=n\end{cases}$.
> 2. Follows from [[Degree of Sphere Maps|Proposition 4]].

^9b61d5

- **Corollary**: there are always exactly two choices for local orientations $\mu_{x}$ and $-\mu_{x}$. ^deef52
---
> [!lemma] Proposition 2
> Let $M^n$ be a manifold and $\varphi:\mathbb{R}^n\to U$ a chart. Now, for $\varphi(B_{<r}(0))=:B$. Then, 
> 1. $H_{n}(M | B)=H_{n}(\mathbb{R}^n , \mathbb{R}^{n} \backslash B_{<r}(0))$. 
> 2. for all $y\in B$, there is a canonical isomorphism $L_{y}:H_{n}(M|B)\to H_{n}(M|y)$ induced by the inclusion.
> 3. for all $x',x''\in B$, there is a canonical isomorphism $H_{n}(M|x')\to H_{n}(M|x'')$ given by $L_{x''}\circ L_{x'}^{-1}$.

^5ff4d7

> [!proof]-
> We have:
> 1. Obvious.
> 2. Obvious.
> 3. From 2.

^1d4dc6

---
