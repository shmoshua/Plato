#Definition #DifferentialGeometry 

> [!definition]
> 
---
##### Properties
> [!lemma] Proposition 1
> The tangent vector and curvature vector are orthogonal, i.e. $\kappa(s) {\bot}\tau(s)$ for all $s$.

> [!proof]-
> Firstly, $$\braket{ \tau(s) , \tau(s) } =\frac{\braket{ \dot{\gamma}(t) , \dot{\gamma}(t) } }{\left| \dot{\gamma} (t)\right|^{2} }=1$$
> Therefore, $$0=\frac{d}{ds}\braket{ \tau(s) , \tau(s) } =2 \braket{  \dot{\tau}(s) , \tau(s) } =2\braket{ \kappa(s) , \tau (s)} $$
---
> [!lemma] Proposition 2
> In an arbitrary parametrization, $$\kappa=\frac{1}{\left| \gamma_{t} \right| ^{2}}\left( \gamma_{tt}-\braket{ \gamma_{tt} , \tau }  \tau\right) =\frac{1}{\left| \gamma_{t} \right| ^{2}}\left( \gamma_{tt}-\braket{ \gamma_{tt} , \frac{\gamma_{t}}{\left| \gamma_{t} \right| } }   \frac{\gamma_{t}}{\left| \gamma_{t} \right| } \right) $$

> [!proof]-
> $$\begin{align}\kappa =\tau_{s}=\left(  \frac{d}{dt} \frac{\gamma_{t}}{\left| \gamma_{t} \right| } \right)\frac{dg}{ds} =\left( \frac{\gamma_{tt}}{|\gamma_{t}|}-\frac{\gamma_{t}}{\left| \gamma_{t} \right| ^{2}}\frac{d}{dt} \left| \gamma _{t} \right| \right)\frac{1}{\left| \gamma_{t} \right| } =\frac{1}{\left| \gamma_{t} \right|^{2} }\left( \gamma_{tt}-\braket{ \gamma_{tt} , \frac{\gamma_{t}}{\left| \gamma_{t} \right| } } \frac{\gamma_{t}}{\left| \gamma_{t} \right| } \right)\end{align}$$
---
##### Curvature Vector in $\mathbb{R}^{2}$
In a regular curve $\gamma:I \to \mathbb{R}^{2}$, the curvature is defined by a scalar $k$ where: $$\kappa=kN$$ given by the normal vector $N$. Then for all $t\in I$, $(\tau(t),N(t))$ define a moving orthonormal basis of $\mathbb{R}^{2}$ called a moving ***frame***. 
> [!lemma] Proposition R2.1
> For a circle of radius $r$, $k=1/r$.

>[!proof]+
> Let $\gamma(t)=(r\sin( t), r\cos( t))$ for $t\in[0,2\pi]$. Then, $s(t)=rt$ and:
> 1. $\tau(t)=(\cos(t),-\sin(t))=(\cos(s/r),-\sin(s /r))$
---
> [!lemma] Proposition R2.2
> For a regular curve $\gamma:I\to \mathbb{R}^2$, 
> 1. $k= \frac{d\theta}{ds}$ where $\theta$ is the angle that $\tau$ makes with the $x$-axis. 
> 2. $\left| k(t) \right|=\frac{1}{ R(t) }$ where $R(t)$ is the radius of the osculating circle to $\gamma$ at $\gamma(t)$, i.e. the circle that is tangent to $\gamma$ at $\gamma(t)$ to order 2.
---