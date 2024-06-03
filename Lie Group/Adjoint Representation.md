#Definition #LieGroups #RepresentationTheory 

> [!definition]
> Let $G$ be a [[Lie group]]. The ***adjoint representatio***n of $G$ is a [[Lie group representation]]:$$\begin{array}{cccc} {\text{Ad}:}&{G}&\to&{\text{GL}(\mathfrak{g})}\\&{g} &\mapsto & {d_{e}\varphi_{g}} \end{array}{}$$where $\varphi_{g}\in \text{Inn}(G)$ is the [[inner automorphism]] $\varphi_{g}(x)=gxg^{-1}$.
---
##### Properties
> [!lemma] Proposition 1
> $\text{Ad}$ is a well-defined Lie group representation.

> [!proof]+
> Firstly, as $\varphi_{g}\in \text{Inn}(G)$, $d_{e}\varphi_{g}:\mathfrak{g}\to \mathfrak{g}$. Furthermore, for $g,h\in G$, $$\text{Ad}(gh)=d_{e}\varphi_{gh}=d_{e}\varphi_{g} \circ d_{e}\varphi_{h}=\text{Ad}(g)\text{Ad}(h)$$To see that this is smooth, consider $F:G\times G\to G,(g,x)\mapsto gxg^{-1}$. Then, $F$ is smooth and $d_{(e,e)}F:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$ is smooth. Let $v\in \mathfrak{g}$ and $g\in G$. Then, $\text{Ad}(g)X$ is the left-invariant vector field whose value at $e\in G$ is: $$d_{e}\varphi_{g}(v)=d_{e}\varphi_{g}(\gamma'_{v}(0))=\left. \frac{d}{dt} \right| _{t=0}\varphi_{g}(\gamma_{v}(t))=\left. \frac{d}{dt} \right| _{t=0}\varphi_{g}(\exp(tv))=\left. \frac{d}{dt} \right| _{t=0}F(g,\exp(tv))=d_{(g,e)}F(0,v)$$