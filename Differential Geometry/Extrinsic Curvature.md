#Definition #DifferentialGeometry 

> [!definition]
> Let $M\subseteq \mathbb{R}^3$ be a [[Surface|smooth surface]] and $N$ a [[Surface|normal vector field]]. The ***extrinsic curvature*** of $M$ at $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$ is:
> 1. $Q_{p}(v):=\braket{ \kappa_{\gamma}(0), N(p) }$ where $\kappa_{\gamma}$ is the curvature of the curve $\gamma:I\to M$ s.t. $0\in I$, $\gamma(0)=p$ and $\dot{\gamma}(0)=v$.
> 2. $A_{p}(v,v)$ where the ***second fundamental form*** $A_{p}:\text{T}_{p}M\times \text{T}_{p}M\to \mathbb{R}$ is given by: $$A_{p}(X,Y)=\sum_{i,j=1}^{2}\left. \frac{ \partial^{2}f }{ \partial x^i\partial x^j} \right| _{(0,0)}X^iY^j$$where given the orthogonal coordinate system s.t. $p=(0,0,0)$, $\text{T}_{p}M=\mathbb{R}^{2}\times \{ 0 \}$ and $N(p)=(0,0,1)$, $f:\mathbb{R}^2\to \mathbb{R}$ is a smooth function s.t. $\text{graph}(f)$ coincides with $M$ in some open neighborhood of $0$. 
---
##### Properties
> [!lemma] Theorem 1
> We have that:
> 1. $Q_{p}(v)$ is well-defined and is a quadratic form in $v$.
> 2. $Q_{p}(v)=Q_{p}(-v)$.

> [!proof]-
> We have:
> 1. Let $p\in M$ and $v\in \text{T}_{p}M$ s.t. $\|v\|=1$. Then, choose a orthogonal coordinate system s.t. 
> 	- $p=(0,0,0)$,
> 	- $\text{T}_{p}M=\mathbb{R}^2\times \{ 0 \}$ and 
> 	- $N(p)=(0,0,1)$.
> 	
> 	One sees that this orthogonal coordinate system does not change $Q_{p}(v)$ as $\kappa$ and $N$ behave nicely under orthogonal transformation and translation. Then, there exists some $0\in U\subseteq \mathbb{R}^2$ open s.t. there exists $f:U\to \mathbb{R}$ a smooth function where $M$ is locally $\text{graph}(f)$. 
> 	
> 	Now, we have $v=(v_{1},v_{2},0)$. Hence, for a smooth curve $\gamma:I\to M$ with $\gamma(0)=p$ and $\dot{\gamma}(0)=v$, from [[Regular Curve in Rn|Proposition 3]] and as $\|\dot{\gamma}(0)\|=\|v\|=1$,   $$Q_{p}(v)=\braket{ \kappa_{\gamma}(0) ,  N(p)}=\braket{ \ddot{\gamma}(0), N(p) }=\ddot{z} (0)  $$where $\gamma(t)=(x(t),y(t),z(t))$. However, as $M=\text{graph}(f)$ locally, $z(t)=f(x(t),y(t))$. Therefore, $$\dot{z}(t)=\frac{\partial f}{\partial x}(x(t),y(t))\dot{x}(t)+\frac{\partial f}{\partial y}(x(t),{y}(t))\dot{y}(t)$$and as $\left. \frac{ \partial f }{ \partial x }\right|_{t=0}=\partial_{x}f(x(0),y(0))=\partial_{x}f(0,0)=0$ as $f$ is tangent to $\text{T}_{p}M$ at $0$.  Therefore, $$\begin{align}\ddot{z}(0)&=\frac{ \partial^2 f }{ \partial x^{2} } (0,0)\dot{x}(0)^{2}+2\frac{ \partial ^2f }{ \partial x\partial y } (0,0))\dot{x}(0)\dot{y}(0)+\frac{ \partial ^2f }{ \partial  y^{2} } (0,0)\dot{y}(0)^{2}\\&=\begin{bmatrix}\dot{x}(0)&\dot{y}(0)\end{bmatrix}\begin{bmatrix}\frac{ \partial^2 f }{ \partial x^{2} } (0,0)&\frac{ \partial^2 f }{ \partial x\partial y } (0,0)\\\frac{ \partial^2 f }{ \partial x\partial y } (0,0)&\frac{ \partial^2 f }{ \partial y^{2} } (0,0)\end{bmatrix}\begin{bmatrix}\dot{x}(0)\\\dot{y}(0)\end{bmatrix}\\&=v^\top\text{H}_{f}|_{(0,0)}v\\&=\sum_{i,j=1}^{2}\left. \frac{ \partial^2f }{ \partial x^i\partial x^j } \right| _{(0,0)}v^iv^j \end{align} $$where $\text{H}_{f}$ denotes the Hessian matrix. 
> 	
> 	This proves that $Q_{p}(v)$ is well-defined and defines a quadratic form in $v$.
> 2. For a curve $\gamma$, let $\gamma'(t):=\gamma(-t)$. Then, $$\tau'(s)=-\tau(-s),\quad \kappa'(s)=\kappa(-s)$$
---
##### Examples
> [!h] Example 1 (Spheres)
> Let $M:=R\cdot S^2\subseteq \mathbb{R}^3$ be a sphere of radius $R$. Then, 
> 1. $Q_{p}(v)=\frac{1}{R}$ for any $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$. 

> [!proof]-
> For $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$, consider the plane $P$ in $\mathbb{R}^3$ that contains $0$, $p$ and $v$. Then, $P\cap M$ is a circle of radius $R$ and by [[Regular Curve in Rn|Example 1]], $$Q_{p}(v)=\frac{1}{R}\braket{ N(p) ,N(p)  } =\frac{1}{R}$$