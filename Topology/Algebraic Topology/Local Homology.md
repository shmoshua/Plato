#Definition #AlgebraicTopology 

> [!definition]
> Let $M$ be a $n$-dimensional [[Topological Manifold|manifold]]. For $x\in M$ and a chart $\varphi:\mathbb{R}^n\to U_{x}\subseteq M$. 
> 1. the ***local homology*** of $M$ at $x$ is given by $H_{i}(M,M \backslash \{ x \})$. 
---
##### Properties
> [!lemma] Proposition 1
> Let $M^n$ be a manifold and $x\in M$ with a chart $\varphi:\mathbb{R}^n\to U_{x}\subseteq M$. Then, 
> 1. we have that:
> $$H_{i}(M,M \backslash \{ x \})\cong\begin{cases}0&i\neq n\\ \mathbb{Z}&i=n\end{cases}$$via an isomorphism $\rho_{\varphi}:H_{i}(M,M \backslash \{ x \})\to \mathbb{Z}$ that depends on $\varphi$.
> 2. for a linear homeomorphism $\tau:\mathbb{R}^n\to \mathbb{R}^n$, $\rho_{\varphi \circ\tau}=\varepsilon_{\tau}\circ\rho_{\psi}$ where $\varepsilon_{\tau}=\text{sgn}(\det \tau)$. 

> [!proof]+
> We have that:
> 1. Note that by excision, $$H_{i}(M,M \backslash \{ x \})\cong H_{i}(M\backslash (M \backslash U_{x}), (M \backslash \{ x  \})\backslash (M \backslash U_{x}))=H_{i}(U_{x}, U_{x} \backslash x)$$then: $$H_{i}(U_{x}, U_{x} \backslash \{ x \})\xrightarrow{ (\varphi ^{-1})_{*} }H_{i}(\mathbb{R}^n,\mathbb{R} \backslash \{ \varphi ^{-1}(x) \})$$is an isomorphism. Now, via the connecting homomorphism, we have from the LES: $$\dots\to \underbrace{ \tilde{H}_{i}(\mathbb{R}^n) }_{ =0 }\to H_{i}(\mathbb{R}^n, \mathbb{R}^n \backslash *)\to \tilde{H}_{i-1}(\mathbb{R} ^n \backslash *)\to \underbrace{ \tilde{H}_{i-1}(\mathbb{R}^n) }_{ =0 }\to \cdots$$Therefore, $H_{i}(M,M \backslash \{ x \})\cong \tilde{H}_{i-1}(\mathbb{R}^n \backslash *)\cong \tilde{H}_{i-1}(S^{n-1})\cong \begin{cases}0&i\neq n\\\mathbb{Z}&i=n\end{cases}$.
> 2. Notice that in 1, everything is canonical except the map $(\varphi ^{-1})_{*}$. 