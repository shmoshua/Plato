#Definition #DifferentialGeometry 

> [!definition]
> Let $M\subseteq \mathbb{R}^3$ be a [[Surface|smooth surface]] and $N$ a [[Surface|normal vector field]]. The ***extrinsic curvature*** of $M$ at $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$ is:
> 1. $Q_{p}(v):=\braket{ \kappa_{\gamma}(0), N(p) }$ where $\kappa_{\gamma}$ is the curvature of the curve $\gamma:I\to M$ s.t. $0\in I$, $\gamma(0)=p$ and $\dot{\gamma}(0)=v$.
> 2. $A_{p}(v,v)$ where the ***second fundamental form*** $A_{p}:\text{T}_{p}M\times \text{T}_{p}M\to \mathbb{R}$ is given by: $$A_{p}(X,Y)=\sum_{i,j=1}^{2}\left. \frac{ \partial^{2}f }{ \partial x^i\partial x^j} \right| _{(0,0)}X^iY^j$$where given the orthogonal coordinate system s.t. $p=(0,0,0)$, $\text{T}_{p}M=\mathbb{R}^{2}\times \{ 0 \}$ and $N(p)=(0,0,1)$, $f:\mathbb{R}^2\to \mathbb{R}$ is a smooth function s.t. $\text{graph}(f)$ coincides with $M$ in some open neighborhood of $0$. 
- **Related definition**: By diagonalizoing the second fundamental form $A_{p}$, we get the ONB vectors $e_{1},e_{2}\in \mathbb{R}^2$ called ***principal axes of curvature*** at $p$ and $A_{p}=\text{diag}(k_{1},k_{2})$ for $k_{1},k_{2}\in \mathbb{R}$ called the ***principal curvatures*** at $p$. Then,
	1. $H:=k_{1}+k_{2}=\text{tr}(A_{p})$ is called the ***mean curvature*** at $p$ and
	2. $K:=k_{1}k_{2}=\text{det}(A_{p})$ is called the ***Gauss curvature*** at $p$.
- **Remark**: If $K>0$, $M$ is a ***bulge*** at $p$. If $K<0$, $M$ is a ***saddle*** at $p$. If $H=0$, then $M$ is a ***minimal surface*** at $p$, e.g. soap film.
- **Related definition**: For $X,Y\in \Gamma(\text{T}M)$, we have that $A(X,Y)_{p}:=A_{p}(X_{p},Y_{p})\in \mathbb{R}$. 
---
##### Properties
> [!lemma] Theorem 1
> We have that:
> 1. $Q_{p}(v)$ is well-defined and is a quadratic form in $v$.
> 2. $Q_{p}(v)=Q_{p}(-v)$.
> 3. $A_{p}$ is a symmetric bilinear form.
> 4. $A_{p}(v,v)=Q_{p}(v)$.

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
> 3. From 1, we see that $A_{p}(X,Y)$ is given by $X^\top\text{H}_{f}|_{(0,0)}Y$ where $\text{H}_{f}$ is the Hessian of $f$.

- **Corollary**:Let $k_{1},k_{2}$ be the principal curvatures of $M$ at $p$ with $k_{1}<k_{2}$. Then, 
	1. $k_{1}=\min_{v\in \text{T}_{p}M,\|v\|=1}A_{p}(v,v)$
	2. $k_{2}=\max_{v\in \text{T}_{p}M,\|v\|=1}A_{p}(v,v)$
---
> [!lemma] Theorem 2
> Let $M\subseteq \mathbb{R}^3$ be a [[Surface|smooth surface]] and $S:\mathbb{R}^3\to \mathbb{R}^3$ be a symmetry of $M$, i.e. $S$ is an isometry s.t. $S(M)=M$. Let $p\in M$. If it holds that:
> 1. $S(p)=p$,
> 2. $S(\text{T}_{p}M)=\text{T}_{p}M$ and 
> 3. there exists a line $L\subseteq \text{T}_{p}M$ s.t. $S|_{\text{T}_{p}M}$ is a reflection across $L$, 
> 
> then, $S$ is either a reflection by $L$ or rotation at $L$ by $\pi$. Further, the principal axes of curvature $e_{1},e_{2}$ at $p$ are:
> 1. contained in $L$ and $L^{\bot}$ in $\text{T}_{p}M$ respectively if $S$ is a reflection.
> 2. $\frac{\pi}{4}$ to $L$ in $\text{T}_{p}M$ if $S$ is a rotation.

> [!proof]-
> From the conditions, we follow that the only possible scenarios are when $S$ is a reflection or a rotation. Then, 
> 1. If $S$ is a reflection, by the condition, it would have to be across a plane $P$ where $L\subseteq P$. Further, we get that $N(p)\in P$. We will now show the statement. Let $e_{1},e_{2}\in \text{T}_{p}M$ s.t. $e_{1},e_{2}$ diagonalize $A_{p}$. Then, we have that: $$A_{p}=[e_{1}|e_{2}]\text{diag}(k_{1},k_{2})\begin{bmatrix}e_{1}|e_{2}\end{bmatrix}^\top$$If $k_{1}=k_{2}$, then $A=k_{1}I$ in any ONB. Therefore, we can construct a ONB contained in $L$ and $L^{\bot}$. 
>    
>    Therefore, assume  $k_{1}\neq k_{2}$. We claim that $S(e_{1}),S(e_{2})$ also diagonalize $A_{p}$. By the geometric symmetry,  $A_{p}(S(X),S(Y))=A_{p}(X,Y)$. Therefore, $S(e_{1}),S(e_{2})$ diagonalize $A_{p}$ as well. However, from $k_{1}\neq k_{2}$, 
>    
>    We have $A_{p}(S(e_{1}),S(e_{1}))=A_{p}(e_{1},e_{1})=k_{1}$. Therefore, $S(e_{1})=\pm e_{1}$. If $S(e_{1})=e_{1}$, then $e_{1}\in L$ otherwise, $e_{1}\in L^{\bot}$. By symmetry, it follows that $e_{1},e_{2}$ are contained in $L$ and $L^{\bot}$ respectively.
> 2. If $S$ is a rotation, by the condition, it has to be a rotation around $L$ by $\pi$ with $p\in L$. Further, $S(N(p))=-N(p)$. Then, the argument is analogous as above, up to a sign change. Therefore, the statement still holds.
---
> [!lemma] Theorem 3
> Let $M\subseteq \mathbb{R}^3$ be a smooth surface and $N$ a normal vector field. Then, for $X,Y\in \Gamma(\text{T}M)$,
> 1. $A(X,Y)=\braket{ D_{X}Y , N }=-\braket{ D_{X}N , Y }$

> [!proof]+

- **Corollary**: $\braket{ D_{X}Y , N }_{p}$ depends on only $X_{p},Y_{p}$ and not on any derivatives of $Y$. 
---
##### Examples
> [!h] Example 1 (Spheres)
> Let $M:=R\cdot S^2\subseteq \mathbb{R}^3$ be a sphere of radius $R$. Then, 
> 1. $Q_{p}(v)=\frac{1}{R}$ for any $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$. 
> 2. $k_{1}=k_{2}=\frac{1}{R}$ from [[Regular Curve in Rn|Exercise 1]].
> 3. $A_{p}(X,Y)=\frac{1}{R}\braket{ X , Y }$
> 4. $H=\frac{2}{R}$,
> 5. $K=\frac{1}{R^{2}}>0$ and $M$ is a bulge everywhere.

> [!proof]-
> For $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$, consider the plane $P$ in $\mathbb{R}^3$ that contains $0$, $p$ and $v$. Then, $P\cap M$ is a circle of radius $R$ and by [[Regular Curve in Rn|Example 1]], $$Q_{p}(v)=\frac{1}{R}\braket{ N(p) ,N(p)  } =\frac{1}{R}$$
---
> [!h] Example 2 (Surface of Revolution)
> Let $f:I\to \mathbb{R}$ be smooth. Then, the surface of revolution is defined as: $$M_{f}:=\{ (x,y,z)\subseteq I\times \mathbb{R}^2:f(x)=\sqrt{ y^{2}+z^{2} } \}$$Then, with respect to the outward $N$, 
> 1. $e_{1}=\tau(s)$ given by $\gamma: x\mapsto (x,f(x))$ and $e_{2}$ is $e_{1}$ rotated by $\frac{\pi}{2}$.
> 1. $k_{1}=\frac{\ddot{f}(x)}{(1+\dot{f}(x)^{2})^{3/2}},k_{2}=-\frac{1}{f(x)\sqrt{ 1+\dot{f}(x)^{2} }}$.
> 2. $H=\frac{1}{\sqrt{ 1+\dot{f}(x)^{2} }}\left( \frac{\ddot{f}(x)}{1+\dot{f}(x)^{2}}-\frac{1}{f(x)} \right)$, $K=-\frac{\ddot{f}(x)}{f(x)(1+\dot{f}(x)^{2})^{2}}$.

> [!proof]-
> By rotational symmetry, we only have to show it for $p:=(x,0,f(x))$. Then, $$e_{1}=\frac{(1,0,\dot{f}(x))}{\sqrt{ 1+\dot{f}(x)^{2} }},\quad e_{2}=(0,1,0)$$Therefore, by [[Regular Curve in Rn|R2 Theorem 1.3]], $$k_{1}=\frac{\ddot{f}(x)}{(1+\dot{f}(x)^{2})^{3/2}}$$For $k_{2}$, the projection of the vertical circle at $x$ onto the plane containing $N(p)$ and $e_{2}$ is the osculating circle at point $x$. Hence, the curvature is given by the projection of the curvature of the circle. Therefore, $$k_{2}=\left\langle \frac{(0,0,-1)}{f(x)} , \frac{(-\dot{f}(x),0,1)}{\sqrt{ 1+\dot{f}(x)^{2} }} \right\rangle=-\frac{1}{f(x)\sqrt{ 1+\dot{f}(x)^{2} }} $$
> The rest follows from the calculations.
---
> [!h] Example 3 (Cylinders)
> Let $M$ be a cylinder of side circle with radius $R$. Then, for $p$ on the side of $M$,
> 1. $e_{1}$ is orthogonal to the base and $e_{2}$ is parallel to the base. 
> 2. $k_{1}=0$, $k_{2}=-\frac{1}{R}$. 
> 3. $H=-\frac{1}{R}$
> 4. $K=0$
---
> [!h] Example 4 (Catenoid)
> Let $\gamma:\mathbb{R}\to \mathbb{R},t\mapsto \cosh(t)$. Then, consider $M$ as the revolution of $\gamma$ along the $x$-axis. Then, 
> 1. $e_{1}=\dot{\gamma}(s)$ and $e_{2}=\begin{bmatrix}0&-1\\1&0\end{bmatrix}e_{1}$ in $\text{T}_{p}M$.
> 2. As $\gamma$ is concave, $k_{1},k_{2}$ have opposite signs.
> 3. $k_{1}=\frac{1}{\cosh ^{2}(t)}=-k_{2}$
> 4. $M$ is a minimal surface.

> [!proof]-
> We have that:
> $$k_{1}=k_{\gamma}(s(t))=\frac{\cosh(t)}{(1+\sinh^2(t))^{3/2}}=\frac{1}{\cosh ^{2}(t)}$$$$k_{2}=-\frac{1}{\cosh(t)\sqrt{ 1+\sinh ^{2}(x) }}=-\frac{1}{\cosh ^{2}(t)}$$
---
> [!h] Example 5 (Helicoid)
> A ***helicoid*** is a smooth surface: $$H_{b}:=\{ (x,y,z)\in \mathbb{R}^3:y=x\tan(bz) \}$$
> Then, 
> 1. $H=0$ and $H_{b}$ is a minimal surface.
---

