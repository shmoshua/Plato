> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ a smooth map. Then, 
> 2. $f$ is an ***submersion*** if $d_{p}f$ is surjective for all $p\in M$.
- **Remark**: If $f$ is a submersion, $m\geq n$.
---
##### Properties
> [!lemma] Theorem 1 (Local Submersion Theorem)
> Let $f:M\to N$ be a smooth map between smooth manifolds and $p\in M$.
> 1. if $d_{p}f$ is surjective, then there exists local coordinates $\varphi:=(x^1,\dots,x^m)$ at $p$ and $\psi:=(y^1,\dots,y^n)$ at $f(p)$ s.t. $$\psi f\varphi ^{-1}(x^1,\dots,x^m)=(x^1,\dots,x^n)$$

> [!proof]-
> Let $(U,\varphi)$ and $(V,\psi)$ be two charts at $p$ and $f(p)$ with $f(U)\subseteq V$. Then, consider $$g:=\psi f\varphi ^{-1}:\varphi(U)\to \psi(V)$$As $d_{0}g:\mathbb{R}^m\to \mathbb{R}^n$ is surjective, there exists a basis $\mathcal{B}$ s.t. $d_{0}g$ is a $n\times m$-matrix with: $$\begin{bmatrix}I_{n}&*\end{bmatrix}\in \text{Mat}_{n,m}(\mathbb{R})$$We now augment $g$ to $G$ defined as: $$G:\varphi(U)\to \mathbb{R}^{n}\times \mathbb{R}^{m-n},\quad x\mapsto(g(x),x^{n+1},\dots,x^m)$$with $d_{0}G:\mathbb{R}^m\to \mathbb{R}^m$ represented as: $$\begin{bmatrix}I_{n}&*\\0&I_{m-n}\end{bmatrix}\in \text{Mat}_{n,n}(\mathbb{R})$$Therefore, by [[Smooth Function|Inverse function theorem]], there exists open neighborhoods $U_{1}\subseteq \varphi(U)$ and $V_{1}\times V_{2}\subseteq \mathbb{R}^{n}\times \mathbb{R}^{m-n}$ s.t. $G|_{U_{1}}$ is a diffeomorphism at $0$ with $G(0)=0$. 
> 
> Let $\Phi:= G|_{U_{1}}\circ\varphi:\varphi ^{-1}(U_{1})\to G(U_{1})$. Then, on $G(U_{1})$, $$\psi f\Phi ^{-1}(x^1,..,x^m)=(g\circ G^{-1})(x^1,\dots,x^m)=(\pi \circ G\circ G^{-1})(x^1,\dots,x^m)=(x^1,\dots,x^n)$$which proves the statement. 
- **Corollary**: The set $\mathcal{I}:=\{ p\in M: d_{p}f\text{ is surjective}\}$ is open and $f|_{\mathcal{I}}$ is an submersion.
---
> [!lemma] Corollary 2 
> Let $f:M\to N$ be a smooth map between smooth manifolds. Then, 
> 1. for any $p\in M$ s.t. $d_{p}f$ is surjective, there exists an open neighborhood $U\ni p$ s.t. $f^{-1}(f(p))\cap U$ is a [[Submanifold|regular $(m-n)$-submanifold]] of $M$.
> 2. if $f$ is a submersion, for any $q\in N$, $f^{-1}(q)$ is either empty, or is a proper regular $(m-n)$-submanifold of $M$.
> 3. if $f$ is a submersion, for a (proper) regular submanifold $L\subseteq M$, $f^{-1}(L)$ is a (proper) 

> [!proof]-
> We have:
> 1. Let $p\in M$. If $d_{p}f$ is surjective, then by the local submersion theorem, there exists $(U,\varphi)$ at $p$ and $(V,\psi)$ at $f(p)$ with $f(U)\subseteq V$ s.t. $$\psi f\varphi ^{-1}(x^1,\dots,x^m)=(x^1,\dots,x^n)$$
>    
>    Let $q\in f^{-1}(f(p))\cap U$. Then, let us define: $$\Psi:U\to \mathbb{R}^{m},\quad x\mapsto(x^{n+1}(x)-x^{n+1}(q),\dots,x^{m}(x)-x^{m}(q),\psi(f(x)))$$which is a smooth chart. We have:
> 	1. $\Psi(q)=0$. 
> 	2. $\Psi(U\cap f^{-1}(f(p)))=\{ y\in \Psi(U):y^{m-n+1}=\dots=y^m=0\}$
> 
> 	Therefore, $U\cap f^{-1}(f(p))$ is a submanifold.
> 2. If $f^{-1}(q)$ is non-empty, by 1 it is a submanifold as being a submanifold is a local condition. Further it is proper as $f^{-1}(q)$ is closed by [[Submanifold|Proposition 3]].
---
##### Examples
> [!lh] Exmaple 1 (Submersion)
> We have that:
> 1. a projection $\pi:M\times N\to M$ is a submersion.
> 3. $\mathbb{R}^n\backslash\{ 0 \}\to S^{n-1},x\mapsto x /\|x\|$ is a submersion.
---
![[Tangent Bundle#^d01715]]
![[Tangent Bundle#^04ed06|p]]
---
