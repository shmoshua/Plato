#Definition #AlgebraicTopology 

> [!definition]
> Let $M$ be a $n$-dimensional [[Topological Manifold|manifold]]. For $x\in M$ and a chart $\varphi:\mathbb{R}^n\to U_{x}\subseteq M$. 
> 1. the ***local homology*** of $M$ at $x$ is given by $H_{*}(M,M \backslash \{ x \})$. 
> 2. the ***local homology*** of $M$ at $A$ is given by $H_{*}(M,M \backslash A)$.
- **Notation**: For $A\subseteq M$, $H_{i}(M|A;G):=H_{i}(M, M \backslash A;G)$.
- **Related definition**: A ***local orientation*** of $M$ at $x$ is a choice of the generator $\mu_{x}\in H_{n}(M, M \backslash x)$
---
##### Properties
> [!lemma] Proposition 1
> Let $M^n$ be a manifold and $x\in M$ with a chart $\varphi:\mathbb{R}^n\to U_{x}\subseteq M$. Then, 
> 1. we have that:
> $$H_{i}(M,M \backslash \{ x \})\cong\begin{cases}0&i\neq n\\ \mathbb{Z}&i=n\end{cases}$$via an isomorphism $\rho_{\varphi}:H_{i}(M,M \backslash \{ x \})\to \mathbb{Z}$ that depends on $\varphi$.
> 2. for a linear homeomorphism $\tau:\mathbb{R}^n\to \mathbb{R}^n$, $\rho_{\varphi \circ\tau}=\text{sgn}(\det \tau)\cdot\rho_{\psi}$.

> [!proof]-
> We have that:
> 1. Note that by excision, $$H_{i}(M,M \backslash \{ x \})\cong H_{i}(M\backslash (M \backslash U_{x}), (M \backslash \{ x  \})\backslash (M \backslash U_{x}))=H_{i}(U_{x}, U_{x} \backslash x)$$then: $$H_{i}(U_{x}, U_{x} \backslash \{ x \})\xrightarrow{ (\varphi ^{-1})_{*} }H_{i}(\mathbb{R}^n,\mathbb{R} \backslash \{ \varphi ^{-1}(x) \})$$is an isomorphism. Now, via the connecting homomorphism, we have from the LES: $$\dots\to \underbrace{ \tilde{H}_{i}(\mathbb{R}^n) }_{ =0 }\to H_{i}(\mathbb{R}^n, \mathbb{R}^n \backslash *)\to \tilde{H}_{i-1}(\mathbb{R} ^n \backslash *)\to \underbrace{ \tilde{H}_{i-1}(\mathbb{R}^n) }_{ =0 }\to \cdots$$Therefore, $H_{i}(M,M \backslash \{ x \})\cong \tilde{H}_{i-1}(\mathbb{R}^n \backslash *)\cong \tilde{H}_{i-1}(S^{n-1})\cong \begin{cases}0&i\neq n\\\mathbb{Z}&i=n\end{cases}$.
> 2. Follows from [[Degree of Sphere Maps|Proposition 4]].

- **Corollary**: there are always exactly two choices for local orientations $\mu_{x}$ and $-\mu_{x}$.
---
> [!lemma] Proposition 2
> 