#Definition #AlgebraicTopology 

> [!definition]
> Let $K$ be a [[CW-complex]]. The ***cellular chain complex*** of $K$ is a [[chain complex ]] $\mathcal{C}(K):=\{ C_{n}(K),\beta_{n} \}_{n\in \mathbb{Z}}$ where:
> 1. $C_{n}(K):=\bigoplus_{\sigma\in I_{n}}\mathbb{Z}\sigma\cong H_{n}(K^{(n)},K^{(n-1)})$ and
> 2. $\beta_{n}:=j_{n-1}\circ\partial_{n}$ where $j_{n}:H_{n}(K^{(n)})\to H_{n}(K^{(n)},K^{(n-1)})$ and $\partial_{n}:H_{n}(K^{(n)},K^{(n-1)})\to H_{n-1}(K^{(n-1)})$ given by the long exact sequence. 
---
##### Properties
> [!lemma] Proposition 1
> For a CW-complex $K$, 
> 1. $\mathcal{C}(K)$ is a chain complex. 
> 2. $C_{n}(K)\cong H_{n}(K^{(n)},K^{(n-1)})$ is given by: $$\Psi:C_{n}(K)\to H_{n}(K^{(n)},K^{(n-1)}),\quad \sum_{\sigma\in I_{n}}^{}n_{\sigma}\cdot \sigma\mapsto \sum_{\sigma\in I_{n}}^{}n_{\sigma}\cdot (f_{\sigma})_{*}[I^n]$$and$$\Phi:H_{n}(K^{(n)},K^{(n-1)})\to C_{n}(K),\quad \alpha\mapsto \sum_{\sigma\in I_{n}}^{}\phi_{n}((p_{\sigma})_{*}(\alpha))\cdot \sigma$$where:
> 	1. $\gamma_{n}:(I^n,\partial I^n)\to (S^n,*)$ s.t. $(\gamma_{n})_{*}:H_{n}(I^n,\partial I^n)\to H_{n}(S^n,*)$ is an isomorphism.
> 	2. $[I^n]\in H_{n}(I^n,\partial I^n)$, $[S^n]\in H_{n}(S^n,*),[\partial I^{n+1}]\in \tilde{H}_{n}(\partial I^{n+1})$ are generators with $(\gamma_{n})_{*}([I^n])=[S^n]$ and $\partial_{*}([I^{n+1}])=[\partial I^{n+1}]$. 
> 	3. $\phi_{n}:H_{n}(S^n,*)\to \mathbb{Z}$ is the unique isomorphism s.t. $\phi_{n}([S^n])=1$.
> 	4. $p_{\sigma}:K^{(n)}\to S^n$ s.t. $\gamma_{n}=p_{\sigma} \circ f_{\sigma}$.

> [!proof]+
> We have:
> 1. Shown in [[[CW-Complex|Proposition 8]].