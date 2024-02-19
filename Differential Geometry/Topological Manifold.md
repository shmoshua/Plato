#Definition #DifferentialGeometry 

> [!definition]
> A ***topological manifold $M$ of dimension $m$*** is a 2nd-countable [[Hausdorff space]] s.t. for all $p\in M$, there exists an open neighborhood $U\subseteq M$ s.t. $\varphi :U\to \varphi(U)\subseteq\mathbb{R}^m$ is a homeomorphism.
- **Related definition**: $(\varphi,U)$ is called a ***chart***.
- **Related definition**: Two charts $(\phi,U),(\psi,V)$ are ***compatible***, if $\phi \circ\psi ^{-1}:\psi(U\cap V)\to \phi(U\cap V)$ is a smooth diffeomorphism.
---

##### Vector fields

---

---
##### Examples
1. $M=\mathbb{R}^m$, chart $x^1,\dots,x^m$ standard coordinates. Then, $$g:=\sum_{i=1}^{m}dx^i\otimes dx^i$$is the Euclidean metric. Identify $\frac{ \partial  }{ \partial x^i }$ with $e_{i}\in \mathbb{R}^m$. Then, $g\left( \frac{ \partial  }{ \partial x^j },\frac{ \partial  }{ \partial x^k } \right)=\delta_{jk}=\braket{ e_{j} , e_{k} }$
2. $M=(0,\infty)\times(0,2\pi)$, with coordinates $r,\varphi$. $$g=dr^{2}+r^{2}d\varphi^{2}$$is the Euclidean coordinates in polar coordinates.
3. Let $M$ be a smooth manifold. Then there exists a Riemannian metric on $M$. 

Let $F:N\to M$ be a smooth map, $g$ a Riemmanian metric on $M$. Then, pullback of $g$ along $F$ is: $$(F^{*}g)_{p}(V,W)=g_{F(p)}(d_{p}F(V),d_{p}F(W))$$for $p\in N$, $V,W\in T_{p}N$

If $F$ is an immersion (i,e $d_{p}F is injective for all $p$$), then $F^{*}g$ is a Riemannian metric on $N$. 

Example: $M=\mathbb{R}^m$, $F:N\subseteq \mathbb{R}^n\hookrightarrow M=\mathbb{R}^m$ embedding. Then, $F^*g_{\text{Euclidean}}$ is the induced metric.

---
A smooth map $F:(N,k)\mapsto(M,g)$ is a local isometry if it is a local diffeomoroism and $F^{*}g=h$. for all $p\in N$, there existrs an open neighborhood $U$ s.t. $F|_{U}$ is a diffeomorphism

Example: $F:()$