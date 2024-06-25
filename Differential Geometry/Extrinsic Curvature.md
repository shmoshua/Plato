#Definition #DifferentialGeometry 

> [!definition]
> Let $M\subseteq \mathbb{R}^3$ be a [[Surface|smooth surface]] and $N$ a [[Surface|normal vector field]]. The ***extrinsic curvature*** of $M$ at $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$ is:
> 1. $Q_{p}(v):=\braket{ \kappa_{\gamma}(0), N(p) }$ where $\kappa_{\gamma}$ is the curvature of the curve $\gamma:I\to M$ s.t. $0\in I$, $\gamma(0)=p$ and $\dot{\gamma}(0)=v$.
---
##### Properties
> [!lemma] Theorem 1
> We have that:
> 1. $Q_{p}(v)$ is well-defined.
> 2. $Q_{p}(v)=Q_{p}(-v)$.

> [!proof]+
> We have:
> 1. Let $p\in M$ and $v\in \text{T}_{p}M$ s.t. $\|v\|=1$. Then, choose a orthogonal coordinate system s.t. 
> 	- $p=(0,0,0)$,
> 	- $\text{T}_{p}M=\mathbb{R}^2\times \{ 0 \}$ and 
> 	- $N(p)=(0,0,1)$.
> 	
> 	One sees that this orthogonal coordinate system does not change $Q_{p}(v)$ as $\kappa$ and $N$ behave nicely under orthogonal transformation and translation. Then, there exists some $0\in U\subseteq \mathbb{R}^2$ open s.t. there exists $f:U\to \mathbb{R}$ a smooth function where $M$ is locally $\text{graph}(f)$. 
> 	
> 	Now, we have $v=(v_{1},v_{2},0)$. Hence, for a smooth curve $\gamma:I\to M$ with $\gamma(0)=p$ and $\dot{\gamma}(0)=v$, from [[Regular Curve in Rn|Proposition 3]] and as $\|\dot{\gamma}(0)\|=\|v\|=1$,   $$Q_{p}(v)=\braket{ \kappa_{\gamma}(0) ,  N(p)}=\braket{ \ddot{\gamma}(0), N(p) }=\ddot{z} (0)  $$where $\gamma(t)=(x(t),y(t),z(t))$. However, as $M=\text{graph}(f)$ locally, $z(t)=f(x(t),y(t))$. Therefore, $$\dot{z}(t)=\frac{\partial f}{\partial x}(x(t),y(t))\dot{x}(t)+\frac{\partial f}{\partial y}(x(t),{y}(t))\dot{y}(t)$$and as $\left. \frac{ \partial f }{ \partial x }\right|_{t=0}=\partial_{x}f(x(0),y(0))=\partial_{x}f(0,0)=0$ as $f$ is tangent to $\text{T}_{p}M$ at $0$.  Therefore, $$\ddot{z}(0)=\frac{ \partial^2 f }{ \partial x^{2} } (x(t),y(t))\dot{x}(t)^{2}+\frac{ \partial ^2f }{ \partial x\partial y } (x(t),y(t))\dot{x}(t)\dot{y}(t)+\frac{ \partial^2 f }{ \partial y\partial x } (x(t),y(t))\dot{x}(t)^{2}+\frac{ \partial ^2f }{ \partial x\partial y } (x(t),y(t))\dot{x}(t)\dot{y}(t) $$
---
##### Examples
> [!h] Example 1 (Spheres)
> Let $M:=R\cdot S^2\subseteq \mathbb{R}^3$ be a sphere of radius $R$. Then, 
> 1. $Q_{p}(v)=\frac{1}{R}$ for any $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$. 

> [!proof]-
> For $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$, consider the plane $P$ in $\mathbb{R}^3$ that contains $0$, $p$ and $v$. Then, $P\cap M$ is a circle of radius $R$ and by [[Regular Curve in Rn|Example 1]], $$Q_{p}(v)=\frac{1}{R}\braket{ N(p) ,N(p)  } =\frac{1}{R}$$