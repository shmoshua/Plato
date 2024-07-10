> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ a smooth map. Then, 
> 1. $f$ is an ***submersion*** if $d_{p}f$ is surjective for all $p\in M$.
- **Remark**: If $f$ is a submersion, $m\geq n$.
- **Related definition**: A point $p\in M$ is: 
	1. a ***critical point*** if $d_{p}f$ is not surjective.
	2. a ***regular point*** if $d_{p}f$ is surjective.
- **Related definition**: A point $q\in N$ is: 
	1. a ***critical value*** if there exists a critical $p\in f^{-1}(q)$.
	2. a ***regular value*** if every $p\in f^{-1}(q)$ is regular.
---
##### Properties
> [!lemma] Theorem 1 (Local Submersion Theorem)
> Let $f:M\to N$ be a smooth map between smooth manifolds and $p\in M$.
> 1. if $d_{p}f$ is surjective, then there exists local coordinates $\varphi:=(x^1,\dots,x^m)$ at $p$ and $\psi:=(y^1,\dots,y^n)$ at $f(p)$ s.t. $$\psi f\varphi ^{-1}(x^1,\dots,x^m)=(x^1,\dots,x^n)$$

> [!proof]-
> Let $(U,\varphi)$ and $(V,\psi)$ be two charts at $p$ and $f(p)$ with $f(U)\subseteq V$. Then, consider $$g:=\psi f\varphi ^{-1}:\varphi(U)\to \psi(V)$$As $d_{0}g:\mathbb{R}^m\to \mathbb{R}^n$ is surjective, there exists a basis $\mathcal{B}$ s.t. $d_{0}g$ is a $n\times m$-matrix with: $$\begin{bmatrix}I_{n}&*\end{bmatrix}\in \text{Mat}_{n,m}(\mathbb{R})$$We now augment $g$ to $G$ defined as: $$G:\varphi(U)\to \mathbb{R}^{n}\times \mathbb{R}^{m-n},\quad x\mapsto(g(x),x^{n+1},\dots,x^m)$$with $d_{0}G:\mathbb{R}^m\to \mathbb{R}^m$ represented as: $$\begin{bmatrix}I_{n}&*\\0&I_{m-n}\end{bmatrix}\in \text{Mat}_{n,n}(\mathbb{R})$$Therefore, by [[Smooth Function|Inverse function theorem]], there exists open neighborhoods $U_{1}\subseteq \varphi(U)$ and $V_{1}\times V_{2}\subseteq \mathbb{R}^{n}\times \mathbb{R}^{m-n}$ s.t. $G|_{U_{1}}$ is a diffeomorphism at $0$ with $G(0)=0$. 
> 
> Let $\Phi:= G|_{U_{1}}\circ\varphi:\varphi ^{-1}(U_{1})\to G(U_{1})$. Then, on $G(U_{1})$, $$\psi f\Phi ^{-1}(x^1,..,x^m)=(g\circ G^{-1})(x^1,\dots,x^m)=(\pi \circ G\circ G^{-1})(x^1,\dots,x^m)=(x^1,\dots,x^n)$$which proves the statement. 
- **Corollary**: The set $\mathcal{I}:=\{ p\in M: p\text{ is regular}\}$ is open and $f|_{\mathcal{I}}$ is an submersion.
---
> [!lemma] Theorem 2 
> Let $f:M\to N$ be a smooth map between smooth manifolds. Then, 
> 1. for any $p\in M$ s.t. $d_{p}f$ is surjective, there exists an open neighborhood $U\ni p$ s.t. $f^{-1}(f(p))\cap U$ is a [[Submanifold|regular $(m-n)$-submanifold]] of $M$.
> 2. for any regular value $q\in N$, $f^{-1}(q)$ is either empty or is a proper regular $(m-n)$-submanifold of $M$.
> 3. if $f$ is a submersion, for any $q\in N$, $f^{-1}(q)$ is either empty, or is a proper regular $(m-n)$-submanifold of $M$.
> 4. if $f$ is a submersion, for a (proper) regular submanifold $L\subseteq N$, $f^{-1}(L)$ is a (proper) regular submanifold of $M$.

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
> 3. from 2.
> 4. Let $p\in f^{-1}(L)$. Then, let $(U,\varphi)$ be a chart at $f(p)$ s.t. $\varphi(f(p))=0$ and $\varphi(U\cap L)=\{ x\in \varphi(U):x^{\ell+1}=\dots =x^{n}=0 \}$.
>    
>    For $V:=f^{-1}(U)$, we have that: $(\varphi \circ f)(V\cap f^{-1}(L))=\varphi(U\cap L)$. This proves the statement.
---
> [!lemma] Theorem 3 (Sard, 1942)
> Let $U\subseteq \mathbb{R}^m$ be open and $f:U\to \mathbb{R}^n$ be a smooth map. Then, $$\lambda(f(C))=0$$where $\lambda$ is the [[Lebesgue measure]] and $C:=\{ x\in U :x\text{ is critical}\}$.

> [!proof]-
> We prove this using an induction on $m$. If $m=0$ and $n\geq 1$, the statement is true as $f(C)$ is at most one point which has measure zero in $\mathbb{R}^n$. 
> 
> Now, let $m\geq 1$ and write $f=(f^1,\dots,f^n)$. We set: $$C_{i}:=\{ x\in U:\partial_{\alpha}f(x)=0,\forall \left| \alpha \right| \leq i\}$$i.e. all partial derivatives of $f$ up to order $i$ vanish at $x$. Then, $C\supseteq C_{1}\supseteq C_{2}\supseteq\dots$. We now have:
> 1. **Showing $f(C \backslash C_{1})$ has measure $0$**:
>    For $n=1$, we have that $C=C_{1}$ and $f(C \backslash C_{1})$ is  empty. Therefore, we may assume $n\geq 2$. let $y\in C\backslash C_{1}$. Wlog we may assume that $\partial_{1}f^1(y)\neq 0$. By a change of variables $$h:U\to \mathbb{R}^m,\quad x\mapsto(f^1(x),x^2,\dots,x^m)$$ we get that $$d_{y}h=\begin{bmatrix}\left. \frac{ \partial f^1 }{ \partial x^1 } \right| _{y}&\cdots&\cdots&\left. \frac{ \partial f^1 }{ \partial x^m } \right| _{y}\\&1 \\&&\ddots\\&&&1\end{bmatrix}$$which is invertible. Therefore by the [[Smooth Function|inverse function theorem]], there is an open subset $y\in V\subseteq U$ and $V'\subseteq \mathbb{R}^m$ s.t. $h|_{V}:V\to V'$ is a diffeomorphism. 
>    
>    Now, define $g:=f\circ (h|_{V})^{-1}:V'\to \mathbb{R}^n$ and let $C'$ be the critical points of $g$. Then, by the chain rule, $h(V\cap C)=C'$. Therefore, $g(C')=f(V\cap C)$. It now suffices to show that $g(C')$ has measure $0$ since we can cover $U \backslash C_{1}$ with countably many $V$s and $f(C \backslash C_{1})$ has measure zero.
>    
>    We will show that $g$ has a special form. Let $$(t,x^2,\dots,x^m)=(f^1(x),x^2,\dots,x^m)=h(x)\in V'$$Then, $$\begin{align}g(t,x^2,\dots,x^m)&=f(x)\\&=(f^1(x),\dots,f^n(x))\\&=(t,f^2h^{-1}(t,x^2,\dots,x^m)),\dots,f^nh^{-1}(t,x^2,\dots,x^m))\\&=:(t,g^t(x^2,\dots,x^m))\end{align}$$where $g^t:\mathbb{R}^{m-1}\to \mathbb{R}^{n-1}$. Further, we have: $$d_{(t,x^2,\dots,x^m)}g=\begin{bmatrix}1&0\\ *&d_{(x^2,\dots,x^m)}g^t\end{bmatrix}$$Therefore, $(t,x^2,\dots,x^m)$ is a critical point of $g$ if and only if $(x^2,\dots,x^m)$ is a critical point of $g^t$. Let $C^t$ denote the critical points of $g^t$. Then, $$g(C')=\{ (t,z)\subseteq \mathbb{R}^n:z \in g^t(C^t) \}$$and $g(C')\cap (\{ t \}\times \mathbb{R}^{m-1})=\{ t \}\times g^t(C^t)$. As $g^t(C^t)$ has measure zero for all $t$, by Fubini $g(C')$ has measure zero.
>  2. **Showing $f(C_{i} \backslash C_{i+1})$ has measure zero for all $i\geq 1$**.
> 	Let $y\in C_{i} \backslash C_{i+1}$. Then, for some $1\leq r\leq n$ and some multi-index $1\leq j_{1}\leq\dots\leq j_{i+1}\leq n$, we have: $$w(y):=\frac{ \partial^i f^r }{ \partial x^{j_{2}}\dots \partial x^{j_{i+1}} }(y) =0$$but $\frac{\partial w}{\partial x^{j_{1}}}\neq 0$. Without loss of generality, assume $j_{1}=1$ and consider: $$h:U\to \mathbb{R}^m,\quad x\mapsto (w(x),x^2,\dots,x^m)$$which is again a diffeomorphism from $y\in V\subseteq U$ to some $V'\subseteq \mathbb{R}^m$. 
> 	
> 	By definition, $h(C_{i}\cap V)\subseteq \{ 0 \}\times \mathbb{R}^{m-1}$. Now, consider again the map $g:=f\circ (h|_{V})^{-1}:V'\to \mathbb{R}^n$. Then $f(C_{i}\cap V)=gh(C_{i}\cap V)\subseteq g(\{ 0 \}\times \mathbb{R}^{m-1})$ and we may consider $g':=g|_{\{ 0 \}\times \mathbb{R}^{m-1}}$. Observe that any point in $h(C_{i}\cap V)$ is certainly a critical point of $g$. Hence we are done by recurrence.
>3. **Showing that $f(C_{i})$ has measure zero for large enough $i$.**
>   Let $I_{\delta}\subseteq U$ be a hypercube of side length $\delta$. We will show that $f(C_{i}\cap I_{\delta})$ has measure zero for $i>m/n-1$. By Taylor, we have for $p\in C_{i}\cap I_{\delta}$ and $h$ with $x+h\in I_{\delta}$, $$f(x+h)=f(x)+R(x,h)$$where $\left\| R(x,h) \right\|\leq \xi \left\| h \right\|^{i+1}$ s.t. $\xi$ only depends on $f$ and $I_{\delta}$, by considering the integral form. Now, choose $N$ to subdivide $I_{\delta}$ into cubes of side length $\frac{\delta}{N}$. Let $I$ be one of these cubes containing $x\in C_{i}\cap I$. 
>   
>    Then, for all $h$ s.t. $f(x+h)\in C_{i}\cap I$, we have: $$\left\| f(x+h)-f(x) \right\| \leq \xi \left\| h \right\| ^{i+1}\leq \xi \left( \sqrt{ m } \frac{\delta}{N}\right)^{i+1} $$Therefore, $f(I)$ is contained in a hypercube with edges of the above length. There are at most $N^m$ such little cubes and hence $f(C_{i}\cap I_{\delta})$ is contained in a union of hypercubes whose sum of volumes is less than $$N^m\left( \xi \sqrt{ m } \frac{\delta}{N} \right)^{(i+1)n}=\left( \xi \sqrt{ m }\delta \right) ^{(i+1)n}N^{m-(i+1)n}$$For $i>m/n -1$, we can make this sum arbitrarily small by choosing $N$ large enough. Hence the assertion holds.
 - **Corollary**: For $f:M\to N$ smooth, for almost every $q\in N$, $f^{-1}(q)$ is a regular manifold of $M$ with $\text{T}_{p}f^{-1}(q)\cong \text{ker }d_{p}f$ as for $\gamma:(-\varepsilon,\varepsilon)\to f^{-1}(q)$ with $\gamma(0)=p$, $$0=\left. \frac{d}{dt} \right| _{t=0}q=\left. \frac{d}{dt} \right| _{t=0}f(\gamma(t))=d_{p}f\left( \dot{\gamma}(t) \right) $$
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
