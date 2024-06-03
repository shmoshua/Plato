#Definition #LieGroups #RepresentationTheory 

> [!definition]
> Let $G$ be a [[Lie group]]. The ***adjoint representatio***n of $G$ is a [[Lie group representation]]:$$\begin{array}{cccc} {\text{Ad}:}&{G}&\to&{\text{GL}(\mathfrak{g})}\\&{g} &\mapsto & {d_{e}\varphi_{g}} \end{array}{}$$where $\varphi_{g}\in \text{Inn}(G)$ is the [[inner automorphism]] $\varphi_{g}(x)=gxg^{-1}$.
---
##### Properties
> [!lemma] Proposition 1
> $\text{Ad}$ is a well-defined Lie group representation.

> [!proof]+
> Firstly, as $\varphi_{g}\in \text{Inn}(G)$, $d_{e}\varphi_{g}:\mathfrak{g}\to \mathfrak{g}$. Furthermore, for $g,h\in G$, $$\text{Ad}(gh)=d_{e}\varphi_{gh}=d_{e}\varphi_{g} \circ d_{e}\varphi_{h}=\text{Ad}(g)\text{Ad}(h)$$To see that this is smooth, consider $F:G\times G\to G,(g,x)\mapsto gxg^{-1}$. Then, $F$ is smooth and $d_{(e,e)}F:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$ is smooth. 