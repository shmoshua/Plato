#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ a smooth map. Then, 
> 1. $f$ is an ***immersion*** if $d_{p}f$ is injective for all $p\in M$.
- **Remark**: If $f$ is a immersion, $m\leq n$.
---
##### Properties
> [!lemma] Theorem 1 (Local Immersion Theorem)
> Let $f:M\to N$ be a smooth map between smooth manifolds and $p\in M$.
> 1. if $d_{p}f$ is injective, then there exists local coordinates $\varphi:=(x^1,\dots,x^m)$ at $p$ and $\psi:=(y^1,\dots,y^n)$ at $f(p)$ s.t. $$\psi f\varphi ^{-1}(x^1,\dots,x^m)=(x^1,\dots,x^m,0,\dots,0)$$

> [!proof]-
> Let $(U,\varphi)$ and $(V,\psi)$ be two charts at $p$ and $f(p)$ with $f(U)\subseteq V$. Then, consider $$g:=\psi f\varphi ^{-1}:\varphi(U)\to \psi(V)$$As $d_{0}g:\mathbb{R}^m\to \mathbb{R}^n$ is injective, there exists a basis $\mathcal{B}$ s.t. $d_{0}g$ is a $n\times m$-matrix with: $$\begin{bmatrix}I_{m}\\0\end{bmatrix}\in \text{Mat}_{n,m}(\mathbb{R})$$We now augment $g$ to $G$ defined as: $$G:\varphi(U)\times \mathbb{R}^{n-m}\to \mathbb{R}^{n},\quad (x,z)=g(x)+(0,z)$$with $d_{0}G:\mathbb{R}^n\to \mathbb{R}^n$ represented as: $$\begin{bmatrix}I_{m}&0\\0&I_{n-m}\end{bmatrix}=I_{n}\in \text{Mat}_{n,n}(\mathbb{R})$$Therefore, by [[Smooth Function|Inverse function theorem]], there exists open neighborhoods $U_{1}\times U_{2}\subseteq \varphi(U)\times \mathbb{R}^{n-m}$ and $W\subseteq \mathbb{R}^{n}$ s.t. $G|_{U_{1}\times U_{2}}$ is a diffeomorphism at $0$ with $G(0)=0$. 
> 
> Let $\Psi:=(G|_{U_{1}\times U_{2}})^{-1}\circ\psi:V\cap \psi ^{-1}(W)\to \Psi(V\cap \psi ^{-1}(W))$, which is a valid chart for $N$ at $f(p)$ as $\Psi(f(p))=0$. Therefore, we have that: $$\Psi f\varphi ^{-1}(x^1,\dots,x^m)=G^{-1}\circ G(x^1,\dots,x^m,0,\dots,0)=(x^1,\dots,x^m,0,\dots,0)$$which proves the statement.
- **Corollary**: The set $\mathcal{I}:=\{ p\in M: d_{p}f\text{ is injective}\}$ is open and $f|_{\mathcal{I}}$ is an immersion.
---
> [!lemma] Corollary 2 (An immersion is locally an embedding)
> Let $f:M\to N$ be a smooth map between smooth manifolds. TFAE:
> 1. $f$ is an immersion.
> 2. For any $p\in M$, there exists an open neighborhood $U\ni p$ s.t. $f|_{U}:U\to f(U)$ is an [[Submanifold|embedding]] of $N$.

> [!proof]-
> We have:
> 1. (1=>2): If $f$ is an immersion, let $p\in M$. Then $d_{p}f$ is injective and by the local immersion theorem, there exists $(U,\varphi)$ at $p$ and $(V,\psi)$ at $f(p)$ with $f(U)\subseteq V$ s.t. $$\psi f\varphi ^{-1}(x^1,\dots,x^m)=(x^1,\dots,x^m,0,\dots,0)$$Then, $f:U\to f(U)$ is of course injective and surjective. Hence, $f$ is a diffeomorphism. 
>    
>    Let $q\in U$. Then, we have that $\psi(f(q))=(x^1(q),\dots,x^m(q),0,\dots,0)$. Modulo translating by a constant and taking a preimage $V$ of $(-\varepsilon,\varepsilon)^n$ and taking $U\cap f^{-1}(V)$, we have that $\psi$ is a chart that gives $f(U)$ a submanifold structure. 
>  2. (2=>1): If every poiint has a neighborhood where $f$ is an embedding, $f$ has full rank everywhere so it is an immersion.
---
![[Submanifold#^77709c]]
![[Submanifold#^ff863e|p]]

---
> [!lemma] Proposition 3 (Properness and Embeddings)
> Let $f\in C^\infty(M,N)$ where $f$ is an injective immersion. Then, 
> 1. if $f$ is [[Proper Map|proper]], then $f$ is an embedding.
> 1. if $M$ is [[Compact Space|compact]], then $f$ is an embedding.

> [!proof]-
> We have that:
> 1. If $f$ is proper, then it is closed by [[Proper Map|Proposition 1]] because topological manifolds are locally compact. Therefore, $f:M\to f(M)$ is a closed continuous bijection, which is a homeomorphism. Hence, by [[Submanifold|Proposition 2]], $f$ is an embedding. 
> 2. For any $K\subseteq N$ compact, $K$ is closed and $f^{-1}(K)$ is closed as well. However, as $M$ is compact, $f^{-1}(K)$ is compact and hence $f$ is proper. This proves the statement.
>    
>    Alternatively, as $M$ is compact and $f(M)\subseteq N$ is Hausdorff, by [[Compact Space|Proposition 1]], $f:M\to f(M)$ is a homeomorphism.
---
> [!lemma] Theorem 4
> Any smooth manifold $M$ immerses into $\mathbb{R}^{2m-b(n)}$ where $b(n)$ denotes the number of binary digits in $n$.
---
##### Examples
> [!h] Example 1 (Immersion)
> Let $\gamma:\mathbb{R}\to \mathbb{R}^{2},t\mapsto(t^2,t^3-t)$ be a [[Regular Curve in Rn|regular curve]]. Then, 
> 1. $\gamma$ is an immersion.
---
> [!h] Example 2 (Projective Space)
> We have that
> 1. $\mathbb{R}\mathbb{P}^2$ does not embed in $\mathbb{R}^3$.
> 2. $\mathbb{R}\mathbb{P}^2$ immerses into $\mathbb{R}^3$ as the Boy's surface.
> 3. $\mathbb{R}\mathbb{P}^{2}$ embeds into $\mathbb{R}^4$ called Veronese embedding, given by: $$S^2\to \mathbb{R}^4,\quad (x,y,z)\mapsto(x^{2}-y^{2},xy,yz,xz)$$
---
