#Definition #MeasureTheory 
> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]], $F:N\to M$ a [[Smooth Function|smooth map]] and $g$ a [[Riemannian metric]] on $M$. Then, the ***pullback of $g$ along $F$***  is: 
> $$(F^{*}g)_{p}(v,w):=g_{F(p)}(d_{p}F(v),d_{p}F(w))$$for $p\in N$, $v,w\in$ [[Tangent Space|$T_{p}N$]].
---
##### Properties
> [!lemma] Proposition 1
> If $F$ is an [[Differential|immersion]], then $F^{*}g$ is a [[Riemannian metric]] on $N$. 

> [!proof]+
> We will show that the metric coefficients $(F^{*}g)_{ij}$ meet the properties. Consider a local coordinate chart $(U,x=(x^1,\dots,x^n))$. Then:
> 1. **$(F^{*}g)_{ij}$ is symmetric**:
> 	$$\begin{align}(F^{*}g)_{ij}(p)&=(F^{*}g)_{p}\left(\left. \frac{ \partial  }{ \partial x ^i}    \right| _{p},\left. \frac{ \partial  }{ \partial x ^j}    \right| _{p}\right)\\&=g_{F(p)}\left(d_{p}F\left( \left. \frac{ \partial  }{ \partial x ^i}    \right| _{p} \right),d_{p}F\left( \left. \frac{ \partial  }{ \partial x ^j}    \right| _{p} \right) \right)\end{align}$$Therefore, the symmetry is inherited from $g_{F(p)}$.
> 2. **$(F^{*}g)_{ij}$ is positive definite**:
> 	For $v\in \mathbb{R}^n$, $$\begin{align}\sum_{i,j=1}^{n}v^i (F^{*}g)_{ij}(p)v^j&=\end{align}$$
> 
> 1. **$(F^{*}g)_{p}$ is bilinear**: we have: $$\begin{align}(F^{*}g)_{p}(av+b,w)&=g_{F(p)}(d_{p}F(av+b),d_{p}F(w))\\&=g_{F(p)}(d_{p}F(av+b),d_{p}F(w))\end{align}$$
> 	
> 2. **$(F^{*}g)_{p}$ is bilinear**:
>    For $[\varphi_{1},v]_{p},[\varphi_{2},w]_{p}\in T_{p}N$, $$(F^{*}g)_{p}([\varphi_{1},v]_{p},[\varphi_{2},w]_{p})=g_{F(p)}([\psi_{1},d_{\varphi(p)}(\psi F\varphi ^{-1})(v)]_{F(p)},[\psi_{2},d_{\varphi(p)}(\psi F\varphi ^{-1})(w)]_{F(p)})$$
> 2. 
 
---

Example: $M=\mathbb{R}^m$, $F:N\subseteq \mathbb{R}^n\hookrightarrow M=\mathbb{R}^m$ embedding. Then, $F^*g_{\text{Euclidean}}$ is the induced metric.

---
A smooth map $F:(N,k)\mapsto(M,g)$ is a local isometry if it is a local diffeomoroism and $F^{*}g=h$. for all $p\in N$, there existrs an open neighborhood $U$ s.t. $F|_{U}$ is a diffeomorphism

Example: $F:()$