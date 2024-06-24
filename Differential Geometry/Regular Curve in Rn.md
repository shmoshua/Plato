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
##### Examples
> [!h] Example 1
> In a regular curve $\gamma:I \to \mathbb{R}^{2}$, the curvature is defined by a scalar $k$ where: $$\kappa=kN$$where $k:s(I)\to \mathbb{R}$ scalar function and $N(s)=\begin{bmatrix}0&-1\\1&0\end{bmatrix}\tau(s)$. Then for all $t\in I$, 
> 1. $(\tau(t),N(t))$ define a moving orthonormal basis of $\mathbb{R}^{2}$ called a moving ***frame***. 
---
> [!h] Example 2
> For a circle of radius $r$, 
> 1. $k=1/r$.

>[!proof]-
> Let $\gamma:[0,2\pi]\to \mathbb{R}^{2},t\mapsto(r\cos t,r\sin t)$. Then, $$\tau(s(t))=\frac{1}{r}(-r\sin t,r\cos t)=(-\sin t,\cos t)$$Therefore, $N(s(t))=-(\cos t,\sin t)$. Then, $$\kappa(s(t))=-\frac{(r\cos(t),r\sin(t))}{r^{2}}=\frac{1}{r}N(s(t))$$

---
> [!h] Example 3 (Regular Curves in R2)
> For a regular curve $\gamma:I\to \mathbb{R}^2$, by considering $\mathbb{R}^{2}\cong\mathbb{C}$, 
> 1. there exists a smooth curve $\theta:s(I)\to \mathbb{R}$ s.t. $\tau(s)=\exp(i\theta(s))$.
> 2. $k(s)=\dot{\theta}(s)$.
> 3. $\left| k(s) \right|=\frac{1}{R(s)}$ where $R(s)$ is the radius of the osculating circle, i.e. the circle that agrees with the curve up to order 2 at $\gamma(s)$ (parametrized by the arc length). 
> 4. Let $u:I\to \mathbb{R}$ be a smooth function and $\gamma:I\to \mathbb{R}^{2},t\mapsto (t,u(t))$ its graph, $$k(s(t))=\frac{\ddot{u}(t)}{(1+\dot{u}(t)^{2})^{3/2}}$$

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
---
> [!h] Example 4 (Curvature determines the curve up to rigid motion)
> In $\mathbb{R}^{2}$, the curvature $k:s(I)\to$
> 
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
