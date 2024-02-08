#Definition #LST #Analysis 

> [!definition]
> The ***Laplace transform*** is a map $\mathcal{L}$ that takes a function $f:\mathbb{R}_{+}\to \mathbb{R}^{n\times m}$ and outputs a complex-valued map: $$F(s):=\mathcal{L}(f)(s)=\int_{0}^{\infty} f(t)e^{ -st } \, dt \in \mathbb{C}^{n,m}$$where the integral is computed element-wise.
---
##### Properties
> [!lemma] Fact 1
> The Laplace transform has the following properties:
> 1. Linearity: for all $f_{1},f_{2}:\mathbb{R}_{+} \to \mathbb{R}^{n,m}$ and $A_{1},A_{2}\in\mathbb{R}^{p,n}$, $$\mathcal{L}(A_{1}f_{1}+A_{2}f_{2})(s)=A_{1}\mathcal{L}(f_{1})(s)+A_{2}\mathcal{L}(f_{2})(s)$$
> 2. $\mathcal{L}\left(  \frac{d}{dt}f \right)(s)=s\mathcal{L}(f)(s)-f(0)$
> 3. $\mathcal{L}(f*g)(s)=\mathcal{L}(f)(s)\cdot\mathcal{L}(g)(s)$
> 4. For all $A\in \mathbb{R}^{n,n}$ and $t\in \mathbb{R}_{+}$, $$\mathcal{L}(e^{At})(s)=(sI-A)^{-1}$$

> [!proof]-
> We have that: 
> 1. $$\begin{align}\mathcal{L}(A_{1}f_{1}+A_{2}f_{2})(s)&=\int_{0}^{\infty} A_{1}f_{1}(t)e^{ -st }+A_{2}f_{2}(t)e^{ -st } \, dt\\&=A_{1}\int_{0}^{\infty} f_{1}(t)e^{ -st } \, dt +A_{2}\int_{0}^{\infty} f_{2}(t)e^{ -st } \, dt\\&=A_{1}\mathcal{L}(f_{1})(s)+A_{2}\mathcal{L}(f_{2})(s) \end{align} $$
> 2. $$\mathcal{L}\left( \frac{d}{dt} f \right) (s)=\int_{0}^{\infty} \frac{d}{dt} f(t)e^{ -st } \, dt=s\int_{0}^{\infty} f(t)e^{ -st } \, dt +\left. e^{ -st }f(t) \right| ^\infty_{0}=s\mathcal{L}(f)(s)-f(0) $$
> 3. $$\begin{align}\mathcal{L}(f*g)(s)&=\int_{0}^{\infty} \left(\int_{0}^{t} f(t-\tau)g(\tau)d\tau  \right) e^{ -st } \, dt \\&=\int_{0}^{\infty} \int_{\tau}^{\infty} f(t-\tau)e^{ -st }  \, dt g(\tau) \, d\tau \\&=\int_{0}^{\infty} \int_{0}^{\infty} f(t)e^{ -st }  \, dt g(\tau) e^{-s\tau}\, d\tau\\&=\mathcal{L}(f)(s)\mathcal{L}(g)(s) \end{align}$$
> 4. We have that: $$\begin{align}s\mathcal{L}(e^{ At })(s)-I&=A\mathcal{L}(e^{ At })(s)\\(sI-A)\mathcal{L}(e^{ At })(s)&=I\end{align}$$
> 	where $(sI-A)$ is invertible for all $s\in \mathbb{C}$, except for the eigenvalues of $A$.