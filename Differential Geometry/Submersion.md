> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ a smooth map. Then, 
> 2. $f$ is an ***submersion*** if $d_{p}f$ is surjective for all $p\in M$.
- **Remark**: If $f$ is a submersion, $m\geq n$.
---
##### Properties
> [!lemma] Theorem 1 (Local Submersion Theorem)
> Let $f:M\to N$ be a smooth map between smooth manifolds and $p\in M$.
> 1. if $d_{p}f$ is surjective, then there exists local coordinates $\varphi:=(x^1,\dots,x^m)$ at $p$ and $\psi:=(y^1,\dots,y^n)$ at $f(p)$ s.t. $$\psi f\varphi ^{-1}(x^1,\dots,x^m)=(x^1,\dots,x^m,0,\dots,0)$$

> [!proof]-
> Let $(U,\varphi)$ and $(V,\psi)$ be two charts at $p$ and $f(p)$ with $f(U)\subseteq V$. Then, consider $$g:=\psi f\varphi ^{-1}:\varphi(U)\to \psi(V)$$As $d_{\varphi(p)}g:\mathbb{R}^m\to \mathbb{R}^n$ is injective, there exists a basis $\mathcal{B}$ s.t. $d_{0}g$ is a $n\times m$-matrix with: $$\begin{bmatrix}I_{m}\\0\end{bmatrix}\in \text{Mat}_{n,m}(\mathbb{R})$$We now augment $g$ to $G$ defined as: $$G:\varphi(U)\times \mathbb{R}^{n-m}\to \mathbb{R}^{n},\quad (x,z)=g(x)+(0,z)$$with $d_{0}G:\mathbb{R}^n\to \mathbb{R}^n$ represented as: $$\begin{bmatrix}I_{m}&0\\0&I_{n-m}\end{bmatrix}=I_{n}\in \text{Mat}_{n,n}(\mathbb{R})$$Therefore, by [[Smooth Function|Inverse function theorem]], there exists open neighborhoods $U_{1}\times U_{2}\subseteq \varphi(U)\times \mathbb{R}^{n-m}$ and $W\subseteq \mathbb{R}^{n}$ s.t. $G|_{U_{1}\times U_{2}}$ is a diffeomorphism at $0$ with $G(0)=0$. 
> 
> Let $\Psi:=(G|_{U_{1}\times U_{2}})^{-1}\circ\psi:V\cap \psi ^{-1}(W)\to \Psi(V\cap \psi ^{-1}(W))$, which is a valid chart for $N$ at $f(p)$ as $\Psi(f(p))=0$. Therefore, we have that: $$\Psi f\varphi ^{-1}(x^1,\dots,x^m)=G(x^1,\dots,x^m,0,\dots,0)=(x^1,\dots,x^m,0,\dots,0)$$which proves the statement.
- **Corollary**: The set $\mathcal{I}:=\{ p\in M: d_{p}f\text{ is injective}\}$ is open and $f|_{\mathcal{I}}$ is an immersion.
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
