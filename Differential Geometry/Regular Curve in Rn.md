#Definition #DifferentialGeometry 

> [!definition]
> A [[Smooth Curve|smooth curve]] $\gamma:I \to \mathbb{R}^n$ is ***regular*** if 
> 1. $\dot{\gamma}(t)\neq 0$ for all $t\in I$.
- **Remark**: the arc length $s:I\to \mathbb{R},t\mapsto \int_{t}^{t_{0}} \left| \dot{\gamma} (\tau)\right| \, d\tau$ is a geometric property, i.e. it is unique up to the choice of the base point and does not depend on the parametrization of $\gamma$.
- **Remark**: From Proposition 1, we abuse the notation and represent $\gamma=\beta$, i.e. $\gamma$ is sometimes treated as the reparametrized curve. 
- **Related definition**: for a regular curve $\gamma:I\to \mathbb{R}^n$, 
  1. the ***unit tangent vector*** $\tau:s(I)\to \mathbb{R}^n$ is given as $\tau(s)=\dot{\gamma}(s):=\dot{\beta}(s)$.
  2. the ***curvature vector*** $\kappa:s(I)\to \mathbb{R}^n$ is given as $\kappa(s)=\dot{\tau}(s)=\ddot{\gamma}(s)$.

- **Remark**: The tangent vector and the curvature vector are ***geometric***, i.e. they only depend on $\gamma(I)$ and not on the parametrization. 
- **Related definition**: If $\kappa(s)\neq 0$ for all $s\in s(I)$, then $\gamma$ is ***ordinary***.

---
##### Properties
> [!lemma] Proposition 1
> If $\gamma:I\to \mathbb{R}^n$ is a regular curve, 
> 1. for [[Smooth Curve|arc length]] $s:I\to \mathbb{R}$ with base $t_{0}\in I$, $\gamma$ can be reparametrized w.r.t. $s$, i.e. there exists another regular curve $\beta:s(I)\to \mathbb{R}^n$ s.t. $\beta \circ s=\gamma$ and $s$ remains the arc length of $\beta$ with base $s(t_{0})$.
> 2. the reparametrization $\beta$ is unique up to the choice of the base point $t_{0}$.

> [!proof]-
> Fix $t_{0}$. Then, 
> 1. We let $s(t)=\int_{t_{0}}^{t} \left\| \dot{\gamma}(\tau) \right\|\, d\tau$. We first show that $s:I\to s(I)$ is bijective. If $t_{1}<t_{2}$, $$s(t_{2})=\int_{t_{0}}^{t_{2}}\left\| \dot{\gamma}(\tau) \right\|    \, d\tau=\int_{t_{0}}^{t_{1}}\left\| \dot{\gamma}(\tau) \right\|   \, d\tau+\int_{t_{1}}^{t_{2}}\underbrace{ \left\| \dot{\gamma}(\tau) \right\|   }_{ >0 }  \, d\tau>s(t_{1}) $$Therefore, we can define $g:s(I)\to I$ as its inverse. By defining $\beta:=\gamma \circ g$, we have a curve $\beta:s(I)\to \mathbb{R}^n$ s.t. $$\beta(s(t))=\gamma(g(s(t)))=\gamma(t)$$
>    
>    
>    Now, we show that $s$ is the arc-length of $\beta$. We have: 
>    $$\left\| \dot{\beta} (x)\right\|=\left\| \dot{\gamma}(g(x))\dot{g}(x)\right\| =\left\| \dot{\gamma}(g(x)) \frac{1}{\dot{s}(g(x))} \right\|  =\left\| \dot{\gamma}(g(x)) \frac{1}{\dot{\gamma}(g(x))} \right\|=1$$
> 	and $\beta$ is regular with $\int_{0}^{s} \left\| \dot{\beta}(x) \right\| \, dx=s$.
> 2. The uniqueness is given by the construction.
---
> [!lemma] Lemma 2
> For any $s\in s(I)$: 
> 1. $\braket{ \kappa(s) , \tau(s) }=0$

> [!proof]-
> We have that:
> 1. As $\tau(s)=\dot{\gamma}(s)$, we have: $\braket{ \tau(s) ,\tau(s)  }=\left\| \tau(s) \right\|=\left\| \dot{\gamma}(s) \right\|=1$. Therefore, $$0=\frac{d}{ds}\braket{ \tau(s) , \tau(s) } =2\left\langle \frac{d}{ds}\tau(s),\tau(s)\right \rangle=2\braket{ \kappa(s) , \tau(s) } $$
---
> [!lemma] Proposition 3 (Parametrization and Curvature)
> Let $\gamma:I\to \mathbb{R}^n$ be a regular curve. Then, for $t\in I$, 
> 1. $\tau(s(t))=\frac{\dot{\gamma}(t)}{\left\| \dot{\gamma}(t) \right\|}$
> 2. $\kappa(s(t))=\frac{1}{\left\| \dot{\gamma}(t) \right\|^{2}}\left(  \ddot{\gamma}(t)-\left\langle \ddot{\gamma}(t) ,  \frac{\dot{\gamma}(t)}{\left\| \dot{\gamma}(t) \right\|} \right\rangle \frac{\dot{\gamma}(t)}{\left\| \dot{\gamma}(t) \right\|} \right)=\frac{1}{\left\| \dot{\gamma}(t) \right\|^{2}}\left(  \ddot{\gamma}(t)-\left\langle \ddot{\gamma}(t) ,  \tau(s(t)) \right\rangle \tau(s(t))\right)$

> [!proof]-
> We have that:
> 1. For the unit tangent vector:$$\tau(s(t))=\dot{\beta}(s(t))=\dot{\gamma}(g(s(t)))\dot{g}(s(t))=\frac{\dot{\gamma}(t)}{\left\| \dot{\gamma}(t) \right\|  }$$
> 2. For the curvature vector: $$\begin{align}\kappa(s(t))&=\dot{\tau}(s(t))\\&=\frac{1}{\left\| \dot{\gamma}(t) \right\|  ^{2}}\left( \left\| \dot{\gamma}(t) \right\|  \ddot{\gamma}(t)-\frac{\braket{ \ddot{\gamma}(t) , \dot{\gamma}(t) }\dot{\gamma}(t) }{\left\| \dot{\gamma}(t) \right\|  } \right) \dot{g}(s(t))\\&=\frac{1}{\left\| \dot{\gamma}(t) \right\|  ^{2}}\left( \left\| \dot{\gamma}(t) \right\|  \ddot{\gamma}(t)-\frac{\braket{ \ddot{\gamma}(t) , \dot{\gamma}(t) }\dot{\gamma}(t) }{\left\| \dot{\gamma}(t) \right\|  } \right) \frac{1}{\left\| \dot{\gamma}(t) \right\| }\\&=\frac{1}{\left\| \dot{\gamma}(t) \right\|^{2}}\left(  \ddot{\gamma}(t)-\left\langle \ddot{\gamma}(t) ,  \frac{\dot{\gamma}(t)}{\left\| \dot{\gamma}(t) \right\|} \right\rangle \frac{\dot{\gamma}(t)}{\left\| \dot{\gamma}(t) \right\|} \right) \end{align}$$
---
###### Regular Curves in R2

> [!lemma] Theorem 1
> For a regular curve $\gamma:I\to \mathbb{R}^{2}$, we can define:
> 1. $N:s(I)\to \mathbb{R}^{2}$ the ***normal vector*** given by $N(s):=\begin{bmatrix}0&-1\\1&0\end{bmatrix}\tau(s)$.
> 2. $k:s(I)\to \mathbb{R}$ the ***curvature scalar*** given by $\kappa(s)=k(s)N(s)$.
> 3. $(\tau(s),N(s))$ defines a moving ONB of $\mathbb{R}^{2}$ called a ***moving frame***.
> 4. $\theta:s(I)\to \mathbb{R}$ the ***angular vector*** given by $\tau(s)=\exp(i\theta(s))$ where $\mathbb{R}^{2}\cong \mathbb{C}$.
> 
> Then, it holds that:
> 1. $k(s)=\dot{\theta}(s)$.
> 2. $\left| k(s) \right|=\frac{1}{R(s)}$ where $R(s)$ is the radius of the osculating circle, i.e. the circle that agrees with the curve up to order 2 at $\gamma(s)$ (parametrized by the arc length). 
> 3. Let $u:I\to \mathbb{R}$ be a smooth function and $\gamma:I\to \mathbb{R}^{2},t\mapsto (t,u(t))$ its graph, $$k(s(t))=\frac{\ddot{u}(t)}{(1+\dot{u}(t)^{2})^{3/2}}$$

> [!proof]- 
> We have that:
> 1. For $\tau:=(\tau_{1},\tau_{2})$, we have $$\theta(s)=\arctan \frac{\tau_{2}(s)}{\tau_{1}(s)}$$
> 2. Then, $$\begin{align}\dot{\theta}(s)&=\frac{1}{1+\frac{\tau_{2}(s)^{2}}{\tau_{1}(s)^{2}}}\cdot \frac{1}{\tau_{1}(s)^{2}}\cdot (\tau_{1}(s)\dot{\tau}_{2}(s)-\dot{\tau}_{1}(s)\tau_{2}(s))\\&=\frac{\tau_{1}(s)\dot{\tau}_{2}(s)-\dot{\tau}_{1}(s)\tau_{2}(s)}{\tau_{1}(s)^{2}+\tau_{2}(s)^{2}}\\&=\frac{\tau_{1}(s)\kappa_{2}(s)-\kappa_{1}(s)\tau_{2}(s)}{\tau_{1}(s)^{2}+\tau_{2}(s)^{2}}\\&=\braket{ N(s) ,\kappa(s)  }\\&=k(s) \end{align}$$
> 3. As such a circle always exists and we have that for such circle, $k(s)=\frac{1}{R(s)}$ from Example 2. 
> 4. We have that 
> 	1. $\gamma(t)=(t,u(t))$, 
> 	2. $\dot{\gamma}(t)=(1,\dot{u}(t))$ and 
> 	3. $\ddot{\gamma}(t)=(0,\ddot{u}(t))$. 
> 	
> 	Therefore, as $\tau(s(t))=(1,\dot{u}(t))/(1+\dot{u}(t)^{2})^{1/2}$ and $N(s(t))=(-\dot{u}(t),1)/(1+\dot{u}(t)^{2})^{1/2}$,
> 	$$\begin{align}\kappa(s(t))&=\frac{1}{1+\dot{u}(t)^{2}}\left( (0,\ddot{u}(t))- \frac{\ddot{u}(t)\dot{u}(t)}{1+\dot{u}(t)^{2}}(1,\dot{u}(t)) \right) \\&=\frac{1}{1+\dot{u}(t)^{2}}\left( -\frac{\ddot{u}(t)\dot{u}(t)}{1+\dot{u}(t)^{2}},\ddot{u}(t)- \frac{\ddot{u}(t)\dot{u}(t)^{2}}{1+\dot{u}(t)^{2}} \right) \\&=\frac{\ddot{u}(t)}{(1+\dot{u}(t)^{2})^{3/2}}\left( -\frac{\dot{u}(t)}{(1+\dot{u}(t)^{2})^{1/2}},\frac{1}{(1+\dot{u}(t)^{2})^{1/2}} \right)\\&=\frac{\ddot{u}(t)}{(1+\dot{u}(t)^{2})^{3/2}}N(s(t))\end{align}$$
- **Remark**: The curvature scalar $k:I\to \mathbb{R}$ determines the curve up to a rigid motion. From $k$ by integration, we get $\theta(s)=\theta(s_{0})+\int_{s_{0}}^{s} k(t) \, dt$ and from $\theta$ we get $\tau$. Finally from $\tau$ we get $\gamma(s)=\gamma(s_{0})+\int_{s_{0}}^{s} \tau(x) \, dx$. Therefore, up to the choice of $\theta(s_{0})$ and $\gamma(s_{0})$, we have the same curve.
- **Remark**: In Theorem 1.3, if $u$ is tangent to the $x$-axis at $t$, then $k(s(t))=\ddot{u}(t)$.

---
> [!lemma] Theorem 2
> Let a regular curve $\gamma:[a,b]\to \mathbb{R}^{2}$ be smooth and closed, i.e. $\gamma$ can be extended to a smooth periodic curve $\mathbb{R}\to \mathbb{R}^{2}$. Then, 
> 1. for the curvature $k:[a,b]\to \mathbb{R}$, there exists $n\in \mathbb{Z}$ s.t.: $$\int_{\gamma}^{} k(s) \, ds =2\pi n$$
> 2. if $\gamma$ is simple, i.e. injective on $I^\circ$, then: $\int_{\gamma}k(s) \, ds\in\{ 2\pi,-2\pi \}$.

> [!proof]-
> We have:
> 1. $$\int_{\gamma}^{} k(s) \, ds=\int_{a}^{b} \dot{\theta}(s) \, ds =\theta(b)-\theta(a)=2\pi n $$for some $n\in \mathbb{Z}$.
> 2. A non-intersective curve can turn at most once.
---
###### Regular Curves in R3
> [!lemma] Theorem 1 (Frenet-Serret Formulas)
> For a regular curve $\gamma:I\to \mathbb{R}^{3}$, we can define:
> 1. $k:s(I)\to \mathbb{R}$ the ***curvature scalar*** given by $k(s):=\left\| \kappa(s) \right\|$.
> 2. $N:s(I)\to \mathbb{R}^3$ the ***normal vector*** given by $N(s):=\frac{\kappa(s)}{\left\| \kappa(s) \right\|}=\frac{\kappa(s)}{k(s)}$.
> 3. $B:s(I)\to \mathbb{R}^3$ the ***binormal vector*** given by $B(s):=\tau(s)\times N(s)$.
> 4. $(\tau(s),N(s),B(s))$ defines a moving ONB of $\mathbb{R}^3$ called a ***Frechet frame***.
> 6. if $\gamma$ ordinary, $\lambda:s(I)\to \mathbb{R}^3$ the ***torsion vector*** given by $\lambda(s):=\braket{ \dot{N}(s) , B(s) }B(s)$.
> 7. if $\gamma$ ordinary, $\ell:s(I)\to \mathbb{R}^3$ the ***torsion scalar*** given by $\ell(s):=\braket{ \dot{N}(s) , B(s) }$.
> 
> Then, it holds that:
> 1. $\dot{\tau}(s)=k(s)N(s)$.
> 1. $\dot{N}(s)=-k(s)\tau(s)+\ell(s)B(s)$
> 2. $\dot{B}(s)=-\ell(s)N(s)$.
> 3. $$\beta(s)=\beta(0)+\left( s-\frac{k(0)^{2}s^3}{6} \right)\tau(0)+\left( \frac{s^{2}k(0)}{2}+\frac{s^3\dot{k}(0)}{6} \right) N(0)+\frac{s^3\ell(0)}{6}B(0)+O(s^4)$$

> [!proof]- Proof (Direct)
> We have that:
> 1. As we have $1=\left\| N(s) \right\|^{2}=\braket{ N(s) , N(s) }$, we have that $\braket{ \dot{N}(s) , N(s) }=0$. Therefore, $$\dot{N}(s)=\alpha(s)\tau(s)+\ell(s)B(s)$$Further, as $\braket{ N(s) , \tau(s) }=0$, $$\braket{ \dot{N}(s) , \tau(s) } +\braket{ N(s) , \kappa(s) } =\alpha(s)+k(s)=0$$Hence, $\dot{N}(s)=-k(s)\tau(s)+\ell(s)B(s)$.
> 2. From product rule, $$\dot{B}(s)=\underbrace{ \kappa(s)\times N(s) }_{ =0 }+\ell(s)(\tau(s)\times B(s))=-\ell(s)N(s)$$
> 3. Using Taylor expansion:
>    
>    $$\begin{align}\beta(s)&=\beta(0)+s\tau(0)+\frac{s^{2}}{2}k(0)N(0)+\frac{s^3}{6}\left( \dot{k}(0)N(0)+k(0)\left( -k(0)\tau(0)+\ell(0)B(0) \right)  \right) +O(s^4)\\&=\beta(0)+\left( s-\frac{k(0)^{2}s^3}{6} \right)\tau(0)+\left( \frac{s^{2}k(0)}{2}+\frac{s^3\dot{k}(0)}{6} \right) N(0)+\frac{s^3\ell(0)}{6}B(0)+O(s^4)\end{align}$$

> [!proof]- Proof (Using a Lemma on ONB) 
> Let $e_{1},e_{2},e_{3}:I\to \mathbb{R}^3$ be a family of ONBs. Then, we show that for: $$\frac{d}{dt}\begin{bmatrix}e_{1}\\e_{2}\\e_{3}\end{bmatrix}=A(t)\begin{bmatrix}e_{1}\\e_{2}\\e_{3}\end{bmatrix}$$with $A(t)\in \text{Mat}_{3,3}(\mathbb{R})$, $A(t)$ is antisymmetric, i.e. $A(t)+A(t)^\top=0$. 
> 
> We have that$\braket{ e_{i}(t) , e_{j}(t) }=\delta_{ij}$. Therefore, $$0=\frac{d}{dt}\braket{ e_{i}(t) , e_{j}(t) } =\braket{ \dot{e_{i}}(t) , e_{j}(t) }+\braket{ e_{i}(t) , \dot{e_{j}}(t) }=A_{ij}+A_{ji}  $$Then, 
> 1. $A_{12}(t)=\braket{ \dot{\tau}(s) ,N(s)  }=k(s)$
> 2. $A_{13}(t)=\braket{ \dot{\tau}(s) , B(s) }=0$
> 3. $A_{23}(t)=\braket{ \dot{N}(s) , B(s) }=\ell(s)$.
---
> [!lemma] Proposition 2
> For an ordinary regular curve $\gamma:I\to \mathbb{R}^3$,
> 1. If $k\equiv 0$, then $\gamma$ is a line.
> 2. If $\ell \equiv 0$, then $\gamma$ lies in a plane.

> [!proof]-
> We have that:
> 1. If $k\equiv 0$, then $\kappa\equiv 0$. Therefore, $\tau\equiv v$ for some $v\in \mathbb{R}^3$ s.t. $\|v\|=1$. Therefore, $$\gamma(s)=\alpha vs+w$$for $\alpha\in \mathbb{R}$, $w\in \mathbb{R}^3$. which shows that $\gamma$ is a line.
> 2. If $\ell \equiv 0$, from 1, $\dot{B}\equiv0$ and $B\equiv v$ for some $v\in \mathbb{R}^3$. In particular all planes spanned by $\tau(s)$ and $N(s)$ are parallel. We want to show that they all coincide.
>    
>    Choose any $s_{0}\in I$ and consider the function $f:I\to \mathbb{R},s\mapsto \braket{ B(s) , \gamma(s)-\gamma(s_{0}) }$. Then, $$\dot{f}(s)=\braket{ 0 , \gamma(s)-\gamma(s_{0}) } +\braket{ B(s) , \tau(s) } =0$$Therefore, $f$ is constant and zero from $f(s_{0})=0$. Hence, $\braket{ v , \gamma(s)-\gamma(s_{0}) }=0$, which is a plane in $\mathbb{R}^3$.
- **Remark**: The curvature scalar is non-negative in $\mathbb{R}^3$ whereas it could be negative in $\mathbb{R}^{2}$.
---
> [!lemma] Theorem 3 (Fundamental Theorem of Curve Theory)
> For any given smooth functions $k,\ell:I\to \mathbb{R}$ where $k(s)>0$ for all $s\in I$, there exists a unique curve up to a unique motion $\gamma:I\to \mathbb{R}^3$ with $k$ as curvature scalar and $\ell$ as torsion scalar.
---
> [!lemma] Theorem 4 (Fenchel, 1929)
> Any closed regular curve $\gamma$ in $\mathbb{R}^3$ has: $$\int_{\gamma}^{}  \left| k(s) \right| \, ds\geq 2\pi $$with an equality if and only if $\gamma$ is a planar convex curve.
---
> [!lemma] Theorem 5 (Milnor)
> Any knotted curve $\gamma$ in $\mathbb{R}^3$ has: $$\int_{\gamma}^{}  \left| k(s) \right| \, ds\geq 4\pi $$
- **Remark**: This bound is sharp, as trefoil has a curvature $4\pi$ when embedded into $\mathbb{R}^{2}$.
---
##### Examples

> [!h] Example 1
> For a circle of radius $r$, 
> 1. $k=1/r$.

>[!proof]-
> Let $\gamma:[0,2\pi]\to \mathbb{R}^{2},t\mapsto(r\cos t,r\sin t)$. Then, $$\tau(s(t))=\frac{1}{r}(-r\sin t,r\cos t)=(-\sin t,\cos t)$$Therefore, $N(s(t))=-(\cos t,\sin t)$. Then, $$\kappa(s(t))=-\frac{(r\cos(t),r\sin(t))}{r^{2}}=\frac{1}{r}N(s(t))$$

---
> [!h] Example 2
> Consider the curve $\gamma:\mathbb{R}\to \mathbb{R}^3,t\mapsto(t,at^{2},bt^3)$ for $a,b\in\mathbb{R}$. Then,
> 1. $k(0)=2a$.
> 2. $\ell(0)=\frac{3b}{a}$

> [!proof]-
> As $\dot{\gamma}(t)=(1,2at,3bt^{2})$ and $\ddot{\gamma}(t)=(0,2a,6bt)$,
> - $\tau(s(t))=\frac{1}{\sqrt{ 1+4a^{2}t^{2}+9b ^{2}t^4 }}(1,2at,3bt^{2})$
> - $\kappa(s(t))=\frac{1}{1+4a^{2}t^{2}+9b ^{2}t^4}\left( (0,2a,6bt)-\frac{4a^{2}t+18b ^{2}t^3}{1+4a^{2}t^{2}+9b ^{2}t^4} (1,2at,3bt^{2})\right)$
> - $$\gamma(s(t))=\gamma(0)+\tau(s(0))s+$$
---
> [!h] Example 3 (Helix)
> If $\gamma:\mathbb{R}\to \mathbb{R}^3$ be an ordinary regular curve. If $k$ and $\ell$ are constant, then $\gamma$ is a helix, i.e. there exists $R>0$ and $m\in \mathbb{R}$ s.t. $$\gamma(t)=(R\cos t,R\sin t,mt)$$

> [!proof]-
> For a helix, we have that:
> - $\dot{\gamma}(t)=(-R\sin t,R\cos t,m)$
> - $\ddot{\gamma}(t)=(-R\cos t,-R\sin t,0)$
> - $\tau(t)=\frac{1}{\sqrt{ R^{2}+m^{2} }}(-R\sin t,R\cos t,m)$
> - $\kappa(t)=\frac{1}{\sqrt{ R^2+m^2 }}(-R\cos t,-R\sin t,0)$
> - $k(t)=\frac{R}{\sqrt{ R^{2}+m^{2} }}$
> - $N(t)=\frac{1}{R}(-R\cos t,-R\sin t,0)$
> - $B(t)=\frac{1}{\sqrt{ R^{2}+m^{2} }}(-m\sin t,-m\cos t,R)$
> - $\begin{align}\dot{N}(t)&=\frac{1}{R}(R\sin t,-R\cos t,0)\\&=-\frac{R}{R^{2}+m^{2}}(-R\sin t,R\cos t,m)+\frac{\ell(t)}{\sqrt{ R^{2}+m^{2} }}(-m\sin t,-m\cos t,R)\\&=-\frac{R}{R^{2}+m^{2}}(-R\sin t,R\cos t,m)-\frac{m}{{ R^{2}+m^{2} }}(-m\sin t,-m\cos t,R)\end{align}$
> - $\ell(t)=\frac{m}{\sqrt{ R^{2}+m^{2} }}$
>   
> Hence, $k$ and $\ell$ are constant and the statement follows from the fundamental theorem of curve theory.
---
##### Non-Examples
- $t\mapsto (t^{2},t^{3})\in \mathbb{R}^2$ is not regular!
	```tikz
	
	\begin{document}
	\begin{tikzpicture}[line cap=round,scale=0.15]
	
	\definecolor{mycolor}{RGB}{126,29,251}
	
	\draw[-latex] (-10,0) -- (10,0){};
	\draw[-latex] (0,-10)     -- (0,10) {};
	%% \foreach[count=\j]\i in {-10,-9,...,10}
	  %% \draw (\i,0.05) -- (\i,-0.05) node [below] {$\i\ifnum\j<3\phantom{-}\fi$}; %%
	%% \foreach\i in {-10,-9,...,10} %%
	  %% \draw (0.05,\i) -- (-0.05,\i) node [left]  {$\i$}; %% 
	\draw[mycolor, thick] plot[variable=\t,domain=-2.1:2.1,smooth,thick] ({\t*\t},{\t*\t*\t});
	\end{tikzpicture}
	\end{document}
	```
	as $\gamma_{t}(0)=(0,0)$.
---
