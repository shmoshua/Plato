#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a non-empty [[topological space]].
> 1. the ***augmented chain complex*** $\mathcal{C}$ of $X$ is a [[chain complex]] given as: $$\cdots \to S_{2}(X)\xrightarrow{\partial}S_{1}(X)\xrightarrow{\partial}S_{0}(X)\xrightarrow{\varepsilon}\mathbb{Z}\to 0 \to \cdots$$where $S_{p}(X)$ denotes the [[p-Simplex|singular $p$-chains]] of $X$ and $$\varepsilon:S_{0}(X)\to G,\quad \sum_{x\in X}^{}g_{x}x\mapsto \sum_{x\in X}^{}g_{x}$$
> 2. the ***reduced cohomology*** of degree $p\in \mathbb{Z}$ is given as $\tilde{H}^p(X;G):=H^p(\mathcal{C};G)$

^f8d920

---
##### Properties
> [!lemma] Proposition 1
> For an abelian group $G$:
> $$\tilde{H}^n(X;G)\cong \begin{cases}H^n(X;G)&n>0\\\text{Hom}(\tilde{H}_{0}(X),G)&n=0\end{cases}$$

^d4c5e7

> [!proof]-
> We have that:
> 1. For $n>0$, the dual of augmented chain complex is the same as the dual of the singular chain complex. 
> 2. For $n=0$ we have that the dual of the augmented chain complex is: $$0 \to \mathbb{Z}^{*} \overset{ \varepsilon ^{*} }{ \to } S^0(X;G) \overset{ \partial ^{*} }{ \to } S^1(X;G)\to \cdots $$We have that: $$0\to \text{Ext}(\tilde{H}_{-1}(X),G)\to \tilde{H}^0(X;G)\to \text{Hom}(\tilde{H}_{0}(X),G)\to 0$$As $\tilde{H}_{-1}(X)=0$, we have our statement.

^14f563

---
> [!lemma] Proposition 2 (Zeroth Reduced Cohomology)
> For the augmented chain complex $\mathcal{C}$:
> 1. $Z^0(\mathcal{C})$ are locally constant functions $X\to G$.
> 2. $B^0(\mathcal{C})$ are globally constant functions $X\to G$.
> 3. $\tilde{H}^0(X;G)=$ locally constant functions modded by globally constant functions.

^e4d557

> [!proof]-
> We have:
> 1.  For $f\in \text{Hom}(S_{0}(X),G)$, we have that $f:S_{0}(X)\to G$ and $$f\circ \partial(e_{0}e_{1})=f(e_{1}-e_{0})=f(e_{1})-f(e_{0})$$Hence, if $\delta(f)=0$, then $f(e_{0})=f(e_{1})$ for all paths $e_{0}e_{1}$ in $X$. This shows the statement.
> 2. As $\text{Hom}(\mathbb{Z} , G)\cong G$, we have that $f\in \text{Hom}(\mathbb{Z}, G)$ is identified with where $1$ is sent. Therefore, $B^0(\mathcal{C})\cong G$.
> 3. Obvious.

^67aed1

---
