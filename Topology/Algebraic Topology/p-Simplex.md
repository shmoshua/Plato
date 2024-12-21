> [!definition]
> Let $\mathbb{R}^\infty:=\bigoplus_{i\geq 0}\mathbb{R}$ be the direct sum. Let $X$ be a [[topological space]]. Then,
> 1. The ***standard $p$-simplex*** is given as: $$\Delta_{p}:=\left\{  \sum_{i=0}^{p}\lambda_{i}e_{i}: \lambda_{i}\geq 0,\sum_{i=0}^{p}\lambda_{i}=1  \right\}=\text{ConvexHull}(e_{0},\dots,e_{p})$$endowed with the [[subspace topology]] from $\mathbb{R}^{p+1}$.
> 2. A ***singular $p$-simplex*** in $X$ is a continuous map $\sigma:\Delta_{p}\to X$.
> 3. A ***singular $p$-chain*** in $X$ is a finite formal sum of singular $p$-simplices. $S_{p}(X)$ denotes the group of singular $p$-chains (or equivalently, the free abelian group of singular $p$-simplices)

^702d30

- **Related definition**: For $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$,  ^a6188b
	1. the ***affine $p$-simplex*** is a map $[v_{0},\dots,v_{p}]:\Delta_{p}\to \mathbb{R}^\infty,\sum_{i=0}^{p}\lambda_{i}e_{i}\mapsto \sum_{i=0}^{p}\lambda_{i}v_{i}$.
	2. the ***$i$-th face map*** $F_{i}^p:=[e_{1},\dots,\widehat{e_{i}},\dots,e_{p}]:\Delta_{p-1}\hookrightarrow \Delta_{p}$
	3. the ***$i$-th face map of a singular $p$-simplex*** $\sigma$, is $\sigma^{(i)}:=\sigma \circ F_{i}^p:\Delta_{p-1}\to X$
	4. the ***boundary of a singular $p$-simplex*** $\sigma$, $$\partial_{p}\sigma:=\sum_{i=0}^{p}(-1)^i\sigma^{(i)}$$
	5. the ***boundary operator*** is then given by linearly extending the boundary for simplices: $\partial_{p}:S_{p}(X)\to S_{p-1}(X)$.
- **Related definition**: For all $p<0$, we define $S_{p}(X):= 0$. For all $p\leq 0$, we define $\partial_{p}:=0$. ^2c4bf0
- **Related definition**: We denote that: ^ff8cc1
	1. $Z_{p}(X):=\text{ker }\partial_{p}\leq S_{p}(X)$ is the **$p$-cycles**.
	2. $B_{p}(X):=\text{im }\partial_{p+1}\leq S_{p}(X)$ is the **$p$-boundaries**
	3. $H_{p}(X):= Z_{p}(X) / B_{p}(X)$ is the **$p$-homology**.
	4. $c_{1},c_{2}\in Z_{p}(X)$ are ***homologous***, if $[c_{1}]=[c_{2}]\in H_{p}(X)$.
---
##### Properties
> [!lemma] Proposition 1
> For all $x\in \Delta_{p}$, 
> 1. the barycentric coordinates $\lambda_{i}$ are unique.
> 2. for any $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$, $[v_{0},\dots,v_{p}]$ is continuous.
> 3. $F^p_{i}\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right)=\sum_{k=0}^{i-1}\lambda_{k}e_{k}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+1}$
> 4. $F^{p+1}_{j}\circ F_{i}^p=F_{i+1}^{p+1}\circ F_{j}^p$ if $j\leq i$.
> 5. We have that: $$F_{j}^{p+1}\circ F_{i}^p=\begin{cases}[e_{0},\dots,\widehat{e_{i}},\dots,\widehat{e_{j}},\dots,e_{p}]&i<j\\ [e_{0},\dots,\widehat{e_{j}},\dots,\widehat{e_{i+1}},\dots,e_{p}]&j\leq i\end{cases}$$

^f65700

> [!proof]-
> We have that:
> 1. Assume we have $\lambda_{i}$ and $\xi_{i}$ both barycentric coordinates. Then, $$\sum_{i=0}^{p}(\lambda_{i}-\xi_{i})e_{i}=0$$Then, from linear independence, $\lambda_{i}=\xi_{i}$ for all $i\in[p]$.
> 2. Obvious.
> 3. By construction.
> 4. We have that: $$\begin{align}F^{p+1}_{j}\left( F_{i}^p\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right) \right)&=F^{p+1}_{j}\left( \sum_{k=0}^{i-1}\lambda_{k}e_{k}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+1}\right)\\&=\sum_{k=0}^{j-1}\lambda_{k}e_{k}+\sum_{k=j}^{i-1}\lambda_{k}e_{k+1}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+2}\\&\end{align}$$$$F_{i+1}^{p+1}\left( F_{j}^p\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right)  \right) =F^{p+1}_{i+1}\left( \sum_{k=0}^{} \right) $$
> 5. From 3 and 4.

^21d685

---
> [!lemma] Lemma 2 (Boundary Lemma)
> We have that:
> 1. $\partial_{p}\circ\partial_{p+1}=0$, i.e. $B_{p}(X)\unlhd Z_{p}(X)$

^71f3bb

> [!proof]-
> We have that:
> 1. it suffices to show that $\partial_{p}(\partial_{p+1}(\sigma))=0$ for all singular $(p+1)$-simplex $\sigma$. We have that: $$\begin{align}\partial_{p}(\partial_{p+1}(\sigma))&=\partial_{p}\left( \sum_{j=0}^{p+1}(-1)^j \sigma \circ F^{p+1}_{j}\right) =\sum_{j=0}^{p+1}(-1)^j\sum_{i=0}^{p}(-1)^i\sigma \circ F^{p+1}_{j}\circ F^p_{i}\\&=\sum_{0\leq i < j\leq p+1}^{}(-1)^{i+j}\sigma \circ F^{p+1}_{j}\circ F^p_{i}+\sum_{0\leq j\leq i\leq p}^{}(-1)^{i+j}\sigma \circ \underbrace{ F^{p+1}_{j}\circ F^p_{i} }_{ =F_{i+1}^{p+1}\circ F_{j}^p }\\&=\sum_{0\leq i < j\leq p+1}^{}(-1)^{i+j}\sigma \circ F^{p+1}_{j}\circ F^p_{i}+\sum_{0\leq j< i'\leq p+1}^{}(-1)^{i'+j-1}\sigma \circ F_{i'}^{p+1}\circ F_{j}^p\\&=0\end{align}$$

^bbbdc3

---
##### Examples
> [!h] Example 1
> For a point space $X=\{ x_{0} \}$, 
> 1. $Z_{p}(X)=\begin{cases}\mathbb{Z}\sigma_{p}&p>0\text{ odd}\\0&p>0\text{ even}\\\mathbb{Z}\sigma_{p}&p=0\\0&p<0\end{cases}$
> 2. $B_{p}(X)=\begin{cases}\mathbb{Z}\sigma_{p}&p>0\text{ odd}\\0&p>0\text{ even}\\0&p\leq0\end{cases}$
> 3. $H_{p}(X)\cong\begin{cases}\mathbb{Z}&p=0\\0&\text{otherwise}\end{cases}$

> [!proof]-
> Fix $p=0$. We have that the only singular $p$-simplex $\sigma_{p}:\Delta_{p}\to X$ is given by the constant map. Therefore, $S_{p}(X)\cong \mathbb{Z}$ for all $p\geq 0$. 
> 
> Further, $\partial_{p}(\sigma_{p})$ is an alternating sum of $(p+1)$ summands of which is up to $\sigma_{p-1}$. Hence, $$\partial_{p}(\sigma_{p})=\begin{cases}0&p>0\text{ odd}\\\pm\sigma_{p-1}&p>0\text{ even}\\0&p\leq 0\end{cases}$$Hence, $\partial_{p}$ is an isomorphism if and only if $p>0$ and even. The rest then follows.
