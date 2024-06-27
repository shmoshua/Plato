#Definition #DifferentialGeometry 

> [!definition]
> Let $M\subseteq \mathbb{R}^3$ be a [[Surface|smooth surface]] and $N$ a [[Surface|normal vector field]]. The ***extrinsic curvature*** of $M$ at $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$ is:
> 1. $Q_{p}(v):=\braket{ \kappa_{\gamma}(0), N(p) }$ where $\kappa_{\gamma}$ is the curvature of the curve $\gamma:I\to M$ s.t. $0\in I$, $\gamma(0)=p$ and $\dot{\gamma}(0)=v$.
> 2. $A_{p}(v,v)$ where the ***second fundamental form*** $A_{p}:\text{T}_{p}M\times \text{T}_{p}M\to \mathbb{R}$ is given by: $$A_{p}(x,y)=\sum_{i,j=1}^{2}\left. \frac{ \partial^{2}f }{ \partial x^i\partial x^j} \right| _{(0,0)}x^iy^j$$where given the orthogonal coordinate system s.t. $p=(0,0,0)$, $\text{T}_{p}M=\mathbb{R}^{2}\times \{ 0 \}$ and $N(p)=(0,0,1)$, $f:\mathbb{R}^2\to \mathbb{R}$ is a smooth function s.t. $\text{graph}(f)$ coincides with $M$ in some open neighborhood of $0$. 
- **Related definition**: By diagonalizoing the second fundamental form $A_{p}$, we get the ONB vectors $e_{1},e_{2}\in \mathbb{R}^2$ called ***principal axes of curvature*** at $p$ and $A_{p}=\text{diag}(k_{1},k_{2})$ for $k_{1},k_{2}\in \mathbb{R}$ called the ***principal curvatures*** at $p$. Then,
	1. $H:=k_{1}+k_{2}=\text{tr}(A_{p})$ is called the ***mean curvature*** at $p$ and
	2. $K:=k_{1}k_{2}=\text{det}(A_{p})$ is called the ***Gauss curvature*** at $p$.
- **Remark**: If $K>0$, $M$ is a ***bulge*** at $p$. If $K<0$, $M$ is a ***saddle*** at $p$. If $H=0$, then $M$ is a ***minimal surface*** at $p$, e.g. soap film.
- **Related definition**: For $X,Y\in \Gamma(\text{T}M)$, we have that $A(X,Y)_{p}:=A_{p}(X_{p},Y_{p})\in \mathbb{R}$. 
- **Related definition**: The ***Weingarten map*** is $W:\Gamma(\text{T}M)\to\Gamma(\text{T}M),X\mapsto D_{X}N$.
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
> 1. $A(X,Y)=\braket{ D_{X}Y , N }=-\braket{ D_{X}N , Y }=-\braket{ W(X) , Y }$

> [!proof]+
> We show that $-\braket{ D_{X}N , Y }=\braket{ D_{X}Y , N }$. We have that $Y_{p}\in \text{T}_{p}M$ and hence $\braket{ Y_{p} , N_{p} }=0$ for all $p\in M$. Therefore, $$0=\left. \frac{d}{dt} \right| _{t=0}\braket{ Y_{p+tX_{p}} ,N_{p+tX_{p}}  }=\braket{ d_{p}Y(X_{p}) , N_{p} } +\braket{ Y_{p} , d_{p}N(X_{p}) }=\braket{ D_{X}Y , N }_{p}+\braket{ D_{X}N , Y}_{p}   $$

- **Corollary**: $\braket{ D_{X}Y , N }_{p}$ depends on only $X_{p},Y_{p}$ and not on any derivatives of $Y$. 
- **Corollary**: $\braket{ D_{X}Y , N }=\braket{ D_{Y}X , N }$ and $\braket{ D_{X}N , Y }=\braket{ D_{Y}N , X }$
---
> [!lemma] Proposition 4 (Properties of Weingarten Map)
> For $M\subseteq \mathbb{R}^3$ smooth surface and $N$ a normal vector field, let $X,Y\in \Gamma(\text{T}M)$. Then, 
> 1. $W_{p}:\text{T}_{p}M\to \text{T}_{p}M, X_{p}\mapsto D_{X}N(p)=d_{p}N(X_{p})$ is well-defined.
> 2. $W_{p}$ is self-adjoint.

> [!proof]-
> We have:
> 1. For any $X\in \Gamma(\text{T}M)$, $$0=\left. \frac{d}{dt} \right| _{t=0}\braket{ N(p+tX_{p}) , N(p+tX_{p}) } =2\braket{ d_{p}N(X_{p}) , N(p) }=2\braket{ W_{p}(X_{p}) , N_{p} }  $$Therefore, $W_{p}(X_{p})$ is normal to $N_{p}$ and $W_{p}(X_{p})\in \text{T}_{p}M$. 
> 2. One sees that: $$\braket{ W_{p}(X_{p}) , Y_{p} } =-A_{p}(X_{p},Y_{p})=-A_{p}(Y_{p},X_{p})=\braket{ W_{p}(Y_{p}) , X_{p} }=\braket{ X_{p} , W_{p}(Y_{p}) }  $$

---
##### Examples
> [!h] Example 1 (The Sphere)
> Let $M:=R\cdot S^2\subseteq \mathbb{R}^3$ be a sphere of radius $R$ w.r.t the inner normal field $N$, i.e. $N_{p}=-\frac{p}{R}$. Then, 
> 1. $Q_{p}(v)=\frac{1}{R}$ for any $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$. 
> 2. $k_{1}=k_{2}=\frac{1}{R}$ from [[Regular Curve in Rn|Exercise 1]].
> 3. $A_{p}(x,y)=\frac{1}{R}\braket{ x , y }$
> 4. $H=\frac{2}{R}$,
> 5. $K=\frac{1}{R^{2}}>0$ and $M$ is a bulge everywhere.
> 6. $W(X)=-\frac{1}{R}X$

> [!proof]-
> For $p\in M$ and $v\in \text{T}_{p}M$ with $\|v\|=1$, consider the plane $P$ in $\mathbb{R}^3$ that contains $0$, $p$ and $v$. Then, $P\cap M$ is a circle of radius $R$ and by [[Regular Curve in Rn|Example 1]], $$Q_{p}(v)=\frac{1}{R}\braket{ N(p) ,N(p)  } =\frac{1}{R}$$
> We can also compute the Weingarten map: $$W_{p}(X_{p})=d_{p}N(X_{p})=-\frac{1}{R}X_{p}$$We can verify this with: $$A_{p}(X_{p},Y_{p})=\frac{1}{R}\braket{ X_{p} , Y_{p} } =-\braket{ W_{p}(X_{p}) , Y_{p} } $$
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
> A ***helicoid*** is a smooth surface $H_{m}:=\Psi(\mathbb{R}^2)$ where: $$\Psi:\mathbb{R}^2\to \mathbb{R}^3,\quad (r,t)\mapsto(r\cos t,r\sin t,mt)$$
> Then, 
> 1. $H=0$ and $H_{b}$ is a minimal surface.
> 2. $K=-\frac{m^2}{(m^2+r^2)^2}$
> 3. $-k_{1}=k_{2}=\frac{m}{m^2+r^2}$

> [!proof]-
> The helicoid is given by the image of $\Psi:\mathbb{R}^2\to \mathbb{R}^3$ by $(r,t)\mapsto(r\cos t,r\sin t,mt)$. Then, $\Psi_{r}(r,t):=\frac{\partial}{\partial r}\Psi(r,t)=(\cos t,\sin t,0)$ and $\Psi_{t}(r,t):=\frac{ \partial  }{ \partial t }\Psi(r,t)=(-r\sin t,r\cos t,m)$ are orthogonal at every point $(r,t)$ and we define the vector fields: 
> 1. $X:H_{b}\to \mathbb{R}^3,p\mapsto \Psi_{r}(\Psi ^{-1}(p))$
> 5. $Y:H_{b}\to \mathbb{R}^3,p\mapsto \Psi_{t}(\Psi ^{-1}(p))$
> 
> Then, we can compute the normal vector field as: $$N:=\frac{X\times Y}{\left\| X\times Y\right\| }$$Now, we compute: $$\begin{align}D_{X}N(p)&=d_{p}N(\Psi_{r}(\Psi ^{-1}(p)))=\left. \frac{ \partial  }{ \partial r } (N\circ \Psi) \right| _{\Psi ^{-1}(p)}\\&=\left. \frac{ \partial  }{ \partial r } \left( \frac{\Psi_{r}\times \Psi_{t}}{\left\| \Psi_{r}\times \Psi_{t} \right\| } \right)  \right| _{\Psi ^{-1}(p)}\\&=\left.\frac{\Psi_{rr}\times \Psi_{t}+\Psi_{r}\times \Psi_{tr} }{\left\| \Psi_{r}\times \Psi_{t} \right\|}-\frac{(\Psi_{r}\times \Psi_{t})\frac{d}{dr}\left\| \Psi_{r}\times \Psi _{t} \right\|}{\left\| \Psi_{r}\times \Psi_{t} \right\| ^{2}}  \right|_{\Psi ^{-1}(p)} \end{align}$$Analogously, $$D_{Y}N(p)=\left.\frac{\Psi_{rt}\times \Psi_{t}+\Psi_{r}\times \Psi_{tt} }{\left\| \Psi_{r}\times \Psi_{t} \right\|}-\frac{(\Psi_{r}\times \Psi_{t})\frac{d}{dt}\left\| \Psi_{r}\times \Psi _{t} \right\|}{\left\| \Psi_{r}\times \Psi_{t} \right\| ^{2}}  \right|_{\Psi ^{-1}(p)} $$Then, 
> 1. We have:$$\begin{align}A_{p}(X_{p},X_{p})=-\braket{ D_{X}N(p) , X_{p} } &=-\left\langle\frac{\Psi_{rr}\times \Psi_{t}+\Psi_{r}\times \Psi_{tr} }{\left\| \Psi_{r}\times \Psi_{t} \right\|},\Psi_{r}\right\rangle_{\Psi ^{-1}(p)}\\&=-\frac{\braket{ \Psi_{rr}\times \Psi_{t} , \Psi_{r} }}{\left\| \Psi_{r}\times \Psi_{t} \right\| }\\&= \frac{\braket{ \Psi_{rr} ,\Psi_{r}\times \Psi _{t}  } }{\left\| \Psi_{r}\times \Psi_{t} \right\| }\\&=\braket{ \Psi_{rr} , N } \end{align}$$
> 2. Similarly, $$\begin{align}A(X,Y)=-\braket{ D_{X}N , Y } &=-\left\langle\frac{\Psi_{rr}\times \Psi_{t}+\Psi_{r}\times \Psi_{tr} }{\left\| \Psi_{r}\times \Psi_{t} \right\|},\Psi_{t}\right\rangle\\&=-\frac{\left\langle\Psi_{r}\times \Psi_{tr},\Psi_{t}\right\rangle}{\left\| \Psi_{r}\times \Psi_{t} \right\|}\\&=\frac{\left\langle\Psi_{tr},\Psi_{r}\times\Psi_{t}\right\rangle}{\left\| \Psi_{r}\times \Psi_{t} \right\|}\\&=\braket{ \Psi_{tr} , N } \end{align}$$
> 3. Lastly,
>    $$\begin{align}A(Y,Y)=-\braket{ D_{Y}N , Y } &=-\left\langle\frac{\Psi_{rt}\times \Psi_{t}+\Psi_{r}\times \Psi_{tt} }{\left\| \Psi_{r}\times \Psi_{t} \right\|},\Psi_{t}\right\rangle\\&=-\frac{\left\langle\Psi_{r}\times \Psi_{tt},\Psi_{t}\right\rangle}{\left\| \Psi_{r}\times \Psi_{t} \right\|}\\&=\frac{\left\langle\Psi_{tt},\Psi_{r}\times\Psi_{t}\right\rangle}{\left\| \Psi_{r}\times \Psi_{t} \right\|}\\&=\braket{ \Psi_{tt} , N } \end{align}$$
>    
>  Therefore, we have that: $$A=\begin{bmatrix}\braket{ \Psi_{rr} , N }&\braket{ \Psi_{tr} , N } \\\braket{ \Psi_{tr} , N }&\braket{ \Psi_{tt} , N }\end{bmatrix}$$in the basis $X,Y$ with 
>  1. $X:H_{b}\to \mathbb{R}^3,(r\cos t,r\sin t,mt)\mapsto(\cos t,\sin t,0)$
> 2. $Y:H_{b}\to \mathbb{R}^3,(r\cos t,r\sin t,mt)\mapsto(-r\sin t,r\cos t,m)$
> 
> and $$N(r\cos t,r\sin t,mt)=\frac{(m\sin t,-m\cos t,r)}{\sqrt{ m^{2}+r^{2} }}$$
> Therefore, $$A=\begin{bmatrix}0&-\frac{m}{{ m^2+r^2 }}\\-\frac{m}{{ m^2+r^2 }}&0\end{bmatrix}$$and $H=\text{tr}(A)=0$ and $K=\det(A)=-\frac{m^{2}}{{ (m^2+r^2 )^{2}}}$ with $-k_{1}=k_{2}=\frac{m}{r^2+m^2}$.
---

