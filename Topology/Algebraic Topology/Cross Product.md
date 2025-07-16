#Definition #AlgebraicTopology 

> [!definition]
> Let $X,Y$ be [[topological space|topological spaces]] and $R$ a [[ring]].
> 1. ***Homological cross product*** is a chain map: $$\times:\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y)\to \mathcal{S}_{*}(X\times Y)$$that is:
> 	1. natural under maps $X\to X'$ and $Y\to Y'$
> 	2. satisfies the Leibniz formula: $\partial(a\times b)=\partial a \times b+(-1)^p a\times \partial b$ for all $a\in S_{p}(X)$ and $b\in S_{q}(X)$.
> 2. ***Cohomological cross product*** is a cochain map:$$\times:\mathcal{S}^{*}(X;R)\otimes_{\mathbb{Z}}  \mathcal{S}^{*}(Y;R)\to \mathcal{S}^{*}(X\times Y;R),\quad $$that is:
> 	1. natural under maps $X\to X'$ and $Y\to Y'$.
- **Remark**: The cross products induce a map in co-/homology:
	1. $\times:H_{p}(X)\otimes H_{q}(Y)\to H_{p+q}(X\times Y),[a]\otimes[b]\mapsto[a\times b]$.
	2. $\times:H^p(X;R)\otimes_{R}H^q(Y;R)\to H^{p+q}(X\times Y;R)$