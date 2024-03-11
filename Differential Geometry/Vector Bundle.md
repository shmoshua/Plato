#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]] of dimension $m$. A ***vector bundle of rank $k$*** is a triple $(E,\pi,M)$ s.t.
> 1. $E$ is a $(m+k)$-dimensional smooth manifold, called ***total space***,
> 2. $\pi: E\to M$ is a surjective smooth map, called ***projection*** s.t. for each $p\in M$, the ***fiber*** of $p$, defined to be $\pi ^{-1}(p)$, has the structure of a $k$-dimensional $\mathbb{R}$-vector space. 
> 3. **local triviality**: for all $p\in M$ there exists an open neighborhood $U\subseteq M$ of $p$ and a [[Diffeomorphism|diffeomorphism]] $\psi:\pi ^{-1}(U)\to U\times \mathbb{R}^k$ s.t. $$\psi|_{\pi ^{-1}(q)}:\pi ^{-1}(q)\to \{ q \}\times \mathbb{R}^k$$ is a linear isomorphism for all $q\in U$.
- **Related definition**: A (smooth) ***section*** $S$ of a vector bundle $(E,\pi,M)$ is a (smooth) map $S:M\to E$ with $\pi \circ S=\text{id}_{M}$. Then, 
	1. $\Gamma(E)$ denotes the 
- Remark: $(E^{*})_{p}=(E_{p})^{*}$
- 
---
##### Properties
> [!lemma] Lemma 1
> Given vector bundles $E,E'$ of rank $k,k'$, the following constructions are vector bundles:
> 1. $E^{*}\to M$ dual vector bundle of rank $k$
> 2. $E\oplus E'\to M$ direct sum of rank $k+k'$
> 3. $E \otimes E'\to M$ tensor product of rank $kk'$

> [!proof]-
> Wlog we can assume $\{ U_{\alpha} \}$ a cover where locally trivialized (by intersections of the covers) Then,
> 1. defined using $\{ U_{\alpha} \}$ and $\tau_{\beta\alpha}^{*}(q)=(\tau_{\beta\alpha}(q^{-1}))^{*}$ (check cocycle condition)
> 2. defined using $\{ U_{\alpha} \}$ and transition functions $\tau_{\beta\alpha}\oplus \tau'_{\beta\alpha}$:$$\begin{bmatrix} \tau_{\beta\alpha}&\\&\tau'_{\beta\alpha}\end{bmatrix}$$with $(E\oplus E')_{p}=E_{p}\oplus E_{p}'$
> 3. defined using $\{ U_{\alpha} \}$ and transition functions $\tau_{\beta\alpha}\otimes \tau'_{\beta\alpha}$
---
##### Examples
> [!h] Example 1
> $TM\xrightarrow{\pi}M$ where $\pi([\varphi,v]_{p})=p$. 
> 2. $T^{*}M\to M$ (exercise)

> [!proof]-
> Local trivialization as $\pi ^{-1}(U)=\bigsqcup_{q\in U}^{}T_{q}M$: $$\psi([\varphi,v]_{q})=(q,v)\in $$
