#Definition #AlgebraicTopology 

> [!definition]
> Let $K$ be a [[CW-complex]]. The ***cellular chain complex*** of $K$ is a [[chain complex ]] $\mathcal{C}(K):=\{ C_{n}(K),d_{n} \}_{n\in \mathbb{Z}}$ where:
> 1. $C_{n}(K):=\bigoplus_{\sigma\in I_{n}}\mathbb{Z}\sigma\cong H_{n}(K^{(n)},K^{(n-1)})$ and
> 2. $d_{n}:C_{n}(K)\to C_{n-1}(K)$ where $d_{n}(\sigma):=\sum_{\tau\in I_{n-1}}^{}[\tau :\sigma]\tau$ for all $\sigma\in I_{n}$ and the ***incidence number*** $[\tau:\sigma]:=\deg(p_{\tau} \circ f_{\partial \sigma})$.

---
##### Properties
> [!lemma] Proposition 1
> For a CW-complex $K$, 
> 1. $C_{n}(K)\cong H_{n}(K^{(n)},K^{(n-1)})$ is given by: $$\Psi:C_{n}(K)\to H_{n}(K^{(n)},K^{(n-1)}),\quad \sum_{\sigma\in I_{n}}^{}n_{\sigma}\cdot \sigma\mapsto \sum_{\sigma\in I_{n}}^{}n_{\sigma}\cdot (f_{\sigma})_{*}[I^n]$$and$$\Psi ^{-1}=\Phi:H_{n}(K^{(n)},K^{(n-1)})\to C_{n}(K),\quad \alpha\mapsto \sum_{\sigma\in I_{n}}^{}\phi_{n}((p_{\sigma})_{*}(\alpha))\cdot \sigma$$where:
> 	1. $\gamma_{n}:(I^n,\partial I^n)\to (S^n,*)$ s.t. $(\gamma_{n})_{*}:H_{n}(I^n,\partial I^n)\to H_{n}(S^n,*)$ is an isomorphism.
> 	2. $[I^n]\in H_{n}(I^n,\partial I^n)$, $[S^n]\in H_{n}(S^n,*),[\partial I^{n+1}]\in \tilde{H}_{n}(\partial I^{n+1})$ are generators with $(\gamma_{n})_{*}([I^n])=[S^n]$ and $\partial_{*}([I^{n+1}])=[\partial I^{n+1}]$. 
> 	3. $\phi_{n}:H_{n}(S^n,*)\to \mathbb{Z}$ is the unique isomorphism s.t. $\phi_{n}([S^n])=1$.
> 	4. $p_{\sigma}:K^{(n)}\to S^n$ s.t. $\gamma_{n}=p_{\sigma} \circ f_{\sigma}$.
> 2. $d_{n}=\Phi_{n-1} \circ \beta_{n}\circ\Psi_{n}$ for all $n$.
> 3. $\mathcal{C}(K)$ is a chain complex. 
> 4. $H_{n}(\mathcal{C}(K))\cong H_{n}(K)$ for all $n\in \mathbb{Z}$.

> [!proof]+
> We have:
> 1. We first notice that $\Psi$ is an isomorphism as it sends every generator to a generator. Hence, it suffices to show that $\Phi \circ\Psi=\text{id}$. By linearity, we can show that $\Phi(\Psi(\sigma))=\sigma$ for all $\sigma\in I_n$. We have: $$\begin{align}\Phi(\Psi(\sigma))=\Phi((f_{\sigma})_{*}[I^n])=\sum_{\tau\in I_{n}}^{}\phi_{n}((p_{\tau})_{*}(f_{\sigma})_{*}[I^n])\tau=\phi_{n}((p_{\sigma}\circ f_{\sigma})_{*}[I^n])\sigma=\phi_{n}([S^n])\sigma=\sigma\end{align}$$where for $\tau\neq\sigma$, $p_{\tau} \circ f_{\sigma}=*$ and $(p_{\tau}\circ f_{\sigma})_{*}=0$.
> 2. We have that for $\sigma\in I_{n}$: $$\begin{align}\Phi \circ \beta_{n}\circ \Psi(\sigma)&=\Phi \circ j_{n-1}\circ \partial_{n} \circ (f_{\sigma})_{*}[I^n]=\Phi \circ j_{n-1}\circ (f_{\partial\sigma})_{*}[\partial I^n]\\&=\sum_{\tau\in I_{n-1}}^{}\phi_{n-1}((p_{\sigma})_{*}\circ j_{n-1}\circ (f_{\partial\sigma})_{*}[\partial I^n])\tau\end{align}$$
> 3. Holds from the fact that $\beta_{n}\circ\beta_{n+1}=0$ from [[CW-Complex|Proposition 8]] and $\Psi \circ\Phi=\text{id}$.
> 4. We have that: $$H_{n}(\mathcal{C}(K))=\text{ker}(d_{n}) / \text{im}(d_{n+1})\cong \text{ker}(\beta_{n}) / \text{im}(\beta_{n+1})\cong H_{n}(K^{(n+1)})\cong H_{n}(K)$$