#Definition #LieGroups #RepresentationTheory 

> [!definition]
> Let $G$ be a [[Lie group]]. The ***adjoint representatio***n of $G$ is a [[Lie group representation]]:$$\text{Ad}:G\to \text{GL}(\mathfrak{g}),\quad g\mapsto d_{e}\alpha_{g}$$where $\alpha_{g}\in \text{Inn}(G)$ is the [[inner automorphism]] $\alpha_{g}(x)=gxg^{-1}$. The ***adjoint representation*** of $\mathfrak{g}$ is a [[Lie algebra representation]]: $$\text{ad}: \mathfrak{g}\to \mathfrak{gl}(\mathfrak{g}),\quad x\mapsto[x,\cdot ]$$
- **Remark**: As $\varphi_{g}:G\to G$ is a smooth homomorphism, by [[Exponential Map|Prop 2]], $g\exp(tx)g^{-1}=\exp(t\text{Ad}(g)x)$ for $x\in \mathfrak{g}$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\text{Ad}$ is a well-defined Lie group representation.
> 2. $\text{ad}=d_{e}\text{Ad}$.

> [!proof]-
> We have:
> 1. Firstly, as $\alpha_{g}\in \text{Inn}(G)$, $d_{e}\alpha_{g}:\mathfrak{g}\to \mathfrak{g}$. Furthermore, for $g,h\in G$, $$\text{Ad}(gh)=d_{e}\alpha_{gh}=d_{e}\alpha_{g} \circ d_{e}\alpha_{h}=\text{Ad}(g)\text{Ad}(h)$$To see that this is smooth, it suffices to show that $g\mapsto \text{Ad}(g)v$ is smooth for all $v\in \mathfrak{g}$. Then, $$d_{e}\alpha_{g}(v)=d_{e}\alpha_{g}(\gamma'_{v}(0))=\left. \frac{d}{dt} \right| _{t=0}\alpha_{g}(\gamma_{v}(t))=\left. \frac{d}{dt} \right| _{t=0}\alpha_{g}(\exp(tv))=\left. \frac{d}{dt} \right| _{t=0}F(g,\exp(tv))=d_{(g,e)}F(0,v)$$where $F:G\times G\to G,(g,x)\mapsto gxg^{-1}$. Then, $F$ is smooth and $d_{(g,e)}F:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$ is smooth. Further $d_{(g,e)}F(0,v)$ smoothly depends on $g$ and $v$. This proves the statement.
> 2. We have: $$d_{e}\text{Ad}(x)(y)=\left. \frac{d}{dt} \right| _{t=0}\text{Ad}(\exp(tx))(y)=\left. \frac{d}{dt} \right| _{t=0}d_{e}\alpha_{\exp(tx)}(y)$$Therefore, we have by [[One-Parameter Subgroup|Example 1]] and [[Integral Curve|Example 1]]: $$\begin{align}d_{e}\text{Ad}(x)(y)&=\left. \frac{d}{dt} \right| _{t=0}dR_{\exp(-tx)}(dL_{\exp(tx)}(y))\\&=\left. \frac{d}{dt} \right| _{t=0}dR_{\exp(-tx)}(y^L_{\exp(tx)})\\&=\left. \frac{d}{dt} \right| _{t=0}dR_{\varphi_{x}(-t)}(y^L_{\varphi_{x}(t)})\\&=\left. \frac{d}{dt} \right| _{t=0}d\Phi^{-t}_{x}(y^L_{\Phi_{x}^t(e)})\\&=(L_{x^L}y^L)_{e}\\&=[x^L,y^L]_{e}\\&=[x,y]\end{align}$$
---
> [!lemma] Proposition 2
> Let $\mathfrak{g}$ be a $\mathbb{K}$-vector space with a skew-symmetric bilinear map $[\cdot,\cdot]:\mathfrak{g}\times \mathfrak{g}\to \mathfrak{g}$. Then, TFAE:
> 1. $\mathfrak{g}$ is a Lie algebra, i.e. the Jacobi identity holds.
> 2. $\text{ad}:\mathfrak{g}\to \mathfrak{gl}(\mathfrak{g})$ is a Lie algebra homomorphism.

> [!proof]-
> We have that:
> 1. $[\text{ad}(x),\text{ad}(y)]z=[x,[y,z]]-[y,[x,z]]=-[[y,z],x]-[[z,x],y]=[[x,y],z]=\text{ad}([x,y])z$
> 2. Similarly, $$[[x,y],z]+[[y,z],x]+[[z,x],y]=0$$
---
> [!lemma] Theorem 3
> Let $G$ be a connected Lie group. Then, $Z(G)=\text{ker }\text{Ad}$.

> [!proof]+
> Let $g\in Z(G)$ and $x\in \mathfrak{g}$, then: $$\exp(tx)=g \exp(tx)g ^{-1}=\exp(t\text{Ad}(g)x)$$
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