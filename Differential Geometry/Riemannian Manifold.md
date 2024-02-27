> [!definition]
> A ***Riemannian manifold*** is a pair $(M,g)$ where $M$ is a [[smooth manifold]] and $g$ is a [[Riemannian metric]].

---
hehe
4. Notation: $d_{p}\varphi^id_{p}\varphi^j= \frac{1}{2}\left(  d_{p}\varphi^i \otimes  d_{p}\varphi^j+d_{p}\varphi^j \otimes  d_{p}\varphi^i \right)$ with $g=g_{ij}d\varphi^id\varphi^j$
5. $\left| V \right|_{g}^{2}=g_{p}(V,V)$ for $V\in T_{p}M$.
---
##### Properties
> [!lemma] Theorem (Nash, 1956)
> There exists $f\in \mathbb{N}\to \mathbb{N}$ s.t. for all RIemannian manifold $(M,g)$ with dimension $m$, there exists a submanifold $\tilde{M}\subseteq \mathbb{R}^{f(m)}$ and an isometry $(M,g)\to(\tilde{M},\text{ induced metric})$.
---
> [!lemma] Lemma 2 (Musical isomorphisms)
> Let $(M,g)$ be a Riemannian manifold. Then, $$\begin{array}{cccc} &{T_{p}M}&\to&{T_{p}^{*}M}\\&{V} &\mapsto & {V^{\flat}:w\mapsto g_{p}(v,w)} \end{array}{}$$is an isomorphism with the inverse: $$\begin{array}{cccc} {}&{T^{*}_{p}M}&\to&{T_{p}M}\\&{\xi} &\mapsto & {\xi^\sharp} \end{array}{}$$is the inverse of this map. 

> [!proof]-
> Follows from the non-degeneracy of the bilinear form $g_{p}$.
---
$$V^\flat=g(V,\cdot )=g_{ij}V^idx^j=V_{j}dx^j$$
$V_{j}=g_{ij}V^i$ flipped sum sign (index lowering)
$\xi=\xi_{j}dx^j$ and 
$$\xi^\sharp=g^{ij}\xi_{j}\partial x^i=\xi^i\partial x^i$$
$\xi^i=g^{ij}\xi_{j}$ "index raising"

Inner product on $T^{*}M$: $$g^{-1}(\xi,\eta)=g(\xi^\sharp,\eta^\sharp)$$
$g^{-1}(dx^i,dx^j)=g^{ij}$
---
##### Examples
> [!h] Example 1
> 