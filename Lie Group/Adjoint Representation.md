#Definition #LieGroups #RepresentationTheory 

> [!definition]
> Let $G$ be a [[Lie group]]. The ***adjoint representatio***n of $G$ is a [[Lie group representation]]:$$\begin{array}{cccc} {\text{Ad}:}&{G}&\to&{\text{GL}(\mathfrak{g})}\\&{g} &\mapsto & {d_{e}\alpha_{g}} \end{array}{}$$where $\alpha_{g}\in \text{Inn}(G)$ is the [[inner automorphism]] $\alpha_{g}(x)=gxg^{-1}$.
- **Remark**: As $\varphi_{g}:G\to G$ is a smooth homomorphism, by [[Exponential Map|Prop 2]], $g\exp(tx)g^{-1}=\exp(t\text{Ad}(g)x)$ for $x\in \mathfrak{g}$.
---
##### Properties
> [!lemma] Proposition 1
> $\text{Ad}$ is a well-defined Lie group representation.

> [!proof]-
> Firstly, as $\alpha_{g}\in \text{Inn}(G)$, $d_{e}\alpha_{g}:\mathfrak{g}\to \mathfrak{g}$. Furthermore, for $g,h\in G$, $$\text{Ad}(gh)=d_{e}\alpha_{gh}=d_{e}\alpha_{g} \circ d_{e}\alpha_{h}=\text{Ad}(g)\text{Ad}(h)$$To see that this is smooth, it suffices to show that $g\mapsto \text{Ad}(g)v$ is smooth for all $v\in \mathfrak{g}$. Then, $$d_{e}\alpha_{g}(v)=d_{e}\alpha_{g}(\gamma'_{v}(0))=\left. \frac{d}{dt} \right| _{t=0}\alpha_{g}(\gamma_{v}(t))=\left. \frac{d}{dt} \right| _{t=0}\alpha_{g}(\exp(tv))=\left. \frac{d}{dt} \right| _{t=0}F(g,\exp(tv))=d_{(g,e)}F(0,v)$$where $F:G\times G\to G,(g,x)\mapsto gxg^{-1}$. Then, $F$ is smooth and $d_{(g,e)}F:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$ is smooth. Further $d_{(g,e)}F(0,v)$ smoothly depends on $g$ and $v$. This proves the statement.
---
##### Examples
> [!h] Example 1
> For $G=\text{Aut}(V)$, we have that $\mathfrak{g}=\text{End}(V)$ and: 
> 1. $\text{Ad}(g)x=gxg^{-1}$
> 2. For $G=\text{GL}(n,\mathbb{R})$, $\text{Ad}(B)X=BXB^{-1}$.

> [!proof]-
> We have:
> $$\text{Ad}(g)x=d_{e}\alpha_{g}(\varphi_{x}'(0))=\left. \frac{d}{dt} \right| _{t=0}\alpha_{g}(\exp(tx))=\left. \frac{d}{dt} \right| _{t=0}g\cdot \exp(tx)\cdot g^{-1}=\left. \frac{d}{dt} \right| _{t=0} \exp(tgxg^{-1})=gxg^{-1}$$
>